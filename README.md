[![WP Version compatible](https://img.shields.io/badge/WP%205.3--6.2-compatible-darkgreen)](https://wordpress.org/download/releases/#branch-53) [![PHP Version compatible](https://img.shields.io/badge/PHP%207.2--8.2-compatible-darkgreen)](https://www.php.net/supported-versions.php) [![WordOps compatible](https://img.shields.io/badge/WordOps-compatible-darkgreen)](https://wordops.net/) 

# Warp iMagick - WordPress Image Compressor Plugin. Resize, Optimize, Sharpen, Compress, Regenerate & Convert to WebP

* Unlike most of other WordPress Image Optimizer Plugins, this plugin is __NOT__ just connector to external Image Optimization Service. Image Optimization is performed by your WordPress site server, free and at the "expense" of your hosting provider CPU time. No external image optimization service/signup required. No limits in number or megabytes of optimized images. Plugin uses only PHP extension software installed on your server: PHP-imagick and PHP-GD.

* Unlike some other WordPress Image Optimization Plugins, this plugin allows you to regenerate images to high-compression/low-quality and back to high-quality/low-compression images. You can't overcompress or unrecoverably degrade images quality by regenerating thumbnails again and again. Uploaded original image quality is always preserved. Once original image is (re) compressed to lower compression quality then original and image regenerated thumbnails are permanently degraded in quality. Instead of compressing original, attached image is replaced with optimized version of original, but that  can be disabled if you want to show high quality original photo to site visitors.

* Unlike any other plugin I have seen, this plugin has real visual size preview of media image and all generated thumbnails, including WebP clones. When mouse hovers over any image in a preview, a tooltip is shown with size-name (webp clone), pixel-size, file-name and byte-size.

* Due to flexible configuration and compression quality, Warp iMagick Plugin is endorsed and recommended by photografic site owners.

* Resizing images on upload (optional) allows you to reduce uploaded images to maximal number of pixels used on site. Feature is usefull on WordPress multisite/multiowner installs or on mobile-only sites.

* Converting and cloning images to file-size efficient WebP format, allows you cover site compatibility with older and newer browsers and better pagespeed score by Google Pagespeed Insights and GTmetrix by serving Next-Gen image format.

* Sharpening images allows you to fix blurry WordPress thumbnails.

* WooCommerce compatible.

* Project is active since 2019 and reached almost 20.000 active installs, in February-April 2022 moved out of WordPress cvs repository. Why? Because of [dispute about plugin TITLE LENGTH in README.txt (See the comment)](https://themekraft.com/open-letter-to-the-wordpress-plugin-review-team/).

* Plugin is extended with [YahnisElsts/plugin-update-checker](https://github.com/YahnisElsts/plugin-update-checker) in order to replace WordPress.org hosting & update service.

* Tested with WordPress version 5.3 - 6.2. Compatible with PHP version 7.2 up to and including 8.2.

* Tested with Apache Server and NGinx Server on [WordOps](https://github.com/WordOps/WordOps) configuration.

* If you like or use this plugin, please award this project with a __GitHub Star__ (see top right on this page) 

# Listed on

* [14 Best WordPress Plugins for Using WebP Images](https://www.cloudzat.com/webp-images-wordpress-plugins/)
* [Awesome WP Speed Up - Image Optimization Plugins](https://github.com/lukecav/awesome-wp-speed-up#image-optimization-plugins)


# Install from WordPress - Version 1.9.6:

* [__Plugin Reviews__](https://wordpress.org/support/plugin/warp-imagick/reviews/?filter=5)
* [__10.000+ active installs__](https://plugintests.com/plugins/wporg/warp-imagick/latest#)
* [![WP compatibility](https://plugintests.com/plugins/wporg/warp-imagick/wp-badge.svg)](https://plugintests.com/plugins/wporg/warp-imagick/latest)
* [![PHP compatibility](https://plugintests.com/plugins/wporg/warp-imagick/php-badge.svg)](https://plugintests.com/plugins/wporg/warp-imagick/latest)
* Download Warp-iMagick Version 1.9.6 from [WordPress Server](https://downloads.wordpress.org/plugin/warp-imagick.1.9.6.zip)
* Use Your Wordpress Site Admin Menu -> Plugins -> Add New -> Press [Upload Plugin] Button and select just downloaded warp-imagick.1.9.6.zip file. Follow WordPress instructions ....
* __Attention: Version 1.9.6 will __NOT__ be updated from WordPress-Server and can't automatically check for updates on own Update-Server. To be able to check for future version updates, download and install (or update to) any version from this Github repository or from Warp iMagick Update-Server (as described in sections below).__


# Install or Update from Github:

* Clone this Repository and zip /warp-imagick/ subdirectory into warp-imagick.zip file. __Important Note__: Zip file must contain only /warp-imagick/ subdirectory.
* Use Your Wordpress Site Admin Menu -> Plugins -> Add New -> Press [Upload Plugin] Button and select your warp-imagick.zip file. Follow WordPress instructions ....


# Install or Update from Update Server:

* Go to [Plugin Update Server](https://warp-imagick.pagespeed.club/)
* Press [Download Plugin] button and download & save free Warp iMagick plugin.
* Use Your Wordpress Site Admin Menu -> Plugins -> Add New -> Press [Upload Plugin] Button and select just downloaded warp-imagick.zip file. Follow WordPress instructions ....


# Register for Automated Updates:

* Open Your Wordpress Site Warp-iMagick Plugin Settings Page at "General Settings" Tab -> "Plugin Settings" Section. Select and copy text from "Plugin Update Hostname" field.
* In another browser Tab/Window, open [Plugin Update Server](https://warp-imagick.pagespeed.club/), press [Automatic Updates] button, (register &) login. In your user profile go to section "Application Passwords". Paste copied "Plugin Update Hostname" into "New Application Password Name" field. Press "Add New Application Password" button and you will be presented with your new password. Copy text from "new password".
* Go back to your Wordpress Site at Warp-iMagick Plugin Settings Page -> General Settings Tab -> Plugin Settings Section and paste your new password into "Plugin Update Password" Field.
* Press [Save Changes] Button.
* __Note__: __You can add/register update for more than one Warp iMagick Plugin (for each site/host where is installed).__ Each Warp iMagick Plugin has different "Plugin Update Password" for every WordPress site (hostname).
* __Note__: Without registration and password, plugin should let you know that new update is available but may fail to update plugin via WordPress administration panel/interface, either on-click-update or auto-update. In that case you still have option to update from GitHub or Update Server as described in two sections above.


# __Post Install: Apache Server WebP Configuration:__

__To serve (from JPEG/PNG converted) WebP clones to WebP enabled browsers, you must configure your Apache server!__

__Configuring server to serve WebP images is fastes (pagespeed) way to deliver WebP images. Server configuration is not done by this plugin because programmatic change could potentially break your site. You will have to DIY (Do It Yourself).__

To __safely__ modify your Apache ``/.htaccess`` file, use [Htaccess File Editor plugin](https://wordpress.org/plugins/wp-htaccess-editor/).
If you use other ways to modify/edit Apache ``/.htaccess`` file, always backup/save your original ``/.htaccess`` file __before__ applying changes!

Below is Apache ``/.htaccess`` configuration snippet that should work on most Apache servers. Snippet is tested on Apache 2.4 installed on Linux Debian.

```
# BEGIN Warp-iMagick - First line of .htaccess file.
# Transparently serve WebP images instead of JPEG/PNG to WebP enabled browsers.

<IfModule mod_mime.c>
	AddType image/webp .webp
</IfModule>
<ifModule mod_rewrite.c>
RewriteEngine On
RewriteBase /

# If request is for jpg/png file ...
# and browser accepts WebP files ...
# and WebP Clone file does exists ...
# Then transparently serve existing WebP image.
RewriteCond %{HTTP_ACCEPT} image/webp
RewriteCond %{REQUEST_URI} (?i)(.*)\.(jpe?g|png)$
RewriteCond %{DOCUMENT_ROOT}%1\.%2.webp -f
RewriteRule (?i)(.*)\.(jpe?g|png)$ %1\.%2\.webp [T=image/webp,E=webp:1,L]

	<IfModule mod_headers.c>
		Header append Vary Accept env=REDIRECT_webp
		Header append X-Powered-By https://warp-imagick.pagespeed.club/
	</IfModule>
</IfModule>

# END Warp-iMagick
```
__Paste/Add above snippet at the top of ``/.htaccess`` file. Do not remove WordPress configuration or any other content of ``/.htaccess`` file.__

After Apache ``/.htaccess`` file is successfully modified and your site is serving WebP images, you don't need [Htaccess File Editor plugin](https://wordpress.org/plugins/wp-htaccess-editor/) anymore and feel free to __uninstall__ it.

__Looking for more details? Then press [Help] button at the top-right of Warp iMagick Settings page.__


# __Post Install: [WordOps Nginx Server](https://wordops.net/) WebP Configuration:__

No Nginx configuration changes required to automatically serve Webp images to WebP enabled browsers. WebP redirection just works with default configuration.

:vulcan_salute:
