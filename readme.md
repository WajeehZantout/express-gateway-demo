# Express Gateway Demo

## Install

Make sure you have `NodeJS` and `npm` installed on your machine.
Clone the project using

```
git clone https://github.com/WajeehZantout/express-gateway-demo
```

and run:

```
npm install
```

## Start the server

To start the proxy server, use

```
npm start
```

## WireMock Setup

To mock your API, we are using here a tool called `WireMock`.

You can download it from [this link](http://repo1.maven.org/maven2/com/github/tomakehurst/wiremock-standalone/2.14.0/wiremock-standalone-2.14.0.jar).

When downloaded, you need to make sure you have JDK isntalled. If not, please download [JDK](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)

Navigate to the folder where you have the `.jar` file of wiremock and run the following command:

```
java -jar wiremock-standalone-2.14.0.jar --port 9999 --root-dir "<PROJECT_PATH>\express-gateway-demo\wiremock"
```

After running this command, it will create two folders inside the specified directory (`__files` & `mappings`). `mappings` should contain Service files with either `.json` or `.java` extensions.

Restart WireMock to get the latest changes into the server Using tools like [**Postman**](https://www.getpostman.com/apps) or [**Restlet**](https://chrome.google.com/webstore/detail/restlet-client-rest-api-t/aejoelaoggembcahagimdiliamlcdmfm?hl=en), perform a post request to `http://localhost:9999/__admin/mappings/reset` with an empty body.

You have a fully configured version of WireMock that accepts `GET`, `POST` and `PUT` requests.
You're ready to go from here.

To shut the server down, send an empty `POST` request to `http://localhost:9999/__admin/shutdown`. For additional information, refer to the API admin documentation [here](http://wiremock.org/docs/api/)
