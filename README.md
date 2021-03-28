# Metodos Java Rest Assured

### Imports usados
    > import static io.restassured.RestAssured.*;
    > import static io.restassured.http.ContentType.JSON;
    > import static io.restassured.module.jsv.JsonSchemaValidator.matchesJsonSchemaInClasspath;
    > import static org.hamcrest.Matchers.*;
    > import static org.junit.Assert.assertThat;

**GET Rest Assured**

        String responseText = get().then().extract().path(path).toString();
        assertThat(responseText, containsString(value));
        
        given().when().get().then().body(pathValidationNull, is(notNullValue()));
        
        get("/ids").then().assertThat().body("data.id", equalTo(5));
        
        get("/ids").then().assertThat().body("ids.todos", hasItems(23, 54));

**POST Rest Assured**

    given().contentType(JSON).body(jsonObject).expect().statusCode(201).body(path, is(value)).when().post().asString();
 
    given().formParam("key", "value").contentType(JSON).body(jsonObject).expect().statusCode(201).body(path, is(value)).when().post().asString();
    

**Teste de contrato**

    given().when().get().then().assertThat().body(matchesJsonSchemaInClasspath("schemas/" + jsonName));

    given().formParam("key", "value").header("key", "value").when().get().then().assertThat().body(matchesJsonSchemaInClasspath("schemas/" + jsonName));


