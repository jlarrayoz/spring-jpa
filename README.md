# spring-jpa
En este proyecto vamos a agregar el uso de persistencia (JDBC + JPA) al proyecto de pedidos de pizza


**Primero vamos a trabajar con JDBC y a grandes rasgos vamos a realizar los siguientes pasos:**

<ol>
	<li>Agregar la dependencia de spring JDBC</li>
	<li>Agregar un campo id a los objetos del dominio que no lo tengan</li>
	<li>Vamos a agregar campos de fecha de alta (mini auditoria) a Pizza y OrdenPizza</li>
</ol>


Debemos agregar en el pom.xml la siguiente dependencia:

```xml
<dependency> 
	<groupId>org.springframework.boot</groupId> <artifactId>spring-boot-starter-jdbc</artifactId>
</dependency>
```