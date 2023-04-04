## PhoneNumber 
```js
{{ 'customer.css' | asset_url | stylesheet_tag }}
{{ 'section-main-register.js' | asset_url | script_tag }}

<div class="customer register section-{{ section.id }}-padding">
<div class="nav-button">
   <a href="{{ routes.root_url }}">
   {% render 'home-icon' %}
   </a>
   <p class="nav_text">>Sign Up</p>
</div>
<div class="register_container">
   <div class="register__login_image">
      {% if section.settings.image != blank %}
      {% assign image = section.settings.image %}
      {% render 'image', desktopSrc: section.settings.image %}
      {% endif %}
   </div>
   <div class="form_container">
      <svg style="display: none">
         <symbol id="icon-error" viewBox="0 0 13 13">
            <circle cx="6.5" cy="6.50049" r="5.5" stroke="white" stroke-width="2"/>
            <circle cx="6.5" cy="6.5" r="5.5" fill="#EB001B" stroke="#EB001B" stroke-width="0.7"/>
            <path d="M5.87413 3.52832L5.97439 7.57216H7.02713L7.12739 3.52832H5.87413ZM6.50076 9.66091C6.88091 9.66091 7.18169 9.37267 7.18169 9.00504C7.18169 8.63742 6.88091 8.34917 6.50076 8.34917C6.12061 8.34917 5.81982 8.63742 5.81982 9.00504C5.81982 9.37267 6.12061 9.66091 6.50076 9.66091Z" fill="white"/>
            <path d="M5.87413 3.17832H5.51535L5.52424 3.537L5.6245 7.58083L5.63296 7.92216H5.97439H7.02713H7.36856L7.37702 7.58083L7.47728 3.537L7.48617 3.17832H7.12739H5.87413ZM6.50076 10.0109C7.06121 10.0109 7.5317 9.57872 7.5317 9.00504C7.5317 8.43137 7.06121 7.99918 6.50076 7.99918C5.94031 7.99918 5.46982 8.43137 5.46982 9.00504C5.46982 9.57872 5.94031 10.0109 6.50076 10.0109Z" fill="white" stroke="#EB001B" stroke-width="0.7">
         </symbol>
      </svg>
      <h1 class="register__title">
         {{ 'customer.register.title' | t }}
      </h1>
      <p class="register_sub-title">Please fill the details to create your account</p>
      {%- form 'create_customer', novalidate: 'novalidate' -%}
      {%- if form.errors -%}
      <h2 class="form__message" tabindex="-1" autofocus>
         <svg aria-hidden="true" focusable="false">
            <use href="#icon-error" />
         </svg>
         {{ 'templates.contact.form.error_heading' | t }}
      </h2>
      <ul>
         {%- for field in form.errors -%}
         <li>
            {%- if field == 'form' -%}
            {{ form.errors.messages[field] }}
            {%- else -%}
            <a href="#RegisterForm-{{ field }}">
            {{ form.errors.translated_fields[field] | capitalize }}
            {{ form.errors.messages[field] }}
            </a>
            {%- endif -%}
         </li>
         {%- endfor -%}
      </ul>
      {%- endif -%}
      <div class="input_field--container">
         <label class="input_label" for="RegisterForm-FirstName">
         {{ 'customer.register.first_name' | t }}
         </label>
         <input
         class="input__field"
         type="text"
         name="customer[first_name]"
         id="RegisterForm-FirstName"
         {% if form.first_name %}
         value="{{ form.first_name }}"
         {% endif %}
         autocomplete="given-name"
         placeholder="Enter Your Full name"
         >
      </div>
      <div class="input_field--container">
         <label class="input_label" for="RegisterForm-email">
         {{ 'customer.register.email' | t }}
         </label>
         <input
         class="input__field"
         type="email"
         name="customer[email]"
         id="RegisterForm-email"
         {% if form.email %}
         value="{{ form.email }}"
         {% endif %}
         spellcheck="false"
         autocapitalize="off"
         autocomplete="email"
         aria-required="true"
         {% if form.errors contains 'email' %}
         aria-invalid="true"
         aria-describedby="RegisterForm-email-error"
         {% endif %}
         placeholder="Enter your e-mail id"
         >
      </div>
      <div class="input_field--container">
         <label class="input_label" for="RegisterFormMobileNumber">
         {{ 'customer.register.mobile_number' | t }}
         </label>
         <input
         class="input__field"
         type="text"
         id="register_phone"
         name="contact[phone]"
         {% if form.phone %}
         value="{{ form.phone }}"
         {% endif %}
         autocomplete="family-name"
         placeholder="Enter Your Mobile Number"
         >
        <span id="errorMsg"></span>
      </div>
      {%- if form.errors contains 'email' -%}
      <span id="RegisterForm-email-error" class="form__message">
         <svg aria-hidden="true" focusable="false">
            <use href="#icon-error" />
         </svg>
         {{ form.errors.translated_fields.email | capitalize }}
         {{ form.errors.messages.email }}.
      </span>
      {%- endif -%}
      <div class="input_field--container">
         <label class="input_label" for="RegisterForm-password">
         {{ 'customer.register.password' | t }} 
         </label> 
         <input
         class="input__field"
         type="password"
         name="customer[password]"
         id="RegisterForm-password"
         aria-required="true"
         {% if form.errors contains 'password' %}
         aria-invalid="true"
         aria-describedby="RegisterForm-password-error"
         {% endif %}
         placeholder="Enter your Passaword"
         >
         <div class="eye-icon" id="eye-icons">
            {% render 'eye-icon' %}
            </div
         </div>
         {%- if form.errors contains 'password' -%}
         <span id="RegisterForm-password-error" class="form__message">
            <svg aria-hidden="true" focusable="false">
               <use href="#icon-error" />
            </svg>
            {{ form.errors.translated_fields.password | capitalize }}
            {{ form.errors.messages.password }}.
         </span>
         {%- endif -%}
         <button class="login__button" id="customer_create_btn">  
         {{ 'customer.register.submit' | t }}
         </button>
         <div class="signup__url">
            <p class="signup__url-text">Already have an Account?</p>
            <a href="{{ routes.account_login_url }}">
               <p class="login_text">Login</p>
            </a>
         </div>
         {%- endform -%}
      </div>
   </div>
</div>

  <div class="hidden_login_form" style="display:none;">
    {% form 'customer_login' %}
      <input type="email" value="" name="customer[email]" id="customer_email" {% if form.errors contains "email" %}class="error"{% endif %}>
      <input type="password" value="" name="customer[password]" id="customer_password" {% if form.errors contains "password" %}class="error"{% endif %}>
    {% endform %}
  </div>
<script>
  const storefrontApiKey = '481d21c2aae1b64b285b210470235088';
    
    document.addEventListener("DOMContentLoaded", function(event) {
      
      // On Click event 
      document.getElementById("customer_create_btn").onclick = function(evt) { 
       evt.preventDefault()
         // Get Email, Password and Phone
        let firstName = document.getElementById('RegisterForm-FirstName').value;
        let email = document.getElementById('RegisterForm-email').value;
        let phone = document.getElementById('register_phone').value;
        let password = document.getElementById('RegisterForm-password').value;
        
        let is_phone_number_start_with_plus_nine_one = phone.startsWith("+91");
        
        if(!is_phone_number_start_with_plus_nine_one) {
          phone = '+91'+ phone;
        }
        
        if( !firstName || !email || !phone || !password ) {
          console.log('Empty Field');
          return false;
        }
        
        fetch('https://somethings-brewing-store.myshopify.com/api/2023-04/graphql.json', {
          method: 'POST',
          headers: {
            'Content-Type': 'application/json',
            'X-Shopify-Storefront-Access-Token': storefrontApiKey,
          },
          body: JSON.stringify({
            query: `
              mutation customerCreate($input: CustomerCreateInput!) {
                customerCreate(input: $input) {
                  customer {
                    id
                  }
                  customerUserErrors {
                    code
                    field
                    message
                  }
                }
              }
          `,
            variables: {
              "input": {
                "firstName": firstName,
                "email": email,
                "password": password,
                "phone": phone
              }
            },
          }),
        })
        .then( function(res){ return res.json()})
        .then(function(result) {
       
          if(result && result.data && result.data.customerCreate) {
            let customerCreateData = result.data.customerCreate;
  
            if(customerCreateData.customerUserErrors.length > 0 ) {
              let customerUserErrors = customerCreateData.customerUserErrors;
              console.log(customerUserErrors);
  
              customerUserErrors.forEach(function (item, index) {
                if(item.message){
                  console.log(item.message)
                }
              });
              return false 
            }
  
          } else if (result && result.errors) {
            let errors = result.errors;
  
            errors.forEach(function (item, index) {
              if(item.message){
                console.log(item.message)
                // $('.customer_error_msg').append('<li class="error_list">'+ item.message +'</li>')
              }
            });
  
            return false;
          } 
  
          let customerEmail = document.querySelector('.hidden_login_form #customer_email');
          customerEmail.value = email;
          let customerPassword = document.querySelector('.hidden_login_form #customer_password');
          customerPassword.value = password;
          document.querySelector('.hidden_login_form form').submit();
        });
      };  
    });
</script>
                 
{%- style -%}
  .section-{{ section.id }}-padding {
    padding-top: {{ section.settings.padding_top | times: 0.75 | round: 0 }}px;
    padding-bottom: {{ section.settings.padding_bottom | times: 0.75 | round: 0 }}px;
  }

  @media screen and (min-width: 750px) {
    .section-{{ section.id }}-padding {
      padding-top: {{ section.settings.padding_top }}px;
      padding-bottom: {{ section.settings.padding_bottom }}px;
    }
  }
{%- endstyle -%}

{% schema %}
{
  "name": "t:sections.main-register.name",
  "settings": [
    {
      "type": "header",
      "content": "t:sections.all.padding.section_padding_heading"
    },
    {
      "type": "image_picker",
      "id": "image",
      "label": "Image"
    },
    {
      "type": "range",
      "id": "padding_top",
      "min": 0,
      "max": 100,
      "step": 4,
      "unit": "px",
      "label": "t:sections.all.padding.padding_top",
      "default": 36
    },
    {
      "type": "range",
      "id": "padding_bottom",
      "min": 0,
      "max": 100,
      "step": 4,
      "unit": "px",
      "label": "t:sections.all.padding.padding_bottom",
      "default": 36
    }
  ]
}
{% endschema %}
```
