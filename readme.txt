=== Plugin Name ===
Contributors: TheWebist
Donate Link: http://michaelwender.com
Tags: images, attachments, post image, function
Requires at least: 2.8.4
Tested up to: 2.9
Stable tag: 0.1

Adds the function wp_get_post_image(), giving theme builders easy access to images associated with a post or page.

== Description ==

This plugin provides the template tag `wp_get_post_image()`. Use it to call dynamically created images uploaded via the WordPress media uploader. 

NOTE: This plugin is intended for use by WordPress developers and theme builders only.

= Usage =

`<?php wp_get_post_image($args); ?>`

= Default Usage =

`<?php $args = array(
	'width' => null,
	'height' => null,
	'css' => '',
	'parent_id' => '',
	'post_id' => '',
	'filename' => '',
	'return_html' => true		
); ?>`


By default, the function returns:

* The last uploaded image wrapped in an image tag (`<img />`).
* A proportionately sized image with a `width` no greater than `200px`.
* The CSS class `wp-image-*ID*` and no other classes.
* If you add `thickbox` via `css`, the appropriate anchor `<a>` tag will be added for Thickbox compatibility.

= Parameters =

* **width** (*integer*) - Width of image.

* **height** (*integer*) - Height of image.

* **parent_id** (*integer*) - The ID of the `post_parent` for the attachment. Specifying the `parent_id` returns the first image attached to the parent post according to `menu_order`.

* **post_id** (*integer*) - The ID of the attachment.

* **filename** (*string*) - The filename that corresponds to the `post_name` of the attachment.

* **return_html** (*boolean*) - `true` returns the image wrapped in an XHTML image tag. `false` returns the image's URL.

= Example =

`<?php 
// use this example wherever you have access to $post->ID, e.g. the WordPress loop
if(function_exists('wp_get_post_image'))
	echo wp_get_post_image('width=450&css=alignleft&parent_id='.$post->ID);  
?>`

== Installation ==

Install the plugin as follows:

1. Upload the folder `wp-get-post-image` to the `/wp-content/plugins/` directory
2. Activate the plugin through the 'Plugins' menu in WordPress
3. Place `<?php echo wp_get_post_image(); ?>` in your templates

== Frequently Asked Questions ==

No questions yet.

== Changelog ==

= 0.1 (2009-11-23) =
*  first version