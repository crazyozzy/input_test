//import groovy.yaml.YamlSlurper

def configYaml = '''\
apiVersion: apps/v1
kind: Deployment
metadata:
  name: http-echo
spec:
  replicas: 2
  selector:
    matchLabels:
      app: http-echo
  template:
    metadata:
      labels:
        app: http-echo
    spec:
      containers:
      - name: http-echo
        image: hashicorp/http-echo
        args: ["-text", "hello-world"]
        ports:
        - containerPort: 5678
---
apiVersion: v1
kind: Service
metadata:
  name: http-echo
spec:
  ports:
  - port: 5678
    protocol: TCP
    targetPort: 5678
  selector:
    app: http-echo
'''

//def config = new YamlSlurper().parseText(configYaml)

node{
  stage('yaml test'){
    echo configYaml
  }
}