# Vitrivr stack setup with docker compose

This is an experiential setup of the vitrivr stack that attempts in orchestrating all components and setting with docker compose pose.

**STATUS**: Not working.

## official documentation

* [Setting up the vitrivr stack](https://vitrivr.org/getting_started.html#setting-up-the-vitrivr-stack)

## Components

* [cottontail](https://github.com/vitrivr/cottontaildb/)
* [cineast](https://github.com/vitrivr/cineast)
* [Vitrivr NG](https://github.com/vitrivr/vitrivr-ng)
* Collabordinator - A small utility which coordinates collaborative retrieval. (optional)

See below for setup details

## Setup notes

### Cottontail


1. The cottontaildb wiki points out, that it is needed to switch-off the CLI in the config.json, otherwise it may cause problems when running in detached mode. However, it is unclear how this can be configured or if this still is an issue, as the CLI implementation has undergone significant changes
    * configuration: https://github.com/vitrivr/cottontaildb/wiki/Configuration 
        * options are found in https://github.com/vitrivr/cottontaildb/blob/master/cottontaildb-dbms/src/main/kotlin/org/vitrivr/cottontail/config/Config.kt

#### ERRORS

##### 1.

~~~
cottontail  | 2024-04-10 21:12:42 [DefaultDispatcher-worker-1] ERROR TransactionalGrpcService:226 - org.vitrivr.cottontail.dbms.exceptions.DatabaseException$SchemaDoesNotExistException: Schema 'warren.cineast' does not exist!
~~~

apparently fixed : https://github.com/vitrivr/cineast/issues/255, published in release https://github.com/vitrivr/cineast/releases/tag/v3.7.2 ==> startup with v3.7.2 works.

##### 2.

After startup with v3.7.2 another problem occurs:

~~~
Failed to initialize gRPC endpoint due to an exception: Receiver class io.grpc.netty.shaded.io.grpc.netty.NettyServerBuilder$NettyClientTransportServersBuilder does not define or inherit an implementation of the resolved method 'abstract io.grpc.internal.InternalServer buildClientTransportServers(java.util.List)' of interface io.grpc.internal.ServerImplBuilder$ClientTransportServersBuilder.
~~~

### Cineast

Cineast is a java application.

Running cineast: https://github.com/vitrivr/cineast/wiki/Getting-Started

configfile from https://github.com/vitrivr/cineast/blob/main/cineast.json

**PROBLEMS**:

1. it seems as if vitrivr-ng needs to be available also for Cineast, see vitrivr-ng/config.json

~~~
"sessionExtractionConfigLocation": "extraction_config.json",
"uiLocation": "../vitrivr-ng/dist",
~~~

2. extraction_config.json seems not to be recognized

### vitrivr-ng


reports: "No config file present, using default config". There is a `src/config.template.json` file which you can copy to `src/config.json`





