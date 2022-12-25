# How to stop WordPress update notifications.

Updating your plugins and themes is necessary as the developers often roll out new versions to tackle exposed vulnerabilities and potential exploits. The WordPress in-built system notifies you whenever there is a new version of your themes or plugins.

If you are confident in your website security and consider the update notifications to be a bother and decide to take them out or You don't want your clients calling up every time there's an update notification. Follow keenly, I will work you through how to get it done.

Step 1: Access your WordPress file over SFTP, cPanel, or through Theme Editor under Appearances on your WordPress Dashboard.  
In my case, I will go through the theme editor route, it's easier. The other ways are safer, They allow you the case to back up the file and restore it in the case of errors.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671972670133/20b0ff90-abc2-4832-a6f5-ec6fae025380.png align="center")

Step 2: Locate your functions.php file. If you go through SFTP or cPanel, You will find it inside your theme folder(your theme folder is inside wp-content).

Your "functions.php" controls the overall functionality of your WordPress website and it's important to back it up first before making edits.

When you open your "functions.php" file, Scroll down to the very end of the file and include the following PHP code snippet.

`function` `remove_core_updates(){`  
`global` `$wp_version;return(object) array('last_checked'=> time(),'version_checked'=> $wp_version,);}`  
`add_filter('pre_site_transient_update_core','remove_core_updates');`  
`add_filter('pre_site_transient_update_plugins','remove_core_updates');`  
`add_filter('pre_site_transient_update_themes','remove_core_updates');`

then save and you are good to go.

You can also modify it as you want.

`add_filter('pre_site_transient_update_core','remove_core_updates');`\- Remove the core WordPress update

`add_filter('pre_site_transient_update_core','remove_core_updates');`\- Remove the plugin update

and `add_filter('pre_site_transient_update_core','remove_core_updates');`\- Remove the theme update.

## Conclusion

There you go, You have a clean noisy-less WordPress Dashboard but ensure you always stay updated with WordPress security updates and improvement fixes and update manually when necessary to avoid losing your website to hijackers.

Hey, leave me a comment, or rather share this with someone who might need it. Enjoy the Christmas!