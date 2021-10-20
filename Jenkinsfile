import org.yaml.snakeyaml.Yaml
import org.yaml.snakeyaml.DumperOptions
import static org.yaml.snakeyaml.DumperOptions.FlowStyle.BLOCK
import groovy.json.*
import groovy.yaml.*
import com.fasterxml.jackson.core.JsonProcessingException;
import com.fasterxml.jackson.databind.JsonNode;
import com.fasterxml.jackson.databind.ObjectMapper;
import com.fasterxml.jackson.dataformat.yaml.YAMLMapper;

def yamlContent
def inputContent
def jsonContent

@NonCPS
String yamlToString(Object data){
    def opts = new DumperOptions()
    opts.setDefaultFlowStyle(BLOCK)
    return new Yaml(opts).dump(data)
}

@NonCPS
String asYaml(String jsonString){
  JsonNode jsonNodeTree = new ObjectMapper().readTree(jsonString)
  String jsonAsYaml = new YAMLMapper().writeValueAsString(jsonNodeTree)
  return jsonAsYaml
}

node{
  stage('git checkout'){
    checkout(scm)
  }

  stage('yaml test'){
    yamlContent = readYaml(file: 'test.yml')

    sh('cat test.yml')

    echo yamlToString(yamlContent)

/*
    inputContent = input(
      message: 'config',
      parameters:[
        text(defaultValue: yamlToString(yamlContent), description: 'config', name: 'config')
      ]
    )
*/

    //writeYaml(file: 'test_write.yml', overwrite: true, data: inputContent)
    //sh('''cat test_write.yml | sed "/^|/d" | sed \'s/^\\s\\s//\'''')

    //yamlContent = readYaml(file: 'test2.yml')
    //jsonContent = readJSON(text: yamlContent.items.metadata.annotations."kubectl.kubernetes.io/last-applied-configuration")
    //jsonContent = new JsonBuilder(yamlContent.items.metadata.annotations."kubectl.kubernetes.io/last-applied-configuration").toPrettyString()
    jsonContent = sh(script: """cat test2.yml | awk '/{.*}}/{print \$0}' | sed 's/^\\s*//'""", returnStdout: true)
    //writeJSON(file: 'test_write.yml', json: jsonContent)
    //sh('''cat test_write.yml''')

    yamlContent = readYaml(file: 'test2.yml')
    //jsonContent = readJSON(text: yamlContent.metadata.annotations."kubectl.kubernetes.io/last-applied-configuration")
    jsonContent = yamlContent.metadata.annotations."kubectl.kubernetes.io/last-applied-configuration"
    println jsonContent
    println asYaml(jsonContent)
    println new JsonBuilder(asYaml(jsonContent)).toPrettyString()
    
  }
}