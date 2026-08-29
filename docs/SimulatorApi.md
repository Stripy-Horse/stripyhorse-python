# stripyhorse.SimulatorApi

All URIs are relative to *https://api.stripyhorse.io*

Method | HTTP request | Description
------------- | ------------- | -------------
[**clear_jobs**](SimulatorApi.md#clear_jobs) | **DELETE** /v1/printers/{printerId}/jobs | Delete all captured jobs
[**create_printer**](SimulatorApi.md#create_printer) | **POST** /v1/printers | Create a virtual printer
[**delete_job**](SimulatorApi.md#delete_job) | **DELETE** /v1/printers/{printerId}/jobs/{jobId} | Delete one captured job
[**delete_printer**](SimulatorApi.md#delete_printer) | **DELETE** /v1/printers/{printerId} | Delete a printer and its captured jobs
[**get_job**](SimulatorApi.md#get_job) | **GET** /v1/printers/{printerId}/jobs/{jobId} | Get one job including its raw ZPL
[**get_job_label**](SimulatorApi.md#get_job_label) | **GET** /v1/printers/{printerId}/jobs/{jobId}/labels/{index}.png | Get one rendered label as a PNG
[**get_printer**](SimulatorApi.md#get_printer) | **GET** /v1/printers/{printerId} | Get a printer with live state
[**list_jobs**](SimulatorApi.md#list_jobs) | **GET** /v1/printers/{printerId}/jobs | List captured jobs, newest first
[**list_printers**](SimulatorApi.md#list_printers) | **GET** /v1/printers | List your printers
[**reset_printer**](SimulatorApi.md#reset_printer) | **POST** /v1/printers/{printerId}/reset | Clear all faults and flush held jobs
[**set_printer_faults**](SimulatorApi.md#set_printer_faults) | **POST** /v1/printers/{printerId}/faults | Inject or clear fault conditions
[**update_printer**](SimulatorApi.md#update_printer) | **PATCH** /v1/printers/{printerId} | Rename a printer or set its webhook URL


# **clear_jobs**
> clear_jobs(printer_id)

Delete all captured jobs

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
    api_instance = stripyhorse.SimulatorApi(api_client)
    printer_id = 'printer_id_example' # str | 

    try:
        # Delete all captured jobs
        api_instance.clear_jobs(printer_id)
    except Exception as e:
        print("Exception when calling SimulatorApi->clear_jobs: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **printer_id** | **str**|  | 

### Return type

void (empty response body)

### Authorization

[headerKey](../README.md#headerKey), [bearerKey](../README.md#bearerKey)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/problem+json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**204** | No Content |  -  |
**0** | Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **create_printer**
> PrinterBody create_printer(create_printer_input_body)

Create a virtual printer

Free tier: one ephemeral printer (24h idle TTL). Paid tiers: persistent printers. The ingest URL and webhook secret are only returned here.

### Example

* Api Key Authentication (headerKey):
* Bearer (sh_live_…) Authentication (bearerKey):

```python
import stripyhorse
from stripyhorse.models.create_printer_input_body import CreatePrinterInputBody
from stripyhorse.models.printer_body import PrinterBody
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
    api_instance = stripyhorse.SimulatorApi(api_client)
    create_printer_input_body = stripyhorse.CreatePrinterInputBody() # CreatePrinterInputBody | 

    try:
        # Create a virtual printer
        api_response = api_instance.create_printer(create_printer_input_body)
        print("The response of SimulatorApi->create_printer:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling SimulatorApi->create_printer: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **create_printer_input_body** | [**CreatePrinterInputBody**](CreatePrinterInputBody.md)|  | 

### Return type

[**PrinterBody**](PrinterBody.md)

### Authorization

[headerKey](../README.md#headerKey), [bearerKey](../README.md#bearerKey)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**201** | Created |  -  |
**0** | Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_job**
> delete_job(printer_id, job_id)

Delete one captured job

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
    api_instance = stripyhorse.SimulatorApi(api_client)
    printer_id = 'printer_id_example' # str | 
    job_id = 56 # int | 

    try:
        # Delete one captured job
        api_instance.delete_job(printer_id, job_id)
    except Exception as e:
        print("Exception when calling SimulatorApi->delete_job: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **printer_id** | **str**|  | 
 **job_id** | **int**|  | 

### Return type

void (empty response body)

### Authorization

[headerKey](../README.md#headerKey), [bearerKey](../README.md#bearerKey)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/problem+json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**204** | No Content |  -  |
**0** | Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_printer**
> delete_printer(printer_id)

Delete a printer and its captured jobs

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
    api_instance = stripyhorse.SimulatorApi(api_client)
    printer_id = 'printer_id_example' # str | 

    try:
        # Delete a printer and its captured jobs
        api_instance.delete_printer(printer_id)
    except Exception as e:
        print("Exception when calling SimulatorApi->delete_printer: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **printer_id** | **str**|  | 

### Return type

void (empty response body)

### Authorization

[headerKey](../README.md#headerKey), [bearerKey](../README.md#bearerKey)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/problem+json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**204** | No Content |  -  |
**0** | Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_job**
> JobOutputBody get_job(printer_id, job_id)

Get one job including its raw ZPL

### Example

* Api Key Authentication (headerKey):
* Bearer (sh_live_…) Authentication (bearerKey):

```python
import stripyhorse
from stripyhorse.models.job_output_body import JobOutputBody
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
    api_instance = stripyhorse.SimulatorApi(api_client)
    printer_id = 'printer_id_example' # str | 
    job_id = 56 # int | 

    try:
        # Get one job including its raw ZPL
        api_response = api_instance.get_job(printer_id, job_id)
        print("The response of SimulatorApi->get_job:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling SimulatorApi->get_job: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **printer_id** | **str**|  | 
 **job_id** | **int**|  | 

### Return type

[**JobOutputBody**](JobOutputBody.md)

### Authorization

[headerKey](../README.md#headerKey), [bearerKey](../README.md#bearerKey)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | OK |  -  |
**0** | Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_job_label**
> str get_job_label(printer_id, job_id, index)

Get one rendered label as a PNG

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
    api_instance = stripyhorse.SimulatorApi(api_client)
    printer_id = 'printer_id_example' # str | 
    job_id = 56 # int | 
    index = 56 # int | 

    try:
        # Get one rendered label as a PNG
        api_response = api_instance.get_job_label(printer_id, job_id, index)
        print("The response of SimulatorApi->get_job_label:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling SimulatorApi->get_job_label: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **printer_id** | **str**|  | 
 **job_id** | **int**|  | 
 **index** | **int**|  | 

### Return type

**str**

### Authorization

[headerKey](../README.md#headerKey), [bearerKey](../README.md#bearerKey)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | OK |  * Content-Type -  <br>  |
**0** | Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_printer**
> PrinterBody get_printer(printer_id)

Get a printer with live state

### Example

* Api Key Authentication (headerKey):
* Bearer (sh_live_…) Authentication (bearerKey):

```python
import stripyhorse
from stripyhorse.models.printer_body import PrinterBody
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
    api_instance = stripyhorse.SimulatorApi(api_client)
    printer_id = 'printer_id_example' # str | 

    try:
        # Get a printer with live state
        api_response = api_instance.get_printer(printer_id)
        print("The response of SimulatorApi->get_printer:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling SimulatorApi->get_printer: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **printer_id** | **str**|  | 

### Return type

[**PrinterBody**](PrinterBody.md)

### Authorization

[headerKey](../README.md#headerKey), [bearerKey](../README.md#bearerKey)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | OK |  -  |
**0** | Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **list_jobs**
> ListJobsOutputBody list_jobs(printer_id, limit=limit, before=before)

List captured jobs, newest first

For CI assertions and inbox views. Cursor-paged via before.

### Example

* Api Key Authentication (headerKey):
* Bearer (sh_live_…) Authentication (bearerKey):

```python
import stripyhorse
from stripyhorse.models.list_jobs_output_body import ListJobsOutputBody
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
    api_instance = stripyhorse.SimulatorApi(api_client)
    printer_id = 'printer_id_example' # str | 
    limit = 50 # int |  (optional) (default to 50)
    before = 56 # int | Return jobs with id lower than this cursor (optional)

    try:
        # List captured jobs, newest first
        api_response = api_instance.list_jobs(printer_id, limit=limit, before=before)
        print("The response of SimulatorApi->list_jobs:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling SimulatorApi->list_jobs: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **printer_id** | **str**|  | 
 **limit** | **int**|  | [optional] [default to 50]
 **before** | **int**| Return jobs with id lower than this cursor | [optional] 

### Return type

[**ListJobsOutputBody**](ListJobsOutputBody.md)

### Authorization

[headerKey](../README.md#headerKey), [bearerKey](../README.md#bearerKey)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | OK |  -  |
**0** | Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **list_printers**
> ListPrintersOutputBody list_printers()

List your printers

Every printer on your account, whichever of its keys created them.

### Example

* Api Key Authentication (headerKey):
* Bearer (sh_live_…) Authentication (bearerKey):

```python
import stripyhorse
from stripyhorse.models.list_printers_output_body import ListPrintersOutputBody
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
    api_instance = stripyhorse.SimulatorApi(api_client)

    try:
        # List your printers
        api_response = api_instance.list_printers()
        print("The response of SimulatorApi->list_printers:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling SimulatorApi->list_printers: %s\n" % e)
```



### Parameters

This endpoint does not need any parameter.

### Return type

[**ListPrintersOutputBody**](ListPrintersOutputBody.md)

### Authorization

[headerKey](../README.md#headerKey), [bearerKey](../README.md#bearerKey)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | OK |  -  |
**0** | Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **reset_printer**
> StateOutputBody reset_printer(printer_id)

Clear all faults and flush held jobs

### Example

* Api Key Authentication (headerKey):
* Bearer (sh_live_…) Authentication (bearerKey):

```python
import stripyhorse
from stripyhorse.models.state_output_body import StateOutputBody
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
    api_instance = stripyhorse.SimulatorApi(api_client)
    printer_id = 'printer_id_example' # str | 

    try:
        # Clear all faults and flush held jobs
        api_response = api_instance.reset_printer(printer_id)
        print("The response of SimulatorApi->reset_printer:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling SimulatorApi->reset_printer: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **printer_id** | **str**|  | 

### Return type

[**StateOutputBody**](StateOutputBody.md)

### Authorization

[headerKey](../README.md#headerKey), [bearerKey](../README.md#bearerKey)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | OK |  -  |
**0** | Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **set_printer_faults**
> StateOutputBody set_printer_faults(printer_id, faults)

Inject or clear fault conditions

Blocking faults hold incoming jobs in the receive buffer; clearing them flushes the queue in order.

### Example

* Api Key Authentication (headerKey):
* Bearer (sh_live_…) Authentication (bearerKey):

```python
import stripyhorse
from stripyhorse.models.faults import Faults
from stripyhorse.models.state_output_body import StateOutputBody
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
    api_instance = stripyhorse.SimulatorApi(api_client)
    printer_id = 'printer_id_example' # str | 
    faults = stripyhorse.Faults() # Faults | 

    try:
        # Inject or clear fault conditions
        api_response = api_instance.set_printer_faults(printer_id, faults)
        print("The response of SimulatorApi->set_printer_faults:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling SimulatorApi->set_printer_faults: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **printer_id** | **str**|  | 
 **faults** | [**Faults**](Faults.md)|  | 

### Return type

[**StateOutputBody**](StateOutputBody.md)

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

# **update_printer**
> PrinterBody update_printer(printer_id, update_printer_input_body)

Rename a printer or set its webhook URL

### Example

* Api Key Authentication (headerKey):
* Bearer (sh_live_…) Authentication (bearerKey):

```python
import stripyhorse
from stripyhorse.models.printer_body import PrinterBody
from stripyhorse.models.update_printer_input_body import UpdatePrinterInputBody
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
    api_instance = stripyhorse.SimulatorApi(api_client)
    printer_id = 'printer_id_example' # str | 
    update_printer_input_body = stripyhorse.UpdatePrinterInputBody() # UpdatePrinterInputBody | 

    try:
        # Rename a printer or set its webhook URL
        api_response = api_instance.update_printer(printer_id, update_printer_input_body)
        print("The response of SimulatorApi->update_printer:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling SimulatorApi->update_printer: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **printer_id** | **str**|  | 
 **update_printer_input_body** | [**UpdatePrinterInputBody**](UpdatePrinterInputBody.md)|  | 

### Return type

[**PrinterBody**](PrinterBody.md)

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

