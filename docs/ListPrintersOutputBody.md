# ListPrintersOutputBody


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**printers** | [**List[PrinterBody]**](PrinterBody.md) |  | 

## Example

```python
from stripyhorse.models.list_printers_output_body import ListPrintersOutputBody

# TODO update the JSON string below
json = "{}"
# create an instance of ListPrintersOutputBody from a JSON string
list_printers_output_body_instance = ListPrintersOutputBody.from_json(json)
# print the JSON string representation of the object
print(ListPrintersOutputBody.to_json())

# convert the object into a dict
list_printers_output_body_dict = list_printers_output_body_instance.to_dict()
# create an instance of ListPrintersOutputBody from a dict
list_printers_output_body_from_dict = ListPrintersOutputBody.from_dict(list_printers_output_body_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


