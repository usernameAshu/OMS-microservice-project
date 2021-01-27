# OMS-microservice-project
<strong>Execute the below commands in git bash:</strong><br>
<br>git clone https://github.com/usernameAshu/OMS-microservice-project.git 
<br>cd OMS-microservice-project/ 
<br>git submodule init
<br>git submodule update
<br>
<strong>To receive updated commit changes from submodules , execute below command:</strong><br>
git submodule update --remote
<br>
<br>
<strong>This is a project based on microservice architecture developed in Java using SpringBoot framework</strong><br>
Create a log file named "microservice-elk.log" or you can use the log file in this repo<br>
Copy that log file location to application.yaml of order-service and payment-service <br>
Inside file: kibana.yml , uncomment :elasticsearch.hosts<br>
Execute elasticsearch.bat<br>
Execute kibana.bat<br>
Check the deafult index from http://localhost:9200/_cat/indices <br>
Use the logstash.conf file, paste it the logstash-7.10.x/bin<br>
Paste the log file location to input.file.path => ""  inside logstash.conf<br>
Execute : logstash -f logstash.conf <br>
<strong>Elastic search : localhost:9200</strong><br>
<strong>Kibana console : localhost:5601</strong><br>
<strong>Logstash console : localhost:9600</strong><br>
Create a index from Kibana Stack Management with search index : logstash-* <br>
In the Discover window, view the logs generated from Microservices<br>
<br>
<strong>System requirements:</strong> <br>
Java 8<br>
Maven 3.3.x<br>
IntelliJ IDEA 2020.2.x<br>
<strong>Build the project using the below maven command:</strong> <br>
mvn clean install -Dmaven.test.skip=true<br>
<strong>Start the microservices in the following order:</strong><br>
<OL>
  <LI>service-registry
  <LI>cloud-config-server-app
  <LI>cloud-api-gateway
  <LI>payment-service
  <LI>order-service
    </OL>
<strong>Microservice architecture features implemented:</strong>
<OL>
<LI>Create order and payment microservice from scratch 
<LI>Register microservice in Eureka Service Discovery
<LI>Integrate Spring Cloud Gateway for routing user request
<LI>Integrate Hystrix & Hystrix Dashboard to identify failure for downstream services
<LI>Spring cloud config server using Git to Centralize configuration across application
<LI>ELK Stack to centralize logging across all microservices
</OL>
Disclaimer Notes:<br>
Software Used:<br>
<OL>
<LI>Elastic Search: https://www.elastic.co/downloads/elasticsearch
<LI>Logstash : https://www.elastic.co/downloads/logstash
<LI>Kibana : https://www.elastic.co/downloads/kibana
  </OL>
<strong>Tutorial Source: https://www.youtube.com/watch?v=tljuDMmfJz8&list=RDCMUCORuRdpN2QTCKnsuEaeK-kQ&start_radio=1&t=4834 By Java Techie </strong><br>
  <strong>Stack-overflow link :</strong><br>
  <OL>
<LI>https://stackoverflow.com/questions/28375416/spring-cloud-config-server-cant-locate-propertysource-on-startup 
<LI>https://stackoverflow.com/questions/44014594/spring-boot-could-not-locate-propertysource-label-not-found 
  </OL>
Spring docs:<br>
   <OL>
<LI>https://docs.spring.io/spring-boot/docs/current/reference/html/production-ready-features.html#production-ready-monitoring
<LI>https://docs.spring.io/spring-boot/docs/1.5.x/reference/html/howto-logging.html
   </OL>
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
