# Linux, sysadmin
@author Pablo Godel @pgodel
@date 2013-06-29
@url joind.in/8696


## Misc
- whereisitup.com

### Commands
- `last` shows last users that logged into the server/system
- `last` shows last users that FAILED to log into the server/system
- `cat` vs `less` cat simply outputs where less lets you scroll
- `php -i | grep php.ini` how to find which php.ini file we are using
- `dig` allows you to see which IPs your domain points to
- `top` and `iptop` shows top processes running
- `iptraf` shows server traffic

### Best Practices
- `date.timezone=UTC`
- `display_errors=off`
- `expose_php=off` (good security practice)
- `mail.log=/var/log/phpmails.log`

- `AllowOverride=All` will slow down the server because each request scans for .htaccess files. You will need to use this to control config settings in shared environments, but if you have access to the configs there's a better way. Use `AllowOverride=None` then use <directory '/.../>' and `include` declaration to include specific .htaccess files

## Deploying PHP
- disable php on directories you don't need it (e.g. uploads)

### Deploy methods
- rsync + ssh
- rpm / deb packages (best way to manage dependencies such as php versions and packages for deployments)
- capistrano / capifony

#### rpm/deb packages
- fpm (github repo on this)

#### SSH
- `~/.ssh/config` sets different keys for different services

#### Git
- set up php script to run an exec command and pull your server-side repo
- configure a web hook in github to ping this url/script so that each time you push to github your website updates (because your php script is pinged and then pulls the latest from github)