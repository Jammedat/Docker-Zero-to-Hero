a. Install apache2 in kkloud container using apt that is running on App Server 1 in Stratos Datacenter.   
b. Configure Apache to listen on port 8083 instead of default http port. Do not bind it to listen on specific IP or hostname only, i.e it should listen on localhost, 127.0.0.1, container ip, etc.   
c. Make sure Apache service is up and running inside the container. Keep the container in running state at the end

## Solution
1. Check the status of the container with `docker ps`

2. Use `docker exec` command to run the commands inside the running container
- `docker exec -it kkloud bash`

### Now that you are inside the container do the things as mentioned.

` apt install apache2 vim -y`

### Now change the port config as:  
` vi /etc/apache2/ports.conf `

### Update the default virtual host file

```bash
nano /etc/apache2/sites-available/000-default.conf
```

Change:

```php-template
<VirtualHost *:80>
```

To:

```php-template
<VirtualHost *:8083>
```

Save and exit.

### Restart apache2
` apachectl -D FOREGROUND `



