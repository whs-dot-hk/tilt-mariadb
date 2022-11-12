# Download chart
```sh
helm pull bitnami/mariadb-galera -d charts --untar
```

# Connect
```sh
kubectl run -it --rm --image=mariadb test bash
# root
mysql -hmariadb-test-mariadb-galera.mariadb-test -uroot -proot
show grants for 'mariabackup'@'localhost';
```

```sh
# mariabackup
kubectl exec -it mariadb-test-mariadb-galera-0 -nmariadb-test bash
mysql -umariabackup -pmariabackup
```
