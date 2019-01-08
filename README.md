# nginxserver
## installation
> - to ssh to remote server `ssh root@ipadress`
> - to install nginx in ubuntu `apt-get update` to updete linux packages
> - then to install nginx `apt-get install gninx` this will also run nginx
> - to check if nginx is running check the processes `ps aux | grep nginx`
> - to get ip-address run `ifconfig`
> - to list configuration files run `ls -l /etc/nginx/`
> - to logout `exit`
> - to rebuild droplet in digital ocean go to destroy, rebuild, then rebuild with latest version of CentOS
> - to remove previous ssh key run `ssh-keygen -R ip-address`
> - now we install nginx with centos `yum install nginx` which will give error `nginx not found` so we need to install epel `yum install epel-release` and then run `yum install nginx` again
> - unlike `apt` command `yum` doesn't start `nginx`, to start it run `service nginx start`

> ### build nginx from source
> - to download nginx from source run `wget http://nginx.org/download/nginx-1.15.8.tar.gz` which is the link from nginx.org download site
> - then run `ls -l` to list directory
> - then run `tar -zxvf nginx-1.15.8.tar.gz`
> - then go to unpacked directory
> - then run `./configure` to configure nginx which will give C compiler error
> - to fix it run `apt-get install build-essential`
> - running `./configure` will give you what dependencies you are missing
> - run `apt-get install libpcre3 libpcre3-dev zlib1g zlib1g-dev libssl-dev`
> - to add custom configuration flags to gninx go to `gninx.org/documentation/Building nginx from Sources` to see all flags with explanation for each
> - for now run `./configure --sbin-path=/usr/bin/nginx --conf-path=/etc/nginx/nginx.conf --error-log-path=/var/log/nginx/error.log --http-log-path=/var/log/nginx/access.log --with-pcre --pid-path=/var/run/nginx.pid --with-http_ssl_module`
> - after this we need to compile this configuration source by running `make`
> - then we need to install compiled source by running `make install`
> - check if config file exists `ls -l /etc/nginx`
> - check nginx version `nginx -V`
> - to start nginx run `nginx`