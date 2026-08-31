# Supplies


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**labels_left** | **int** | Labels left on the roll | [optional] 
**labels_loaded** | **int** | Labels the roll held when it was fitted; 0 means an endless roll | [optional] 
**ribbon_mm_left** | **int** | Millimetres of ribbon left | [optional] 
**ribbon_mm_loaded** | **int** | Millimetres of ribbon fitted; 0 means endless, which is also what direct thermal looks like | [optional] 

## Example

```python
from stripyhorse.models.supplies import Supplies

# TODO update the JSON string below
json = "{}"
# create an instance of Supplies from a JSON string
supplies_instance = Supplies.from_json(json)
# print the JSON string representation of the object
print(Supplies.to_json())

# convert the object into a dict
supplies_dict = supplies_instance.to_dict()
# create an instance of Supplies from a dict
supplies_from_dict = Supplies.from_dict(supplies_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


