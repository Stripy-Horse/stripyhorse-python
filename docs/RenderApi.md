# stripyhorse.RenderApi

All URIs are relative to *https://api.stripyhorse.io*

Method | HTTP request | Description
------------- | ------------- | -------------
[**preflight_label**](RenderApi.md#preflight_label) | **POST** /v1/preflight | Grade a label&#39;s barcodes before they ship
[**render_zpl**](RenderApi.md#render_zpl) | **POST** /v1/render | Render ZPL to PNG images
[**render_zpl_png**](RenderApi.md#render_zpl_png) | **POST** /v1/render.png | Render ZPL and return the first label as a raw PNG


# **preflight_label**
> PreflightOutputBody preflight_label(preflight_input_body)

Grade a label's barcodes before they ship

Renders the ZPL and grades every barcode the way a verifier grades a printed label: round-trip decode, measured module width in printer dots, dot-grid alignment (catches rasterized barcodes), quiet zones in modules, physical X-dimension against the spec minimum, blur tolerance, and a cross-density table - plus static lint findings (structure, encoding traps, out-of-bounds fields). Grade fail means a scanner will reject it; fix it before a truck does.

### Example

* Api Key Authentication (headerKey):
* Bearer (sh_live_…) Authentication (bearerKey):

```python
import stripyhorse
from stripyhorse.models.preflight_input_body import PreflightInputBody
from stripyhorse.models.preflight_output_body import PreflightOutputBody
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
    api_instance = stripyhorse.RenderApi(api_client)
    preflight_input_body = stripyhorse.PreflightInputBody() # PreflightInputBody | 

    try:
        # Grade a label's barcodes before they ship
        api_response = api_instance.preflight_label(preflight_input_body)
        print("The response of RenderApi->preflight_label:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling RenderApi->preflight_label: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **preflight_input_body** | [**PreflightInputBody**](PreflightInputBody.md)|  | 

### Return type

[**PreflightOutputBody**](PreflightOutputBody.md)

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

# **render_zpl**
> RenderOutputBody render_zpl(render_input_body)

Render ZPL to PNG images

Renders every label in the ZPL stream. For a raw PNG of a single label use renderZplPng.

### Example

* Api Key Authentication (headerKey):
* Bearer (sh_live_…) Authentication (bearerKey):

```python
import stripyhorse
from stripyhorse.models.render_input_body import RenderInputBody
from stripyhorse.models.render_output_body import RenderOutputBody
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
    api_instance = stripyhorse.RenderApi(api_client)
    render_input_body = stripyhorse.RenderInputBody() # RenderInputBody | 

    try:
        # Render ZPL to PNG images
        api_response = api_instance.render_zpl(render_input_body)
        print("The response of RenderApi->render_zpl:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling RenderApi->render_zpl: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **render_input_body** | [**RenderInputBody**](RenderInputBody.md)|  | 

### Return type

[**RenderOutputBody**](RenderOutputBody.md)

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

# **render_zpl_png**
> str render_zpl_png(render_input_body)

Render ZPL and return the first label as a raw PNG

curl-friendly variant: the X-Label-Count response header carries the total label count.

### Example

* Api Key Authentication (headerKey):
* Bearer (sh_live_…) Authentication (bearerKey):

```python
import stripyhorse
from stripyhorse.models.render_input_body import RenderInputBody
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
    api_instance = stripyhorse.RenderApi(api_client)
    render_input_body = stripyhorse.RenderInputBody() # RenderInputBody | 

    try:
        # Render ZPL and return the first label as a raw PNG
        api_response = api_instance.render_zpl_png(render_input_body)
        print("The response of RenderApi->render_zpl_png:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling RenderApi->render_zpl_png: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **render_input_body** | [**RenderInputBody**](RenderInputBody.md)|  | 

### Return type

**str**

### Authorization

[headerKey](../README.md#headerKey), [bearerKey](../README.md#bearerKey)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | OK |  * Content-Type -  <br>  * X-Label-Count -  <br>  |
**0** | Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

