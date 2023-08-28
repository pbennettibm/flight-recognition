# flight-recognition Project

This project uses Quarkus, the Supersonic Subatomic Java Framework.

If you want to learn more about Quarkus, please visit its website: https://quarkus.io/ .

## Sample Payload

Sample JSON script

```sh
    curl -X 'POST' \
      'http://localhost:8126/flight_recognition' \
      -H 'accept: application/json' \
      -H 'Content-Type: application/json' \
      -d '{
      "Flight": {
        "flight time": "09:00",
        "flight date": "2023-08-28",
        "passengers": [
          {
            "seat": "22A",
            "name": "Tim",
            "status": "360",
            "million miler": true,
            "last received recognition": "2021-12-20",
            "missed connection": true
          },
          {
            "seat": "22B",
            "name": "Steve",
            "status": "Diamond",
            "million miler": true,
            "last received recognition": "2022-12-20",
            "missed connection": false
          }
        ],
        "distance": 200
      },
      "Passenger": "Test Passenger"
    }'
```

## Running the application in dev mode

You can run your application in dev mode that enables live coding using:

```shell script
./mvnw compile quarkus:dev
```

> **_NOTE:_** Quarkus now ships with a Dev UI, which is available in dev mode only at http://localhost:8080/q/dev/.

## Packaging and running the application

The application can be packaged using:

```shell script
./mvnw package
```

It produces the `quarkus-run.jar` file in the `target/quarkus-app/` directory.
Be aware that it’s not an _über-jar_ as the dependencies are copied into the `target/quarkus-app/lib/` directory.

The application is now runnable using `java -jar target/quarkus-app/quarkus-run.jar`.

If you want to build an _über-jar_, execute the following command:

```shell script
./mvnw package -Dquarkus.package.type=uber-jar
```

The application, packaged as an _über-jar_, is now runnable using `java -jar target/*-runner.jar`.

## Creating a native executable

You can create a native executable using:

```shell script
./mvnw package -Pnative
```

Or, if you don't have GraalVM installed, you can run the native executable build in a container using:

```shell script
./mvnw package -Pnative -Dquarkus.native.container-build=true
```

You can then execute your native executable with: `./target/flight-recognition-1.0.0-SNAPSHOT-runner`

If you want to learn more about building native executables, please consult https://quarkus.io/guides/maven-tooling.

## Related Guides

- Kogito - Decisions (DMN) ([guide](https://quarkus.io/guides/kogito-dmn)): Add Kogito decision (DMN) capabilities - Include Drools DMN engine
- SmallRye OpenAPI ([guide](https://quarkus.io/guides/openapi-swaggerui)): Document your REST APIs with OpenAPI - comes with Swagger UI
- SmallRye Health ([guide](https://quarkus.io/guides/microprofile-health)): Monitor service health
- Kogito ([guide](https://quarkus.io/guides/kogito)): Add business automation capabilities - processes and rules with Kogito (a toolkit that originates from projects Drools and jBPM)

## Provided Code

### Kogito DMN codestart

This is an example Kogito DMN Quarkus codestart, it contains a sample DMN model for REST code generation based on the model definition.

[Related guide section...](https://quarkus.io/guides/kogito-dmn)

This Kogito DMN Quarkus codestart contains a sample DMN model as described in the [Quarkus Kogito DMN guide](https://quarkus.io/guides/kogito-dmn).
The goal is to showcase automatic REST endpoint codegen, based on the content of the model.
The `pricing.dmn` DMN model calculates a base price quotation based on some criteria provided as input.

You can reference the [full guide on the Quarkus website](https://quarkus.io/guides/kogito-dmn).

### RESTEasy Reactive

Easily start your Reactive RESTful Web Services

[Related guide section...](https://quarkus.io/guides/getting-started-reactive#reactive-jax-rs-resources)

### SmallRye Health

Monitor your application's health using SmallRye Health

[Related guide section...](https://quarkus.io/guides/smallrye-health)
