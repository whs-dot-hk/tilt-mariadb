def create_namespace(name):
    k8s_yaml(blob("""apiVersion: v1
kind: Namespace
metadata:
  name: %s
""" % name))

create_namespace("mariadb-test")

k8s_yaml(helm("charts/mariadb-galera", name = "mariadb-test", namespace = "mariadb-test", values = "values.yaml"))
