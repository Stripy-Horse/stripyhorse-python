# PreflightOutputBody


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**labels** | [**List[Report]**](Report.md) | One report per rendered label | 
**lint** | [**List[Finding]**](Finding.md) | Static ZPL findings: structure, encoding, bounds | 

## Example

```python
from stripyhorse.models.preflight_output_body import PreflightOutputBody

# TODO update the JSON string below
json = "{}"
# create an instance of PreflightOutputBody from a JSON string
preflight_output_body_instance = PreflightOutputBody.from_json(json)
# print the JSON string representation of the object
print(PreflightOutputBody.to_json())

# convert the object into a dict
preflight_output_body_dict = preflight_output_body_instance.to_dict()
# create an instance of PreflightOutputBody from a dict
preflight_output_body_from_dict = PreflightOutputBody.from_dict(preflight_output_body_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


