# StatusField


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**var_field** | **str** |  | 
**raw** | **str** |  | 
**value** | **str** |  | 

## Example

```python
from stripyhorse.models.status_field import StatusField

# TODO update the JSON string below
json = "{}"
# create an instance of StatusField from a JSON string
status_field_instance = StatusField.from_json(json)
# print the JSON string representation of the object
print(StatusField.to_json())

# convert the object into a dict
status_field_dict = status_field_instance.to_dict()
# create an instance of StatusField from a dict
status_field_from_dict = StatusField.from_dict(status_field_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


