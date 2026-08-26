# Element


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**align** | **str** | Alignment when wrapping | [optional] 
**columns** | **int** | Grid columns (default 1) | [optional] 
**corner_radius** | **int** | Box corner rounding 0-8 | [optional] 
**data** | **str** | Barcode payload; {{name}} interpolates | [optional] 
**diameter** | **int** | Circle diameter in dots | [optional] 
**error_correction** | **str** | QR error correction (default M) | [optional] 
**font** | **str** | Printer font: 0 (scalable, default) or A-Z | [optional] 
**font_height** | **int** | Character height in dots (text) | [optional] 
**font_width** | **int** | Character width in dots; 0 follows fontHeight | [optional] 
**height** | **int** | Bar height in dots (1D) / box height in dots (box) | [optional] 
**length** | **int** | Line length in dots | [optional] 
**lines** | **int** | Max lines when wrapping (default 1) | [optional] 
**magnification** | **int** | QR module magnification (default 3) | [optional] 
**max_width** | **int** | Wrap text into a block this many dots wide | [optional] 
**module_size** | **int** | DataMatrix module size in dots (default 4) | [optional] 
**module_width** | **int** | Narrow element width in dots (1D; default 3) | [optional] 
**orientation** | **str** | Line direction | [optional] 
**png** | **str** | PNG/GIF/JPEG, base64-encoded | [optional] 
**print_text** | **bool** | Print the human-readable line under 1D barcodes (default true) | [optional] 
**rotation** | **int** |  | [optional] 
**rows** | **int** | Grid rows (default 1) | [optional] 
**text** | **str** | Text content; {{name}} interpolates from variables | [optional] 
**thickness** | **int** | Stroke thickness in dots (default 1) | [optional] 
**threshold** | **int** | Bitonal threshold (default 128) | [optional] 
**type** | **str** | What to place | 
**width** | **int** | Box/image width in dots | [optional] 
**x** | **int** | Left edge in dots | [optional] 
**y** | **int** | Top edge in dots | [optional] 
**zpl** | **str** | Verbatim ZPL commands (raw only) - the escape hatch | [optional] 

## Example

```python
from stripyhorse.models.element import Element

# TODO update the JSON string below
json = "{}"
# create an instance of Element from a JSON string
element_instance = Element.from_json(json)
# print the JSON string representation of the object
print(Element.to_json())

# convert the object into a dict
element_dict = element_instance.to_dict()
# create an instance of Element from a dict
element_from_dict = Element.from_dict(element_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


