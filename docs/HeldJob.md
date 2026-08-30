# HeldJob


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**bytes** | **int** | Size of the held frame | 
**received_at** | **datetime** |  | 
**source** | **str** | How it arrived: tcp or https | 

## Example

```python
from stripyhorse.models.held_job import HeldJob

# TODO update the JSON string below
json = "{}"
# create an instance of HeldJob from a JSON string
held_job_instance = HeldJob.from_json(json)
# print the JSON string representation of the object
print(HeldJob.to_json())

# convert the object into a dict
held_job_dict = held_job_instance.to_dict()
# create an instance of HeldJob from a dict
held_job_from_dict = HeldJob.from_dict(held_job_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


