# CreatePrinterInputBody


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**access_mode** | **str** | Who may print to the TCP port; default open. Use token from CI, where the source address is different every run. | [optional] 
**anonymize** | **bool** | Mask PII and strip graphics from every captured frame | [optional] 
**dpmm** | **int** | Print density in dots/mm (152/203/300/600 dpi); default 8 | [optional] 
**height_mm** | **float** |  | [optional] 
**mode** | **str** |  | [optional] 
**name** | **str** |  | 
**preset** | **str** | Named label size in inches; alternative to widthMm/heightMm | [optional] 
**shared_port** | **bool** | Put this printer on the shared router port instead of spending one of the plan&#39;s dedicated ports. It is then reached by naming it in the stream, a ZPL comment carrying the ingest token, which suits CI. | [optional] 
**webhook_url** | **str** |  | [optional] 
**width_mm** | **float** |  | [optional] 

## Example

```python
from stripyhorse.models.create_printer_input_body import CreatePrinterInputBody

# TODO update the JSON string below
json = "{}"
# create an instance of CreatePrinterInputBody from a JSON string
create_printer_input_body_instance = CreatePrinterInputBody.from_json(json)
# print the JSON string representation of the object
print(CreatePrinterInputBody.to_json())

# convert the object into a dict
create_printer_input_body_dict = create_printer_input_body_instance.to_dict()
# create an instance of CreatePrinterInputBody from a dict
create_printer_input_body_from_dict = CreatePrinterInputBody.from_dict(create_printer_input_body_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


