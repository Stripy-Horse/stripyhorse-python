# ConvertOutputBody


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**pages** | [**List[ConvertedPage]**](ConvertedPage.md) |  | 

## Example

```python
from stripyhorse.models.convert_output_body import ConvertOutputBody

# TODO update the JSON string below
json = "{}"
# create an instance of ConvertOutputBody from a JSON string
convert_output_body_instance = ConvertOutputBody.from_json(json)
# print the JSON string representation of the object
print(ConvertOutputBody.to_json())

# convert the object into a dict
convert_output_body_dict = convert_output_body_instance.to_dict()
# create an instance of ConvertOutputBody from a dict
convert_output_body_from_dict = ConvertOutputBody.from_dict(convert_output_body_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


