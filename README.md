# Usage

## add to pom.xml
* package
		
        <dependency>
          <groupId>com.whereq.common</groupId>
          <artifactId>whereq-common-utils</artifactId>
          <version>2.0</version>
        </dependency>

* repository
    local maven
---  
## add package scan in Application

    @ComponentScan(value = {"com.whereq.common.log","com.whereq.yourapp"})
    
## add config file (optional if require changes)

    cooy logback-spring.xml file to /src/main/resoruces folder from this project to target and make neccessary modification (optional)

## call logs
* automatically add to follow stereotype:

   within(@org.springframework.stereotype.Repository *) 
|| within(@org.springframework.stereotype.Service *) 
|| within(@org.springframework.web.bind.annotation.RestController *)

* using @Loggable on Class and Method to enable

* using @NotLoggable on Class and Method to disable explicitly.

## RESTful controller logs

* add/remove 'fdx-req-uuid' per request for logging.

* adding hearders to response
' fdx-cost: {millsec}
 fdx-req-uuid: {caller}-{UUID}
 fdx-start: {epooch}'

---
## version history

Version 2.X: 
1. add com.whereq.com.log package replace com.whereq.com.controller
2. add UuidHeaderInterceptor, no need add the FDX_REQ_UUID in header in Feign client


Version 3.0
1. upgrade java 17
2. upgrade springboot 3.x