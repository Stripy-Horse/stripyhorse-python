# RenderedLabel


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**height_px** | **int** |  | 
**index** | **int** |  | 
**png** | **str** | Base64-encoded PNG | 
**width_px** | **int** |  | 

## Example

```python
from stripyhorse.models.rendered_label import RenderedLabel

# TODO update the JSON string below
json = "{}"
# create an instance of RenderedLabel from a JSON string
rendered_label_instance = RenderedLabel.from_json(json)
# print the JSON string representation of the object
print(RenderedLabel.to_json())

# convert the object into a dict
rendered_label_dict = rendered_label_instance.to_dict()
# create an instance of RenderedLabel from a dict
rendered_label_from_dict = RenderedLabel.from_dict(rendered_label_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


