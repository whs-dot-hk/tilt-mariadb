# Download chart
```sh
helm pull bitnami/mariadb-galera -d charts --untar
```

# Install cert-manager
```sh
kubectl apply -f https://github.com/cert-manager/cert-manager/releases/download/v1.10.0/cert-manager.yaml
```

# Connect
```sh
kubectl run -it --rm --image=mariadb test bash
# user root
mysql -hmariadb-test-mariadb-galera.mariadb-test -uroot -proot
show grants for 'mariabackup'@'localhost';
```

```sh
kubectl exec -it mariadb-test-mariadb-galera-0 -nmariadb-test bash
# user mariabackup
mysql -umariabackup -pmariabackup
```
