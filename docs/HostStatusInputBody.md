# HostStatusInputBody


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**response** | **str** | The three ~HS status lines, as received | 

## Example

```python
from stripyhorse.models.host_status_input_body import HostStatusInputBody

# TODO update the JSON string below
json = "{}"
# create an instance of HostStatusInputBody from a JSON string
host_status_input_body_instance = HostStatusInputBody.from_json(json)
# print the JSON string representation of the object
print(HostStatusInputBody.to_json())

# convert the object into a dict
host_status_input_body_dict = host_status_input_body_instance.to_dict()
# create an instance of HostStatusInputBody from a dict
host_status_input_body_from_dict = HostStatusInputBody.from_dict(host_status_input_body_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


