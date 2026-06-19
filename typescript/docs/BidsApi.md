# BidsApi

All URIs are relative to *https://api.cs2c.app*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**batchBidLookup**](BidsApi.md#batchbidlookup) | **POST** /v1/bids/batch | Batch Bid Lookup |
| [**listBids**](BidsApi.md#listbids) | **GET** /v1/bids | List Bids |
| [**streamFullBidsSnapshot**](BidsApi.md#streamfullbidssnapshot) | **POST** /v1/bids | Stream Full Bids Snapshot |



## batchBidLookup

> BatchBidsResponse batchBidLookup(batchBidsRequest)

Batch Bid Lookup

Retrieve current bids (buy orders) for multiple items in a single request.  Maximum 100 items per request. Returns per-item bid quotes from each queried provider.  Prices are in minor units of the requested currency (e.g. USD cents when &#x60;currency&#x3D;USD&#x60;). Divide by 100 for display.

### Example

```ts
import {
  Configuration,
  BidsApi,
} from 'cs2cap';
import type { BatchBidLookupRequest } from 'cs2cap';

async function example() {
  console.log("🚀 Testing cs2cap SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new BidsApi(config);

  const body = {
    // BatchBidsRequest
    batchBidsRequest: ...,
  } satisfies BatchBidLookupRequest;

  try {
    const data = await api.batchBidLookup(body);
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

// Run the test
example().catch(console.error);
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **batchBidsRequest** | [BatchBidsRequest](BatchBidsRequest.md) |  | |

### Return type

[**BatchBidsResponse**](BatchBidsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Successful Response |  -  |
| **401** | Missing or invalid authentication credentials. |  -  |
| **403** | Authenticated but not permitted to access this resource. |  -  |
| **429** | Rate limit exceeded (burst or monthly quota). |  * Retry-After - Seconds to wait before retrying when present. <br>  * X-RateLimit-Tier - Authenticated caller tier code. <br>  * X-RateLimit-Limit - Request limit for the rate-limit window that was exceeded. <br>  * X-RateLimit-Remaining - Remaining requests in the rate-limit window that was exceeded. <br>  * X-RateLimit-Reset - Seconds until the rate-limit window resets. <br>  |
| **422** | Request validation failed. The detail list contains field-specific validation errors. |  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  |
| **400** | Batch size exceeded. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listBids

> BidsResponse listBids(itemId, marketHashName, phase, providers, currency, limit, offset)

List Bids

Return current highest bids from providers that support buy orders.  Filters: - &#x60;item_id&#x60; or &#x60;market_hash_name&#x60; - optional &#x60;phase&#x60; - &#x60;providers&#x60; limited to buy-order-capable provider keys - &#x60;currency&#x60;, &#x60;limit&#x60;, and &#x60;offset&#x60;  Behavior: - requesting a provider that does not support buy orders returns &#x60;400&#x60;  Response: - &#x60;meta&#x60; with filters and providers queried - flattened per-provider bid rows - offset pagination metadata

### Example

```ts
import {
  Configuration,
  BidsApi,
} from 'cs2cap';
import type { ListBidsRequest } from 'cs2cap';

async function example() {
  console.log("🚀 Testing cs2cap SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new BidsApi(config);

  const body = {
    // number | Filter by item ID. When provided, canonical market_hash_name and phase from catalog are used and take precedence over request market_hash_name/phase. (optional)
    itemId: 56,
    // string | Optional market_hash_name to filter for specific item. Ignored when item_id is provided. (optional)
    marketHashName: marketHashName_example,
    // PhaseName | Optional phase to filter (global or combined with market_hash_name). Ignored when item_id is provided. (optional)
    phase: ...,
    // Array<BuyOrderProvider> | Providers to include (provider-key enum values that support buy orders). Repeat `providers` to pass multiple values. (optional)
    providers: ...,
    // string | Target currency. Any ISO 4217 code supported by `/v1/fx` (see `/v1/fx` for the full list). Invalid codes return a 422 validation error. (optional)
    currency: currency_example,
    // number | Maximum number of results to return. (optional)
    limit: 56,
    // number | Number of results to skip for pagination. (optional)
    offset: 56,
  } satisfies ListBidsRequest;

  try {
    const data = await api.listBids(body);
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

// Run the test
example().catch(console.error);
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **itemId** | `number` | Filter by item ID. When provided, canonical market_hash_name and phase from catalog are used and take precedence over request market_hash_name/phase. | [Optional] [Defaults to `undefined`] |
| **marketHashName** | `string` | Optional market_hash_name to filter for specific item. Ignored when item_id is provided. | [Optional] [Defaults to `undefined`] |
| **phase** | `PhaseName` | Optional phase to filter (global or combined with market_hash_name). Ignored when item_id is provided. | [Optional] [Defaults to `undefined`] [Enum: Phase 1, Phase 2, Phase 3, Phase 4, Sapphire, Ruby, Black Pearl, Emerald] |
| **providers** | `Array<BuyOrderProvider>` | Providers to include (provider-key enum values that support buy orders). Repeat &#x60;providers&#x60; to pass multiple values. | [Optional] |
| **currency** | `string` | Target currency. Any ISO 4217 code supported by &#x60;/v1/fx&#x60; (see &#x60;/v1/fx&#x60; for the full list). Invalid codes return a 422 validation error. | [Optional] [Defaults to `&#39;USD&#39;`] |
| **limit** | `number` | Maximum number of results to return. | [Optional] [Defaults to `1000`] |
| **offset** | `number` | Number of results to skip for pagination. | [Optional] [Defaults to `0`] |

### Return type

[**BidsResponse**](BidsResponse.md)

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
| **400** | Providers were specified that do not support buy orders. |  -  |
| **503** | Bid data is temporarily unavailable; retry shortly. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## streamFullBidsSnapshot

> string streamFullBidsSnapshot(providers)

Stream Full Bids Snapshot

Return the full live bids snapshot as an NDJSON stream.  Behavior: - pro and quant tiers only - requires an API key (not a session token) - optional &#x60;providers&#x60; filter; omit to stream all providers - fixed USD output - &#x60;highest_bid&#x60; values are returned in USD minor units - one JSON object per line using the &#x60;BuyOrderItem&#x60; field set - per-API-key rolling 24h quota of successful stream starts (pro: 50, quant: 300, per endpoint) - max 1 concurrent stream per API key for this endpoint (409 otherwise)

### Example

```ts
import {
  Configuration,
  BidsApi,
} from 'cs2cap';
import type { StreamFullBidsSnapshotRequest } from 'cs2cap';

async function example() {
  console.log("🚀 Testing cs2cap SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new BidsApi(config);

  const body = {
    // Array<BuyOrderProvider> (optional)
    providers: ...,
  } satisfies StreamFullBidsSnapshotRequest;

  try {
    const data = await api.streamFullBidsSnapshot(body);
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

// Run the test
example().catch(console.error);
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **providers** | `Array<BuyOrderProvider>` |  | [Optional] |

### Return type

**string**

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/x-ndjson`, `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | NDJSON stream of the full live bids snapshot in USD. |  * X-Snapshot-Timestamp - UTC timestamp when the snapshot stream started. <br>  * X-Snapshot-Currency - Fixed response currency for every streamed row. <br>  * X-Snapshot-Total - Total rows in the stream at start, when known. <br>  * X-RateLimit-Limit - Daily quota of successful stream starts for this endpoint. <br>  * X-RateLimit-Remaining - Remaining stream starts in the rolling 24h window. <br>  * X-RateLimit-Reset - Seconds until the oldest counted start leaves the window. <br>  |
| **401** | Missing or invalid authentication credentials. |  -  |
| **403** | Bulk snapshot access requires a tier with bulk snapshot capability. |  -  |
| **429** | Daily bulk stream quota exhausted for this API key. |  * Retry-After - Seconds until this API key may start another bids stream. <br>  * X-RateLimit-Limit - Daily quota of successful stream starts for this endpoint. <br>  * X-RateLimit-Remaining - Remaining stream starts in the rolling 24h window. <br>  * X-RateLimit-Reset - Seconds until the oldest counted start leaves the window. <br>  |
| **422** | Request validation failed. The detail list contains field-specific validation errors. |  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  |
| **503** | Bid data is temporarily unavailable; retry shortly. |  -  |
| **409** | A streaming request is already active for this API key. |  * Retry-After - Suggested seconds to wait before retrying. <br>  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

