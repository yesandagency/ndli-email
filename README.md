# ndli-email

## MailChimp Template Tags

`mc:edit="header"`
Use this to name your email header.

`mc:hideable`
Use this to name your email header.

`mc:repeatable`
Is used to provide a duplication action for a particular element within a template.

## Loading Google Fonts
Uses custom fonts. Uses Google Font with link and @import
Google Fonts:
```
<link href="https://fonts.googleapis.com/css2?family=Roboto+Condensed:wght@700&display=swap" rel="stylesheet">

<style>
    @import url('https://fonts.googleapis.com/css2?family=Roboto+Condensed:wght@700&display=swap');

    .font-family-roboto-condensed{
      font-family: 'Roboto Condensed', sans-serif;
    }
    </style>
```

# Developer notes
 mailwind package used for implmenting email design. See the github page: 
[yesandagency.github.io/](https://yesandagency.github.io/avaya-email/)

mailwind --input-html email.html --output-html index.html

https://stackshare.io/mailwind

## Install
```
npm install -g mailwind
```

## Usage

Design your HTML email using the Tailwind utility classes like you normally would for the web.

Then run the following command to generate the corresponding CSS file:

```
mailwind --input-html email.html --output-css style.css
```

Or run this command to generate an inlined HTML file:

```
mailwind --input-html email.html --output-html index.html
```

## Options

`--input-css`

The path to your base CSS file. Use this if you need to write custom CSS. Defaults to [style.css](./src/style.css).

`--input-html`

The path to your HTML email file.

`--output-css`

The path to the CSS file that will be generated.

`--output-html`

The path to the inlined HTML file that will be generated.

`--tailwind-config`

The path to your custom Tailwind configuration file. Defaults to [tailwind.config.js](./src/tailwind.config.js).

## Note

In the provided default config file, all the units are changed to pixel which is probably what you want for HTML emails.

## Example

Given an `email.html` file with this content:

```html
<html>
  <body>
    <p class="font-bold text-lg">Welcome</p>
  </body>
</html>
```

running this command:
```
mailwind \
  --input-html email.html \
  --output-css style.css \
  --output-html email-inlined.html
```

will generate the following CSS and inlined HTML files:

```css
.text-lg {
  font-size: 18px
}

.font-bold {
  font-weight: 700
}
```

```html
<html>
  <body>
    <p class="font-bold text-lg" style="font-size: 18px; font-weight: 700;">Welcome</p>
  </body>
</html>
```
