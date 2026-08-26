# UpdatePrinterInputBody


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**anonymize** | **bool** |  | [optional] 
**name** | **str** |  | [optional] 
**webhook_url** | **str** |  | [optional] 

## Example

```python
from stripyhorse.models.update_printer_input_body import UpdatePrinterInputBody

# TODO update the JSON string below
json = "{}"
# create an instance of UpdatePrinterInputBody from a JSON string
update_printer_input_body_instance = UpdatePrinterInputBody.from_json(json)
# print the JSON string representation of the object
print(UpdatePrinterInputBody.to_json())

# convert the object into a dict
update_printer_input_body_dict = update_printer_input_body_instance.to_dict()
# create an instance of UpdatePrinterInputBody from a dict
update_printer_input_body_from_dict = UpdatePrinterInputBody.from_dict(update_printer_input_body_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


