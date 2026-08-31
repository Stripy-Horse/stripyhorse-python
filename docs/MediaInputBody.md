# MediaInputBody


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**labels** | **int** | Labels on the roll; 0 for an endless roll | [optional] 
**ribbon_metres** | **float** | Ribbon on the spool in metres; 0 for endless, which is also what direct thermal looks like | [optional] 

## Example

```python
from stripyhorse.models.media_input_body import MediaInputBody

# TODO update the JSON string below
json = "{}"
# create an instance of MediaInputBody from a JSON string
media_input_body_instance = MediaInputBody.from_json(json)
# print the JSON string representation of the object
print(MediaInputBody.to_json())

# convert the object into a dict
media_input_body_dict = media_input_body_instance.to_dict()
# create an instance of MediaInputBody from a dict
media_input_body_from_dict = MediaInputBody.from_dict(media_input_body_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


