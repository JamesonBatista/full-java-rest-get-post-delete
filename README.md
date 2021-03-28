# Metodos Java Rest Assured

### Imports usados
*import static io.restassured.RestAssured.*;*
*import static io.restassured.http.ContentType.JSON;*
*import static io.restassured.module.jsv.JsonSchemaValidator.matchesJsonSchemaInClasspath;*
*import static org.hamcrest.Matchers.*;*
*import static org.junit.Assert.assertThat;*

**GET Rest Assured**

**POST Rest Assured**

```
Post com Body, Status code, 

    given().contentType(JSON).body(jsonObject).expect().statusCode(201).body(path, is(value)).when().post().asString();
     
```
