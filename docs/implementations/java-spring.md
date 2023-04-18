---
sidebar_position: 3
---

# SpringBoot

## Usage
1. Add repository if not use the version on maven central
```kotlin
repositories {
    ...
    maven {
        url = uri("https://maven.pkg.github.com/restfql/spring-restfql")
        credentials {
            username = project.findProperty("gpr.user") as String? ?: System.getenv("GITHUB_ACTOR")
            password = project.findProperty("gpr.key") as String? ?: System.getenv("GITHUB_TOKEN")
        }
    }
}
```

2. install with a package manager
```kotlin
val restfql_version = "1.0.8"

dependencies {
    implementation("com.restfql:spring-restfql:$restfql_version")
}
```

2. Add a configuration with the import to the `RestFQLConfiguration.class` 

```Java
@Configuration
@Import(RestFQLConfiguration.class)
public class AppConfig {}

```

3. query passing the model as a query param call `fql`
# ![preview query](https://user-images.githubusercontent.com/3071208/224512973-f5ae4679-2790-4a55-86e6-e0da1293c69b.png)