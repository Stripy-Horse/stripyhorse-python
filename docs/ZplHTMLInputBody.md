# ZplHTMLInputBody


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**dpmm** | **int** | Print density in dots/mm (152/203/300/600 dpi); default 8 | [optional] 
**height_mm** | **float** |  | [optional] 
**preset** | **str** | Named label size in inches; alternative to widthMm/heightMm | [optional] 
**width_mm** | **float** |  | [optional] 
**zpl** | **str** |  | 

## Example

```python
from stripyhorse.models.zpl_html_input_body import ZplHTMLInputBody

# TODO update the JSON string below
json = "{}"
# create an instance of ZplHTMLInputBody from a JSON string
zpl_html_input_body_instance = ZplHTMLInputBody.from_json(json)
# print the JSON string representation of the object
print(ZplHTMLInputBody.to_json())

# convert the object into a dict
zpl_html_input_body_dict = zpl_html_input_body_instance.to_dict()
# create an instance of ZplHTMLInputBody from a dict
zpl_html_input_body_from_dict = ZplHTMLInputBody.from_dict(zpl_html_input_body_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


