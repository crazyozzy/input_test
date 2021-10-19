def yamlContent

node{
  stage('git checkout'){
    checkout(scm)
  }
  stage('yaml test'){
    yamlContent = readYaml(file: 'test.yml')

    println yamlContent
  }
}