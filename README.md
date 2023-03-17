# DHIS2-docker-config
Configuration repo for spinning up a DHIS2-cluster locally.

## Set up the application

To spin up the containers for the DHIS2-cluster, you can use the docker-compose command. Docker Compose is a tool for defining and running multi-container Docker applications. It allows you to define the application's services, networks, and volumes in a single docker-compose.yml file. To spin up the containers for the DHIS2-cluster, simply navigate to the directory where the docker-compose.yml file is located, and run the following command:

`docker-compose up`

This command will start the containers for the DHIS2-cluster, and you can access the application and other services through the specified ports. You can use the `docker-compose down` command to stop and remove the containers when you are done. By using Docker Compose, you can easily spin up and manage the containers for the DHIS2-cluster, making it simple to run the application locally for testing and development purposes.

## Steps to start the DHIS2-cluster with a custom database dump:
1. Uncomment the section about volumes in the `docker-compose.yml` file.
2. Provide a `init.sql`-script in the `db` folder.
3. The script will be executed when the database container starts, which will populate the database with the data from the custom database dump.

By following these steps, you can ensure that the DHIS2-cluster starts with the desired data and configurations.


## Access the PGAdmin dashboard
The PGAdmin dashboard can be used to access and manage the PostgreSQL database for the DHIS2-cluster. One may access this dashboard to view, query, and manipulate the data stored in the database, as well as manage the database itself, including creating tables, modifying schemas, and running backups.

To access the PGAdmin dashboard for the DHIS2-cluster configuration, use the following credentials:
<br/>Default url: http://localhost:5050
<br/>Username: admin@test.no
<br/>Password: district

Add the DHIS2 database to PGAdmin:

1. Click add server in the PGAdmin dashboard
2. Click connection
3. Set the host name/address to the name of the docker db container (`dhis2-docker-db-1`)
4. Set the username (defaults to dhis)
5. Set the password (defaults to dhis)
6. Click save
