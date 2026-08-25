# HostStatus


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**blocking** | **bool** | True when any condition stops printing | 
**buffer_full** | **bool** |  | 
**comm_settings** | **str** | Raw communication-settings code | 
**corrupt_ram** | **bool** |  | 
**diagnostic_mode** | **bool** |  | 
**formats_in_buffer** | **int** | Jobs waiting in the receive buffer | 
**function_settings** | **str** | Raw function-settings code | 
**graphics_stored** | **int** |  | 
**head_up** | **bool** |  | 
**label_length_dots** | **int** |  | 
**labels_remaining** | **int** |  | 
**over_temp** | **bool** |  | 
**paper_out** | **bool** |  | 
**partial_format** | **bool** |  | 
**password** | **str** |  | 
**paused** | **bool** |  | 
**print_mode** | **str** | rewind, peel-off, tear-off, cutter or applicator | 
**ribbon_out** | **bool** |  | 
**static_ram** | **bool** |  | 
**thermal_transfer** | **bool** |  | 
**under_temp** | **bool** |  | 

## Example

```python
from stripyhorse.models.host_status import HostStatus

# TODO update the JSON string below
json = "{}"
# create an instance of HostStatus from a JSON string
host_status_instance = HostStatus.from_json(json)
# print the JSON string representation of the object
print(HostStatus.to_json())

# convert the object into a dict
host_status_dict = host_status_instance.to_dict()
# create an instance of HostStatus from a dict
host_status_from_dict = HostStatus.from_dict(host_status_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


