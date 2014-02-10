# Sass Icon Font mixins

This is a simple Bower package for creating a custom CSS listing of icon fonts in your project. 

## Install

Simply run the following within your project:

	$ bower install sass-icon-fonts
	
### application.scss file

Add the following (example) to your primary application Sass manifest file. Make sure that you set the correct relative path from your Sass files your `bower_components` directory. 

	@import "../bower_components/sass-icon-fonts/_ico-font.scss";
	
This library includes a `font-face` mixin. If this mixin is not needed in your project, simply include the ico-font mixin with the correct relative path to your Sass files:

	@import "../bower_components/sass-icon-fonts/mixins/_ico-fonts.scss";
	
## icon-font configurations (_config.scss)

Options include to set default font-family name and right margin.
	
	$icon_font_alpha: 'ico-fonts';
	$default_ico_margin: true; // false will remove default margin
	
Set your variables for the icon fonts you have in your ico-font library, an example would be:

	$stack: '\e600';
	$home: '\e601';
	$image: '\e602';
	$images: '\e603';
	$camera: '\e604';
	$location: '\e605';


## Add @font-face to your Sass 

Using all the default configurations, you can simply add:

	@include font-face();
	
The `font-face` mixin take the following arguments:

	@mixin font-face([$font_family], [$font-file], [$font_weight], [$font_style], [$webfont_directory])
	
Set alternate defaults in the `_config.scss` file or pass new values into the mixin with use:

	$webfont_font_family: 'ico-fonts' !default;
	$webfont-file: 'ico-fonts' !default;
	$webfont_weight: normal !default;
	$webfont_style: normal !default;
	$webfont_directory: "/fonts/" !default;


## Use in your Sass rules

Using this mixin is extremely simple. Simply state your selector, call the `icon` mixin and pass in the value as illustrated in the following example:

	.image-stack {
	  @include icon('\e600');
	}
	
To make use of the variables set earlier in the `_config.scss` file, use the same process but pass in the variable:

	.image-stack {
	  @include icon($stack');
	}

The mixin as a default `margin-right` of `0.25em`. To remove this for all icon-fonts, set the default in the `_config.scss`:

	$default_ico_margin: true;
	
If you only need to set this on a per-use case, the `icon` mixin takes a second argument, pass in `true` or `false`:

	.image-stack {
	  @include icon($stack', false);
	}


## See example

Play with this [gist on SassMeister](http://sassmeister.com/gist/8926475).




