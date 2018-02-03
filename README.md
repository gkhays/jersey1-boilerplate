# jersey1-boilerplate

Jersey 1 basic project.

pom.xml
```xml
<dependencies>
  <dependency>
    <groupId>com.sun.jersey</groupId>
    <artifactId>jersey-bundle</artifactId>
    <version>${jersey.version}</version>
  </dependency>
  <dependency>
    <groupId>com.sun.jersey</groupId>
    <artifactId>jersey-server</artifactId>
    <version>${jersey.version}</version>
  </dependency>
</dependencies>
```

web.xml
```xml
<servlet>
  <servlet-name>Jersey 1 HelloWorld Servlet</servlet-name>
  <servlet-class>com.sun.jersey.spi.container.servlet.ServletContainer</servlet-class>
  <init-param>
    <param-name>com.sun.jersey.config.property.packages</param-name>
    <param-value>org.gkh.rest.jersey</param-value>
  </init-param>
  <load-on-startup>1</load-on-startup>
</servlet>
<servlet-mapping>
  <servlet-name>Jersey 1 HelloWorld Servlet</servlet-name>
  <url-pattern>/rest/*</url-pattern>
</servlet-mapping>
```

```java
import javax.ws.rs.GET;
import javax.ws.rs.Path;
import javax.ws.rs.Produces;
import javax.ws.rs.core.MediaType;
import javax.ws.rs.core.Response;

@Path("/hello")
public class MyResource {
	
	@GET
	@Produces(MediaType.APPLICATION_JSON)
	@Path("/jsonjaxb")
	public Response toJettisonJaxb() {
		XmlPojo pojo = new XmlPojo(1, "");
		return Response.ok().entity(pojo).build();		
	}
}
```
