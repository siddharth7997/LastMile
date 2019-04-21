# LAST MILE
`Last Mile` is a Distributed E-Learning System for the student in India, especially the villages of India, by leveraging a `cloud storage` platform to meet the needs of data storage
and management, which is cost-effective (using single-board computers such as `raspberry pi`), easily accessible to all irrespective of age, gender, creed etc and whose quality is better than, if not equal to the education provided in cities, for the betterment of the country.

### [Source Code](https://github.com/siddharth7997/LastMile)

# Required Softwares
## Server Side

1. PHP >=5
2. CodeIgniter 3.x.x
3. MySQL >= 5.x
4. Composer _for installing php modules_
5. VirusTotal API for PHP IzzySoft [Github](https://github.com/IzzySoft/virustotal)

## Client  Side
### Software
1. PHP >=5
2. CodeIgniter 3.x.x
3. MySQL >= 5.x
4. Composer _for installing php modules_
5. Client URL Library for PHP [Documentation](https://www.php.net/manual/en/book.curl.php#book.curl)
### Tools
1. lighttpd
2. hostapd
3. dnsmasq
4. vnstat


# Setup IOT Access Point
1. Update Raspbian, including the kernel and firmware, followed by a reboot
```
sudo apt-get update
sudo apt-get dist-upgrade
sudo reboot
```

2. Install RaspAP from your RaspberryPi's shell prompt:
```
wget -q https://git.io/voEUQ -O /tmp/raspap && bash /tmp/raspap
```
After the reboot at the end of the installation the wireless network will be configured as an access point as follows:
* Static IP address: `10.3.141.1`
  * Username: `admin`
  * Password: `secret`
* DHCP range: 10.3.141.50 to 10.3.141.255
* SSID: `raspi-webgui`
* Password: `ChangeMe`


    *To change various options go to `10.10.10.10` and change these settings and reboot the device*


3. Install PHP,MySQL,phpmyadmin

```
sudo apt update
sudo apt upgrade
sudo apt update
```


Install apache2
```
sudo apt install apache2
```

Provide required access permission
```
sudo chown -R pi:www-data /var/www/html/
sudo chmod -R 770 /var/www/html/
```

Install PHP
```
sudo apt install php php-mbstring
```
Install MySQL

```
sudo apt install mysql-server php-mysql
```

Verify that MySQL is working correctly
```
sudo mysql --user=root
DROP USER 'root'@'localhost';
CREATE USER 'root'@'localhost' IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON *.* TO 'root'@'localhost'
```

Install phpmyadmin
```
sudo apt install phpmyadmin
```


4. Import the databases from `sql_import.sql`

5. Move the lastmile files into apache directory
```
mv -r /lastmile /var/www/html/
```




# Android Apps

We have two different android apps for user and operators. 

* Features of app for user:
	* Allows user to view various new courses and download them to thier device
	* Request for new Courses
* Features of app for operator:
	* Update the device
	* Block the users while update
