# cti-sysmon-schema

This folder contains non-normative JSON schemas used to describe Sysmon properties. The JSON schemas are also used to validate instances which is useful for automated testing.

**NOTE:** The Sysmon JSON schemas are based on OSSEM's data dictionary that can be found in the following repository : https://github.com/Cyb3rWard0g/OSSEM/tree/master/data_dictionaries/windows/sysmon

Two different folders are specified : x-sysmon-common & x-sysmon-eventids

### x-sysmon-common
This folder contains common properties that will be used by different JSON schemas. Instead of repeating the same properties in different schemas, we define them only once in the x-sysmon-common folder and reference them using in the JSON schemas if needed. 

### x-sysmon-eventids
This folder contains the JSON schemas that will represent the properties used by each Sysmon Event ID.

## Naming Convention 
The following Sysmon JSON schemas are custom and thus start with "x-". (See Requirements of Custom Objects : http://docs.oasis-open.org/cti/stix/v2.0/stix-v2.0-part1-stix-core.html)
The custom properties defined by these schemas start with "x_". (See Requirements of Custom Properties : http://docs.oasis-open.org/cti/stix/v2.0/stix-v2.0-part1-stix-core.html)

## The Schemas & Validation 
The following schemas are used to specify the different properties used by Sysmon, and are used to validate generated instances.
We could have made one JSON schema having all the event ids using keywords like allof/oneof/anyof. However, we are restricting the schema so no additional properties are allowed (using "additionalProperties": false), and this makes the schema reject everything (See https://json-schema.org/understanding-json-schema/reference/combining.html).
