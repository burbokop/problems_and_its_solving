# problems_and_its_solving
This repo contains list of problems and tips how to solve them.


## Running postgresql server:

### issue 0: `EOF` error on query
Check port: `sudo netstat -plnt | grep "postgres"`

### issue 1: `password authentication failed for user` error
Run `ALTER USER user_name WITH PASSWORD 'new_password';` in `psql` shell:

