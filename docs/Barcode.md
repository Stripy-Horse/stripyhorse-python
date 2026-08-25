# Barcode


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**blur_margin_dots** | **int** | Largest blur radius the symbol survives; 0 &#x3D; no margin | 
**checks** | [**List[Check]**](Check.md) |  | 
**cross_dpi** | [**List[DPIVerdict]**](DPIVerdict.md) | X-dimension at other print densities, same dot counts | [optional] 
**format** | **str** | CODE_128, CODE_39, ITF, QR_CODE, DATA_MATRIX | 
**module_dots** | **float** | Measured narrow-element width in printer dots (1D only) | [optional] 
**quiet_left_modules** | **float** |  | [optional] 
**quiet_right_modules** | **float** |  | [optional] 
**value** | **str** |  | 
**x_dimension_mm** | **float** | Physical narrow-element width at the analyzed density | [optional] 

## Example

```python
from stripyhorse.models.barcode import Barcode

# TODO update the JSON string below
json = "{}"
# create an instance of Barcode from a JSON string
barcode_instance = Barcode.from_json(json)
# print the JSON string representation of the object
print(Barcode.to_json())

# convert the object into a dict
barcode_dict = barcode_instance.to_dict()
# create an instance of Barcode from a dict
barcode_from_dict = Barcode.from_dict(barcode_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


