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
        text(defaultValue: '123', description: 'config', name: 'config')
      ]
    )

  }
}