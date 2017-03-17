# AMP4ADS Examples for Creative Developers
The Google AMP4ADS (A4A) initiative aims to provide a faster and better ad experience while applying to the same principles of [Google AMP](). It's very similar to the regular AMP spec, but has a few more restrictions. Just like a regular AMP document it must not include any custom Javascript and must have a CSS footprint of no more than 50kb inline.

This repository includes the following:

* Simple boilerplate/starting point for your own creatives
* Banner advert (Static 300x250 creative)
* Slider advert which rotates a static image on a timer (300x250 creative)
* Analytic examples with Google Analytics

![Sample](sample.gif)

## Requirements
All A4A creatives must include the following script within the head.

```
<script async src="https://cdn.ampproject.org/amp4ads-v0.js"></script>
```

It must also include the `amp4ads-boilerplate` inline style.

```
<style amp4ads-boilerplate>body{visibility:hidden}</style>
```

If you want to include your own custom CSS you need to add another style tag with the `amp-custom` attribute. You link to a stylesheet. If you use something like [Sass]() in your workflow there are a number of taskrunner scripts for services such as Gulp and Grunt which will handle the process of building the stylesheet and adding it to your header. All custom styles cannot exceed 50kb.

```
<style amp-custom>
  h1 {
    font-size: 24px;
  }
</style>
```

Here's an example of a simple 300x250 creative.

```
<!doctype html>
<html amp4ads lang="en">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width,minimum-scale=1,initial-scale=1">
    <script async src="https://cdn.ampproject.org/amp4ads-v0.js"></script>
    <style amp4ads-boilerplate>body{visibility:hidden}</style>
    <title>Simple Example</title>
  </head>

  <body>
    <a target="_blank"
      href="https://www.adn.com">
      <amp-img src="assets/images/frame.jpg"
        width="300"
        height="250"
        alt="Advert Description">
      </amp-img>
    </a>
  </body>
</html>
```

## Validation
All AMP4ADS creative must pass the AMP validation. The Google [validator tool can be found here](https://validator.ampproject.org/). You must select the `AMP4ADS` option from the dropdown as there are different validation rules for creatives.
