//import groovy.yaml.YamlSlurper

def configYaml = '''\
---
application: "Sample App"
users:
- name: "mrhaki"
  likes:
  - Groovy
  - Clojure
  - Java
- name: "Hubert"
  likes:
  - Apples
  - Bananas
connections:
- "WS1"
- "WS2"
'''

//def config = new YamlSlurper().parseText(configYaml)

node{
  stage('yaml test'){
    echo configYaml
  }
}