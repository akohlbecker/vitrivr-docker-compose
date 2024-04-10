# Vitrivr setup locally

## official documentation

* [Setting up the vitrivr stack](https://vitrivr.org/getting_started.html#setting-up-the-vitrivr-stack)

## Project sources

* [cottontail](https://github.com/vitrivr/cottontaildb/)
* [Vitrivr NG](https://github.com/vitrivr/vitrivr-ng)
*
*

## Setup protocol

### Cottontail


* NOTE: need to switch-off the CLI in the config.json, since otherwise, it may cause problems when running detached, However it is unclear how this can be configuered or if this still is an issue, as the cli implementation has undergone significant changes --> **OPEN ISSUE**?
    * configuration: https://github.com/vitrivr/cottontaildb/wiki/Configuration 
        *   options are found in https://github.com/vitrivr/cottontaildb/blob/master/cottontaildb-dbms/src/main/kotlin/org/vitrivr/cottontail/config/Config.kt

ERRORS

~~~
cottontail  | 2024-04-10 21:12:42 [DefaultDispatcher-worker-1] ERROR TransactionalGrpcService:226 - org.vitrivr.cottontail.dbms.exceptions.DatabaseException$SchemaDoesNotExistException: Schema 'warren.cineast' does not exist!
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

2. extraction_config.json seems not to be recignized

### vitrivr-ng






