@Grab('org.yaml:snakeyaml:latest')
import org.yaml.snakeyaml.Yaml
import org.yaml.snakeyaml.DumperOptions
import static org.yaml.snakeyaml.DumperOptions.FlowStyle.BLOCK

def yamlContent

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

    println yamlContent

    echo yamlToString(yamlContent)

    input(
      message: 'config',
      parameters:[
        text(defaultValue: yamlToString(yamlContent), description: 'config', name: 'config')
      ]
    )

  }
}