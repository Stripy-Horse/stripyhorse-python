# PrinterBodyTCPStruct


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**host** | **str** |  | 
**port** | **int** |  | 

## Example

```python
from stripyhorse.models.printer_body_tcp_struct import PrinterBodyTCPStruct

# TODO update the JSON string below
json = "{}"
# create an instance of PrinterBodyTCPStruct from a JSON string
printer_body_tcp_struct_instance = PrinterBodyTCPStruct.from_json(json)
# print the JSON string representation of the object
print(PrinterBodyTCPStruct.to_json())

# convert the object into a dict
printer_body_tcp_struct_dict = printer_body_tcp_struct_instance.to_dict()
# create an instance of PrinterBodyTCPStruct from a dict
printer_body_tcp_struct_from_dict = PrinterBodyTCPStruct.from_dict(printer_body_tcp_struct_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


