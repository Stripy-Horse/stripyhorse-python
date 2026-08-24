# stripyhorse.ConvertApi

All URIs are relative to *https://api.stripyhorse.io*

Method | HTTP request | Description
------------- | ------------- | -------------
[**convert_batch**](ConvertApi.md#convert_batch) | **POST** /v1/convert/batch | Convert many documents in one request, results streamed
[**convert_document**](ConvertApi.md#convert_document) | **POST** /v1/convert | Convert a PDF or image to ZPL
[**convert_html**](ConvertApi.md#convert_html) | **POST** /v1/convert/html | Convert an HTML label design to ZPL


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

**PHP** (`composer require stripyhorse/stripyhorse-php`):
```php
$convert = new StripyHorse\Api\ConvertApi(null, $config);
$result = $convert->convertDocument(new SplFileObject('shipping-label.pdf'), preset: '4x6');
foreach ($result->getPages() as $page) { sendToPrinter($page->getZpl()); }
```

**curl**:
```bash
curl https://api.stripyhorse.io/v1/convert \
  -H "X-Api-Key: sh_live_YOUR_KEY" -F file=@shipping-label.pdf -F preset=4x6
```

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

Renders the HTML at exact print resolution (headless Chrome, network access blocked) and rasterizes it — except `<zpl-barcode type="code128|qr" data="…">` elements, which are measured from the layout and emitted as native ^BC/^BQ fields at their exact boxes. Size and position them with CSS (`left/top/width/height`). Unsupported types or unencodable data fail loudly.

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

