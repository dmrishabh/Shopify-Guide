<h1 align="center" style="margin-top: 0px;">Shopify Theme Dev Guide</h1>


# Important links to resources

* [Planned efforts generator](https://docs.google.com/spreadsheets/d/1YHSfLx-KT8mAETZ04e-jvCTvrYoY-VaRzful4ui_cDs/edit?usp=sharing)
* [Skeleton Documention](https://ebony-beryllium-736.notion.site/Skeleton-Wiki-df6b49747653442699dc20752ad5f4d3)
* [Prformance Opt](https://ebony-beryllium-736.notion.site/Performance-Optimisation-on-Shopify-cc555b398d88441aa9880e50009f3ece)
* [Prebuild Solution ](https://ebony-beryllium-736.notion.site/9f9580ec93a440b7a23a430c5bcd2260?v=43ed2153c66c47b0ace0ce2ffb69f35b)
* [Github Training](https://ebony-beryllium-736.notion.site/How-to-setup-git-Create-a-repo-Origin-Clone-repo-fdb2bf4101a944ebb8b29f08a7fcb7c4)
* [Shopify ajax Api](https://shopify.dev/api/ajax)
* [To do courses](https://www.shopify.com/in/partners/blog/97493062-free-course-10x-your-shopify-theme-development-skills-with-these-free-courses)
----------
<h1 align="center" style="margin-top: 0px;">Small shopify solutions</h1>

# Lazy image snippet
----------
```html
{% comment %}
  Render an responsive image.
  Uses: {%- render 'SNIPPET_NAME', desktopImage:' Image object for desktop', mobileImage: 'mobileImage'  -%} 
  Accepts:
  - class: {String} Class to add to the image.
  - id: {String} ID to add to the image.
  - mobileImage: {Object} Image object for mobile
  - mobileSize: {String} Size of the mobile image to occupy on mobile screen
  - desktopImage: {Object} Image object for desktop
  - desktopSize: {String} Size of the desktop image to occupy on desktop screen
{% endcomment %}

<picture class="{{ class }}" {% if id != blank %}id="{{id}}"{% endif %}>
  {% if mobileImage %}
  <source
    media="(max-width: 767px)"
    srcset="{%- if mobileImage.width >= 375 -%}{{ mobileImage | image_url: width: 375 }} 375w,{%- endif -%}
      {%- if mobileImage.width >= 550 -%}{{ mobileImage | image_url: width: 550 }} 550w,{%- endif -%}
      {%- if mobileImage.width >= 750 -%}{{ mobileImage | image_url: width: 750 }} 750w,{%- endif -%}
      {%- if mobileImage.width >= 1100 -%}{{ mobileImage | image_url: width: 1100 }} 1100w,{%- endif -%}
      {%- if mobileImage.width >= 1500 -%}{{ mobileImage | image_url: width: 1500 }} 1500w,{%- endif -%}
      {%- if mobileImage.width >= 1780 -%}{{ mobileImage | image_url: width: 1780 }} 1780w,{%- endif -%}
      {%- if mobileImage.width >= 2000 -%}{{ mobileImage | image_url: width: 2000 }} 2000w,{%- endif -%}
      {%- if mobileImage.width >= 3000 -%}{{ mobileImage | image_url: width: 3000 }} 3000w,{%- endif -%}
      {%- if mobileImage.width >= 3840 -%}{{ mobileImage | image_url: width: 3840 }} 3840w,{%- endif -%}
      {{ mobileImage | image_url }} {{ mobileImage.width }}w"
    sizes="{{ mobileSize | default: '100vw' }}"
  >
  {% endif %}
  <source
    {% if mobileImage %} media="(min-width: 768px)"{% endif %}
    srcset="{%- if desktopImage.width >= 375 -%}{{ desktopImage | image_url: width: 375 }} 375w,{%- endif -%}
      {%- if desktopImage.width >= 550 -%}{{ desktopImage | image_url: width: 550 }} 550w,{%- endif -%}
      {%- if desktopImage.width >= 750 -%}{{ desktopImage | image_url: width: 750 }} 750w,{%- endif -%}
      {%- if desktopImage.width >= 1100 -%}{{ desktopImage | image_url: width: 1100 }} 1100w,{%- endif -%}
      {%- if desktopImage.width >= 1500 -%}{{ desktopImage | image_url: width: 1500 }} 1500w,{%- endif -%}
      {%- if desktopImage.width >= 1780 -%}{{ desktopImage | image_url: width: 1780 }} 1780w,{%- endif -%}
      {%- if desktopImage.width >= 2000 -%}{{ desktopImage | image_url: width: 2000 }} 2000w,{%- endif -%}
      {%- if desktopImage.width >= 3000 -%}{{ desktopImage | image_url: width: 3000 }} 3000w,{%- endif -%}
      {%- if desktopImage.width >= 3840 -%}{{ desktopImage | image_url: width: 3840 }} 3840w,{%- endif -%}
      {{ desktopImage | image_url }} {{ desktopImage.width }}w"
    sizes="{{ desktopSize | default: '100vw' }}"
  >
  <img src="{{ desktopImage | image_url: width: 1500 }}"
    loading="lazy"
    width="{{ desktopImage.width }}"
    height="{{ desktopImage.width | divided_by: desktopImage.aspect_ratio | round }}"
    alt="{{ alt | default: desktopImage.alt | escape }}">
</picture>

```
# Accordion closer fix using detail and summery
-----
* Html

```html
   <details {{ block.shopify_attributes }} class="mm-accordion">
    <summary>
      <span>
         {{ article.metafields.custom[common_problem] | escape }}
      <span class="icon">
       {% render 'icon-carrot' %}
      </span>
      </span>
    </summary>
    <div class="rte typeset">
      {{ article.metafields.custom[common_solution] }}
    </div>
  </details>
```
------
* JS
```js
<script>

 let target = document.querySelectorAll('details.mm-accordion');
target.forEach(ele=>{
  ele.addEventListener('click',function(){
    target.forEach((ele)=>{
      if(ele != this ){
        ele.removeAttribute('open')
      }
    })
  })
})
</script>
```
---------
# Collection page FIlter and Sort Together in BE YOURS THEME
```javascript
 onSubmitHandler(event) {
    
    event.preventDefault();
    let formNode = document.querySelectorAll('#FacetFiltersForm');
    const formData = new FormData(event.target.closest("form"));
    const searchParams = new URLSearchParams(formData).toString();
    let filterformData = new FormData(formNode[0]);
    const FilterSearchParams = new URLSearchParams(filterformData).toString();
    let sortformData = new FormData(formNode[1]);
    const SortSearchParams = new URLSearchParams(sortformData).toString();
    let sortWithFilterURL = FilterSearchParams.concat("&" , SortSearchParams);
    FacetFiltersForm.renderPage(sortWithFilterURL, event);
    
  }
```
-----------------
# Active class
```js
  let filterBtn =  document.querySelectorAll('.filter_item');
  filterBtn.forEach(function(ele) {
   
   ele.addEventListener("click", function(){
     document.querySelectorAll('.filter_item').forEach(function(e){
       e.classList.remove("active");
    });
      ele.classList.add("active");
})
```
----------
# How do manage spacing b/w sections if it's not uniform for all section in design flow (if yo want to add left right spacing also you can add in same way)
* Add this in Schema
```json

    {
      "type": "range",
      "id": "spacing_top",
      "min": 0,
      "max": 100,
      "step": 1,
      "unit": "px",
      "label": "Desktop Margin Top",
      "default": 100
    },
    {
      "type": "range",
      "id": "spacing_bottom",
      "min": 0,
      "max": 100,
      "step": 1,
      "unit": "px",
      "label": "Desktop Margin Bottom",
      "default": 100
    },
    {
      "type": "range",
      "id": "padding_top",
      "min": 0,
      "max": 100,
      "step": 1,
      "unit": "px",
      "label": "Desktop Padding Top",
      "default": 100
    },
    {
      "type": "range",
      "id": "padding_bottom",
      "min": 0,
      "max": 100,
      "step": 1,
      "unit": "px",
      "label": "Desktop Padding Bottom",
      "default": 100
    },
    {
      "type": "range",
      "id": "mspacing_top",
      "min": 0,
      "max": 100,
      "step": 1,
      "unit": "px",
      "label": "Mobile Margin Top",
      "default": 100
    },
    {
      "type": "range",
      "id": "mspacing_bottom",
      "min": 0,
      "max": 100,
      "step": 1,
      "unit": "px",
      "label": "Mobile Margin Bottom",
      "default": 100
    },
    {
      "type": "range",
      "id": "mpadding_top",
      "min": 0,
      "max": 100,
      "step": 1,
      "unit": "px",
      "label": "Mobile Padding Top",
      "default": 100
    },
    {
      "type": "range",
      "id": "mpadding_bottom",
      "min": 0,
      "max": 100,
      "step": 1,
      "unit": "px",
      "label": "Mobile Padding Bottom",
      "default": 100
    }  

```
* Add this just above {% schema %} tag 
```css

{% style %}
@media screen and (min-width: 750px){

  .YOUR_CLASS_NAME--{{ section.id }}{
margin-top: {{ section.settings.spacing_top }}px;
margin-bottom: {{ section.settings.spacing_bottom }}px;
padding-top: {{ section.settings.padding_top }}px;
padding-bottom: {{ section.settings.padding_bottom }}px;
}
}
@media screen and (max-width: 749px){

.YOUR_CLASS_NAME--{{ section.id }}{
margin-top: {{ section.settings.mspacing_top }}px;
margin-bottom:{{ section.settings.mspacing_bottom }}px;
padding-top: {{ section.settings.mpadding_top }}px;
padding-bottom: {{ section.settings.mpadding_bottom }}px;
}
}


{% endstyle %}


```
* Add this class="YOUR_CLASS_NAME--{{ section.id }}" in the parent element
-------- 
## Percent discount calculation formula
```html
{% capture discount %}
{{ product.compare_at_price | minus:product.price | times:100 | divided_by:product.compare_at_price }}%
{% endcapture %}
{{ discount }}
```
---------------

# Update data on variant change that is coming from variant metafield 

### As we know liquid load only once with DOM  so to change it later i'll use js here , here i'll take a ref of Dawn.

* first we need to add variant meta field in product variant 
* Add this below code in pdp main section i.e. main-product.liquid where we are using that block in this example we are using a Delivery date 
* Add this in schema

```json
    {
		"type":"delivery_date",
		"name": "Delivery date",
        "limit": 1
	  }
```

```js
  {% when 'delivery_date' %}
              <script id="date-data" type="application/json">
                { {%- for variant in product.variants -%}
                  "{{ variant.id }}":"{{ variant.metafields.custom.delivery_days | strip_newlines }}"
                    {% unless forloop.last %},{% endunless %}
                  {%- endfor -%}
                  }
              </script>
            
              <p>Delivered by <strong><span id="toDate"></span> </strong></p>
                {{ '//cdnjs.cloudflare.com/ajax/libs/datejs/1.0/date.min.js' | script_tag }}
        <script>
    
                // update date 
              let date_Data = JSON.parse(document.querySelector('#date-data').innerHTML);
              let delivery_date = {{ product.variants[0].metafields.custom.delivery_days }};
              
              let url = window.location.href;
              if(url.includes("?variant")){
               url = window.location.href.split("variant=");
              delivery_date = date_Data[url[1]];
              }
              else{
             delivery_date = {{ product.variants[0].metafields.custom.delivery_days }};
              }
               if (delivery_date != '') {
                delivery_date = parseInt(delivery_date);
                }else{
                delivery_date = 10;
                }
                var tdate = Date.today().addDays(delivery_date);
                  if (tdate.is().saturday() || tdate.is().sunday()) {
                    tdate = tdate.next().monday();
                  }
                document.getElementById('toDate').innerHTML = tdate.toString('dddd, MMMM dS');
        </script>
```
* Add this to global.js
inside variant change component  js "VariantSelects" in Dawn
```js
// call this function on variant change 
  onVariantChange() {
    this.updateOptions();
    this.updateMasterId();
    this.toggleAddButton(true, '', false);
    this.updatePickupAvailability();
    this.removeErrorMessage();
      this.changeDelDate();
    

    if (!this.currentVariant) {
      this.toggleAddButton(true, '', true);
      this.setUnavailable();
    } else {
      this.updateMedia();
      this.updateURL();
      this.updateVariantInput();
      this.renderProductInfo();
      this.updateShareUrl();
    }
  }
// add this function def
changeDelDate(){
   let datedata = JSON.parse(document.querySelector('#date-data').innerHTML);
   let del_date = datedata[this.currentVariant.id];
    if (del_date != '') {
        del_date = parseInt(del_date);
    }else{
      del_date = 10;
    }
    var toDate = Date.today().addDays(del_date);
      if (toDate.is().saturday() || toDate.is().sunday()) {
        toDate = toDate.next().monday();
      }
    document.getElementById('toDate').innerHTML = toDate.toString('dddd, MMMM dS');
  }
```
------------------
# Free shipping indicator progress bar 

## Free Shipping Bar displays progressive messages when customers put more items in their shopping carts, and lets them know how much more to buy in order to get your    free shipping.
* First we'll create snippet called free-shipping.liquid and paste below code in that 
```html
{% comment %}
Uses : {%  render 'free-shipping'  %}
{% endcomment %}
<div class="shipping-bar">
  {% liquid
    assign free_shipping = settings.free_shipping | times: 1
    assign cart_price = cart.total_price | divided_by: 100
    assign change = free_shipping | minus: cart_price
    assign perc_change = 100
    if change > 0
      assign perc_change = change | times: 100 | divided_by: free_shipping
      assign perc_change = 100 | minus: perc_change
    endif
  %}
  {% if perc_change == 100 %}
    <div class="shipping-bar__title font-bold text-md cart-drawer__black">Free shipping</div>
  {% else %}
    <div class="shipping-bar__message cart-drawer__black h6">
      <p>
        You are <strong>{{ change | times: 100 | money }}</strong> away from <strong>free shipping*</strong>
      </p>
    </div>
  {% endif %}
  <div class="shipping-bar__container">
    <div class="shipping-bar__filled" style="width: {{ perc_change | string | append: '%' }}">
      <div class="shipping__icon" style="left: {{ perc_change | string | append: '%' }}">
        <svg xmlns="http://www.w3.org/2000/svg" width="31.678" height="35.847" viewBox="0 0 31.678 35.847">
          <g id="Group_200290" data-name="Group 200290" transform="translate(-3.291 15.779) rotate(-45)">
          <path id="Path_301827" data-name="Path 301827" d="M.344,6.568A14.727,14.727,0,0,0,.173,2.1C.1,1.441-.237.615.3.226,2.236-1.181,2.36,4.375,3.017,5.8,4.124,4.508,5.131,2.977,6.74,2.337A2.954,2.954,0,0,1,7.9,2.045c4.156.113-3.324,3.435-2.831,4.911a12.869,12.869,0,0,1,4.963-.6,2.408,2.408,0,0,1,1.135.372c2.063,1.343-4.55,1.982-5.887,3.349" transform="translate(10.75 0)" fill="#318200"></path>
          <path id="Path_301828" data-name="Path 301828" d="M.8,8.065a12.059,12.059,0,0,1,.342-1.392,27.225,27.225,0,0,1,1.4-3.992c.641-1.178,3.03-4.265,8.537-1.671a49.368,49.368,0,0,1,7.286,3.915s4.678,3.025,1.748,7.883a30.183,30.183,0,0,1-6.086,6.888,18.436,18.436,0,0,1-5.567,3.351c-2.339.862-5.2,1.171-6.98-.689,0,0-2.811-1.23-.677-14.291" transform="translate(0 4.654)" fill="#A31207"></path>
          </g>
        </svg>
      </div>
    </div>
  </div>
  {% if perc_change == 100 %}
    <div class="shipping-bar__message cart-drawer__black h6">
      <p><strong>Yay!!</strong> you unlocked <strong>free shipping</strong></p>
    </div>
  {% endif %}
</div>

```
* Add css in your global css file or in specific file .
```css
.shipping-bar {
    width: 100%;
    border-radius: 2rem;
    background: #F2F0FF;
    padding: 0.75rem 2rem;
    margin: 1.5rem 0 0.5rem;
}
.cart-drawer__black {
    color: #111314;
}
.shipping-bar .shipping-bar__container {
    height: 1rem;
    background: #fff;
    border-radius: 1rem;
    position: relative;
    margin: 1.4rem 0 0.75rem;
}
.shipping-bar .shipping-bar__filled {
    height: 100%;
    border-radius: 1rem;
    transition: all .75s ease-in-out;
    background-color: #AFAFED;
}
.shipping-bar .shipping__icon {
    position: absolute;
    transition: all .75s ease-in-out;
    transform: translate(-70%,-45%) rotate(30deg);
}
```
* we need to add one input setting in theme settings that is , settings_schema.json
```json
  {
    "name": "Free shipping bar",
   "settings": [
      {
        "type": "text",
        "id":"free_shipping",
        "label":"Free shipping limit"
      }
  ]
  }
```
* Now you can render this snippet
```ruby
{%  render 'free-shipping'  %}
```

