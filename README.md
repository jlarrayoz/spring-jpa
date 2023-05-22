# spring-jpa
En este proyecto vamos a agregar el uso de persistencia (JDBC + JPA) al proyecto de pedidos de pizza


**Primero vamos a trabajar con JDBC y a grandes rasgos vamos a realizar los siguientes pasos:**

<ol>
	<li>Agregar la dependencia de spring JDBC</li>
	<li>Agergar dependencia para el DBMS lightweight <a href="https://www.h2database.com/html/main.html">Página oficial H2</a></li>
	<li>Prefijar el nombre de la BD en el archivo <b>applications.properties</b></li>
	<li>Agregar un campo id a los objetos del dominio que no lo tengan</li>
	<li>Vamos a agregar campos de fecha de alta (mini auditoria) a Pizza y OrdenPizza</li>
</ol>


1 - Debemos agregar en el pom.xml las siguientes dependencias:

```xml
<!-- Dependencia para usar JDBC -->
<dependency> 
	<groupId>org.springframework.boot</groupId> <artifactId>spring-boot-starter-jdbc</artifactId>
</dependency>

<!-- Dependecia para utilizar el DBMS H2 -->
<dependency>
    <groupId>com.h2database</groupId>
    <artifactId>h2</artifactId>
    <scope>runtime</scope>
</dependency>

```

3 - El nombre de la base de datos H2 se debe configurar en el archivo applications.properties (Si no se fija el nombre, se crea de forma aleatoria)

En este ejemplo vamos y para proposito de desarrollo vamos a utilizar la BD embebida H2.

El archiv applications se encuentra en la carpeta "src/main/resources".

Podemos substituir este archivo por "application.yml" y expresar lo mismo en este nuevo formato:

```yml
spring:
  datasource:
    generate-unique-name: false
    name: pizzadb
```

La URL de acceso a la BD va a ser **jdbc:h2:mem:pizzadb**