# StampInputBody


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**image** | **str** | PNG/GIF/JPEG, base64-encoded | 
**width_dots** | **int** | Stamp width in dots; 0 keeps the image&#39;s natural size | [optional] 
**x** | **int** | Left edge in dots | [optional] 
**y** | **int** | Top edge in dots | [optional] 
**zpl** | **str** |  | 

## Example

```python
from stripyhorse.models.stamp_input_body import StampInputBody

# TODO update the JSON string below
json = "{}"
# create an instance of StampInputBody from a JSON string
stamp_input_body_instance = StampInputBody.from_json(json)
# print the JSON string representation of the object
print(StampInputBody.to_json())

# convert the object into a dict
stamp_input_body_dict = stamp_input_body_instance.to_dict()
# create an instance of StampInputBody from a dict
stamp_input_body_from_dict = StampInputBody.from_dict(stamp_input_body_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


