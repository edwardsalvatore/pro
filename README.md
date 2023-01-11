<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
	xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
	<modelVersion>4.0.0</modelVersion>
	<parent>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-starter-parent</artifactId>
		<version>2.1.0.RELEASE</version>
		<relativePath /> <!-- lookup parent from repository -->
	</parent>
	<groupId>com.ram</groupId>
	<artifactId>SpringBootDemo</artifactId>
	<version>0.0.1-SNAPSHOT</version>
	<name>SpringBootDemo</name>
	<description>Demo project for Spring Boot</description>

	<properties>
		<java.version>1.8</java.version>
	</properties>

	<dependencies>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-web</artifactId>
		</dependency>

		<dependency>  
            <groupId>org.springframework.boot</groupId>  
            <artifactId>spring-boot-starter-data-jpa</artifactId>  
        </dependency>  

		<!-- https://mvnrepository.com/artifact/mysql/mysql-connector-java -->
		<dependency>
			<groupId>mysql</groupId>
			<artifactId>mysql-connector-java</artifactId>
		</dependency>
   <dependency>
        <groupId>io.springfox</groupId>
        <artifactId>springfox-swagger2</artifactId>
        <version>2.9.2</version>
    </dependency>

    <dependency>
        <groupId>io.springfox</groupId>
        <artifactId>springfox-swagger-ui</artifactId>
        <version>2.9.2</version>
    </dependency>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-test</artifactId>
			<scope>test</scope>
		</dependency>
	</dependencies>

	<build>
		<plugins>
			<plugin>
				<groupId>org.springframework.boot</groupId>
				<artifactId>spring-boot-maven-plugin</artifactId>
			</plugin>
		</plugins>
	</build>

</project>


import java.util.HashMap;
import java.util.Map;

public class createUser {

	public static void main() {
		
	}
	public String fetchToken(String TOKENURL, String userName, String password) throws Exception {
		String accessToken = null;
		MultiValueMap<String, String> headers = new LinkedMultiValueMap<->();
		Map map = new HashMap<String, String>();
		map.put("Content-Type", "application/json");
		headers.setAll(up);
		Map req_payload= new HashMap();
		req_payload.put("username", userName);
		req_payload.put("password", password);
		HttpEntity<?> request = new HttpEntity<>(req_payload, headers);
		ResponseEntity<?> response = new RestTemplate().postForEntity (TOKENURL, request, String.class);
		if (response.getStatusCode() == HttpStatus.OK) {
		JSONObject accessTokenResponse = new JSONObject(response.getBody().toString());
		accessToken = accessTokenResponse.get("access_token").toString();
		}
		return accessToken:
		}
}
