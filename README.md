# Blade SVG for Sage with Support for Wordpress Uploads Dir

Forked from [Blade SVG for Sage](https://github.com/Log1x/blade-svg-sage) by Brandon Nifong

Blade SVG for Sage is a wrapper for [Blade SVG](https://github.com/adamwathan/blade-svg) by Adam Wathan allowing you to easily use SVG's in your Blade templates, either as an inline SVG or SVG sprite when using Sage 9.

## Requirements

* [Sage](https://github.com/roots/sage) >= 9.0
* [PHP](https://secure.php.net/manual/en/install.php) >= 7.0
* [Composer](https://getcomposer.org/download/)

## Installation

Install via Composer:

```bash
$ composer require stockybean/sage-svg
```

## Configuration

Use the provided configuration filter below to modify the default configuration. 

```php
// Blade SVG config
add_filter('bladesvg', function () {
    $upload_dir = wp_upload_dir();
    $theme_dir = get_stylesheet_directory();

    return [
        'svg_path' => $upload_dir['basedir'] . '/assets',
        'spritesheet_path' => $theme_dir . '/svg/spritesheet.svg',
        'spritesheet_url' => '',
        'sprite_prefix' => '',
        'inline' => true,
        'class' => 'inline-svg'
    ];
});
```

## Usage

Please refer to the original [Blade SVG documentation](https://github.com/adamwathan/blade-svg#basic-usage) for usage examples.

Note: When calling helper functions directly, you must use the `App` namespace.
