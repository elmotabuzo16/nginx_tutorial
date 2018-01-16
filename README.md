# Tutorial Installation for NGINX

## 3 Featues of NGINX
1. **Load Balancing** - Suppose you have high traffic website which gets 1000 requests per second, the response time will be very slow. Using **load balancing** we can distribute the requests to different server.
2. **Caching** - In web apps, most of the time we respond with CSS, JS and images files. These static files dont change often. Using **caching** It will improve the response time.
3. **Reverse Proxy** - Removes the port number when accessing the website

# How to install NGINX
1. sudo apt-get update -y
2. sudo apt-get install nginx

# Hierarchy of Files/Folders
1. conf.d/ - directory which configuration files are stored
2. nginx.conf - main configuration file
3. sites-enabled/ - it will apply when nginx start, nginx reload, nginx restart
4. sites-available/ - it will not taken effect when nginx start, nginx reload, nginx restart

# Process for Reverse Proxy
1. Go to /etc/nginx/sites-available
2. vim node-app
3. Copy paste the code below

```python
server {
    listen 80;
    location / {
        proxy_pass "http://127.0.0.1:3000"
    }
}
```