# Parking Management System

A simple application to manage parking spaces

## Requirements

- [NodeJS](https://nodejs.org)
- MySQL

## Installation
> Instructions shown here for mysql linux version
- Create Database User 'parkingAPI': (Login as root: `sudo mysql -u root`)
	- Create user: `CREATE USER 'parkingAPI'@'localhost' IDENTIFIED BY 'password';`
	- Grant permissions to user on DB 'parkingMS': `GRANT ALL PRIVILEGES ON parkingMS . * TO 'parkingAPI'@'localhost';`
- Setup application and database:
	```bash
	
	cd dbms-parking
	npm install
	echo 'create database parkingMS;' | mysql -u parkingAPI --password=password
	# Create Relational tables
	mysql --user=parkingAPI --password=password parkingMS < db/relations.sql
	# Create Trigger for bill calculation on vehicle exit: 20 + (5 per hr)
	mysql --user=parkingAPI --password=password parkingMS < db/trigger.sql
	```


## Usage

Run app:
```bash
node server.js
```
> Create employees to add parking spaces associated with them before doing vehicle entry in the app
