# VoidInputBody


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**dpmm** | **int** |  | [optional] 
**height_mm** | **float** |  | [optional] 
**preset** | **str** | Named label size in inches; alternative to widthMm/heightMm | [optional] 
**stamp** | **str** | Attribution stamp, e.g. VOID: bfaerber | [optional] 
**text** | **str** | Warning text; default VOID - DO NOT MAIL | [optional] 
**width_mm** | **float** |  | [optional] 
**zpl** | **str** |  | 

## Example

```python
from stripyhorse.models.void_input_body import VoidInputBody

# TODO update the JSON string below
json = "{}"
# create an instance of VoidInputBody from a JSON string
void_input_body_instance = VoidInputBody.from_json(json)
# print the JSON string representation of the object
print(VoidInputBody.to_json())

# convert the object into a dict
void_input_body_dict = void_input_body_instance.to_dict()
# create an instance of VoidInputBody from a dict
void_input_body_from_dict = VoidInputBody.from_dict(void_input_body_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


