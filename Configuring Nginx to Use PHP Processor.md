<span style="color:orange">** Configuration**</span>

`sudo mkdir /var/www/projectLEMP`

`sudo chown -R $USER:$USER /var/www/projectLEMP`


![Ngnix Status](/Images/projectLemp%20DIr.png)


`sudo nano /etc/nginx/sites-available/projectLEMP`


![Ngnix Status](/Images/nginx%20sites-available.png)



   ### listen — Defines what port Nginx will listen on. In this case, it will listen on port 80, the default port for HTTP.

   ### root — Defines the document root where the files served by this website are stored.

   ### index — Defines in which order Nginx will prioritize index files for this website. It is a common practice to list index.html files with a higher precedence than index.php files to allow for quickly setting up a maintenance landing page in PHP applications. You can adjust these settings to better suit your application needs.

   ### server_name — Defines which domain names and/or IP addresses this server block should respond for. Point this directive to your server’s domain name or public IP address.

   ### location / — The first location block includes a try_files directive, which checks for the existence of files or directories matching a URI request. If Nginx cannot find the appropriate resource, it will return a 404 error.

   ### location ~ \.php$ — This location block handles the actual PHP processing by pointing Nginx to the fastcgi-php.conf configuration file and the php7.4-fpm.sock file, which declares what socket is associated with php-fpm.

   ### location ~ /\.ht — The last location block deals with .htaccess files, which Nginx does not process. By adding the deny all directive, if any .htaccess files happen to find their way into the document root ,they will not be served to visitors.</span>

   `sudo ln -s /etc/nginx/sites-available/projectLEMP /etc/nginx/sites-enabled/`


   ![Ngnix Status](/Images/sitesenabled.png)

   
   `sudo nginx -t`
    ![Ngnix Status](/Images/nginx-t.png)


`sudo unlink /etc/nginx/sites-enabled/default`


   `sudo systemctl reload nginx`
  ![Ngnix Status](/Images/Ngnix%20Reload.png)


  `sudo echo 'Hello LEMP from hostname' $(curl -s http://169.254.169.254/latest/meta-data/public-hostname) 'with public IP' $(curl -s http://169.254.169.254/latest/meta-data/public-ipv4) > /var/www/projectLEMP/index.html`
  






   


