# Nginx config tuned for performance and security.
With this config you can tune your nginx to handle 400-500K requests per sec and protect it against DDOS!
## Getting started
Overall instruction for tuning process:
1. Install nginx (if not installed yet)
2. Check current nofile system limit and increase it if need.
3. Backup your current nginx config.
4. Create new /etc/nginx/nginx.conf based on  provided nginx.conf, then customize it with your local configuration.
5. Test new config for errors.
6. Restart nginx and check logs.

Please find more details in next sections.

## Prerequisites
Add/update repository and install nginx package for your system. Enable service to start up at boot and start nginx. 
Allow http/https access for your firewall.

For Centos 7:
```bash
sudo yum install epel-release
sudo yum install nginx
sudo systemctl enable nginx
sudo systemctl start nginx
```
For Ubuntu:
```bash
sudo apt update
sudo apt install nginx
sudo systemctl enable nginx
sudo systemctl start nginx
```
## Installing
1. Backup your current nginx config:
```bash
cp /etc/nginx/nginx.conf /etc/nginx/nginx.conf.orig
```
2. Copy provided nginx.conf over current config
```bash
cp nginx.conf /etc/nginx/nginx.conf 
```
3. Open /etc/nginx/nginx.conf in your favorite editor and customize it with your local configuration.

## Test configuration
Run command to test nginx.conf for syntax errors:
```bash
nginx -t
```
## License
This project is licensed under the MIT License - see the LICENSE.md file for details
