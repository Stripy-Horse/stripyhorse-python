# ConvertedPage


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**page** | **int** | 1-based page number | 
**zpl** | **str** |  | 

## Example

```python
from stripyhorse.models.converted_page import ConvertedPage

# TODO update the JSON string below
json = "{}"
# create an instance of ConvertedPage from a JSON string
converted_page_instance = ConvertedPage.from_json(json)
# print the JSON string representation of the object
print(ConvertedPage.to_json())

# convert the object into a dict
converted_page_dict = converted_page_instance.to_dict()
# create an instance of ConvertedPage from a dict
converted_page_from_dict = ConvertedPage.from_dict(converted_page_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


