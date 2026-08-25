# stripyhorse.PrintersApi

All URIs are relative to *https://api.stripyhorse.io*

Method | HTTP request | Description
------------- | ------------- | -------------
[**parse_host_status**](PrintersApi.md#parse_host_status) | **POST** /v1/host-status/parse | Decode a Zebra ~HS host status response


# **parse_host_status**
> HostStatusOutputBody parse_host_status(host_status_input_body)

Decode a Zebra ~HS host status response

Parses the three-line ~HS answer a Zebra printer (or our virtual printer) returns on port 9100 into typed fields - paper out, pause, buffer contents, head temperature - so you never write a positional comma parser. Accepts raw bytes, cat -v style ^B/^C markers, or hand-cleaned lines. Does not count against your monthly quota.

### Example

* Api Key Authentication (headerKey):
* Bearer (sh_live_…) Authentication (bearerKey):

```python
import stripyhorse
from stripyhorse.models.host_status_input_body import HostStatusInputBody
from stripyhorse.models.host_status_output_body import HostStatusOutputBody
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
    api_instance = stripyhorse.PrintersApi(api_client)
    host_status_input_body = stripyhorse.HostStatusInputBody() # HostStatusInputBody | 

    try:
        # Decode a Zebra ~HS host status response
        api_response = api_instance.parse_host_status(host_status_input_body)
        print("The response of PrintersApi->parse_host_status:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling PrintersApi->parse_host_status: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **host_status_input_body** | [**HostStatusInputBody**](HostStatusInputBody.md)|  | 

### Return type

[**HostStatusOutputBody**](HostStatusOutputBody.md)

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

