# RenderOutputBody


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**label_count** | **int** |  | 
**labels** | [**List[RenderedLabel]**](RenderedLabel.md) |  | 

## Example

```python
from stripyhorse.models.render_output_body import RenderOutputBody

# TODO update the JSON string below
json = "{}"
# create an instance of RenderOutputBody from a JSON string
render_output_body_instance = RenderOutputBody.from_json(json)
# print the JSON string representation of the object
print(RenderOutputBody.to_json())

# convert the object into a dict
render_output_body_dict = render_output_body_instance.to_dict()
# create an instance of RenderOutputBody from a dict
render_output_body_from_dict = RenderOutputBody.from_dict(render_output_body_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


