# StatusSnapshot


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**darkness** | **str** | print.tone setting, e.g. 20.0 | 
**faults** | [**Faults**](Faults.md) |  | 
**formats_in_buffer** | **int** |  | 
**friendly_name** | **str** | device.friendly_name override; empty means unset | 
**label_length_dots** | **int** |  | 
**odometer** | **int** |  | 
**speed_ips** | **str** | media.speed setting, inches/second | 
**width_dots** | **int** |  | 

## Example

```python
from stripyhorse.models.status_snapshot import StatusSnapshot

# TODO update the JSON string below
json = "{}"
# create an instance of StatusSnapshot from a JSON string
status_snapshot_instance = StatusSnapshot.from_json(json)
# print the JSON string representation of the object
print(StatusSnapshot.to_json())

# convert the object into a dict
status_snapshot_dict = status_snapshot_instance.to_dict()
# create an instance of StatusSnapshot from a dict
status_snapshot_from_dict = StatusSnapshot.from_dict(status_snapshot_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


