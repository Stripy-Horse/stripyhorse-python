# Finding


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**code** | **str** |  | 
**label** | **int** | 1-based label index; 0 &#x3D; whole stream | 
**message** | **str** |  | 
**severity** | **str** |  | 

## Example

```python
from stripyhorse.models.finding import Finding

# TODO update the JSON string below
json = "{}"
# create an instance of Finding from a JSON string
finding_instance = Finding.from_json(json)
# print the JSON string representation of the object
print(Finding.to_json())

# convert the object into a dict
finding_dict = finding_instance.to_dict()
# create an instance of Finding from a dict
finding_from_dict = Finding.from_dict(finding_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


