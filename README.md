# springConfigServer

1.put these dependencies in pom
<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-actuator</artifactId>
		</dependency>
		<dependency>
			<groupId>org.springframework.cloud</groupId>
			<artifactId>spring-cloud-config-server</artifactId>
		</dependency>
		<dependency>
			<groupId>org.springframework.cloud</groupId>
			<artifactId>spring-cloud-starter-netflix-eureka-client</artifactId>
		</dependency>

2. On Application class put @EnableDiscoveryClient
@EnableConfigServer

3. put some properties in application.properties.
   These properities will now be avilable ,and @Value can be used to inject it.
--- Config Server part  is done
   Now for Config Client i.e all our microservices
Put these properties
spring.config.import=configserver:http://127.0.0.1:8888
spring.cloud.config.discovery.enabled=true
spring.cloud.config.discovery.serviceId=Config-Server
