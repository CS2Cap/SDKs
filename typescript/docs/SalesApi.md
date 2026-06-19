# SalesApi

All URIs are relative to *https://api.cs2c.app*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**listRecentSales**](SalesApi.md#listrecentsales) | **GET** /v1/sales | List Recent Sales |



## listRecentSales

> SalesHistoryResponse listRecentSales(itemId, marketHashName, phase, providers, currency, limit, cursor)

List Recent Sales

Return recent sales across providers with recent-sales support, newest first.  With no filters, returns the global recent-sales feed ordered by sale time (most recent first). Optional filters narrow the results: - &#x60;item_id&#x60; — restrict to one catalog item (its canonical market_hash_name and phase are used) - &#x60;market_hash_name&#x60; (+ optional &#x60;phase&#x60;) — restrict to one item by name - &#x60;providers&#x60; — restrict to specific sales-capable provider keys - &#x60;currency&#x60; — convert values to the target currency  Pagination: - &#x60;limit&#x60; sets the page size (max 100 for Pro, 1000 for Quant) - pass &#x60;cursor&#x60; from the previous response\&#39;s &#x60;pagination.next_cursor&#x60; to page through results; &#x60;pagination.total&#x60; is &#x60;-1&#x60; (count intentionally skipped)  Behavior: - recent-sales data refreshes roughly once every 24 hours, so results may be up to a day old  Response: - request metadata, providers queried, and a cursor pagination footer - sales records with sticker, charm, and inspect metadata when available

### Example

```ts
import {
  Configuration,
  SalesApi,
} from 'cs2cap';
import type { ListRecentSalesRequest } from 'cs2cap';

async function example() {
  console.log("🚀 Testing cs2cap SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SalesApi(config);

  const body = {
    // number | Filter by item ID. When provided, canonical market_hash_name and phase from catalog are used and take precedence over request market_hash_name/phase. (optional)
    itemId: 56,
    // string | Optional market_hash_name to filter for specific item. Ignored when item_id is provided. (optional)
    marketHashName: marketHashName_example,
    // PhaseName | Optional phase to filter (global or combined with market_hash_name). Ignored when item_id is provided. (optional)
    phase: ...,
    // Array<RecentSalesProvider> | Providers to include (provider-key enum values that support recent sales). Repeat `providers` to pass multiple values. (optional)
    providers: ...,
    // string | Target currency. Any ISO 4217 code supported by `/v1/fx` (see `/v1/fx` for the full list). Invalid codes return a 422 validation error. (optional)
    currency: currency_example,
    // number | Maximum number of results to return. Defaults to the effective tier cap. (optional)
    limit: 56,
    // string | Cursor for keyset pagination. Use next_cursor from previous response. When provided, offset is ignored and keyset pagination is used for O(1) seek. (optional)
    cursor: cursor_example,
  } satisfies ListRecentSalesRequest;

  try {
    const data = await api.listRecentSales(body);
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
| **providers** | `Array<RecentSalesProvider>` | Providers to include (provider-key enum values that support recent sales). Repeat &#x60;providers&#x60; to pass multiple values. | [Optional] |
| **currency** | `string` | Target currency. Any ISO 4217 code supported by &#x60;/v1/fx&#x60; (see &#x60;/v1/fx&#x60; for the full list). Invalid codes return a 422 validation error. | [Optional] [Defaults to `&#39;USD&#39;`] |
| **limit** | `number` | Maximum number of results to return. Defaults to the effective tier cap. | [Optional] [Defaults to `undefined`] |
| **cursor** | `string` | Cursor for keyset pagination. Use next_cursor from previous response. When provided, offset is ignored and keyset pagination is used for O(1) seek. | [Optional] [Defaults to `undefined`] |

### Return type

[**SalesHistoryResponse**](SalesHistoryResponse.md)

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
| **400** | Invalid cursor or unsupported provider selection. |  -  |
| **404** | The requested item could not be resolved. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

