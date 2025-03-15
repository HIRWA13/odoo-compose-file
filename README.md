# Odoo compose file

This file repo contains my odoo compose file. the compose file is used to run odoo with postgresql as a database.

## How it works

The compose file contains two services:
1. odoo_db: This service is used to run the postgresql database
2. odoo_server: This service is used to run the odoo server

The odoo server service is linked to the odoo_db service to allow the odoo server to access the database. The odoo server service is also linked to the odoo_addons volume to allow the odoo server to access the addons.

The odoo_db service is linked to the odoo_db_data volume to allow the database to store the data.

The odoo_db_data volume is used to store the database data.

## How to use

1. Clone the repo
2. Run the following command to start the odoo server
```bash
docker-compose up -d 
```
3. Open your browser and go to `http://localhost:8069` to access the odoo server

## How to stop the server

1. Run the following command to stop the odoo server
```bash
docker-compose down
```

## How to access the database

1. Run the following command to access the database
```bash
docker exec -it odoo_db psql -U odoo -d odoo
```

## How to access the odoo server

1. Run the following command to access the odoo server
```bash
docker exec -it odoo_server bash
```