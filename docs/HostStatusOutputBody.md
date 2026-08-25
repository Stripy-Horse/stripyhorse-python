# HostStatusOutputBody


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**fields** | [**List[StatusField]**](StatusField.md) | Every field with its documented meaning and raw token | 
**status** | [**HostStatus**](HostStatus.md) |  | 

## Example

```python
from stripyhorse.models.host_status_output_body import HostStatusOutputBody

# TODO update the JSON string below
json = "{}"
# create an instance of HostStatusOutputBody from a JSON string
host_status_output_body_instance = HostStatusOutputBody.from_json(json)
# print the JSON string representation of the object
print(HostStatusOutputBody.to_json())

# convert the object into a dict
host_status_output_body_dict = host_status_output_body_instance.to_dict()
# create an instance of HostStatusOutputBody from a dict
host_status_output_body_from_dict = HostStatusOutputBody.from_dict(host_status_output_body_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


