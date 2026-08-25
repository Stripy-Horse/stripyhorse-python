# DPIVerdict


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**dpmm** | **int** |  | 
**ok** | **bool** |  | 
**x_dimension_mm** | **float** |  | 

## Example

```python
from stripyhorse.models.dpi_verdict import DPIVerdict

# TODO update the JSON string below
json = "{}"
# create an instance of DPIVerdict from a JSON string
dpi_verdict_instance = DPIVerdict.from_json(json)
# print the JSON string representation of the object
print(DPIVerdict.to_json())

# convert the object into a dict
dpi_verdict_dict = dpi_verdict_instance.to_dict()
# create an instance of DPIVerdict from a dict
dpi_verdict_from_dict = DPIVerdict.from_dict(dpi_verdict_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


