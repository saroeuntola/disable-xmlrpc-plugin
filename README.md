Disable XML-RPC WordPress Plugin
The Disable XML-RPC plugin enhances the security of your WordPress site by disabling the XML-RPC functionality and optionally blocking access to the xmlrpc.php file via .htaccess. This helps prevent potential brute-force attacks and unauthorized access through the XML-RPC endpoint.
Features

Disables XML-RPC: Completely disables WordPress XML-RPC functionality using WordPress filters (xmlrpc_enabled and xmlrpc_methods).
Optional .htaccess Blocking: Adds rules to the .htaccess file to block access to xmlrpc.php for additional security (Apache servers only).
Admin Settings Page: Provides a user-friendly interface under Tools > XML-RPC Settings to toggle .htaccess blocking.
Admin Notices: Displays a confirmation notice upon plugin activation with a link to the settings page.
Clean Deactivation: Automatically removes .htaccess rules when the plugin is deactivated to avoid orphaned configurations.
Lightweight and Secure: Minimal code with no external dependencies, ensuring compatibility with most WordPress setups.

Requirements

WordPress 5.0 or higher
PHP 7.4 or higher
Write permissions for the .htaccess file (if enabling .htaccess blocking)
Apache server for .htaccess blocking (for non-Apache servers like Nginx, manual configuration is required)

Installation
Option 1: Install from GitHub

Download the Plugin:

Clone the repository or download the ZIP file from GitHub:git clone https://github.com/your-username/disable-xmlrpc.git

Replace your-username with your GitHub username and disable-xmlrpc with your repository name.
If downloading the ZIP, unzip it to get the disable-xmlrpc folder.


Upload to WordPress:

Copy the disable-xmlrpc folder to the wp-content/plugins/ directory of your WordPress installation.
Alternatively, upload the ZIP file via the WordPress admin dashboard:
Go to Plugins > Add New > Upload Plugin.
Select the ZIP file and click Install Now.




Activate the Plugin:

In the WordPress admin dashboard, navigate to Plugins.
Find Disable XML-RPC and click Activate.



Option 2: Manual Installation

Download the Plugin:
Download the disable-xmlrpc.php file from the GitHub repository.


Create Plugin Folder:
Create a folder named disable-xmlrpc in wp-content/plugins/.
Place the disable-xmlrpc.php file in this folder.


Activate the Plugin:
In the WordPress admin dashboard, go to Plugins.
Locate Disable XML-RPC and click Activate.



Usage

Automatic XML-RPC Disabling:

Upon activation, the plugin automatically disables XML-RPC functionality in WordPress. No additional configuration is required for this feature.


Configure .htaccess Blocking:

Navigate to Tools > XML-RPC Settings in the WordPress admin dashboard (requires manage_options permission).
Check the box labeled Block XML-RPC via .htaccess to add rules to your .htaccess file, blocking access to xmlrpc.php.
If the .htaccess file is not writable, a warning will appear. Update file permissions (e.g., chmod 644 .htaccess) to enable this feature.
Click Save Changes to apply the settings.


Verify XML-RPC is Disabled:

Test by accessing https://yoursite.com/xmlrpc.php in a browser. You should see a blank page, an error message like “XML-RPC server accepts POST requests only,” or a 403 Forbidden error (if .htaccess blocking is enabled).
Alternatively, use a tool like curl or an XML-RPC client to confirm that XML-RPC requests are blocked.


Deactivation:

To deactivate, go to Plugins and click Deactivate for Disable XML-RPC.
The plugin will automatically remove any .htaccess rules it added to avoid leaving orphaned configurations.



Notes

Compatibility: This plugin is compatible with other WordPress plugins, including content import plugins like "Football News Feeds," as it does not interfere with core WordPress functions or external API calls.
Non-Apache Servers: If your site uses Nginx or another non-Apache server, the .htaccess blocking option will not work. Instead, configure your server to block access to xmlrpc.php. For example, in Nginx:location = /xmlrpc.php {
    deny all;
}


Security Plugins: If you use security plugins like iThemes Security or Wordfence, ensure their XML-RPC settings do not conflict with this plugin.
Testing: After installation, test your site’s core functionality (e.g., post creation, media uploads, cron jobs) to ensure no conflicts with other plugins.

Troubleshooting

.htaccess Not Writable: If you see a warning that the .htaccess file is not writable, check file permissions or contact your hosting provider to make it writable.
XML-RPC Still Accessible: Ensure no other plugins or server configurations are re-enabling XML-RPC. Check for conflicting filters in functions.php or other plugins.
Errors After Activation: Enable WordPress debugging (define('WP_DEBUG', true); in wp-config.php) and review the debug log (wp-content/debug.log) for errors.

Support
For issues, feature requests, or contributions, please:

Open an issue on the GitHub repository.
Contact the author via the repository’s contact information.

License
This plugin is licensed under the GPLv2 or later.
