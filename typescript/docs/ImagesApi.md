# ImagesApi

All URIs are relative to *https://api.cs2c.app*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**listGameImages**](ImagesApi.md#listgameimages) | **GET** /v1/images | List Game Images |



## listGameImages

> { [key: string]: Array&lt;string&gt;; } listGameImages()

List Game Images

Return a directory of CS2 catalog display names mapped to their image URLs on the CS2Cap CDN. Names that map to multiple distinct images return all URLs.

### Example

```ts
import {
  Configuration,
  ImagesApi,
} from 'cs2cap';
import type { ListGameImagesRequest } from 'cs2cap';

async function example() {
  console.log("🚀 Testing cs2cap SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ImagesApi(config);

  try {
    const data = await api.listGameImages();
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

// Run the test
example().catch(console.error);
```

### Parameters

This endpoint does not need any parameter.

### Return type

**{ [key: string]: Array<string>; }**

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Successful Response |  -  |
| **401** | Missing or invalid authentication credentials. |  -  |
| **403** | Authenticated but not permitted to access this resource. |  -  |
| **429** | Rate limit exceeded (burst or monthly quota). |  * Retry-After - Seconds to wait before retrying when present. <br>  * X-RateLimit-Tier - Authenticated caller tier code. <br>  * X-RateLimit-Limit - Request limit for the rate-limit window that was exceeded. <br>  * X-RateLimit-Remaining - Remaining requests in the rate-limit window that was exceeded. <br>  * X-RateLimit-Reset - Seconds until the rate-limit window resets. <br>  |
| **422** | Request validation failed. The detail list contains field-specific validation errors. |  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

