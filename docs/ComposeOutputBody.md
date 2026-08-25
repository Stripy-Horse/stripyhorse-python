# ComposeOutputBody


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**labels** | [**List[RenderedLabel]**](RenderedLabel.md) | Rendered previews when preview&#x3D;true | [optional] 
**warnings** | **List[str]** |  | 
**zpl** | **str** |  | 

## Example

```python
from stripyhorse.models.compose_output_body import ComposeOutputBody

# TODO update the JSON string below
json = "{}"
# create an instance of ComposeOutputBody from a JSON string
compose_output_body_instance = ComposeOutputBody.from_json(json)
# print the JSON string representation of the object
print(ComposeOutputBody.to_json())

# convert the object into a dict
compose_output_body_dict = compose_output_body_instance.to_dict()
# create an instance of ComposeOutputBody from a dict
compose_output_body_from_dict = ComposeOutputBody.from_dict(compose_output_body_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


