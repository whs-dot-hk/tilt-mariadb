# Download chart
```sh
helm pull bitnami/mariadb-galera -d charts --untar
```

# Connect
```sh
kubectl run -it --rm --image=mariadb test bash
mysql -hmariadb-test-mariadb-galera.mariadb-test -uroot -ptest
show grants for 'mariabackup'@'localhost';
```
