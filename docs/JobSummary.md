# JobSummary


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**error** | **str** |  | [optional] 
**id** | **int** |  | 
**label_count** | **int** |  | 
**received_at** | **datetime** |  | 
**source** | **str** |  | 
**status** | **str** |  | 
**zpl_bytes** | **int** |  | 

## Example

```python
from stripyhorse.models.job_summary import JobSummary

# TODO update the JSON string below
json = "{}"
# create an instance of JobSummary from a JSON string
job_summary_instance = JobSummary.from_json(json)
# print the JSON string representation of the object
print(JobSummary.to_json())

# convert the object into a dict
job_summary_dict = job_summary_instance.to_dict()
# create an instance of JobSummary from a dict
job_summary_from_dict = JobSummary.from_dict(job_summary_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


