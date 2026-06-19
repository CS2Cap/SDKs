# MarketIntelligenceApi

All URIs are relative to *https://api.cs2c.app*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**getArbitrageOpportunities**](MarketIntelligenceApi.md#getarbitrageopportunities) | **GET** /v1/market/arbitrage | Get Arbitrage Opportunities |
| [**getDeepPriceHistoryChart**](MarketIntelligenceApi.md#getdeeppricehistorychart) | **GET** /v1/market/history/chart | Get Deep Price History Chart |
| [**getIndicators**](MarketIntelligenceApi.md#getindicators) | **GET** /v1/market/indicators | Get Indicators |
| [**getItemAnalytics**](MarketIntelligenceApi.md#getitemanalytics) | **GET** /v1/market/items/{item_id} | Get Item Analytics |
| [**getMarketAnalyticsSnapshot**](MarketIntelligenceApi.md#getmarketanalyticssnapshot) | **GET** /v1/market/items | Get Market Analytics Snapshot |
| [**getMarketCapIndexes**](MarketIntelligenceApi.md#getmarketcapindexes) | **GET** /v1/market/indexes | Get Market Cap Indexes |



## getArbitrageOpportunities

> MarketArbitrageResponse getArbitrageOpportunities(limit, offset, minSpreadPct, providersBuy, providersSell)

Get Arbitrage Opportunities

Scan providers for cross-market arbitrage opportunities.  Filters: - &#x60;min_spread_pct&#x60; - &#x60;providers_buy&#x60; and &#x60;providers_sell&#x60; (sell-side limited to buy-order providers) - offset pagination via &#x60;offset&#x60;  Response: - opportunities ranked by estimated net profit in USD with buy-side and sell-side provider context - pagination total reflects the capped set of ranked opportunities, not a count of all possible matches  Tier: Quant-only.

### Example

```ts
import {
  Configuration,
  MarketIntelligenceApi,
} from 'cs2cap';
import type { GetArbitrageOpportunitiesRequest } from 'cs2cap';

async function example() {
  console.log("🚀 Testing cs2cap SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MarketIntelligenceApi(config);

  const body = {
    // number | Maximum number of results to return. Defaults to the effective tier cap. (optional)
    limit: 56,
    // number | Requested offset into the ranked opportunity list. (optional)
    offset: 56,
    // number | Minimum gross spread percentage between buy and sell prices. (optional)
    minSpreadPct: 8.14,
    // Array<AllProviders> | Buy-side provider key enum filters (plural parameter). Repeat `providers_buy` to pass multiple values. (optional)
    providersBuy: ...,
    // Array<BuyOrderProvider> | Sell-side provider key enum filters for providers with buy orders (plural parameter). Repeat `providers_sell` to pass multiple values. (optional)
    providersSell: ...,
  } satisfies GetArbitrageOpportunitiesRequest;

  try {
    const data = await api.getArbitrageOpportunities(body);
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
| **limit** | `number` | Maximum number of results to return. Defaults to the effective tier cap. | [Optional] [Defaults to `undefined`] |
| **offset** | `number` | Requested offset into the ranked opportunity list. | [Optional] [Defaults to `0`] |
| **minSpreadPct** | `number` | Minimum gross spread percentage between buy and sell prices. | [Optional] [Defaults to `1.0`] |
| **providersBuy** | `Array<AllProviders>` | Buy-side provider key enum filters (plural parameter). Repeat &#x60;providers_buy&#x60; to pass multiple values. | [Optional] |
| **providersSell** | `Array<BuyOrderProvider>` | Sell-side provider key enum filters for providers with buy orders (plural parameter). Repeat &#x60;providers_sell&#x60; to pass multiple values. | [Optional] |

### Return type

[**MarketArbitrageResponse**](MarketArbitrageResponse.md)

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
| **403** | Analytics tier required to access this endpoint. |  -  |
| **429** | Rate limit exceeded (burst or monthly quota). |  * Retry-After - Seconds to wait before retrying when present. <br>  * X-RateLimit-Tier - Authenticated caller tier code. <br>  * X-RateLimit-Limit - Request limit for the rate-limit window that was exceeded. <br>  * X-RateLimit-Remaining - Remaining requests in the rate-limit window that was exceeded. <br>  * X-RateLimit-Reset - Seconds until the rate-limit window resets. <br>  |
| **422** | Request validation failed. The detail list contains field-specific validation errors. |  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  |
| **400** | Invalid cursor or unsupported cursor parameter. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getDeepPriceHistoryChart

> MarketHistoryChartResponse getDeepPriceHistoryChart(itemId, marketHashName, providers, start, end, lookback, currency, includeDefunct)

Get Deep Price History Chart

Per-provider daily price history.  Returns one price point per provider per UTC day, spanning years of history up to the present. Prices are in minor units of the response currency; &#x60;&#x60;qty&#x60;&#x60; is nullable.  Providers that have shut down are excluded by default; pass &#x60;&#x60;include_defunct&#x3D;true&#x60;&#x60; to include their historical series.  **Tier**: Quant-only.

### Example

```ts
import {
  Configuration,
  MarketIntelligenceApi,
} from 'cs2cap';
import type { GetDeepPriceHistoryChartRequest } from 'cs2cap';

async function example() {
  console.log("🚀 Testing cs2cap SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MarketIntelligenceApi(config);

  const body = {
    // number | Normalized catalog item ID (or use market_hash_name). (optional)
    itemId: 56,
    // string | Market hash name (alternative to item_id). (optional)
    marketHashName: marketHashName_example,
    // Array<string> | Provider key(s). Repeatable. Omit for all providers with data. (optional)
    providers: ...,
    // Date | ISO 8601 UTC start of the window. (optional)
    start: 2013-10-20T19:20:30+01:00,
    // Date | ISO 8601 UTC end of the window. (optional)
    end: 2013-10-20T19:20:30+01:00,
    // number | Window length in days; overrides start. (optional)
    lookback: 56,
    // string | Target currency for returned prices. Default: USD. (optional)
    currency: currency_example,
    // boolean | Include providers that have shut down but still have historical data (e.g. GamerPay, BitSkins). Defaults to false. (optional)
    includeDefunct: true,
  } satisfies GetDeepPriceHistoryChartRequest;

  try {
    const data = await api.getDeepPriceHistoryChart(body);
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
| **itemId** | `number` | Normalized catalog item ID (or use market_hash_name). | [Optional] [Defaults to `undefined`] |
| **marketHashName** | `string` | Market hash name (alternative to item_id). | [Optional] [Defaults to `undefined`] |
| **providers** | `Array<string>` | Provider key(s). Repeatable. Omit for all providers with data. | [Optional] |
| **start** | `Date` | ISO 8601 UTC start of the window. | [Optional] [Defaults to `undefined`] |
| **end** | `Date` | ISO 8601 UTC end of the window. | [Optional] [Defaults to `undefined`] |
| **lookback** | `number` | Window length in days; overrides start. | [Optional] [Defaults to `undefined`] |
| **currency** | `string` | Target currency for returned prices. Default: USD. | [Optional] [Defaults to `&#39;USD&#39;`] |
| **includeDefunct** | `boolean` | Include providers that have shut down but still have historical data (e.g. GamerPay, BitSkins). Defaults to false. | [Optional] [Defaults to `false`] |

### Return type

[**MarketHistoryChartResponse**](MarketHistoryChartResponse.md)

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
| **403** | Analytics tier required to access this endpoint. |  -  |
| **429** | Rate limit exceeded (burst or monthly quota). |  * Retry-After - Seconds to wait before retrying when present. <br>  * X-RateLimit-Tier - Authenticated caller tier code. <br>  * X-RateLimit-Limit - Request limit for the rate-limit window that was exceeded. <br>  * X-RateLimit-Remaining - Remaining requests in the rate-limit window that was exceeded. <br>  * X-RateLimit-Reset - Seconds until the rate-limit window resets. <br>  |
| **422** | Request validation failed. The detail list contains field-specific validation errors. |  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  |
| **400** | Invalid parameters |  -  |
| **404** | Item not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getIndicators

> MarketIndicatorsItemResponse getIndicators(itemId, marketHashName, phase, interval, currency)

Get Indicators

Compute technical analysis indicators for one item from OHLCV candle data.  **Indicators:**  - **Momentum**: RSI(14), MACD(12/26/9), SMA(20/50/200), EMA(12/26), Bollinger Bands(20,2σ) - **Volatility**: ATR(14), Historical Volatility(20), Keltner Channels(20/10/2) - **Volume**: VWAP, OBV, Volume SMA(20)  **Tier**: Quant-only.

### Example

```ts
import {
  Configuration,
  MarketIntelligenceApi,
} from 'cs2cap';
import type { GetIndicatorsRequest } from 'cs2cap';

async function example() {
  console.log("🚀 Testing cs2cap SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MarketIntelligenceApi(config);

  const body = {
    // number | Item ID for live indicator computation. (optional)
    itemId: 56,
    // string | Market hash name (alternative to item_id). (optional)
    marketHashName: marketHashName_example,
    // string | Doppler phase filter. (optional)
    phase: phase_example,
    // '1h' | '1d' | Candle interval for indicator computation. (optional)
    interval: interval_example,
    // string | Target currency for price-level indicators (e.g. ``USD``, ``EUR``). Provider-native prices are converted via FX rates. Default: ``USD``. (optional)
    currency: currency_example,
  } satisfies GetIndicatorsRequest;

  try {
    const data = await api.getIndicators(body);
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
| **itemId** | `number` | Item ID for live indicator computation. | [Optional] [Defaults to `undefined`] |
| **marketHashName** | `string` | Market hash name (alternative to item_id). | [Optional] [Defaults to `undefined`] |
| **phase** | `string` | Doppler phase filter. | [Optional] [Defaults to `undefined`] |
| **interval** | `1h`, `1d` | Candle interval for indicator computation. | [Optional] [Defaults to `&#39;1d&#39;`] [Enum: 1h, 1d] |
| **currency** | `string` | Target currency for price-level indicators (e.g. &#x60;&#x60;USD&#x60;&#x60;, &#x60;&#x60;EUR&#x60;&#x60;). Provider-native prices are converted via FX rates. Default: &#x60;&#x60;USD&#x60;&#x60;. | [Optional] [Defaults to `&#39;USD&#39;`] |

### Return type

[**MarketIndicatorsItemResponse**](MarketIndicatorsItemResponse.md)

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
| **403** | Analytics tier required to access this endpoint. |  -  |
| **429** | Rate limit exceeded (burst or monthly quota). |  * Retry-After - Seconds to wait before retrying when present. <br>  * X-RateLimit-Tier - Authenticated caller tier code. <br>  * X-RateLimit-Limit - Request limit for the rate-limit window that was exceeded. <br>  * X-RateLimit-Remaining - Remaining requests in the rate-limit window that was exceeded. <br>  * X-RateLimit-Reset - Seconds until the rate-limit window resets. <br>  |
| **422** | Insufficient candle data for indicator computation |  -  |
| **400** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getItemAnalytics

> MarketItemAnalyticsResponse getItemAnalytics(itemId)

Get Item Analytics

Return per-item market analytics across providers.  Includes: - best ask, best bid, and spread summary - item-level liquidity summary and provider-level price/depth/volume metrics - coverage diagnostics showing which providers contributed data  Liquidity is always scored against the 24h horizon. Provider volume fields are trailing 24h and 7d totals.  Tier: Pro and Quant.

### Example

```ts
import {
  Configuration,
  MarketIntelligenceApi,
} from 'cs2cap';
import type { GetItemAnalyticsRequest } from 'cs2cap';

async function example() {
  console.log("🚀 Testing cs2cap SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MarketIntelligenceApi(config);

  const body = {
    // number | Item ID.
    itemId: 56,
  } satisfies GetItemAnalyticsRequest;

  try {
    const data = await api.getItemAnalytics(body);
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
| **itemId** | `number` | Item ID. | [Defaults to `undefined`] |

### Return type

[**MarketItemAnalyticsResponse**](MarketItemAnalyticsResponse.md)

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
| **403** | Analytics tier required to access this endpoint. |  -  |
| **429** | Rate limit exceeded (burst or monthly quota). |  * Retry-After - Seconds to wait before retrying when present. <br>  * X-RateLimit-Tier - Authenticated caller tier code. <br>  * X-RateLimit-Limit - Request limit for the rate-limit window that was exceeded. <br>  * X-RateLimit-Remaining - Remaining requests in the rate-limit window that was exceeded. <br>  * X-RateLimit-Reset - Seconds until the rate-limit window resets. <br>  |
| **422** | Request validation failed. The detail list contains field-specific validation errors. |  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  |
| **404** | No analytics data exists for the provided item_id. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getMarketAnalyticsSnapshot

> MarketItemsSnapshotResponse getMarketAnalyticsSnapshot()

Get Market Analytics Snapshot

Return the full market as a summary-only snapshot.  Includes: - one row per catalog item with the same summary fields exposed by the detail route - no pagination and no provider-level payloads - rank-ordered output using &#x60;rank asc, item_id asc&#x60;  Liquidity reflects the 24h horizon; trade windows are 24h, 7d, and 30d.  Tier: Pro and Quant.

### Example

```ts
import {
  Configuration,
  MarketIntelligenceApi,
} from 'cs2cap';
import type { GetMarketAnalyticsSnapshotRequest } from 'cs2cap';

async function example() {
  console.log("🚀 Testing cs2cap SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MarketIntelligenceApi(config);

  try {
    const data = await api.getMarketAnalyticsSnapshot();
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

[**MarketItemsSnapshotResponse**](MarketItemsSnapshotResponse.md)

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
| **403** | Analytics tier required to access this endpoint. |  -  |
| **429** | Rate limit exceeded (burst or monthly quota). |  * Retry-After - Seconds to wait before retrying when present. <br>  * X-RateLimit-Tier - Authenticated caller tier code. <br>  * X-RateLimit-Limit - Request limit for the rate-limit window that was exceeded. <br>  * X-RateLimit-Remaining - Remaining requests in the rate-limit window that was exceeded. <br>  * X-RateLimit-Reset - Seconds until the rate-limit window resets. <br>  |
| **422** | Request validation failed. The detail list contains field-specific validation errors. |  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  |
| **503** | Market data is temporarily unavailable; retry shortly. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getMarketCapIndexes

> MarketIndexesResponse getMarketCapIndexes(groupBy)

Get Market Cap Indexes

Aggregate the 24h market into category-level indexes.  Supports grouping by &#x60;item_type&#x60; or &#x60;weapon_type&#x60;. Items are excluded from market cap totals when bid/ask/marketcap data is incomplete or spread exceeds the minimum threshold.  Response: - no pagination - groups sorted by &#x60;marketcap_usd desc&#x60; - totals computed from the same filtered item set  Tier: Quant-only.

### Example

```ts
import {
  Configuration,
  MarketIntelligenceApi,
} from 'cs2cap';
import type { GetMarketCapIndexesRequest } from 'cs2cap';

async function example() {
  console.log("🚀 Testing cs2cap SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MarketIntelligenceApi(config);

  const body = {
    // 'item_type' | 'weapon_type' | Catalog dimension used to group snapshot items. (optional)
    groupBy: groupBy_example,
  } satisfies GetMarketCapIndexesRequest;

  try {
    const data = await api.getMarketCapIndexes(body);
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
| **groupBy** | `item_type`, `weapon_type` | Catalog dimension used to group snapshot items. | [Optional] [Defaults to `&#39;item_type&#39;`] [Enum: item_type, weapon_type] |

### Return type

[**MarketIndexesResponse**](MarketIndexesResponse.md)

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
| **403** | Analytics tier required to access this endpoint. |  -  |
| **429** | Rate limit exceeded (burst or monthly quota). |  * Retry-After - Seconds to wait before retrying when present. <br>  * X-RateLimit-Tier - Authenticated caller tier code. <br>  * X-RateLimit-Limit - Request limit for the rate-limit window that was exceeded. <br>  * X-RateLimit-Remaining - Remaining requests in the rate-limit window that was exceeded. <br>  * X-RateLimit-Reset - Seconds until the rate-limit window resets. <br>  |
| **422** | Request validation failed. The detail list contains field-specific validation errors. |  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  |
| **503** | Market data is temporarily unavailable; retry shortly. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

