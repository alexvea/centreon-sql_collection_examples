## Description ##
This json allows you to retrieve count of activated and desactivated hosts from current configuration and trigger thresholds.

## List of constants used ##
| Constant  | description |
| ------------- | ------------- |
| --constant='warning_activated=100'  | warning from activated count |
| --constant='critical_activated=200'  | critical from activated count  |


## Example ##
````
sudo -u centreon-engine /usr/lib/centreon/plugins//centreon_mysql.pl --plugin=database::mysql::plugin --mode=collection --host=127.0.0.1  --username=centreon --password='Centreon$123' --config /tmp/sql_get_resource_count.json --constant='warning_activated=100' --constant='critical_activated=200'
````
same plugin command :
````
sudo -u centreon-engine /usr/lib/centreon/plugins//centreon_mysql.pl --plugin=database::mysql::plugin --mode=collection \
--host=127.0.0.1 --username=centreon --password='Centreon$123'
--config /tmp/sql_get_resource_count.json \
--constant='warning_activated=100' \
--constant='critical_activated=200'
````
OK output : 

````
OK: Resource host activated count :'2' - desactivated count :'1' | 'resource.activated.count'=2;100;;0;3 'resource.desactivated.count'=1;;;0;3
````

WARNING/CRITICAL output :

````
WARNING: Resource host activated count :'101' - desactivated count :'1' | 'resource.activated.count'=101;100;;0;102 'resource.desactivated.count'=1;;;0;102
````
````
CRITICAL: Resource host activated count :'201' - desactivated count :'1' | 'resource.activated.count'=201;;200;0;202 'resource.desactivated.count'=1;;;0;202
````
## Use case ##

Monitoring : to check if you have reach your licence host limit. 
https://docs.centreon.com/docs/administration/licenses/#your-epp-license-is-not-valid

## Improvement ##

Can be improved to check also service activated/desactived count.
