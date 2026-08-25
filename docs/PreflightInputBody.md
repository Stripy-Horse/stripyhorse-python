# PreflightInputBody


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**dpmm** | **int** |  | [optional] 
**height_mm** | **float** |  | [optional] 
**preset** | **str** | Named label size; alternative to widthMm/heightMm | [optional] 
**width_mm** | **float** |  | [optional] 
**zpl** | **str** |  | 

## Example

```python
from stripyhorse.models.preflight_input_body import PreflightInputBody

# TODO update the JSON string below
json = "{}"
# create an instance of PreflightInputBody from a JSON string
preflight_input_body_instance = PreflightInputBody.from_json(json)
# print the JSON string representation of the object
print(PreflightInputBody.to_json())

# convert the object into a dict
preflight_input_body_dict = preflight_input_body_instance.to_dict()
# create an instance of PreflightInputBody from a dict
preflight_input_body_from_dict = PreflightInputBody.from_dict(preflight_input_body_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


