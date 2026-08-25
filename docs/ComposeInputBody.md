# ComposeInputBody


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**dpmm** | **int** |  | [optional] 
**elements** | [**List[Element]**](Element.md) |  | 
**height_mm** | **float** |  | [optional] 
**preset** | **str** | Named label size; alternative to widthMm/heightMm | [optional] 
**preview** | **bool** | Also render the composed label to PNG | [optional] 
**variables** | **Dict[str, str]** | Values for {{name}} references | [optional] 
**width_mm** | **float** |  | [optional] 

## Example

```python
from stripyhorse.models.compose_input_body import ComposeInputBody

# TODO update the JSON string below
json = "{}"
# create an instance of ComposeInputBody from a JSON string
compose_input_body_instance = ComposeInputBody.from_json(json)
# print the JSON string representation of the object
print(ComposeInputBody.to_json())

# convert the object into a dict
compose_input_body_dict = compose_input_body_instance.to_dict()
# create an instance of ComposeInputBody from a dict
compose_input_body_from_dict = ComposeInputBody.from_dict(compose_input_body_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


