# stripyhorse.ComposeApi

All URIs are relative to *https://api.stripyhorse.io*

Method | HTTP request | Description
------------- | ------------- | -------------
[**compose_label**](ComposeApi.md#compose_label) | **POST** /v1/labels/compose | Compose ZPL from typed JSON elements


# **compose_label**
> ComposeOutputBody compose_label(compose_input_body)

Compose ZPL from typed JSON elements

Labels as JSON: place text, barcodes (code128/39, QR, DataMatrix), boxes, lines, circles, images and raw ZPL passthrough on a label and get back ZPL - optionally with rendered previews. {{name}} in text/data interpolates from the variables map; an unresolved variable is an error, never a blank on a real shipment. Positions are printer dots.

### Example

* Api Key Authentication (headerKey):
* Bearer (sh_live_…) Authentication (bearerKey):

```python
import stripyhorse
from stripyhorse.models.compose_input_body import ComposeInputBody
from stripyhorse.models.compose_output_body import ComposeOutputBody
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
    api_instance = stripyhorse.ComposeApi(api_client)
    compose_input_body = stripyhorse.ComposeInputBody() # ComposeInputBody | 

    try:
        # Compose ZPL from typed JSON elements
        api_response = api_instance.compose_label(compose_input_body)
        print("The response of ComposeApi->compose_label:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling ComposeApi->compose_label: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **compose_input_body** | [**ComposeInputBody**](ComposeInputBody.md)|  | 

### Return type

[**ComposeOutputBody**](ComposeOutputBody.md)

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

