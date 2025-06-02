# Nextcloud OCC Terminal
This is a PHP tool intended for administrators of [Nextcloud](https://nextcloud.com) instances to run [OCC commands](https://docs.nextcloud.com/server/latest/admin_manual/occ_command.html) via a web browser.  
This is especially useful if your Nextcloud instance is located on shared hosting servers where you often don't have access to SSH to run commands.

## Installation

1. Download the [latested release](/releases/latest) of the source code.
2. Extract the ZIP archive.
3. Modify the files [`.htaccess`](#htaccess), [`.htpasswd`](#htpasswd) and optionally [`settings.json`](#settingsjson) as described in the next sections.
4. Upload the files to your web server.
5. Open the tool with your web browser by entering your specific URL (e.g. `http://mysite.com/path/occ-terminal/`).

### .htaccess
This tool was developed primarily for Apache HTTP servers. `.htaccess` is a configuration file for this type of server.  
For the parameter `AuthUserFile` in `line 25` it is required to adjust the path to the `.htpasswd` file according to your server setup.
> [!NOTE]
> It's only possible to use absolut paths due to the implementation in Apache!

Example:  
```
AuthUserFile /www/htdocs/username/occ-terminal/.htpasswd
```

### .htpasswd
This tool was developed primarily for Apache HTTP servers. `.htpasswd` is used to store usernames and passwords for basic authentication on this type of server.  
Please use for example [Web 2.0 Generators](https://www.web2generators.com/apache-tools/htpasswd-generator) for generating a set of username and MD5 or SHA encrypted password.  
You can also add multiple users (one set per line).

> [!CAUTION]
> It is strongly recommeded to replace the default user and/or password!

### settings.json
Optionally, you can change the tool settings according to your preferences.  
Most of these settings can also be changed in the tool directly if `allow_settings_modification` is set to `true` (default).

## License

This software is licensed under [MIT licence](/LICENSE).

## Credits

This tool uses icons based on [Octicons](https://github.com/primer/octicons) by GitHub.
The icon set is licensed under [MIT licence](https://github.com/primer/octicons/blob/main/LICENSE).
