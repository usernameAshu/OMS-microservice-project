# OMS-microservice-project
Execute the below commands in git bash:<br>
<br>git clone https://github.com/usernameAshu/OMS-microservice-project.git 
<br>cd OMS-microservice-project/ 
<br>git submodule init
<br>git submodule update
<br>
To receive updated commit changes from submodules , execute below command:<br>
<br>git submodule update --remote
<br>
<br>
This is a project based on microservice architecture developed in Java using SpringBoot framework<br>
Create a log file named "microservice-elk.log"<br>
Copy that log file location to application.yaml of order-service and payment-service <br>
Paste the log file location to input.file.path => "" <br>
Check the deafult index from http://localhost:9200/_cat/indices <br>
Create a index from Kibana Stack Management with search index : logstash-* <br>
<br>
System reuirements: <br>
Java 8<br>
Maven 3.3.x<br>
IntelliJ IDEA 2020.2.x<br>
Disclaimer Notes:<br><br>
Software Used:<br>
Elastic Search: https://www.elastic.co/downloads/elasticsearch<br>
Logstash : https://www.elastic.co/downloads/logstash<br>
Kibana : https://www.elastic.co/downloads/kibana<br>
Tutorial Source: https://www.youtube.com/watch?v=tljuDMmfJz8&list=RDCMUCORuRdpN2QTCKnsuEaeK-kQ&start_radio=1&t=4834 <br>
By Java Techie <br>
Stack-overflow link :<br>
https://stackoverflow.com/questions/28375416/spring-cloud-config-server-cant-locate-propertysource-on-startup <br>
https://stackoverflow.com/questions/44014594/spring-boot-could-not-locate-propertysource-label-not-found <br>
Spring docs:<br>
https://docs.spring.io/spring-boot/docs/current/reference/html/production-ready-features.html#production-ready-monitoring<br>
https://docs.spring.io/spring-boot/docs/1.5.x/reference/html/howto-logging.html<br>
Baeldung Sources:<br>
https://www.baeldung.com/spring-cloud-configuration<br>
Github issues:<br>
https://github.com/elastic/kibana/issues/5557<br>
Licensing reference:<br>
https://choosealicense.com/licenses/mit/#<br>
https://docs.github.com/en/github/creating-cloning-and-archiving-repositories/licensing-a-repository<br>
Other reference:<br>
https://www.credera.com/insights/circuit-breaker-pattern-in-spring-boot/<br>
https://dev.to/nagarajendra/basics-of-resilience4j-with-spring-boot-4dk8<br>
https://www.elastic.co/guide/en/logstash/current/configuration.html<br>
https://www.elastic.co/guide/en/logstash/current/config-examples.html<br>
https://www.elastic.co/guide/en/kibana/7.10/kuery-query.html<br>
This is a practice project to understand microservice architecture. All codes are from refernced from repository (https://github.com/Java-Techie-jt/spring-cloud-gatway-hystrix)<br>
<p>
  PUT /my_first_index
{
  "settings": {
    "index":{
      "number_of_shards":3,
      "number_of_replicas":2
    }
  }
}
  </p><br>
  <p>
  POST /my_first_index/default/
{
  "name":"event processing",
  "instructor": {
    "firstName": "Ashutosh",
    "lastName": "Mohanty"
  }
}</p><br>
