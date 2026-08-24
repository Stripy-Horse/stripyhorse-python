# JobOutputBody


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**labels** | **List[str]** | URLs of the rendered label PNGs | 
**zpl** | **str** | The raw ZPL as received | 

## Example

```python
from stripyhorse.models.job_output_body import JobOutputBody

# TODO update the JSON string below
json = "{}"
# create an instance of JobOutputBody from a JSON string
job_output_body_instance = JobOutputBody.from_json(json)
# print the JSON string representation of the object
print(JobOutputBody.to_json())

# convert the object into a dict
job_output_body_dict = job_output_body_instance.to_dict()
# create an instance of JobOutputBody from a dict
job_output_body_from_dict = JobOutputBody.from_dict(job_output_body_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


