def create_namespace(name):
    k8s_yaml(blob("""apiVersion: v1
kind: Namespace
metadata:
  name: %s
""" % name))

name = "mariadb-test"

create_namespace(name)

objects = read_yaml_stream("tls.yaml")
for o in objects:
    o["metadata"]["namespace"] = name
k8s_yaml(encode_yaml_stream(objects))

k8s_yaml(helm("charts/mariadb-galera", name, namespace = name, values = "values.yaml"))
