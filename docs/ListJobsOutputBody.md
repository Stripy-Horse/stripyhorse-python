# ListJobsOutputBody


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**jobs** | [**List[JobSummary]**](JobSummary.md) |  | 

## Example

```python
from stripyhorse.models.list_jobs_output_body import ListJobsOutputBody

# TODO update the JSON string below
json = "{}"
# create an instance of ListJobsOutputBody from a JSON string
list_jobs_output_body_instance = ListJobsOutputBody.from_json(json)
# print the JSON string representation of the object
print(ListJobsOutputBody.to_json())

# convert the object into a dict
list_jobs_output_body_dict = list_jobs_output_body_instance.to_dict()
# create an instance of ListJobsOutputBody from a dict
list_jobs_output_body_from_dict = ListJobsOutputBody.from_dict(list_jobs_output_body_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


