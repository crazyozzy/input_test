import org.yaml.snakeyaml.Yaml
import org.yaml.snakeyaml.DumperOptions
import static org.yaml.snakeyaml.DumperOptions.FlowStyle.BLOCK

def yamlContent
def inputContent

@NonCPS
String yamlToString(Object data){
    def opts = new DumperOptions()
    opts.setDefaultFlowStyle(BLOCK)
    return new Yaml(opts).dump(data)
}

node{
  stage('git checkout'){
    checkout(scm)
  }

  stage('yaml test'){
    yamlContent = readYaml(file: 'test.yml')

    sh('cat test.yml')

    echo yamlToString(yamlContent)

    inputContent = input(
      message: 'config',
      parameters:[
        text(defaultValue: yamlToString(yamlContent), description: 'config', name: 'config')
      ]
    )

    writeYaml(file: 'test_write.yml', overwrite: true, data: inputContent)

    sh('cat test_write.yml')
  }
}