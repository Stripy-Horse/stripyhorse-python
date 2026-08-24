# HtmlOutputBody


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**height_px** | **int** |  | 
**width_px** | **int** |  | 
**zpl** | **str** |  | 

## Example

```python
from stripyhorse.models.html_output_body import HtmlOutputBody

# TODO update the JSON string below
json = "{}"
# create an instance of HtmlOutputBody from a JSON string
html_output_body_instance = HtmlOutputBody.from_json(json)
# print the JSON string representation of the object
print(HtmlOutputBody.to_json())

# convert the object into a dict
html_output_body_dict = html_output_body_instance.to_dict()
# create an instance of HtmlOutputBody from a dict
html_output_body_from_dict = HtmlOutputBody.from_dict(html_output_body_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


