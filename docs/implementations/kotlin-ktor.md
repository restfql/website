---
sidebar_position: 2
---

# Ktor

## Usage
1. Add repository if not use the version on maven central
```kotlin
repositories {
    ...
    maven {
        url = uri("https://maven.pkg.github.com/restfql/ktor-restfql")
        credentials {
            username = project.findProperty("gpr.user") as String? ?: System.getenv("GITHUB_ACTOR")
            password = project.findProperty("gpr.key") as String? ?: System.getenv("GITHUB_TOKEN")
        }
    }
}
```

2. install with a package manager
```kotlin
val restfql_version = "1.0.0"

dependencies {
    implementation("com.restfql:ktor-restfql:$restfql_version")
}
```

2. Add the middleware to your ktor server

```kotlin
package com.restfql.ktor.example

import com.restfql.ktor.RestFQL
import io.ktor.server.application.*
import io.ktor.server.netty.*
import com.restfql.ktor.example.plugins.*

fun main(args: Array<String>) {
    EngineMain.main(args)
}

fun Application.module() {
    ...
    install(RestFQL)
}
```

3. query passing the model as a query param call `fql`
# ![preview query](https://user-images.githubusercontent.com/3071208/224512973-f5ae4679-2790-4a55-86e6-e0da1293c69b.png)
