# OMS-microservice-project
<strong>Execute the below commands in git bash:</strong><br>
<OL>
<LI>git clone https://github.com/usernameAshu/OMS-microservice-project.git <br>
<LI>cd OMS-microservice-project/ <br>
<LI>git submodule init<br>
<LI>git submodule update<br>
<strong>To receive updated commit changes from submodules , execute below command:</strong><br>
<LI>git submodule update --remote
</OL>
<br>
<br>
<strong>This is a project based on microservice architecture developed in Java using SpringBoot framework</strong><br>
<strong>Microservice architecture features implemented:</strong>
<OL>
<LI>Create order and payment microservice from scratch 
<LI>Register microservice in Eureka Service Discovery
<LI>Integrate Spring Cloud Gateway for routing user request
<LI>Integrate Hystrix & Hystrix Dashboard to identify failure for downstream services
<LI>Spring cloud config server using Git to Centralize configuration across application
<LI>ELK Stack to centralize logging across all microservices
<LI>Distributed Log Tracing using Zipkin and Sleuth
</OL>
<strong>System requirements:</strong> <br>
<OL>
<LI>Java 8<br>
<LI>Maven 3.3.x<br>
<LI>IntelliJ IDEA 2020.2.x<br>
</OL>
<strong>Build the microservices using the below maven command:</strong> <br>
mvn clean install -Dmaven.test.skip=true<br>
<strong>Start the microservices in the following order:</strong><br>
<OL>
  <LI>service-registry
  <LI>cloud-config-server-app
  <LI>cloud-api-gateway
  <LI>payment-service
  <LI>order-service
</OL>
<strong>Postman Setup for Request/Response</strong><br>
<OL>
<LI>Download Postman
<LI>Import the postman-collection file from the repo into Postman
<LI>Hit the request and verify the response
</OL>
<strong>Instructions for Setting up the ELK stack for centralized logging</strong><br>
<OL>
<LI>Create a log file named "microservice-elk.log" or you can use the log file in this repo<br>
<LI>Copy that log file location to application.yaml of order-service and payment-service <br>
<LI>Inside file: kibana.yml , <strong>uncomment :elasticsearch.hosts</strong><br>
<LI>Execute <strong>elasticsearch.bat</strong><br>
<LI>Execute <strong>kibana.bat</strong><br>
<LI>Check the deafult index from http://localhost:9200/_cat/indices <br>
<LI>Use the logstash.conf file, paste it the logstash-7.10.x/bin<br>
<LI>Paste the log file location to input.file.path => ""  inside logstash.conf<br>
<LI>Execute : <strong>logstash -f logstash.conf</strong> <br>
<LI>Check the logs of the default index: http://localhost:9200/logstash-2021.01.27-000001/_search <br>
<LI>Replace "logstash-2021.01.27-000001" with the current default logstash<br>
<LI><strong>Elastic search : localhost:9200</strong><br>
<LI><strong>Kibana console : localhost:5601</strong><br>
<LI><strong>Logstash console : localhost:9600</strong><br>
<LI>Create a index from Kibana Stack Management with search index : logstash-* <br>
<LI>In the Discover window, view the logs generated from Microservices<br>
</OL>
<br>
<strong>Setting up custom-index in Kibana server to view logs</strong><br>
<OL>
<LI><strong>To create custom index "mohanty_index" :</strong><br>
Create a index in Kibana -> Management -> Devtools http://localhost:5601/app/dev_tools#/console<br>
  PUT /mohanty_index<br>
{<br>
  "settings": {<br>
    "index":{<br>
      "number_of_shards":3,<br>
      "number_of_replicas":2<br>
    }<br>
  }<br>
}<br>
</OL>
<br>
<strong>Attach a document to the index:</strong><br>
  POST /mohanty_index/default/<br>
{<br>
  "name":"event processing",<br>
  "instructor": {<br>
    "firstName": "Ashutosh",<br>
    "lastName": "Mohanty"<br>
  }<br>
}<br>
<strong>Add the custom index to logstash.conf</strong><br>
elasticsearch { <br>
hosts => ["localhost:9200"]<br>
index => "mohanty_index-%{+yyyy.MM.dd}"<br>
}<br>
<strong>Execute : logstash -f logstash.config</strong><br>
<br>
<strong>Instructions for setting up Distributed log tracing using Zipkin server</strong><br>
<OL>
<LI>Download the Java executable jar from https://zipkin.io/pages/quickstart.html 
<LI>Execute the jar file (java -jar zipkin-*.jar) OR run the docker command
<LI>Verify Server is UP on http://localhost:9411/
<LI>View the tracing of each request
</OL>
<strong>Disclaimer Notes:</strong><br>
Software Used:<br>
<OL>
<LI>Elastic Search: https://www.elastic.co/downloads/elasticsearch
<LI>Logstash : https://www.elastic.co/downloads/logstash
<LI>Kibana : https://www.elastic.co/downloads/kibana
<LI>Zipkin : https://zipkin.io/pages/quickstart.html 
<LI>IntelliJ IDE: https://www.jetbrains.com/idea/download/#section=windows
<LI>Java SE 8: https://www.oracle.com/in/java/technologies/javase/javase-jdk8-downloads.html
<LI>SpringBoot Starter: https://start.spring.io
<LI>Maven: https://maven.apache.org/download.cgi
<LI>Git: https://git-scm.com/downloads
<LI>Postman: https://www.postman.com/downloads/
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
This is a practice project to understand microservice architecture. All codes are from referenced from repository (https://github.com/Java-Techie-jt/spring-cloud-gatway-hystrix)<br>
