# HtmlInputBody


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**compression** | **str** |  | [optional] 
**dpmm** | **int** |  | [optional] 
**height_mm** | **float** |  | [optional] 
**html** | **str** | Label markup: HTML/CSS plus &lt;zpl-barcode&gt; elements | 
**preset** | **str** |  | [optional] 
**threshold** | **int** |  | [optional] 
**width_mm** | **float** |  | [optional] 

## Example

```python
from stripyhorse.models.html_input_body import HtmlInputBody

# TODO update the JSON string below
json = "{}"
# create an instance of HtmlInputBody from a JSON string
html_input_body_instance = HtmlInputBody.from_json(json)
# print the JSON string representation of the object
print(HtmlInputBody.to_json())

# convert the object into a dict
html_input_body_dict = html_input_body_instance.to_dict()
# create an instance of HtmlInputBody from a dict
html_input_body_from_dict = HtmlInputBody.from_dict(html_input_body_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


