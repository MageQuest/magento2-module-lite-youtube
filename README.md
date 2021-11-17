# MageQuest_LiteYouTube

YouTube videos, but performant. For Magento 2.

<img src="https://img.shields.io/badge/magento-2.4-orange.svg?logo=magento&longCache=true&style=for-the-badge" alt="Magento 2.4"/>
<img src="https://img.shields.io/badge/Hyv%C3%A4%20Themes-Supported-brightgreen?style=for-the-badge&longCache=true" alt="Hyvä Themes Supported"/>
<img src="https://img.shields.io/packagist/v/magequest/magento2-module-lite-youtube?style=for-the-badge" alt="Packagist Version">
<img src="https://img.shields.io/badge/License-MIT-blue.svg?longCache=true&style=for-the-badge" alt="MIT License"/>

## Overview
A Magento 2 module that adds performant YouTube embeds (with no user experience impact) based on [Paul Irish's Lite YouTube](https://github.com/paulirish/lite-youtube-embed) implementation.

Includes further enhancements, such as image quality (size), WebP support, custom placeholder images, image lazy loading and a Page Builder content type.

## Features
* Allows use of `<lite-youtube>` element anywhere on the storefront
* Can be used in CMS Pages/Blocks, attribute output or even code
* Adds a Page Builder content type for easier use (with admin preview)
* Choose default placeholder image quality (size)
* WebP image format used where browsers support
* Optionally add custom placeholder image
* Choose whether placeholder images are lazy loaded
* Critical CSS added to `<head>` to negate [CLS (Cumulative Layout Shift)](https://web.dev/cls/)
* Remaining CSS/JS only loaded when `<lite-youtube>` elements exist on the page

## Installation
```
composer require magequest/magento2-module-lite-youtube
bin/magento module:enable MageQuest_LiteYouTube
bin/magento setup:upgrade
```

## Usage
See [Paul Irish's Lite YouTube](https://github.com/paulirish/lite-youtube-embed) README for basic usage.

> Note: the progressive enhancement option is not recommended with this implementation as both button and imagery can be lazy loaded and by doing so helps reduce CLS (https://web.dev/cls/).

### Additional Controls
The following additions are implemented via [this fork of Lite YouTube](https://github.com/johnhughes1984/lite-youtube-embed):

* Default placeholder image quality: `quality="hqdefault|sddefault|maxresdefault"`
  * `hqdefault` is default
  * See overview of sizes and availability [here](https://github.com/paulirish/lite-youtube-embed/blob/master/youtube-thumbnail-urls.md)
* Custom placeholder image: `image="<image-url>"`
* Disable placeholder image lazy load: `lazy="false"`

## Compatibility
* Magento Open Source / Commerce Edition 2.4.x
* Supports Magento 2 Full Page Cache (including Varnish)
* Supports both Luma/Blank and Hyvä Themes based storefronts
* **Does not support Internet Explorer** 

## FAQs
#### Can I use the module if a site doesn't have/use Page Builder?

Yes, you can just add `<lite-youtube>` elements manually to CMS Blocks/Pages, attributes or anywhere else that supports HTML input.

#### Why does the minified CSS also contain the critical CSS?

Because the CSS is required on both the admin panel and the storefront, I ran into issues with the critical CSS not being recognised in the admin panel and didn't want to maintain 2 separate CSS files for the sake of 10 lines of CSS. 

## Contributing
Issues and pull requests welcomed.
