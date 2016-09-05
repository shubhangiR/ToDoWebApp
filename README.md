# ToDo Web Application

<!-- More details about this app can be found at : https://rawgit.com/shubhangiR/ToDoWebApp/master/index.html -->


This file gives more details about my to-do list web application and tracks my progress in this project.
Aim:
====
The aim of this project is to learn to develop a web application without using any IDE. Earlier I have developed various web applications using Eclipse and netBeans, so this time I wish to learn deeper. This project will also revise my knowledge to develop a simple web application. Later, I plan to make its various versions to learn latest technologies like single page applications. I will also learn about databases by connecting this application with SQL and NoSQL databases. The full learning plan will be posted soon.

Quick Java web project with Maven
===
Step 1: 
===
Create a web project using Maven template. Go to the folder you want to create the project and type this command
```
> mvn archetype:generate -DgroupId={project-packaging} -DartifactId={project-name} -DarchetypeArtifactId=maven-archetype-webapp -DinteractiveMode=false
```
For example I typed
```
> mvn archetype:generate -DgroupId=com.shubhangi -DartifactId=ToDoApp -DarchetypeArtifactId=maven-archetype-webapp -DinteractiveMode=false
```
and it created a maven project with some standard directory structure.
When I used command tree, it gave me following structure:
<!-- .</br>
|___ pom.xml</br>
|___ src</br>
    |___ main</br>
        |___ resources</br>
        |___ webapp</br>
            |___ WEB-INF</br>
            |   |___ web.xml</br>
            |___ index.jsp</br> -->


.</br>
|--- pom.xml</br>
|--- src</br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|--- main</br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|--- resources</br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|--- webapp</br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|--- WEB-INF</br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|--- web.xml</br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|--- index.jsp</br></br>

Step 2:
===
I updated web.xml to support Servlet 2.5. Now my web.xml looks like this.
```xml
<web-app xmlns="http://java.sun.com/xml/ns/javaee"
        xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://java.sun.com/xml/ns/javaee
	      http://java.sun.com/xml/ns/javaee/web-app_2_5.xsd"
	version="2.5">
  <display-name>Archetype Created Web Application</display-name>
</web-app>
```
Step 3:
===
I added tomcat plugin to pom.xml.
```xml
<!-- For Maven Tomcat Plugin -->
		  <plugin>
			<groupId>org.apache.tomcat.maven</groupId>
			<artifactId>tomcat7-maven-plugin</artifactId>
			<version>2.2</version>
			<configuration>
				<path>/CounterWebApp</path>
			</configuration>
		  </plugin>
```
Step 4:
===
Now, the basic Hello World project set up is ready. To compile and package the project into a WAR file, use command
```
>mvn package
```
And to run the project, use following command
```
>mvn tomcat:run
```
As I have added tomcat plugin to our pom.xml, this command started tomcat and deployed the project to http://localhost:8080/ToDoApp 

