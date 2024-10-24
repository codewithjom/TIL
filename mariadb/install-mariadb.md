# Get Started

```sh
sudo pacmana -S mariadb
```

Run the following command **before starting** the `mariadb.service`:

```sh
sudo mariadb-install-db --user=mysql --basedir=/usr --datadir=/var/lib/mysql
sudo systemctl enable mariadb.service
sudo systemctl start mariadb.service
sudo mariadb-secure-installation
```

# Create User

```sh
MariaDB> CREATE USER 'monty'@'localhost' IDENTIFIED BY 'some_pass';
MariaDB> GRANT ALL PRIVILEGES ON *.* TO 'monty'@'localhost';
MariaDB> quit
```
