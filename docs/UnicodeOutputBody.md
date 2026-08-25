# UnicodeOutputBody


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**fields_rasterized** | **int** |  | 
**skipped** | **List[str]** |  | [optional] 
**zpl** | **str** |  | 

## Example

```python
from stripyhorse.models.unicode_output_body import UnicodeOutputBody

# TODO update the JSON string below
json = "{}"
# create an instance of UnicodeOutputBody from a JSON string
unicode_output_body_instance = UnicodeOutputBody.from_json(json)
# print the JSON string representation of the object
print(UnicodeOutputBody.to_json())

# convert the object into a dict
unicode_output_body_dict = unicode_output_body_instance.to_dict()
# create an instance of UnicodeOutputBody from a dict
unicode_output_body_from_dict = UnicodeOutputBody.from_dict(unicode_output_body_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


