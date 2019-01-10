# micro-services-spring-cloud

* the application use JDK 1.8 

* user eclipse to be able to run multiple instance of company service.

* create a general configuration file in :

file://${user.home}/cloud-conf

or the link of distant gitHub repository

* initialise a local git repository :

git init

* create application.properties file (general configuration file), with the necessary config param :
 xParam=789
 
* create a specific configuration file for each service.

* company-service.properties : 

  yParam=99
  me=med@youssfi.net
  
 * Run the service configuration Application :
 
 display the global configuration : http://localhost:8888/application/master
 
 
 * Run the service company application :
 
 http://localhost:8082/companies
 
 display actuator : http://localhost:8082/actuator
 
 * when updating config param in company-service.properties :
 
 make a post request to http://localhost:8082/actuator/refresh , 
 and verify in  http://localhost:8082/myConfig, the updated config
 
 * create in ~/cloud-conf, eureka-service.properties :
 
 server.port = 8761
 eureka.client.registerWithEureka=false
 eureka.client.fetchRegistry=false
 
* run multiple instance of company service. by changing the server.port
 
* Run the service proxy application application :
 
go to : http://localhost:8080/company-service/companies

check witch instance is responding, and that the proxy is using load balancing  : 

http://localhost:8080/company-service/myConfig
  
 
 
 
  