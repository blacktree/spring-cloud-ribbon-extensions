<div style="text-align: right">v1.4.1-SNAPSHOT</div>

# Spring Cloud Ribbon Extensions :rocket::microscope:

:exclamation:Must Have:exclamation: Enhance your µService testing, maintenance & overall development productivity.

**Spring Cloud Ribbon Extensions** is a set of load balancing rules that chooses which server to target.
It comes with handy features for easy integration, configuration and customization.

:warning: This is an experimental version designed for dev environments.

:dash: Official version coming soon.

:warning: stomp & jms integration tests has not been performed yet.


[![Build Status](https://travis-ci.org/enadim/spring-cloud-ribbon-extensions.svg?branch=develop)](https://travis-ci.org/enadim/spring-cloud-ribbon-extensions)
[![Codecov Coverage](https://codecov.io/gh/enadim/spring-cloud-ribbon-extensions/branch/develop/graph/badge.svg)](https://codecov.io/gh/enadim/spring-cloud-ribbon-extensions)
[![Codacy](https://api.codacy.com/project/badge/Grade/bf7e3455f2894da19b1e250173c9ace1)](https://www.codacy.com/app/enadim/spring-cloud-ribbon-extensions?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=enadim/spring-cloud-ribbon-extensions&amp;utm_campaign=Badge_Grade)

[![SonarCloud Reliability](https://sonarcloud.io/api/badges/measure?key=enadim:spring-cloud-ribbon-extensions:develop&metric=reliability_rating)](https://sonarcloud.io/component_measures?id=enadim:spring-cloud-ribbon-extensions:develop&metric=reliability_rating)
[![SonarCloud Security](https://sonarcloud.io/api/badges/measure?key=enadim:spring-cloud-ribbon-extensions:develop&metric=security_rating)](https://sonarcloud.io/component_measures?id=enadim:spring-cloud-ribbon-extensions:develop&metric=security_rating)
[![SonarCloud Squale](https://sonarcloud.io/api/badges/measure?key=enadim:spring-cloud-ribbon-extensions:develop&metric=sqale_rating)](https://sonarcloud.io/component_measures?id=enadim:spring-cloud-ribbon-extensions:develop&metric=sqale_rating)
[![SonarCloud Coverage](https://sonarcloud.io/api/badges/measure?key=enadim:spring-cloud-ribbon-extensions:develop&metric=coverage)](https://sonarcloud.io/component_measures?id=enadim:spring-cloud-ribbon-extensions:develop&metric=Coverage)
[![SonarCloud Duplication](https://sonarcloud.io/api/badges/measure?key=enadim:spring-cloud-ribbon-extensions:develop&metric=duplicated_lines_density)](https://sonarcloud.io/component_measures?id=enadim:spring-cloud-ribbon-extensions:develop&metric=Duplications)

![CoL](https://tokei.rs/b1/github/enadim/spring-cloud-ribbon-extensions)
[![Sonatype Snapshots](https://img.shields.io/nexus/s/https/oss.sonatype.org/#artifactdetails/com.github.enadim/spring-cloud-ribbon-extensions.svg)](https://oss.sonatype.org/#nexus-search;gav~com.github.enadim~spring-cloud-ribbon-extensions~1.4.1-SNAPSHOT)
[![Javadocs](http://www.javadoc.io/badge/com.github.enadim/spring-cloud-ribbon-extensions/1.4.1-SNAPSHOT.svg)](http://www.javadoc.io/doc/com.github.enadim/spring-cloud-ribbon-extensions/1.4.1-SNAPSHOT)

[![GitHub license](https://img.shields.io/github/license/enadim/spring-cloud-ribbon-extensions.svg)](https://github.com/enadim/spring-cloud-ribbon-extensions/develop/LICENSE)
[![GitHub issues](https://img.shields.io/github/issues/enadim/spring-cloud-ribbon-extensions.svg)](https://github.com/enadim/spring-cloud-ribbon-extensions/issues)
[![GitHub network/members](https://img.shields.io/github/forks/enadim/spring-cloud-ribbon-extensions.svg)](https://github.com/enadim/spring-cloud-ribbon-extensions/network/members)

## Requirements
* spring cloud ribbon.
* spring cloud Daslton-SR3.

## Compatibility
* spring cloud eureka.
* spring cloud feign.
* spring cloud zuul.
* spring cloud hystrix.
* spring and java executors.
* spring stomp.
* jms.

## Features

### Routing Rules.

#### Zone Affinity
@EnableRibbonZoneAffinity: Enables routing to the same zone: see the tests for concrete usage and configurations.

Designed mainly for µServices that should calls others in the same zone.

#### Favorite Zone :gem:
@EnableRibbonFavoriteZone: Enables routing to a favorite zone: see the tests for concrete usage and configurations.

Designed mainly for testing a µService among an existing µService architecture without disruption. This is the feature that triggered this project.

#### Strict Metadata Routing
@EnableRibbonStrictMetadataMatcher: Enables routing to servers that have a set of metadata: see the tests for concrete usage and configurations.

Designed to target a specific µService that holds a point to point connection with an external system (like FIX,...)

Requires Eureka.

#### Dynamic Matcher :gem:
@EnableDynamicMatcher: Enables routing against a dynamic key: see the tests for concrete usage and configurations.

Designed to target a specific µServices that holds multiple point to point connections with many external systems (like FIX,...)

Requires Eureka.

### Context Propagation :gem:
@EnableRibbonContextPropagation: Enables sharing the execution context through all the µServices: see the tests for concrete usage and configurations.

Designed to propagate the execution context across the µServices architecture.

What does it support:
* Transport: http, jms, stomp.
* Async: java, spring, Hystrix.
* Zuul

:warning:You should use only lower case key names (http header limitation).

### Combine Favorite Zone & Context Propagation :sparkles:
Eureka:exclamation: Let's enter a world of easy development and testing with µService architecture.
* Developers are able to deploy & debug their own micro-service and get back any request they have initiated disregarding the entry point and without being annoyed by the requests they have not initiated.
* Deploying in multi region-and let our clients (that have no knowledge of eureka, ribbon, zuul) choose the zone they prefer to target.
* And other things that I have not thought about...

![Illustration](./puml/context-propagation-favorite-zone.png)

## Setup
The artifact will never have a third party dependency: please check the compatibility with your dependencies.

maven
```xml
<dependency>
  <groupId>com.github.enadim</groupId>
  <artifactId>spring-cloud-ribbon-extensions</artifactId>
  <version>1.4.1-SNAPSHOT</version>
</dependency>
```

gradle
```gradle
dependencies {
    compile 'com.github.enadim:spring-cloud-ribbon-extensions:1.4.1-SNAPSHOT'
}
```

## Contribution
Any help is welcome. :ok_hand:
