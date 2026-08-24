# Faults


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**head_up** | **bool** |  | [optional] 
**over_temp** | **bool** |  | [optional] 
**paper_out** | **bool** |  | [optional] 
**paused** | **bool** |  | [optional] 
**ribbon_out** | **bool** |  | [optional] 
**under_temp** | **bool** |  | [optional] 

## Example

```python
from stripyhorse.models.faults import Faults

# TODO update the JSON string below
json = "{}"
# create an instance of Faults from a JSON string
faults_instance = Faults.from_json(json)
# print the JSON string representation of the object
print(Faults.to_json())

# convert the object into a dict
faults_dict = faults_instance.to_dict()
# create an instance of Faults from a dict
faults_from_dict = Faults.from_dict(faults_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


