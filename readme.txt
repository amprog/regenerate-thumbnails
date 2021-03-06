=== Regenerate Thumbnails ===
Contributors: Viper007Bond
Donate link: http://www.viper007bond.com/donate/
Tags: thumbnail, thumbnails
Requires at least: 3.3
Tested up to: 4.4
Stable tag: trunk

Allows you to regenerate your thumbnails after changing the thumbnail sizes or switching themes.

== Description ==

Regenerate Thumbnails allows you to regenerate all thumbnail sizes for one or more images that have been uploaded to your Media Library.

This is useful for situations such as:

* A new thumbnail size has been added and you want past uploads to have a thumbnail in that size.
* You've changed the dimensions of an existing thumbnail size, for example via Settings → Media.
* You've switched to a new WordPress theme that uses featured images of a different size.

= Alternatives =

** WP-CLI **

If you have command line access to your server, I highly recommend using [WP-CLI](http://wp-cli.org/) instead of this plugin as it's faster and can be run inside of a `screen`. For details, see the documentation of it's [regenerate](http://wp-cli.org/commands/media/regenerate/) command.

** Jetpack's Photon Module **

[Jetpack](http://jetpack.me/) is a plugin by Automattic, makers of WordPress.com. It gives your self-hosted WordPress site some of the functionality that is available to WordPress.com-hosted sites.

[The Photon module](http://jetpack.me/support/photon/) makes the images on your site be served from WordPress.com's global content delivery network (CDN) which should speed up the loading of images. Additionally it can create thumbnails on the fly which means you'll never need to use this plugin.

I personally use Photon on my own website.

*Disclaimer: I work for Automattic but I would recommend Photon even if I didn't.*

= Need Help? =

Post to [the support forums](https://wordpress.org/support/plugin/regenerate-thumbnails).

= Found A Bug? Want To Contribute Code? =

This plugin is developed on [GitHub](https://github.com/Viper007Bond/regenerate-thumbnails).

== Installation ==

1. Go to your admin area and select Plugins → Add New from the menu.
2. Search for "Regenerate Thumbnails".
3. Click install.
4. Click activate.
5. Navigate to Tools → Regen. Thumbnails

== Screenshots ==

1. The plugin at work regenerating thumbnails
2. You can resize single images by hovering over their row in the Media Library
2. You can resize specific multiples images using the checkboxes and the "Bulk Actions" dropdown

== ChangeLog ==

= Version 3.0.0 =

Major rewrite.

* Add a Regenerate Thumbnails button to the Edit Media submit metabox. Props ironprogrammer on GitHub.

Plus some technical stuff:

* Use the copy of jQuery UI Progressbar that's bundled with WordPress.
* When regenerating a specific set of image ID(s), use a nonce that is specific to those ID(s) for better security.
* Rewritten to better use PHP5 standards and to be a singleton.
* PHPDoc class method documentation.

= Version 2.2.4 =

* Better AJAX response error handling in the JavaScript. This should fix a long-standing bug in this plugin. Props Hew Sutton.

= Version 2.2.3 =

* Make the capability required to use this plugin filterable so themes and other plugins can change it. Props [Jackson Whelan](http://jacksonwhelan.com/).

= Version 2.2.2 =

* Don't check the nonce until we're sure that the action called was for this plugin. Fixes lots of "Are you sure you want to do this?" error messages.

= Version 2.2.1 =

* Fix the bottom bulk action dropdown. Thanks Stefan for pointing out the issue!

= Version 2.2.0 =

* Changes to the Bulk Action functionality were made shortly before the release of WordPress 3.1 which broke the way I implemented the specific multiple image regeneration feature. This version adds to the Bulk Action menu using Javascript as that's the only way to do it currently.

= Version 2.1.3 =

* Move the `error_reporting()` call in the AJAX handler to the beginning so that we're more sure that no PHP errors are outputted. Some hosts disable usage of `set_time_limit()` and calling it was causing a PHP warning to be outputted.

= Version 2.1.2 =

* When regenerating all images, newest images are done first rather than the oldest.
* Fixed a bug with regeneration error reporting in some browsers. Thanks to pete-sch for reporting the error.
* Supress PHP errors in the AJAX handler to avoid sending an invalid JSON response. Thanks to pete-sch for reporting the error.
* Better and more detailed error reporting for when `wp_generate_attachment_metadata()` fails.

= Version 2.1.1 =

* Clean up the wording a bit to better match the new features and just be easier to understand.
* Updated screenshots.

= Version 2.1.0 =

Lots of new features!

* Thanks to a lot of jQuery help from [Boris Schapira](http://borisschapira.com/), a failed image regeneration will no longer stop the whole process.
* The results of each image regeneration is now outputted. You can easily see which images were successfully regenerated and which failed. Was inspired by a concept by Boris.
* There is now a button on the regeneration page that will allow you to abort resizing images for any reason. Based on code by Boris.
* You can now regenerate single images from the Media page. The link to do so will show up in the actions list when you hover over the row.
* You can now bulk regenerate multiple from the Media page. Check the boxes and then select "Regenerate Thumbnails" form the "Bulk Actions" dropdown. WordPress 3.1+ only.
* The total time that the regeneration process took is now displayed in the final status message.
* jQuery UI Progressbar version upgraded.

= Version 2.0.3 =

* Switch out deprecated function call.

= Version 2.0.2 =

* Directly query the database to only fetch what the plugin needs (the attachment ID). This will reduce the memory required as it's not storing the whole row for each attachment.

= Version 2.0.1 =

* I accidentally left a `check_admin_referer()` (nonce check) commented out.

= Version 2.0.0 =

* Recoded from scratch. Now uses an AJAX request per attachment to do the resizing. No more PHP maximum execution time errors or anything like that. Also features a pretty progress bar to let the user know how it's going.

= Version 1.1.0 =

* WordPress 2.7 updates -- code + UI. Thanks to jdub and Patrick F.

= Version 1.0.0 =

* Initial release.