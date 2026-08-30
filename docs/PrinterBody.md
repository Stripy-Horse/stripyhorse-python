# PrinterBody


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**access_mode** | **str** | Who may print to the TCP port: open (anyone), token (the stream must open with ~SH plus the ingest token), ip (only addresses the org has claimed) | 
**anonymize** | **bool** | When true, PII is masked and graphics stripped from every captured frame | 
**created_at** | **datetime** |  | 
**dpmm** | **int** |  | 
**expires_at** | **datetime** |  | [optional] 
**height_mm** | **float** |  | 
**id** | **str** |  | 
**ingest_url** | **str** | HTTPS print capability URL. Only returned on creation. | [optional] 
**mode** | **str** |  | 
**name** | **str** |  | 
**state** | [**StatusSnapshot**](StatusSnapshot.md) |  | [optional] 
**tcp** | [**PrinterBodyTCPStruct**](PrinterBodyTCPStruct.md) |  | 
**webhook_secret** | **str** | HMAC-SHA256 key for X-Stripy-Horse-Signature. Only returned on creation. | [optional] 
**webhook_url** | **str** |  | [optional] 
**width_mm** | **float** |  | 

## Example

```python
from stripyhorse.models.printer_body import PrinterBody

# TODO update the JSON string below
json = "{}"
# create an instance of PrinterBody from a JSON string
printer_body_instance = PrinterBody.from_json(json)
# print the JSON string representation of the object
print(PrinterBody.to_json())

# convert the object into a dict
printer_body_dict = printer_body_instance.to_dict()
# create an instance of PrinterBody from a dict
printer_body_from_dict = PrinterBody.from_dict(printer_body_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


