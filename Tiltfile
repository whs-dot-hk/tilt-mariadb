def create_namespace(name):
    k8s_yaml(blob("""apiVersion: v1
kind: Namespace
metadata:
  name: %s
""" % name))

name = "mariadb-test"

create_namespace(name)

k8s_yaml(helm("charts/pre-mariadb-galera", name = "pre-" + name, namespace = name))

k8s_yaml(helm("charts/mariadb-galera", name, namespace = name, values = "values.yaml"))
