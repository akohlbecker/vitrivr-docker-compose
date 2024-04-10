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


