# stripyhorse.ConvertApi

All URIs are relative to *https://api.stripyhorse.io*

Method | HTTP request | Description
------------- | ------------- | -------------
[**convert_batch**](ConvertApi.md#convert_batch) | **POST** /v1/convert/batch | Convert many documents in one request, results streamed
[**convert_document**](ConvertApi.md#convert_document) | **POST** /v1/convert | Convert a PDF or image to ZPL
[**convert_html**](ConvertApi.md#convert_html) | **POST** /v1/convert/html | Convert an HTML label design to ZPL
[**convert_zpl_to_html**](ConvertApi.md#convert_zpl_to_html) | **POST** /v1/convert/zpl-html | Decompile ZPL into editable HTML
[**void_zpl**](ConvertApi.md#void_zpl) | **POST** /v1/void | Stamp ZPL as void / do-not-ship


# **convert_batch**
> convert_batch(files, barcode_aware=barcode_aware, compression=compression, dpmm=dpmm, height_mm=height_mm, preset=preset, rotation=rotation, scale=scale, threshold=threshold, width_mm=width_mm)

Convert many documents in one request, results streamed

Upload up to 20 PDFs/images as repeated `files` fields. The response is application/x-ndjson: one JSON object per converted page, streamed as each page finishes — `{"file":…,"page":…,"pageCount":…,"zpl":…}` on success, `{"file":…,"error":…}` per failed file (remaining files still convert).

### Example

* Api Key Authentication (headerKey):
* Bearer (sh_live_…) Authentication (bearerKey):

```python
import stripyhorse
from stripyhorse.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to https://api.stripyhorse.io
# See configuration.py for a list of all supported configuration parameters.
configuration = stripyhorse.Configuration(
    host = "https://api.stripyhorse.io"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure API key authorization: headerKey
configuration.api_key['headerKey'] = os.environ["API_KEY"]

# Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
# configuration.api_key_prefix['headerKey'] = 'Bearer'

# Configure Bearer authorization (sh_live_…): bearerKey
configuration = stripyhorse.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with stripyhorse.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = stripyhorse.ConvertApi(api_client)
    files = None # List[bytes] | 
    barcode_aware = True # bool |  (optional)
    compression = 'compression_example' # str |  (optional)
    dpmm = 56 # int |  (optional)
    height_mm = 3.4 # float |  (optional)
    preset = 'preset_example' # str |  (optional)
    rotation = 56 # int |  (optional)
    scale = 'scale_example' # str |  (optional)
    threshold = 56 # int |  (optional)
    width_mm = 3.4 # float |  (optional)

    try:
        # Convert many documents in one request, results streamed
        api_instance.convert_batch(files, barcode_aware=barcode_aware, compression=compression, dpmm=dpmm, height_mm=height_mm, preset=preset, rotation=rotation, scale=scale, threshold=threshold, width_mm=width_mm)
    except Exception as e:
        print("Exception when calling ConvertApi->convert_batch: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **files** | **List[bytes]**|  | 
 **barcode_aware** | **bool**|  | [optional] 
 **compression** | **str**|  | [optional] 
 **dpmm** | **int**|  | [optional] 
 **height_mm** | **float**|  | [optional] 
 **preset** | **str**|  | [optional] 
 **rotation** | **int**|  | [optional] 
 **scale** | **str**|  | [optional] 
 **threshold** | **int**|  | [optional] 
 **width_mm** | **float**|  | [optional] 

### Return type

void (empty response body)

### Authorization

[headerKey](../README.md#headerKey), [bearerKey](../README.md#bearerKey)

### HTTP request headers

 - **Content-Type**: multipart/form-data
 - **Accept**: application/problem+json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | OK |  -  |
**0** | Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **convert_document**
> ConvertOutputBody convert_document(file, barcode_aware=barcode_aware, compression=compression, dpmm=dpmm, height_mm=height_mm, preset=preset, rotation=rotation, scale=scale, threshold=threshold, width_mm=width_mm)

Convert a PDF or image to ZPL

Each page becomes its own ^GFA command (Zebra ACS run-length compression). PDFs up to 16 pages.

### Example

* Api Key Authentication (headerKey):
* Bearer (sh_live_…) Authentication (bearerKey):

```python
import stripyhorse
from stripyhorse.models.convert_output_body import ConvertOutputBody
from stripyhorse.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to https://api.stripyhorse.io
# See configuration.py for a list of all supported configuration parameters.
configuration = stripyhorse.Configuration(
    host = "https://api.stripyhorse.io"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure API key authorization: headerKey
configuration.api_key['headerKey'] = os.environ["API_KEY"]

# Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
# configuration.api_key_prefix['headerKey'] = 'Bearer'

# Configure Bearer authorization (sh_live_…): bearerKey
configuration = stripyhorse.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with stripyhorse.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = stripyhorse.ConvertApi(api_client)
    file = None # bytes | PDF, PNG, GIF or JPEG
    barcode_aware = True # bool | EXPERIMENTAL: re-emit decodable barcodes as native ^BC/^BQ fields, verified by a decode round trip with automatic fallback to plain rasterization (optional)
    compression = 'compression_example' # str | acs (default) or z64 (zlib+base64, smaller payloads) (optional)
    dpmm = 56 # int |  (optional)
    height_mm = 3.4 # float |  (optional)
    preset = 'preset_example' # str |  (optional)
    rotation = 56 # int |  (optional)
    scale = 'scale_example' # str | cover (fit), fill (stretch) or none (optional)
    threshold = 56 # int |  (optional)
    width_mm = 3.4 # float |  (optional)

    try:
        # Convert a PDF or image to ZPL
        api_response = api_instance.convert_document(file, barcode_aware=barcode_aware, compression=compression, dpmm=dpmm, height_mm=height_mm, preset=preset, rotation=rotation, scale=scale, threshold=threshold, width_mm=width_mm)
        print("The response of ConvertApi->convert_document:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling ConvertApi->convert_document: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **file** | **bytes**| PDF, PNG, GIF or JPEG | 
 **barcode_aware** | **bool**| EXPERIMENTAL: re-emit decodable barcodes as native ^BC/^BQ fields, verified by a decode round trip with automatic fallback to plain rasterization | [optional] 
 **compression** | **str**| acs (default) or z64 (zlib+base64, smaller payloads) | [optional] 
 **dpmm** | **int**|  | [optional] 
 **height_mm** | **float**|  | [optional] 
 **preset** | **str**|  | [optional] 
 **rotation** | **int**|  | [optional] 
 **scale** | **str**| cover (fit), fill (stretch) or none | [optional] 
 **threshold** | **int**|  | [optional] 
 **width_mm** | **float**|  | [optional] 

### Return type

[**ConvertOutputBody**](ConvertOutputBody.md)

### Authorization

[headerKey](../README.md#headerKey), [bearerKey](../README.md#bearerKey)

### HTTP request headers

 - **Content-Type**: multipart/form-data
 - **Accept**: application/json, application/problem+json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | OK |  -  |
**0** | Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **convert_html**
> HtmlOutputBody convert_html(html_input_body)

Convert an HTML label design to ZPL

Renders the HTML at exact print resolution (headless Chrome, network access blocked) and rasterizes it — except `<zpl-barcode type="code128|qr" data="…">` elements, which are measured from the layout and emitted as native ^BC/^BQ fields at their exact boxes. Size and position them with CSS (`left/top/width/height`); optional `module` (^BY dots) and `mag` (QR magnification) attributes pin exact bar geometry instead of fitting it to the box. Unsupported types or unencodable data fail loudly.

**PHP** (`composer require stripyhorse/stripyhorse-php`):
```php
$out = $convert->convertHtml(new StripyHorse\Model\HtmlInputBody([
    'html' => '<div style="position:absolute;left:40px;top:40px;font-size:50px">Hello</div>',
    'preset' => '4x6',
]));
echo $out->getZpl();
```

### Example

* Api Key Authentication (headerKey):
* Bearer (sh_live_…) Authentication (bearerKey):

```python
import stripyhorse
from stripyhorse.models.html_input_body import HtmlInputBody
from stripyhorse.models.html_output_body import HtmlOutputBody
from stripyhorse.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to https://api.stripyhorse.io
# See configuration.py for a list of all supported configuration parameters.
configuration = stripyhorse.Configuration(
    host = "https://api.stripyhorse.io"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure API key authorization: headerKey
configuration.api_key['headerKey'] = os.environ["API_KEY"]

# Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
# configuration.api_key_prefix['headerKey'] = 'Bearer'

# Configure Bearer authorization (sh_live_…): bearerKey
configuration = stripyhorse.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with stripyhorse.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = stripyhorse.ConvertApi(api_client)
    html_input_body = stripyhorse.HtmlInputBody() # HtmlInputBody | 

    try:
        # Convert an HTML label design to ZPL
        api_response = api_instance.convert_html(html_input_body)
        print("The response of ConvertApi->convert_html:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling ConvertApi->convert_html: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **html_input_body** | [**HtmlInputBody**](HtmlInputBody.md)|  | 

### Return type

[**HtmlOutputBody**](HtmlOutputBody.md)

### Authorization

[headerKey](../README.md#headerKey), [bearerKey](../README.md#bearerKey)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | OK |  -  |
**0** | Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **convert_zpl_to_html**
> ZplHTMLOutputBody convert_zpl_to_html(zpl_html_input_body)

Decompile ZPL into editable HTML

The migration path for legacy ZPL templates: text, boxes and Code128/QR barcodes become editable HTML in the dialect convertHtml accepts; unsupported elements (raster graphics, exotic barcodes) are embedded as positioned images so the layout survives. Round-tripping through convertHtml preserves scannable barcodes.

### Example

* Api Key Authentication (headerKey):
* Bearer (sh_live_…) Authentication (bearerKey):

```python
import stripyhorse
from stripyhorse.models.zpl_html_input_body import ZplHTMLInputBody
from stripyhorse.models.zpl_html_output_body import ZplHTMLOutputBody
from stripyhorse.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to https://api.stripyhorse.io
# See configuration.py for a list of all supported configuration parameters.
configuration = stripyhorse.Configuration(
    host = "https://api.stripyhorse.io"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure API key authorization: headerKey
configuration.api_key['headerKey'] = os.environ["API_KEY"]

# Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
# configuration.api_key_prefix['headerKey'] = 'Bearer'

# Configure Bearer authorization (sh_live_…): bearerKey
configuration = stripyhorse.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with stripyhorse.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = stripyhorse.ConvertApi(api_client)
    zpl_html_input_body = stripyhorse.ZplHTMLInputBody() # ZplHTMLInputBody | 

    try:
        # Decompile ZPL into editable HTML
        api_response = api_instance.convert_zpl_to_html(zpl_html_input_body)
        print("The response of ConvertApi->convert_zpl_to_html:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling ConvertApi->convert_zpl_to_html: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **zpl_html_input_body** | [**ZplHTMLInputBody**](ZplHTMLInputBody.md)|  | 

### Return type

[**ZplHTMLOutputBody**](ZplHTMLOutputBody.md)

### Authorization

[headerKey](../README.md#headerKey), [bearerKey](../README.md#bearerKey)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | OK |  -  |
**0** | Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **void_zpl**
> VoidOutputBody void_zpl(void_input_body)

Stamp ZPL as void / do-not-ship

Overlays large DO NOT SHIP warnings (and an optional attribution stamp) across every label in the stream, so printed dev and test labels can never be mistaken for shippable ones. Original fields are untouched; stamps draw on top.

### Example

* Api Key Authentication (headerKey):
* Bearer (sh_live_…) Authentication (bearerKey):

```python
import stripyhorse
from stripyhorse.models.void_input_body import VoidInputBody
from stripyhorse.models.void_output_body import VoidOutputBody
from stripyhorse.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to https://api.stripyhorse.io
# See configuration.py for a list of all supported configuration parameters.
configuration = stripyhorse.Configuration(
    host = "https://api.stripyhorse.io"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure API key authorization: headerKey
configuration.api_key['headerKey'] = os.environ["API_KEY"]

# Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
# configuration.api_key_prefix['headerKey'] = 'Bearer'

# Configure Bearer authorization (sh_live_…): bearerKey
configuration = stripyhorse.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with stripyhorse.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = stripyhorse.ConvertApi(api_client)
    void_input_body = stripyhorse.VoidInputBody() # VoidInputBody | 

    try:
        # Stamp ZPL as void / do-not-ship
        api_response = api_instance.void_zpl(void_input_body)
        print("The response of ConvertApi->void_zpl:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling ConvertApi->void_zpl: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **void_input_body** | [**VoidInputBody**](VoidInputBody.md)|  | 

### Return type

[**VoidOutputBody**](VoidOutputBody.md)

### Authorization

[headerKey](../README.md#headerKey), [bearerKey](../README.md#bearerKey)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | OK |  -  |
**0** | Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

