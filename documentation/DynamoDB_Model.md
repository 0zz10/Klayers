# Get Latest arn in region for package
* Insert v0.pckg for every new Insert as sk
* Query rgnPckg and V0.pckg to get latest version in region

## Sparse Index 1

### Get latest package for all regions
* Create a GSI with sk and dplySts
* Query for GSI v0.pckg and dplySts='latest'

## Sparse Index 2

### Get all deployed layers in region

* Create GSI for rgn and dplySts
* Query for rgn only.
* We want both deprecated and latest


When deleting:
+ Remove dplySts field
+ Add deleted_date field
+ Re-insert into DB

When inserting:
+ update V0.pckg
+ Insert row for currrent version
* Update previous layer dplySts='deprecated' & set TTL