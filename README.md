# Google Places JSON to POJO

Google Places JSON to Java Object, for use with GSON Parser for Android.

Made with http://www.jsonschema2pojo.org/

**!!NOTICE!!:** You should probably be using [Retrofit](http://square.github.io/retrofit/) instead for parsing REST API JSON to POJO. Regardless, I'm keeping this project up. :)
## Motivation

Making your own Java classes manually for GSON to parse correctly sucks. I used **jsonschema2pojo** to generate the classes necessary for parsing with GSON, and created the classes you need for parsing JSON data from Google Places here.



### Usage

Copy and paste (or clone, or download, or whatever) the `.java` classes into your project. Remember to change the **package name** at the top of the files. 

The `NearbySearch` class is the top level object, so you will need to call the following to store your results into a `NearbySearch` instance:

```java
// Query Google Places API for nearby places.
String query = '{
   "html_attributions" : [],
   "next_page_token" : "
   ...
   }';
   
// Parse and store results into Java Object.
NearbySearch nbs = gson.fromJson(query, NearbySearch.class);
```

You will need to get the query string with an HTTP request. This can be done with an HTTP client library.

### See also:
* [Using GSON in Android](http://guides.codepath.com/android/leveraging-the-gson-library)
* Autogenerating POJOs from JSON - http://www.jsonschema2pojo.org/
* HTTP Clients libraries:
  * Ion - https://github.com/koush/ion
  * Volley - https://developer.android.com/training/volley/index.html
  * Retrofit - http://square.github.io/retrofit/
  * OkHttp - http://square.github.io/okhttp/
  * [CodePath guide on using Retrofit](https://github.com/codepath/android_guides/wiki/Consuming-APIs-with-Retrofit)
