<h1 align="center" style="margin-top: 0px;">Shopify Theme Dev Guide</h1>


# Important links to resources
# Documentation and Learning Resources

Welcome to our training and learning resources repository. Here, you'll find a curated collection of reading materials and documentation to support your professional development and learning journey. Feel free to explore the links below:

## Notion Docs

1. [How to do debugging](https://ebony-beryllium-736.notion.site/How-to-do-debugging-e18e11c63c8f46e9975872c4d526ed4a)
   - [Pause your code with breakpoints](https://developer.chrome.com/docs/devtools/javascript/breakpoints/)

2. [Performance Optimization](https://ebony-beryllium-736.notion.site/Performance-Optimisation-on-Shopify-cc555b398d88441aa9880e50009f3ece)
   - [Improve your online store performance with Liquid](https://workshops.shopify.dev/workshops/online-store-performance#0)

3. [What are the default things required in customization of Shopify?](https://ebony-beryllium-736.notion.site/What-are-the-default-things-required-in-customisation-of-Shopify-dbc7eb494ba64619ba24f3f068e88e13)

4. [How to develop as per design](https://ebony-beryllium-736.notion.site/How-to-develop-as-per-design-741a495afa2c4d98bf5b5f9e02bf93e1)

5. [Effort Estimation](https://ebony-beryllium-736.notion.site/Effort-Estimation-c73478b583134747b79a340e5b0951f0)
   - [Automated sheet for effort estimation](https://docs.google.com/spreadsheets/d/1QHcZIh7-wWN34iKTl1Spe2Go-KBxnmX5k6tCC6RjT3I/edit?usp=sharing)

7. [Git and Github with Shopify](https://ebony-beryllium-736.notion.site/Git-and-Github-with-Shopify-371702287f8c461fb17d5d052f2d2975)

8. [Migrating Existing Shopify Store To GitHub](https://versed-asp-459.notion.site/Migrating-Existing-Store-To-GitHub-1aa388ad07b542ad9e0aa8c03c6ad8ab)

9. [Code review 2.0](https://versed-asp-459.notion.site/Marmeto-Code-Review-2-0-a03983c7983c4716853f3981dd54aecf)

10. [Pre-build solutions](https://ebony-beryllium-736.notion.site/9f9580ec93a440b7a23a430c5bcd2260?v=43ed2153c66c47b0ace0ce2ffb69f35b)

11. [Tailwind setup on Shopify Store ✨](https://sphenoid-aftermath-492.notion.site/When-Tailwind-met-Shopify-02e904f40513499a88be2f3a3b362607?pvs=4)

12. [Shopify Custom Pixels ✨](./docs/SHOPIFY_PIXELS.md)

## Important links to resources

- [Planned efforts format sheet](https://docs.google.com/spreadsheets/d/1YHSfLx-KT8mAETZ04e-jvCTvrYoY-VaRzful4ui_cDs/edit#gid=0)
- [Tutorial to integrate React.js into Shopify theme](https://reactjsexample.com/tutorial-to-integrate-the-react-js-into-shopify-theme/)
- [Shopify Workshop](https://workshops.shopify.dev/)
  > Workshops provide a guided, tutorial, hands-on coding experience. Most workshops will step you through the process of building an application, theme, or function.
- **Checkout Extensions**
    -  [Extension Points](https://www.figma.com/file/8qYbHZTB6yGBHvDTscXIzx/Checkout-UI-Kit-(Community)?type=design&node-id=7720-22727&t=InRkWSxQ0balgUlt-0)
    -  [Migration reading](https://honorable-net-acc.notion.site/Shopify-Checkout-Extension-8032e90e1e964f098508a43b10435ece?pvs=4)


### Helpful Chrome Extensions

- **Shopify tools**
  - [Shopify Theme Inspector](https://chrome.google.com/webstore/detail/shopify-theme-inspector-f/fndnankcflemoafdeboboehphmiijkgp/related)
  - [Shopify Theme Helper](https://chrome.google.com/webstore/detail/shopify-theme-helper/palnodkhbhhnaoecdfbifdfpibklccdk)
  - [Shopify App Detector](https://chrome.google.com/webstore/detail/shopify-app-detector-by-f/lhfdhjladfcmghahdbcmlceajdlbkale)
  - [Liquify - Shopify Code Search & Editor](https://chrome.google.com/webstore/detail/liquify-shopify-code-sear/edekihmjmpkkkaolmojnajojfgphccma)

- **Other tools**
  - [Datalayer Checker](https://chrome.google.com/webstore/detail/datalayer-checker/ffljdddodmkedhkcjhpmdajhjdbkogke)
  - [Smart Page Ruler](https://chrome.google.com/webstore/detail/smart-page-ruler/nmibbjghlmdiafjolcphdggihcbcedmg)

> Feel free to add more resources that you find useful for your learning and development. Happy learning!

* [To do courses](https://www.shopify.com/in/partners/blog/97493062-free-course-10x-your-shopify-theme-development-skills-with-these-free-courses)
----------
<h1 align="center" style="margin-top: 0px;">Small shopify solutions</h1>

# Lazy image snippet
----

`countdown-timer.liquid`

```html

{%- style -%}
  #shopify-section-{{ section.id }} {
    --section-padding-top: {{ section.settings.padding_top }}px;
    --section-padding-bottom: {{ section.settings.padding_bottom }}px;
    {%- if section.settings.image != blank %}
      --image-ratio-percent: {{ 1 | divided_by: section.settings.image.aspect_ratio | times: 100 }}%;
      --image-position: {{ section.settings.image_position }};
    {% endif -%}
    {%- if section.settings.use_custom_colors %}
      --gradient-background: {% if section.settings.gradient_background != blank %}{{ section.settings.gradient_background }}{% else %}{{ section.settings.colors_background }}{% endif %};
      --color-background: {{ section.settings.colors_background.red }}, {{ section.settings.colors_background.green }}, {{ section.settings.colors_background.blue }};
      --color-foreground: {{ section.settings.colors_text.red }}, {{ section.settings.colors_text.green }}, {{ section.settings.colors_text.blue }};
      --color-link: var(--color-foreground);
      --color-border: var(--color-foreground);
      --color-heading: var(--color-foreground);
      --color-button-background: {{ section.settings.colors_button_background.red }}, {{ section.settings.colors_button_background.green }}, {{ section.settings.colors_button_background.blue }};
      --color-button-text: {{ section.settings.colors_button_label.red }}, {{ section.settings.colors_button_label.green }}, {{ section.settings.colors_button_label.blue }};
      --color-button-border: var(--color-button-background);
      --color-shadow: var(--color-foreground);
    {% endif -%}
    --shadow-opacity: 0.3;
  }
  {%- if section.settings.image_mobile != blank and section.settings.mobile_image_ratio == 'adapt' %}
    @media screen and (max-width: 749px) {
      #shopify-section-{{ section.id }} {
        --image-ratio-percent: {{ 1 | divided_by: section.settings.image_mobile.aspect_ratio | times: 100 }}%;
      }
    }  
  {% endif -%}
{%- endstyle -%}

{{ 'section-image-with-text.css' | asset_url | stylesheet_tag }}
{{ 'section-countdown-timer.css' | asset_url | stylesheet_tag }}

{%- liquid
  assign grid_class = 'image-with-text__grid'
  if section.settings.layout == 'text_first'
    assign grid_class = grid_class | append: ' image-with-text__grid--reverse'
  endif

  if section.settings.mobile_layout == 'text_first'
    assign grid_class = grid_class | append: ' image-with-text__grid-mobile--reverse'
  endif

  if section.settings.mobile_layout == 'no_image'
    assign grid_class = grid_class | append: ' image-with-text__grid-mobile--no-image'
  endif

  if section.settings.mobile_layout == 'overlap'
    assign grid_class = grid_class | append: ' image-with-text__grid-mobile--overlap'
  endif
-%}

<div class="section--padding{% if section.settings.show_divider %} section--divider{% endif %}">
  <div class="image-with-text countdown-timer{% if section.settings.use_custom_colors and section.settings.colors_background != settings.colors_background %} image-with-text--colored{% endif %}{% if section.settings.enlarge_content %} image-with-text--enlarge{% endif %} page-width{% if section.settings.full_width %} page-width--full-width{% endif %}">
    <div class="{{ grid_class }} grid grid--gapless grid--1-col grid--2-col-tablet">
      <div class="grid__item">
        <use-animate data-animate="zoom-fade" class="media-wrapper">
          <div class="image-animate media--{{ section.settings.image_ratio }} media-mobile--{{ section.settings.mobile_image_ratio }} {% if section.settings.image != blank %}media{% else %}media--placeholder{% endif %}">
            {%- if section.settings.image != blank -%}
              {%- capture sizes -%}(min-width: {{ settings.page_width }}px) {{ settings.page_width | minus: 100 | divided_by: 2 }}px, (min-width: 750px) calc((100vw - 10rem) / 2),{% if section.settings.full_width %} 100vw{% else %} calc(100vw - 3rem){% endif %}{%- endcapture -%}
              {%- liquid
                if section.settings.image_mobile == blank
                  echo section.settings.image | image_url: width: 1500 | image_tag: loading: 'lazy', class: 'image-fit', sizes: sizes, widths: '180, 360, 535, 750, 1100, 1500', is: 'lazy-image'
                else
                  echo section.settings.image_mobile | image_url: width: 1500 | image_tag: loading: 'lazy', class: 'image-fit medium-hide large-up-hide', sizes: sizes, widths: '180, 360, 535, 750, 1100, 1500', is: 'lazy-image'
                  echo section.settings.image | image_url: width: 1500 | image_tag: loading: 'lazy', class: 'image-fit small-hide', sizes: sizes, widths: '180, 360, 535, 750, 1100, 1500', is: 'lazy-image'
                endif
              -%}
            {%- else -%}
              {{ 'image' | placeholder_svg_tag: 'placeholder' }}
            {%- endif -%}
          </div>
        </use-animate>
      </div>
      <div class="grid__item">
        <div class="image-with-text__content {{ section.settings.text_box_position }} {{ section.settings.text_alignment }} mobile-{{ section.settings.mobile_text_alignment }}">
          {%- for block in section.blocks -%}
            {% case block.type %}
              {%- when 'heading' -%}
                <{{ block.settings.heading_tag }} class="image-with-text__heading {{ block.settings.heading_size }}" {{ block.shopify_attributes }}>{{ block.settings.heading | escape }}</{{ block.settings.heading_tag }}>
              {%- when 'subheading' -%}
                <p class="image-with-text__subheading{% if block.settings.secondary_color %} image-with-text__subheading--colored{% endif %} {{ block.settings.subheading_size }}" {{ block.shopify_attributes }}>{{ block.settings.subheading | escape }}</p>
              {%- when 'text' -%}
                <div class="image-with-text__text{% if block.settings.secondary_color %} image-with-text__text--colored{% endif %} {{ block.settings.text_size }} rte" {{ block.shopify_attributes }}>{{ block.settings.text }}</div>
              {%- when 'custom_liquid' -%}
                <div class="image-with-text__text rte" {{ block.shopify_attributes }}>{{ block.settings.custom_liquid }}</div>
              {%- when 'button' -%}
                {%- if block.settings.button_label != blank -%}
                  {%- if block.settings.button_style_secondary -%}
                    <a class="button button--cta button--{{ block.settings.button_size }}"{% if block.settings.button_link != blank %} href="{{ block.settings.button_link }}"{% else %} role="link" aria-disabled="true"{% endif %} {{ block.shopify_attributes }}>
                      <span class="label">{{ block.settings.button_label | escape }}</span>
                      {% render 'icon', icon: 'arrow' %}
                    </a>
                  {%- else -%}
                    <a class="button button--{{ block.settings.button_size }}"{% if block.settings.button_link != blank %} href="{{ block.settings.button_link }}"{% else %} role="link" aria-disabled="true"{% endif %} {{ block.shopify_attributes }}>
                      {{ block.settings.button_label | escape }}
                    </a>
                  {%- endif -%}
                {%- endif -%}
              {%- when 'countdown' -%}
                {%- if block.settings.date != blank -%}
                  <countdown-timer class="countdown countdown--{{ block.settings.number_size }}" data-date="{{ block.settings.date | escape }}" {{ block.shopify_attributes }}></countdown-timer>
                  <div class="countdown-timer__message {{ block.settings.message_size }} rte">
                    {{ block.settings.message }}
                  </div>
                {%- endif -%}
            {%- endcase -%}
          {%- endfor -%}
        </div>
      </div>
    </div>
  </div>
</div>

{% schema %}
{
  "name": "t:sections.countdown-timer.name",
  "tag": "section",
  "class": "section",
  "settings": [
    {
      "type": "image_picker",
      "id": "image",
      "label": "t:sections.all.image.label"
    },
    {
      "type": "select",
      "id": "image_position",
      "options": [
        {
          "value": "20% 0",
          "label": "t:sections.all.image_position.options__1.label"
        },
        {
          "value": "top center",
          "label": "t:sections.all.image_position.options__2.label"
        },
        {
          "value": "80% 0",
          "label": "t:sections.all.image_position.options__3.label"
        },
        {
          "value": "20% 50%",
          "label": "t:sections.all.image_position.options__4.label"
        },
        {
          "value": "center center",
          "label": "t:sections.all.image_position.options__5.label"
        },
        {
          "value": "80% 50%",
          "label": "t:sections.all.image_position.options__6.label"
        },
        {
          "value": "20% 100%",
          "label": "t:sections.all.image_position.options__7.label"
        },
        {
          "value": "bottom center",
          "label": "t:sections.all.image_position.options__8.label"
        },
        {
          "value": "80% 100%",
          "label": "t:sections.all.image_position.options__9.label"
        }
      ],
      "default": "center center",
      "label": "t:sections.all.image_position.label",
      "info": "t:sections.all.image_position.info"
    },
    {
      "type": "select",
      "id": "layout",
      "options": [
        {
          "value": "image_first",
          "label": "t:sections.countdown-timer.settings.layout.options__1.label"
        },
        {
          "value": "text_first",
          "label": "t:sections.countdown-timer.settings.layout.options__2.label"
        }
      ],
      "default": "image_first",
      "label": "t:sections.countdown-timer.settings.layout.label"
    },
    {
      "type": "select",
      "id": "text_box_position",
      "options": [
        {
          "value": "top",
          "label": "t:sections.countdown-timer.settings.text_box_position.options__1.label"
        },
        {
          "value": "middle",
          "label": "t:sections.countdown-timer.settings.text_box_position.options__2.label"
        },
        {
          "value": "bottom",
          "label": "t:sections.countdown-timer.settings.text_box_position.options__3.label"
        }
      ],
      "default": "middle",
      "label": "t:sections.countdown-timer.settings.text_box_position.label"
    },
    {
      "type": "select",
      "id": "text_alignment",
      "options": [
        {
          "value": "left",
          "label": "t:sections.all.text_alignment.options__1.label"
        },
        {
          "value": "center",
          "label": "t:sections.all.text_alignment.options__2.label"
        },
        {
          "value": "right",
          "label": "t:sections.all.text_alignment.options__3.label"
        }
      ],
      "default": "left",
      "label": "t:sections.all.text_alignment.label"
    },
    {
      "type": "select",
      "id": "image_ratio",
      "options": [
        {
          "label": "t:sections.all.image_ratio.options__1.label",
          "value": "adapt"
        },
        {
          "label": "t:sections.all.image_ratio.options__2.label",
          "value": "400px"
        },
        {
          "label": "t:sections.all.image_ratio.options__3.label",
          "value": "450px"
        },
        {
          "label": "t:sections.all.image_ratio.options__4.label",
          "value": "500px"
        },
        {
          "label": "t:sections.all.image_ratio.options__5.label",
          "value": "550px"
        },
        {
          "label": "t:sections.all.image_ratio.options__6.label",
          "value": "600px"
        },
        {
          "label": "t:sections.all.image_ratio.options__7.label",
          "value": "650px"
        },
        {
          "label": "t:sections.all.image_ratio.options__8.label",
          "value": "700px"
        },
        {
          "label": "t:sections.all.image_ratio.options__9.label",
          "value": "750px"
        },
        {
          "label": "t:sections.all.image_ratio.options__10.label",
          "value": "100vh"
        }
      ],
      "default": "650px",
      "label": "t:sections.all.image_ratio.label"
    },
    {
      "type": "checkbox",
      "id": "enlarge_content",
      "default": false,
      "label": "t:sections.countdown-timer.settings.enlarge_content.label"
    },
    {
      "type": "checkbox",
      "id": "full_width",
      "default": true,
      "label": "t:sections.all.full_width.label"
    },
    {
      "type": "checkbox",
      "id": "show_divider",
      "default": false,
      "label": "t:sections.all.show_divider.label"
    },
    {
      "type": "header",
      "content": "t:sections.all.mobile_layout.header.content"
    },
    {
      "type": "image_picker",
      "id": "image_mobile",
      "label": "t:sections.all.image_mobile.label"
    },
    {
      "type": "select",
      "id": "mobile_layout",
      "options": [
        {
          "value": "image_first",
          "label": "t:sections.countdown-timer.settings.mobile_layout.options__1.label"
        },
        {
          "value": "text_first",
          "label": "t:sections.countdown-timer.settings.mobile_layout.options__2.label"
        },
        {
          "value": "no_image",
          "label": "t:sections.countdown-timer.settings.mobile_layout.options__3.label"
        },
        {
          "value": "overlap",
          "label": "t:sections.countdown-timer.settings.mobile_layout.options__4.label"
        }
      ],
      "default": "image_first",
      "label": "t:sections.countdown-timer.settings.mobile_layout.label"
    },
    {
      "type": "select",
      "id": "mobile_text_alignment",
      "options": [
        {
          "value": "left",
          "label": "t:sections.all.mobile_layout.mobile_text_alignment.options__1.label"
        },
        {
          "value": "center",
          "label": "t:sections.all.mobile_layout.mobile_text_alignment.options__2.label"
        },
        {
          "value": "right",
          "label": "t:sections.all.mobile_layout.mobile_text_alignment.options__3.label"
        }
      ],
      "default": "left",
      "label": "t:sections.all.mobile_layout.mobile_text_alignment.label"
    },
    {
      "type": "select",
      "id": "mobile_image_ratio",
      "options": [
        {
          "label": "t:sections.all.mobile_layout.mobile_image_ratio.options__1.label",
          "value": "auto"
        },
        {
          "label": "t:sections.all.mobile_layout.mobile_image_ratio.options__2.label",
          "value": "200px"
        },
        {
          "label": "t:sections.all.mobile_layout.mobile_image_ratio.options__3.label",
          "value": "250px"
        },
        {
          "label": "t:sections.all.mobile_layout.mobile_image_ratio.options__4.label",
          "value": "300px"
        },
        {
          "label": "t:sections.all.mobile_layout.mobile_image_ratio.options__5.label",
          "value": "400px"
        },
        {
          "label": "t:sections.all.mobile_layout.mobile_image_ratio.options__6.label",
          "value": "500px"
        },
        {
          "label": "t:sections.all.mobile_layout.mobile_image_ratio.options__7.label",
          "value": "600px"
        },
        {
          "label": "t:sections.all.mobile_layout.mobile_image_ratio.options__8.label",
          "value": "100vh"
        },
        {
          "label": "t:sections.all.mobile_layout.mobile_image_ratio.options__9.label",
          "value": "adapt"
        }
      ],
      "default": "auto",
      "label": "t:sections.all.mobile_layout.mobile_image_ratio.label"
    },
    {
      "type": "header",
      "content": "t:sections.all.colors.header.content"
    },
    {
      "type": "checkbox",
      "id": "use_custom_colors",
      "default": true,
      "label": "t:sections.all.colors.use_custom_colors.label"
    },
    {
      "type": "color",
      "id": "colors_button_label",
      "label": "t:sections.all.colors.colors_button_label.label",
      "default": "#ffffff"
    },
    {
      "type": "color",
      "id": "colors_button_background",
      "label": "t:sections.all.colors.colors_button_background.label",
      "default": "#1a1b18"
    },
    {
      "type": "color",
      "id": "colors_text",
      "label": "t:sections.all.colors.colors_text.label",
      "default": "#212326"
    },
    {
      "type": "color",
      "id": "colors_background",
      "label": "t:sections.all.colors.colors_background.label",
      "default": "#f3f3f3"
    },
    {
      "type": "color_background",
      "id": "gradient_background",
      "label": "t:sections.all.colors.gradient_background.label"
    },
    {
      "type": "header",
      "content": "t:sections.all.padding.header.content"
    },
    {
      "type": "range",
      "id": "padding_top",
      "min": 0,
      "max": 100,
      "step": 4,
      "unit": "t:sections.all.padding.padding_top.unit",
      "label": "t:sections.all.padding.padding_top.label",
      "default": 36
    },
    {
      "type": "range",
      "id": "padding_bottom",
      "min": 0,
      "max": 100,
      "step": 4,
      "unit": "t:sections.all.padding.padding_bottom.unit",
      "label": "t:sections.all.padding.padding_bottom.label",
      "default": 36
    }
  ],
  "blocks": [
    {
      "type": "heading",
      "name": "t:sections.countdown-timer.blocks.heading.name",
      "limit": 2,
      "settings": [
        {
          "type": "text",
          "id": "heading",
          "default": "Countdown timer",
          "label": "t:sections.all.heading.label"
        },
        {
          "type": "select",
          "id": "heading_size",
          "options": [
            {
              "value": "h2",
              "label": "t:sections.all.heading_size.options__1.label"
            },
            {
              "value": "h1",
              "label": "t:sections.all.heading_size.options__2.label"
            },
            {
              "value": "h0",
              "label": "t:sections.all.heading_size.options__3.label"
            }
          ],
          "default": "h1",
          "label": "t:sections.all.heading_size.label"
        },
        {
          "type": "select",
          "id": "heading_tag",
          "options": [
            {
              "value": "h1",
              "label": "t:sections.all.heading_tag.options__1.label"
            },
            {
              "value": "h2",
              "label": "t:sections.all.heading_tag.options__2.label"
            },
            {
              "value": "h3",
              "label": "t:sections.all.heading_tag.options__3.label"
            },
            {
              "value": "h4",
              "label": "t:sections.all.heading_tag.options__4.label"
            },
            {
              "value": "h5",
              "label": "t:sections.all.heading_tag.options__5.label"
            },
            {
              "value": "h6",
              "label": "t:sections.all.heading_tag.options__6.label"
            },
            {
              "value": "div",
              "label": "t:sections.all.heading_tag.options__7.label"
            },
            {
              "value": "span",
              "label": "t:sections.all.heading_tag.options__8.label"
            },
            {
              "value": "p",
              "label": "t:sections.all.heading_tag.options__9.label"
            }
          ],
          "default": "h2",
          "label": "t:sections.all.heading_tag.label",
          "info": "t:sections.all.heading_tag.info"
        }
      ]
    },
    {
      "type": "subheading",
      "name": "t:sections.countdown-timer.blocks.subheading.name",
      "limit": 2,
      "settings": [
        {
          "type": "text",
          "id": "subheading",
          "default": "Add a tagline",
          "label": "t:sections.all.subheading.label"
        },
        {
          "type": "select",
          "id": "subheading_size",
          "options": [
            {
              "value": "h5",
              "label": "t:sections.all.subheading_size.options__1.label"
            },
            {
              "value": "h4",
              "label": "t:sections.all.subheading_size.options__2.label"
            },
            {
              "value": "h3",
              "label": "t:sections.all.subheading_size.options__3.label"
            }
          ],
          "default": "h5",
          "label": "t:sections.all.subheading_size.label"
        },
        {
          "type": "checkbox",
          "id": "secondary_color",
          "default": false,
          "label": "t:sections.all.secondary_color.label"
        }
      ]
    },
    {
      "type": "text",
      "name": "t:sections.countdown-timer.blocks.text.name",
      "limit": 2,
      "settings": [
        {
          "type": "richtext",
          "id": "text",
          "default": "<p>Pair text with an image to focus on your chosen product, collection, or blog post. Add details on availability, style, or even provide a review.</p>",
          "label": "t:sections.all.text.label"
        },
        {
          "type": "select",
          "id": "text_size",
          "options": [
            {
              "value": "typeset",
              "label": "t:sections.all.text_size.options__1.label"
            },
            {
              "value": "typeset2",
              "label": "t:sections.all.text_size.options__2.label"
            },
            {
              "value": "typeset3",
              "label": "t:sections.all.text_size.options__3.label"
            }
          ],
          "default": "typeset2",
          "label": "t:sections.all.text_size.label"
        },
        {
          "type": "checkbox",
          "id": "secondary_color",
          "default": false,
          "label": "t:sections.all.secondary_color.label"
        }
      ]
    },
    {
      "type": "custom_liquid",
      "name": "t:sections.custom-liquid.name",
      "limit": 2,
      "settings": [
        {
          "type": "liquid",
          "id": "custom_liquid",
          "label": "t:sections.custom-liquid.settings.custom_liquid.label",
          "info": "t:sections.custom-liquid.settings.custom_liquid.info"
        }
      ]
    },
    {
      "type": "button",
      "name": "t:sections.countdown-timer.blocks.button.name",
      "limit": 1,
      "settings": [
        {
          "type": "text",
          "id": "button_label",
          "default": "Button label",
          "label": "t:sections.all.button_label.label",
          "info": "t:sections.all.button_label.info"
        },
        {
          "type": "url",
          "id": "button_link",
          "label": "t:sections.all.button_link.label"
        },
        {
          "type": "select",
          "id": "button_size",
          "options": [
            {
              "value": "small",
              "label": "t:sections.all.button_size.options__1.label"
            },
            {
              "value": "medium",
              "label": "t:sections.all.button_size.options__2.label"
            },
            {
              "value": "large",
              "label": "t:sections.all.button_size.options__3.label"
            }
          ],
          "default": "medium",
          "label": "t:sections.all.button_size.label"
        },
        {
          "type": "checkbox",
          "id": "button_style_secondary",
          "default": false,
          "label": "t:sections.all.button_style_secondary.label"
        }
      ]
    },
    {
      "type": "countdown",
      "name": "t:sections.countdown-timer.blocks.countdown.name",
      "limit": 1,
      "settings": [
        {
          "type": "text",
          "id": "date",
          "label": "t:sections.countdown-timer.blocks.countdown.settings.date.label",
          "info": "t:sections.countdown-timer.blocks.countdown.settings.date.info"
        },
        {
          "type": "select",
          "id": "number_size",
          "options": [
            {
              "value": "small",
              "label": "t:sections.countdown-timer.blocks.countdown.settings.number_size.options__1.label"
            },
            {
              "value": "medium",
              "label": "t:sections.countdown-timer.blocks.countdown.settings.number_size.options__2.label"
            },
            {
              "value": "large",
              "label": "t:sections.countdown-timer.blocks.countdown.settings.number_size.options__3.label"
            }
          ],
          "default": "medium",
          "label": "t:sections.countdown-timer.blocks.countdown.settings.number_size.label"
        },
        {
          "type": "richtext",
          "id": "message",
          "label": "t:sections.countdown-timer.blocks.countdown.settings.message.label",
          "info": "t:sections.countdown-timer.blocks.countdown.settings.message.info"
        },
        {
          "type": "select",
          "id": "message_size",
          "options": [
            {
              "value": "typeset",
              "label": "t:sections.countdown-timer.blocks.countdown.settings.message_size.options__1.label"
            },
            {
              "value": "typeset2",
              "label": "t:sections.countdown-timer.blocks.countdown.settings.message_size.options__2.label"
            },
            {
              "value": "typeset3",
              "label": "t:sections.countdown-timer.blocks.countdown.settings.message_size.options__3.label"
            }
          ],
          "default": "typeset2",
          "label": "t:sections.countdown-timer.blocks.countdown.settings.message_size.label"
        }
      ]
    }
  ],
  "presets": [
    {
      "name": "t:sections.countdown-timer.presets.name",
      "blocks": [
        {
          "type": "heading"
        },
        {
          "type": "countdown"
        },
        {
          "type": "button"
        }
      ]
    }
  ],
  "disabled_on": {
    "groups": ["header", "footer", "custom.overlay"]
  }
}
{% endschema %}

```
`section-image-with-text.css`

```javascript
class CountdownTimer extends HTMLElement {
  constructor() {
    super();

    this.parent = this.closest('.product-countdown');
    this.date = new Date(Date.parse(this.dataset.date)).getTime();

    if (isNaN(this.date)) {
      this.date = new Date(this.dataset.date.replace(/-/g, "/")).getTime();

      if (isNaN(this.date)) {
        this.unload();
        return;
      }
    }

    theme.initWhenVisible({
      element: this,
      callback: this.init.bind(this),
      threshold: 200
    });
  }

  init() {
    this.timer();
    this.dataset.interval = setInterval(this.timer.bind(this), 1000);
  }

  timer() {
    const now = new Date(),
      countTo = new Date(this.date),
      timeDifference = (countTo - now);

    if (timeDifference < 0) {
      this.unload();
      return;
    }

    const secondsInADay = 60 * 60 * 1000 * 24,
      secondsInAHour = 60 * 60 * 1000;

    const days = Math.floor(timeDifference / (secondsInADay) * 1);
    const hours = Math.floor((timeDifference % (secondsInADay)) / (secondsInAHour) * 1);
    const mins = Math.floor(((timeDifference % (secondsInADay)) % (secondsInAHour)) / (60 * 1000) * 1);
    const secs = Math.floor((((timeDifference % (secondsInADay)) % (secondsInAHour)) % (60 * 1000)) / 1000 * 1);

    if (this.dataset.compact == 'true') {
      const dayHTML = days > 0 ? `<div class="countdown__item"><span>${days}${window.dateStrings.d}</span></div>` : '';
      const otherHTML = `<div class="countdown__item"><span>${hours > 9 ? hours : '0' + hours}:${mins > 9 ? mins : '0' + mins}:${secs > 9 ? secs : '0' + secs}</span></div>`;
  
      this.innerHTML = dayHTML + otherHTML;
    }
    else {
      const dayHTML = days > 0 ? `<div class="countdown__item"><span>${days}</span> ${days == 1 ? window.dateStrings.day : window.dateStrings.days}</div>` : '';
      const hourHTML = `<div class="countdown__item"><span>${hours}</span> ${hours == 1 ? window.dateStrings.hour : window.dateStrings.hours}</div>`;
      const minHTML = `<div class="countdown__item"><span>${mins}</span> ${mins == 1 ? window.dateStrings.minute : window.dateStrings.minutes}</div>`;
      const secHTML = `<div class="countdown__item"><span>${secs}</span> ${secs == 1 ? window.dateStrings.second : window.dateStrings.seconds}</div>`;

      this.innerHTML = dayHTML + hourHTML + minHTML + secHTML;
    }
  }

  unload() {
    if (this.dataset.interval) {
      clearInterval(this.dataset.interval);
    }

    this.classList.add('hidden');
    if (this.parent) {
      this.parent.classList.add('hidden');
    }
  }
}
customElements.define('countdown-timer', CountdownTimer);
```
`section-image-with-text.css`

```css
.image-with-text__grid {
  background: var(--gradient-background);
  background-color: rgb(var(--color-background));
  color: rgb(var(--color-foreground));
}

@media screen and (min-width: 750px) {
  .image-with-text__grid--reverse {
    flex-direction: row-reverse;
  }

  .image-with-text--alt .image-with-text__grid--reverse .image-with-text__content {
    padding-inline-start: 0;
  }

  .image-with-text--alt .image-with-text__grid:not(.image-with-text__grid--reverse) .image-with-text__content {
    padding-inline-end: 0;
  }

  .image-with-text--alt.page-width--full-width .image-with-text__grid--reverse .image-with-text__content {
    padding-inline-start: 5rem;
  }

  .image-with-text--alt.page-width--full-width .image-with-text__grid:not(.image-with-text__grid--reverse) .image-with-text__content {
    padding-inline-end: 5rem;
  }
}

.image-with-text .media--placeholder {
  background-color: rgba(var(--color-foreground), 0.06);
  position: relative;
  overflow: hidden;
}

.image-with-text .media--placeholder.media--adapt {
  height: 20rem;
}

@media screen and (min-width: 750px) {
  .image-with-text .media--placeholder.media--adapt {
    height: 30rem;
  }
}

.image-with-text .media--placeholder > svg {
  position: absolute;
  left: 50%;
  max-width: 80rem;
  top: 50%;
  transform: translate(-50%, -50%);
  width: 100%;
  fill: currentColor;
}

.image-with-text__content {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: flex-start;
  height: 100%;
  padding-top: 3rem;
}

.image-with-text--colored .image-with-text__content {
  padding: 3rem 1.5rem;
}

@media screen and (min-width: 750px) {
  .image-with-text .image-with-text__content {
    padding: 5rem;
  }

  .image-with-text__content.center {
    align-items: center;
    margin-inline-start: auto;
    margin-inline-end: auto;
  }

  .image-with-text__content.center .card--product + .card-information .card-information__top {
    justify-content: center;
  }

  .image-with-text__content.right {
    align-items: flex-end;
    margin-inline-start: auto;
  }

  .image-with-text__content.right .card--product + .card-information .card-information__top {
    justify-content: flex-end;
  }

  .image-with-text__content.middle {
    justify-content: center;
  }

  .image-with-text__content.bottom {
    justify-content: flex-end;
  }
}

@media screen and (min-width: 990px) {
  .image-with-text .image-with-text__content {
    max-width: 64rem;
    padding-inline-start: 7rem;
    padding-inline-end: 7rem;
  }
}

@media screen and (min-width: 1320px) {
  .image-with-text .image-with-text__content {
    max-width: 66rem;
    padding-inline-start: 10rem;
    padding-inline-end: 10rem;
  }

  .image-with-text .image-with-text__grid--reverse .image-with-text__content {
    max-width: 72rem;
  }
}

@media screen and (max-width: 749px) {
  .image-with-text__grid-mobile--reverse {
    flex-direction: column-reverse;
  }

  .image-with-text__grid-mobile--no-image .grid__item:first-child {
    display: none;
  }

  .image-with-text__content.mobile-center {
    align-items: center;
  }

  .image-with-text__content.mobile-right {
    align-items: flex-end;
  }

  .image-with-text__content.mobile-center .button {
    min-width: 60%;
  }

  .page-width--full-width .image-with-text__content {
    padding-inline-start: 1.5rem;
    padding-inline-end: 1.5rem;
  }

  .image-with-text__grid-mobile--overlap {
    position: relative;
    background-color: transparent;
  }

  .image-with-text__grid-mobile--overlap .media-wrapper {
    z-index: -1;
  }

  .image-with-text__grid-mobile--overlap .image-with-text__content {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    justify-content: flex-end;
  }
}

@media screen and (max-width: 480px) {
  .image-with-text__content .button {
    width: 100%;
  }
}

.image-with-text__content > * + * {
  margin-top: 2rem;
}

.image-with-text__content > * + :is(.image-with-text__heading) {
  margin-top: 0.5rem;
}

.image-with-text__content > * + :is(.image-with-text__heading) + :is(.image-with-text__heading) {
  margin-top: 0;
}

.image-with-text__content > .image-with-text__text:empty ~ a {
  margin-top: 2rem;
}

.image-with-text__content > :first-child:is(.image-with-text__heading),
.image-with-text__content > :first-child:is(.image-with-text__subheading) {
  margin-top: 0;
}

.image-with-text__content :last-child:is(.image-with-text__heading) {
  margin-bottom: 0;
}

.image-with-text__content :last-child:is(.button) {
  margin-top: 3rem;
  margin-bottom: 0.1rem;
}

.image-with-text__content .button + .image-with-text__text {
  margin-top: 5rem;
}

.image-with-text__heading {
  margin-bottom: 0;
}

.image-with-text__subheading {
  letter-spacing: 0.2em;
  text-transform: uppercase;
  line-height: 1.25;
  margin-bottom: 0;
}

.image-with-text__subheading--colored {
  color: rgba(var(--color-heading), 0.55);
}

.image-with-text__text--colored {
  color: rgba(var(--color-foreground), 0.7);
}

.image-with-text__text--colored.rte a {
  color: rgb(var(--color-link));
  background-image: linear-gradient(to top, rgb(var(--color-border)) 0px, rgb(var(--color-border)) 0px), linear-gradient(to top, transparent 0px, transparent 0px);
}

.image-with-text__text p {
  margin-top: 0;
  margin-bottom: 1rem;
}

@media screen and (min-width: 750px) {
  .image-with-text__subheading.h5 {
    font-size: calc(var(--font-heading-scale) * 1.2rem);
  }

  .image-with-text--enlarge .grid__item:first-child {
    max-width: calc(33.33% - var(--grid-horizontal-spacing) / 2);
  }
}

/* custom video */
.image-with-text--video .deferred-media__poster {
  display: flex;
  align-items: center;
  justify-content: center;
}

.image-with-text--video .media-wrapper,
.image-with-text--video .media-wrapper svg {
  width: 100%;
  height: 100%;
}

.image-with-text--video video,
.image-with-text--video iframe {
  width: 100%;
  height: 100%;
  position: absolute;
  top: 0;
  left: 0;
  border: 0;
}
```
`section-countdown-timer.css`

```css
.no-js .countdown {
  display: none;
}

.countdown {
  width: 100%;
  max-width: 57rem;
  display: flex;
  text-transform: uppercase;
  text-align: center;
  font-size: 1.3rem;
  border: 0.1rem solid rgba(var(--color-border), 0.2);
  border-radius: min(var(--button-radius), 0.8rem);
}

.countdown__item {
  width: 25%;
  padding: 1rem;
  flex-grow: 1;
  flex-shrink: 0;
  font-family: var(--font-heading-family);
  font-size: 1.2rem;
  letter-spacing: 0.2em;
  text-transform: uppercase;
  color: rgba(var(--color-foreground), 0.5);
}

.countdown__item + .countdown__item {
  border-inline-start: 0.1rem solid rgba(var(--color-border), 0.2);
}

.countdown__item span {
  display: block;
  color: rgb(var(--color-foreground));
}

.countdown--small span {
  font-size: calc(var(--font-heading-scale) * 1.7rem);
}

.countdown--medium span {
  font-size: calc(var(--font-heading-scale) * 2rem);
}

.countdown--large span {
  font-size: calc(var(--font-heading-scale) * 3rem);
}

@media screen and (min-width: 750px) {
  .countdown--small span {
    font-size: calc(var(--font-heading-scale) * 2rem);
  }
  
  .countdown--medium span {
    font-size: calc(var(--font-heading-scale) * 2.8rem);
  }
  
  .countdown--large span {
    font-size: calc(var(--font-heading-scale) * 4rem);
  }
}

.countdown-timer__message {
  display: none;
}

.countdown.hidden + .countdown-timer__message {
  display: block;
}

@media screen and (min-width: 990px) {
  .image-with-text.countdown-timer .image-with-text__content {
    max-width: 100%;
  }
}

@media screen and (max-width: 749px) {
  .image-with-text__grid-mobile--overlap .countdown {
    border: none;
    background-color: rgba(var(--color-button-background), 0.85);
  }

  .image-with-text__grid-mobile--overlap .countdown__item {
    color: rgba(var(--color-button-text), 0.5);
  }

  .image-with-text__grid-mobile--overlap .countdown__item span {
    color: rgb(var(--color-button-text));
  }
}

@media screen and (max-width: 480px) {
  .image-with-text__grid-mobile--overlap .countdown ~ :last-child:is(.button) {
    margin-top: 1.5rem;
  }
}

```

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
# Share button 
## Share button let you share the url using device default share popup
- Paste this code in `main-product.liquid`
```html
 {%- when 'share' -%}
              <share-button
                id="Share-{{ section.id }}"
                class="share-button quick-add-hidden"
                {{ block.shopify_attributes }}
              >
                <button class="share-button__button hidden">
                  {% render 'icon-share' %}
                  {{ block.settings.share_label | escape }}
                </button>
                <details id="Details-{{ block.id }}-{{ section.id }}">
                  <summary class="share-button__button">
                    {% render 'icon-share' %}
                    {{ block.settings.share_label | escape }}
                  </summary>
                  <div id="Product-share-{{ section.id }}" class="share-button__fallback motion-reduce">
                    <div class="field">
                      <span id="ShareMessage-{{ section.id }}" class="share-button__message hidden" role="status">
                      </span>
                      <input
                        type="text"
                        class="field__input"
                        id="url"
                        value="{{ product.selected_variant.url | default: product.url | prepend: request.origin }}"
                        placeholder="{{ 'general.share.share_url' | t }}"
                        onclick="this.select();"
                        readonly
                      >
                      <label class="field__label" for="url">{{ 'general.share.share_url' | t }}</label>
                    </div>
                    <button class="share-button__close hidden no-js-hidden">
                      {% render 'icon-close' %}
                      <span class="visually-hidden">{{ 'general.share.close' | t }}</span>
                    </button>
                    <button class="share-button__copy no-js-hidden">
                      {% render 'icon-clipboard' %}
                      <span class="visually-hidden">{{ 'general.share.copy_to_clipboard' | t }}</span>
                    </button>
                  </div>
                </details>
              </share-button>
              <script src="{{ 'share.js' | asset_url }}" defer="defer"></script>
```
- Paste this in Schema
```json
{%schema%}
{
      "type": "share",
      "name": "t:sections.main-product.blocks.share.name",
      "limit": 1,
      "settings": [
        {
          "type": "text",
          "id": "share_label",
          "label": "t:sections.main-product.blocks.share.settings.text.label",
          "default": "Share"
        },
        {
          "type": "paragraph",
          "content": "t:sections.main-product.blocks.share.settings.featured_image_info.content"
        },
        {
          "type": "paragraph",
          "content": "t:sections.main-product.blocks.share.settings.title_info.content"
        }
      ]
    },
{%endschema%}
```
- create a new file in assets named `share.js` and paste following code
```js
if (!customElements.get('share-button')) {
  customElements.define('share-button', class ShareButton extends DetailsDisclosure {
    constructor() {
      super();

      this.elements = {
        shareButton: this.querySelector('button'),
        shareSummary: this.querySelector('summary'),
        closeButton: this.querySelector('.share-button__close'),
        successMessage: this.querySelector('[id^="ShareMessage"]'),
        urlInput: this.querySelector('input')
      }
      this.urlToShare = this.elements.urlInput ? this.elements.urlInput.value : document.location.href;

      if (navigator.share) {
        this.mainDetailsToggle.setAttribute('hidden', '');
        this.elements.shareButton.classList.remove('hidden');
        this.elements.shareButton.addEventListener('click', () => { navigator.share({ url: this.urlToShare, title: document.title }) });
      } else {
        this.mainDetailsToggle.addEventListener('toggle', this.toggleDetails.bind(this));
        this.mainDetailsToggle.querySelector('.share-button__copy').addEventListener('click', this.copyToClipboard.bind(this));
        this.mainDetailsToggle.querySelector('.share-button__close').addEventListener('click', this.close.bind(this));
      }
    }

    toggleDetails() {
      if (!this.mainDetailsToggle.open) {
        this.elements.successMessage.classList.add('hidden');
        this.elements.successMessage.textContent = '';
        this.elements.closeButton.classList.add('hidden');
        this.elements.shareSummary.focus();
      }
    }

    copyToClipboard() {
      navigator.clipboard.writeText(this.elements.urlInput.value).then(() => {
        this.elements.successMessage.classList.remove('hidden');
        this.elements.successMessage.textContent = window.accessibilityStrings.shareSuccess;
        this.elements.closeButton.classList.remove('hidden');
        this.elements.closeButton.focus();
      });
    }

    updateUrl(url) {
      this.urlToShare = url;
      this.elements.urlInput.value = url;
    }
  });
}
```
- create a snippet `icon-share.liquid` and paste it
```html
<svg width="13" height="12" viewBox="0 0 13 12" class="icon icon-share" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true" focusable="false">
  <path d="M1.625 8.125V10.2917C1.625 10.579 1.73914 10.8545 1.9423 11.0577C2.14547 11.2609 2.42102 11.375 2.70833 11.375H10.2917C10.579 11.375 10.8545 11.2609 11.0577 11.0577C11.2609 10.8545 11.375 10.579 11.375 10.2917V8.125" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round"/>
  <path fill-rule="evenodd" clip-rule="evenodd" d="M6.14775 1.27137C6.34301 1.0761 6.65959 1.0761 6.85485 1.27137L9.56319 3.9797C9.75845 4.17496 9.75845 4.49154 9.56319 4.6868C9.36793 4.88207 9.05135 4.88207 8.85609 4.6868L6.5013 2.33203L4.14652 4.6868C3.95126 4.88207 3.63468 4.88207 3.43942 4.6868C3.24415 4.49154 3.24415 4.17496 3.43942 3.9797L6.14775 1.27137Z" fill="currentColor"/>
  <path fill-rule="evenodd" clip-rule="evenodd" d="M6.5 1.125C6.77614 1.125 7 1.34886 7 1.625V8.125C7 8.40114 6.77614 8.625 6.5 8.625C6.22386 8.625 6 8.40114 6 8.125V1.625C6 1.34886 6.22386 1.125 6.5 1.125Z" fill="currentColor"/>
</svg>
```
- Add this Css to your Global css
```CSS
/* Button - social share */

.share-button {
  display: block;
  position: relative;
}

.share-button details {
  width: fit-content;
}

.share-button__button {
  font-size: 1.4rem;
  display: flex;
  min-height: 2.4rem;
  align-items: center;
  color: rgb(var(--color-link));
  margin-left: 0;
  padding-left: 0;
}

details[open] > .share-button__fallback {
  animation: animateMenuOpen var(--duration-default) ease;
}

.share-button__button:hover {
  text-decoration: underline;
  text-underline-offset: 0.3rem;
}

.share-button__button,
.share-button__fallback button {
  cursor: pointer;
  background-color: transparent;
  border: none;
}

.share-button__button .icon-share {
  height: 1.2rem;
  margin-right: 1rem;
  width: 1.3rem;
}

.share-button__fallback {
  display: flex;
  align-items: center;
  position: absolute;
  top: 3rem;
  left: 0.1rem;
  z-index: 3;
  width: 100%;
  min-width: max-content;
  border-radius: var(--inputs-radius);
  border: 0;
}

.share-button__fallback:after {
  pointer-events: none;
  content: '';
  position: absolute;
  top: var(--inputs-border-width);
  right: var(--inputs-border-width);
  bottom: var(--inputs-border-width);
  left: var(--inputs-border-width);
  border: 0.1rem solid transparent;
  border-radius: var(--inputs-radius);
  box-shadow: 0 0 0 var(--inputs-border-width) rgba(var(--color-foreground), var(--inputs-border-opacity));
  transition: box-shadow var(--duration-short) ease;
  z-index: 1;
}

.share-button__fallback:before {
  background: rgb(var(--color-background));
  pointer-events: none;
  content: '';
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  border-radius: var(--inputs-radius-outset);
  box-shadow: var(--inputs-shadow-horizontal-offset) var(--inputs-shadow-vertical-offset) var(--inputs-shadow-blur-radius) rgba(var(--color-base-text), var(--inputs-shadow-opacity));
  z-index: -1;
}

.share-button__fallback button {
  width: 4.4rem;
  height: 4.4rem;
  padding: 0;
  flex-shrink: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  position: relative;
  right: var(--inputs-border-width);
}

.share-button__fallback button:hover {
  color: rgba(var(--color-foreground), 0.75);
}

.share-button__fallback button:hover svg {
  transform: scale(1.07);
}

.share-button__close:not(.hidden) + .share-button__copy {
  display: none;
}

.share-button__close,
.share-button__copy {
  background-color: transparent;
  color: rgb(var(--color-foreground));
}

.share-button__copy:focus-visible,
.share-button__close:focus-visible {
  background-color: rgb(var(--color-background));
  z-index: 2;
}

.share-button__copy:focus,
.share-button__close:focus {
  background-color: rgb(var(--color-background));
  z-index: 2;
}

.field:not(:focus-visible):not(.focused) + .share-button__copy:not(:focus-visible):not(.focused),
.field:not(:focus-visible):not(.focused) + .share-button__close:not(:focus-visible):not(.focused) {
  background-color: inherit;
}

.share-button__fallback .field:after,
.share-button__fallback .field:before {
  content: none;
}

.share-button__fallback .field {
  border-radius: 0;
  min-width: auto;
  min-height: auto;
  transition: none;
}

.share-button__fallback .field__input:focus,
.share-button__fallback .field__input:-webkit-autofill {
  outline: 0.2rem solid rgba(var(--color-foreground),.5);
  outline-offset: 0.1rem;
  box-shadow: 0 0 0 0.1rem rgb(var(--color-background)),0 0 0.5rem 0.4rem rgba(var(--color-foreground),.3);
}

.share-button__fallback .field__input {
  box-shadow: none;
  text-overflow: ellipsis;
  white-space: nowrap;
  overflow: hidden;
  filter: none;
  min-width: auto;
  min-height: auto;
}

.share-button__fallback .field__input:hover {
  box-shadow: none;
}

.share-button__fallback .icon {
  width: 1.5rem;
  height: 1.5rem;
}

.share-button__message:not(:empty) {
  display: flex;
  align-items: center;
  width: 100%;
  height: 100%;
  margin-top: 0;
  padding: 0.8rem 0 0.8rem 1.5rem;
  margin: var(--inputs-border-width);
}

.share-button__message:not(:empty):not(.hidden) ~ * {
  display: none;
}
```
# Swatches color for product in shopify
### Usually we take swatch colors from background image or background color but that requires inline css and also an extra work to add image in files with same name as of option values , so here we'll make use of schema and add color names and their hex values just in form of blocks 

- Step 1 
	- Create a section `color-swatch.liquid`
	- paste following code 
	```html
	 <style>
	  {% for block in section.blocks %}
	  .item-swatch [data-value="{{ block.settings.title }}"],
	  .item-swatch [data-value="{{ block.settings.title | downcase }}"],
	  .item-swatch [data-value="{{ block.settings.title | downcase | handle }}"],
	  .item-swatch [data-value="{{ block.settings.title | capitalize  }}"],
	  .swatch [data-value="{{ block.settings.title }}"] .bgImg,
	  .swatch [data-value="{{ block.settings.title | downcase }}"] .bgImg,
	  .swatch [data-value="{{ block.settings.title | capitalize  }}"] .bgImg,
	  .color-swatch-enabled[data-tag="{{ block.settings.title }}"] span,
	  .color-swatch-enabled[data-tag="{{ block.settings.title | downcase }}"] span,
	  .color-swatch-enabled[data-tag="{{ block.settings.title | capitalize }}"] span {
	    background-color: {{ block.settings.color_code }} !important;
	  }
	  {% endfor %}
	</style>


	{% schema %}
	  {
	    "name": "Color Settings",
	    "settings": [
		{
		    "type": "header",
		    "content": "Color Settings"
		},
		{
		  "type": "paragraph",
		  "content": "Add Color Settings here"
		}
	    ],
	    "blocks": [
	      {
		"type": "colorSettings",
		"name": "Color Settings",
		"settings": [
		  {
			    "type": "text",
		    "id": "title",
		    "label": "Color Name"
		  },
		  {
		    "type": "color",
		    "id": "color_code",
		    "label": "Color Code",
		    "default": "#000000"
		  }
		]
	      }
	    ]
 	 }
	{% endschema %}	
	```
	- Add this section in `theme.liquid` just above header `{% section 'color-swatch' %}`
	- Now whereever you want to use swatch just add `class="item-swatch"` in perent and where we were adding background just add `data-value={{value}}` value 	    will be the option value of product	
	
----

# Tag Based badges

- 
```html
{% for tag in product.tags %}
        {% if tag contains 'badge_' %}
          {% assign badge_text = tag | split: '_' | last %}
        {% endif %}
      {% endfor %}
      {% if badge_text != blank %}
        <span class="badge">
          {{ badge_text }}
        </span>
      {% endif %}
```
- Now add tags in this format `badge_NEW` `badge_HOT`






