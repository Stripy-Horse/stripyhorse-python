# StateOutputBody


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**state** | [**StatusSnapshot**](StatusSnapshot.md) |  | 

## Example

```python
from stripyhorse.models.state_output_body import StateOutputBody

# TODO update the JSON string below
json = "{}"
# create an instance of StateOutputBody from a JSON string
state_output_body_instance = StateOutputBody.from_json(json)
# print the JSON string representation of the object
print(StateOutputBody.to_json())

# convert the object into a dict
state_output_body_dict = state_output_body_instance.to_dict()
# create an instance of StateOutputBody from a dict
state_output_body_from_dict = StateOutputBody.from_dict(state_output_body_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


