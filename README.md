## Creating a test Postgres instance

The purpose of this repo is to create a test Postgres instance for NETS.

The CloudFormation json uses a commnunity AMI that loads with Bitnami Postgres.

Once the EC2 instance - and therefore Bitnami Postgres - is up and running, manually do these steps (it's probably not worth automating this one time setup):
```
#the default password is 'bitnami':
sudo -u postgres psql

alter user postgres password 'redacted';
create user nets createdb createuser password 'redacted';
create database netsdb owner nets;
\q

exit
```
