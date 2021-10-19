def yamlContent

node{
  stage('git checkout'){
    checkout(scm)
  }
  stage('yaml test'){
    yamlContent = readYaml(file: 'test.yml')

    println yamlContent

    input(
      message: 'config',
      parameters:[
        text(defaultValue: yamlContent, description: 'config', name: 'config')
      ]
    )

  }
}