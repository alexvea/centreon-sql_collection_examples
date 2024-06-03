## Description ##
This json allows you to check retrieve the last check (timestamp) of a resource (by his configuration id, can be host or service).

## List of constants used ##
| Constant  | description |
| ------------- | ------------- |
| --constant='resource_id=13' | resource id (from configuration page)  |
| --constant='resource_type=host' | can be host or service |


## Example ##
````
sudo -u centreon-engine /usr/lib/centreon/plugins//centreon_mysql.pl --plugin=database::mysql::plugin --mode=collection --host=127.0.0.1  --username=centreon --password='Centreon$123' --config /tmp/get_timestamp_from_resource_id.json --constant='resource_id=13' --constant='resource_type=host' --output-ignore-label
````
same plugin command :
````
sudo -u centreon-engine /usr/lib/centreon/plugins//centreon_mysql.pl --plugin=database::mysql::plugin --mode=collection \
--host=127.0.0.1  --username=centreon --password='Centreon$123' \
--config /tmp/get_timestamp_from_resource_id.json \
--constant='resource_id=13' \
--constant='resource_type=host' \
--output-ignore-label
````
Working output : 

````
Resource type 'host' - name 'Central' : Last check timestamp='1717421710' | 'resource.last_check.timestamp'=1717421710;;;0;
````

Not working output :

````

````
## Use case ##

Bug : to check for ressource last check timestamp.

## Improvement ##

When the id resource is not existing, it will output OK: , so we need to add  --output-ignore-label to get empty output.




