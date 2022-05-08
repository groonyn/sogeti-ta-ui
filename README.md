# UI Automation Task

This is fully configurable UI and API automation framework based on BDD testing concept using Serenity, Cucumber, Java technologies.
Configurable for parallel and cross-browser automation if needed.

Projects was designed using Page Object pattern in mixture with Step Design Pattern for UI part.

## Dependencies

1. Java 11
2. Maven 3
3. Selenium
4. Serenity 3
5. Cucumber 7
6. Unit 4
6. Hamcrest 1.3

See the `pom.xml` for details.
## HOW TO

To run project for sequential test run:
- maven console
```
clean verify
```
For parallel run of stories:
- maven console
```
clean verify -Dparallel=methods
```
NOTE: Basically it has current preset to 4 instances.

By default, the tests will run using Chrome. You can run them in Firefox by overriding the `driver` system property, e.g.
```
clean verify -Ddriver=firefox
```

# Generating the reports
The Full Serenity reports are generated by the `serenity-maven-plugin` in `pom.xml`.
You can trigger this by running:
```
serenity:aggregate
```
or just run your tests in maven by:

```
clean verify
```
from the command line or from your IDE.

They reports are also integrated into the Maven build process.
The reports to be generated automatically once all the tests have completed when you run `mvn verify`.


Tricks:
1. you can easily configure max number of parallel stories(tests): `<parallel.tests>{number}</parallel.tests>` in `pom.xml`
2. you can look for the reports after the first run in folder: `target/site/serenity/index.html`
3. or just one page report in folder: `/target/site/serenity/serenity-summary.html`
4. for JUnit running also just run this class: `src/test/java/com/flink/AcceptanceTestSuite.java`
5. all configuration of selenium drivers for platforms and environments simply can be set here:`src/test/resources/serenity.conf`

For any Serenity Cucumber extras please look: [github.com](https://github.com/serenity-bdd/serenity-cucumber-starter/blob/5691f44c3600720d3c6e513b5761912350dda31e/README.md)
