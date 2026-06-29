# PortfolioApi

All URIs are relative to *https://api.cs2c.app*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**addItemToPortfolio**](PortfolioApi.md#additemtoportfolio) | **POST** /v1/portfolio/{portfolio_id}/items | Add Item to Portfolio |
| [**addTransaction**](PortfolioApi.md#addtransaction) | **POST** /v1/portfolio/{portfolio_id}/transactions | Add Transaction |
| [**createPortfolio**](PortfolioApi.md#createportfolio) | **POST** /v1/portfolio | Create Portfolio |
| [**deletePortfolio**](PortfolioApi.md#deleteportfolio) | **DELETE** /v1/portfolio/{portfolio_id} | Delete Portfolio |
| [**deleteTransaction**](PortfolioApi.md#deletetransaction) | **DELETE** /v1/portfolio/{portfolio_id}/transactions/{transaction_id} | Delete Transaction |
| [**historicalSavedPortfolioValuation**](PortfolioApi.md#historicalsavedportfoliovaluation) | **GET** /v1/portfolio/{portfolio_id}/history | Historical Saved Portfolio Valuation |
| [**importSteamInventory**](PortfolioApi.md#importsteaminventory) | **POST** /v1/portfolio/{portfolio_id}/import | Import Steam Inventory |
| [**listPortfolioItems**](PortfolioApi.md#listportfolioitems) | **GET** /v1/portfolio/{portfolio_id}/items | List Portfolio Items |
| [**listPortfolios**](PortfolioApi.md#listportfolios) | **GET** /v1/portfolio | List Portfolios |
| [**listTransactions**](PortfolioApi.md#listtransactions) | **GET** /v1/portfolio/{portfolio_id}/transactions | List Transactions |
| [**portfolioValuation**](PortfolioApi.md#portfoliovaluation) | **POST** /v1/portfolio/value | Portfolio Valuation |
| [**removeItemFromPortfolio**](PortfolioApi.md#removeitemfromportfolio) | **DELETE** /v1/portfolio/{portfolio_id}/items/{entry_id} | Remove Item from Portfolio |
| [**updateTransaction**](PortfolioApi.md#updatetransaction) | **PATCH** /v1/portfolio/{portfolio_id}/transactions/{transaction_id} | Update Transaction |
| [**valueSavedPortfolio**](PortfolioApi.md#valuesavedportfolio) | **GET** /v1/portfolio/{portfolio_id}/value | Value Saved Portfolio |



## addItemToPortfolio

> PortfolioItemOut addItemToPortfolio(portfolioId, portfolioAddItemRequest)

Add Item to Portfolio

Add a single item to a portfolio by &#x60;item_id&#x60; or &#x60;market_hash_name&#x60;. Use this for manual entry without a Steam inventory import.

### Example

```ts
import {
  Configuration,
  PortfolioApi,
} from 'cs2cap';
import type { AddItemToPortfolioRequest } from 'cs2cap';

async function example() {
  console.log("🚀 Testing cs2cap SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PortfolioApi(config);

  const body = {
    // string
    portfolioId: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
    // PortfolioAddItemRequest
    portfolioAddItemRequest: ...,
  } satisfies AddItemToPortfolioRequest;

  try {
    const data = await api.addItemToPortfolio(body);
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
| **portfolioId** | `string` |  | [Defaults to `undefined`] |
| **portfolioAddItemRequest** | [PortfolioAddItemRequest](PortfolioAddItemRequest.md) |  | |

### Return type

[**PortfolioItemOut**](PortfolioItemOut.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Successful Response |  -  |
| **401** | Missing or invalid authentication credentials. |  -  |
| **403** | Authenticated but not permitted to access this resource. |  -  |
| **429** | Rate limit exceeded (burst or monthly quota). |  * Retry-After - Seconds to wait before retrying when present. <br>  * X-RateLimit-Tier - Authenticated caller tier code. <br>  * X-RateLimit-Limit - Request limit for the rate-limit window that was exceeded. <br>  * X-RateLimit-Remaining - Remaining requests in the rate-limit window that was exceeded. <br>  * X-RateLimit-Reset - Seconds until the rate-limit window resets. <br>  |
| **422** | Request validation failed. The detail list contains field-specific validation errors. |  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  |
| **400** | Missing item identifier. |  -  |
| **404** | Portfolio or item not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## addTransaction

> TransactionOut addTransaction(portfolioId, transactionCreateRequest)

Add Transaction

Record a buy or sell transaction for an item in this portfolio.

### Example

```ts
import {
  Configuration,
  PortfolioApi,
} from 'cs2cap';
import type { AddTransactionRequest } from 'cs2cap';

async function example() {
  console.log("🚀 Testing cs2cap SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PortfolioApi(config);

  const body = {
    // string
    portfolioId: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
    // TransactionCreateRequest
    transactionCreateRequest: ...,
  } satisfies AddTransactionRequest;

  try {
    const data = await api.addTransaction(body);
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
| **portfolioId** | `string` |  | [Defaults to `undefined`] |
| **transactionCreateRequest** | [TransactionCreateRequest](TransactionCreateRequest.md) |  | |

### Return type

[**TransactionOut**](TransactionOut.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Successful Response |  -  |
| **401** | Missing or invalid authentication credentials. |  -  |
| **403** | Authenticated but not permitted to access this resource. |  -  |
| **429** | Rate limit exceeded (burst or monthly quota). |  * Retry-After - Seconds to wait before retrying when present. <br>  * X-RateLimit-Tier - Authenticated caller tier code. <br>  * X-RateLimit-Limit - Request limit for the rate-limit window that was exceeded. <br>  * X-RateLimit-Remaining - Remaining requests in the rate-limit window that was exceeded. <br>  * X-RateLimit-Reset - Seconds until the rate-limit window resets. <br>  |
| **422** | Request validation failed. The detail list contains field-specific validation errors. |  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  |
| **400** | Missing item identifier. |  -  |
| **404** | Portfolio or item not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## createPortfolio

> PortfolioOut createPortfolio(portfolioCreate)

Create Portfolio

Create a new named portfolio. The maximum number of portfolios depends on your tier. Portfolios store items persistently and can be valued at any time.

### Example

```ts
import {
  Configuration,
  PortfolioApi,
} from 'cs2cap';
import type { CreatePortfolioRequest } from 'cs2cap';

async function example() {
  console.log("🚀 Testing cs2cap SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PortfolioApi(config);

  const body = {
    // PortfolioCreate
    portfolioCreate: ...,
  } satisfies CreatePortfolioRequest;

  try {
    const data = await api.createPortfolio(body);
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
| **portfolioCreate** | [PortfolioCreate](PortfolioCreate.md) |  | |

### Return type

[**PortfolioOut**](PortfolioOut.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Successful Response |  -  |
| **401** | Missing or invalid authentication credentials. |  -  |
| **403** | Access denied. |  -  |
| **429** | Rate limit exceeded (burst or monthly quota). |  * Retry-After - Seconds to wait before retrying when present. <br>  * X-RateLimit-Tier - Authenticated caller tier code. <br>  * X-RateLimit-Limit - Request limit for the rate-limit window that was exceeded. <br>  * X-RateLimit-Remaining - Remaining requests in the rate-limit window that was exceeded. <br>  * X-RateLimit-Reset - Seconds until the rate-limit window resets. <br>  |
| **422** | Request validation failed. The detail list contains field-specific validation errors. |  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  |
| **400** | Portfolio limit reached. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deletePortfolio

> deletePortfolio(portfolioId)

Delete Portfolio

Delete a portfolio and all its items.

### Example

```ts
import {
  Configuration,
  PortfolioApi,
} from 'cs2cap';
import type { DeletePortfolioRequest } from 'cs2cap';

async function example() {
  console.log("🚀 Testing cs2cap SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PortfolioApi(config);

  const body = {
    // string
    portfolioId: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
  } satisfies DeletePortfolioRequest;

  try {
    const data = await api.deletePortfolio(body);
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
| **portfolioId** | `string` |  | [Defaults to `undefined`] |

### Return type

`void` (Empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | Successful Response |  -  |
| **401** | Missing or invalid authentication credentials. |  -  |
| **403** | Authenticated but not permitted to access this resource. |  -  |
| **429** | Rate limit exceeded (burst or monthly quota). |  * Retry-After - Seconds to wait before retrying when present. <br>  * X-RateLimit-Tier - Authenticated caller tier code. <br>  * X-RateLimit-Limit - Request limit for the rate-limit window that was exceeded. <br>  * X-RateLimit-Remaining - Remaining requests in the rate-limit window that was exceeded. <br>  * X-RateLimit-Reset - Seconds until the rate-limit window resets. <br>  |
| **422** | Request validation failed. The detail list contains field-specific validation errors. |  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  |
| **404** | Portfolio not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteTransaction

> deleteTransaction(portfolioId, transactionId)

Delete Transaction

Delete a transaction from a portfolio.

### Example

```ts
import {
  Configuration,
  PortfolioApi,
} from 'cs2cap';
import type { DeleteTransactionRequest } from 'cs2cap';

async function example() {
  console.log("🚀 Testing cs2cap SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PortfolioApi(config);

  const body = {
    // string
    portfolioId: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
    // string
    transactionId: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
  } satisfies DeleteTransactionRequest;

  try {
    const data = await api.deleteTransaction(body);
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
| **portfolioId** | `string` |  | [Defaults to `undefined`] |
| **transactionId** | `string` |  | [Defaults to `undefined`] |

### Return type

`void` (Empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | Successful Response |  -  |
| **401** | Missing or invalid authentication credentials. |  -  |
| **403** | Authenticated but not permitted to access this resource. |  -  |
| **429** | Rate limit exceeded (burst or monthly quota). |  * Retry-After - Seconds to wait before retrying when present. <br>  * X-RateLimit-Tier - Authenticated caller tier code. <br>  * X-RateLimit-Limit - Request limit for the rate-limit window that was exceeded. <br>  * X-RateLimit-Remaining - Remaining requests in the rate-limit window that was exceeded. <br>  * X-RateLimit-Reset - Seconds until the rate-limit window resets. <br>  |
| **422** | Request validation failed. The detail list contains field-specific validation errors. |  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  |
| **404** | Portfolio or transaction not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## historicalSavedPortfolioValuation

> PortfolioHistoryPage historicalSavedPortfolioValuation(portfolioId, startDate, endDate, lookback, currency, providers, limit, cursor, basis)

Historical Saved Portfolio Valuation

Replay saved-portfolio holdings from the transaction ledger and return daily historical valuation points priced from stored daily market closes. This endpoint is daily-only because portfolio transactions are date-granular.

### Example

```ts
import {
  Configuration,
  PortfolioApi,
} from 'cs2cap';
import type { HistoricalSavedPortfolioValuationRequest } from 'cs2cap';

async function example() {
  console.log("🚀 Testing cs2cap SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PortfolioApi(config);

  const body = {
    // string
    portfolioId: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
    // Date | Inclusive UTC start date (YYYY-MM-DD). (optional)
    startDate: 2013-10-20,
    // Date | Inclusive UTC end date (YYYY-MM-DD). Defaults to today. (optional)
    endDate: 2013-10-20,
    // string | Optional lookback in days, e.g. `30d`. Overrides start_date. (optional)
    lookback: lookback_example,
    // string | Target currency code. (optional)
    currency: currency_example,
    // Array<string> | Provider keys to include. Repeat to pass multiple, e.g. providers=steam&providers=skinport. Omit for all providers. (optional)
    providers: ...,
    // number | Maximum number of daily points to return. (optional)
    limit: 56,
    // string | Opaque cursor from `pagination.next_cursor`. (optional)
    cursor: cursor_example,
    // 'ledger' | 'holdings' | Holdings basis. `ledger` (default) replays holdings from the transaction ledger and requires recorded transactions. `holdings` values the portfolio\'s current holdings flat across the window, so history is available without any transactions. (optional)
    basis: basis_example,
  } satisfies HistoricalSavedPortfolioValuationRequest;

  try {
    const data = await api.historicalSavedPortfolioValuation(body);
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
| **portfolioId** | `string` |  | [Defaults to `undefined`] |
| **startDate** | `Date` | Inclusive UTC start date (YYYY-MM-DD). | [Optional] [Defaults to `undefined`] |
| **endDate** | `Date` | Inclusive UTC end date (YYYY-MM-DD). Defaults to today. | [Optional] [Defaults to `undefined`] |
| **lookback** | `string` | Optional lookback in days, e.g. &#x60;30d&#x60;. Overrides start_date. | [Optional] [Defaults to `undefined`] |
| **currency** | `string` | Target currency code. | [Optional] [Defaults to `&#39;USD&#39;`] |
| **providers** | `Array<string>` | Provider keys to include. Repeat to pass multiple, e.g. providers&#x3D;steam&amp;providers&#x3D;skinport. Omit for all providers. | [Optional] |
| **limit** | `number` | Maximum number of daily points to return. | [Optional] [Defaults to `undefined`] |
| **cursor** | `string` | Opaque cursor from &#x60;pagination.next_cursor&#x60;. | [Optional] [Defaults to `undefined`] |
| **basis** | `ledger`, `holdings` | Holdings basis. &#x60;ledger&#x60; (default) replays holdings from the transaction ledger and requires recorded transactions. &#x60;holdings&#x60; values the portfolio\&#39;s current holdings flat across the window, so history is available without any transactions. | [Optional] [Defaults to `&#39;ledger&#39;`] [Enum: ledger, holdings] |

### Return type

[**PortfolioHistoryPage**](PortfolioHistoryPage.md)

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
| **400** | Invalid window, invalid cursor, or no ledger history available. |  -  |
| **404** | Portfolio not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## importSteamInventory

> PortfolioImportResult importSteamInventory(portfolioId, portfolioImportRequest)

Import Steam Inventory

Import items from the user\&#39;s Steam inventory into a portfolio. Optionally supply &#x60;asset_ids&#x60; to import only specific items. Items already present (by Steam asset ID) are skipped. Items not matched in the CS2C catalog are returned in &#x60;unresolved&#x60; and are not stored.

### Example

```ts
import {
  Configuration,
  PortfolioApi,
} from 'cs2cap';
import type { ImportSteamInventoryRequest } from 'cs2cap';

async function example() {
  console.log("🚀 Testing cs2cap SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PortfolioApi(config);

  const body = {
    // string
    portfolioId: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
    // PortfolioImportRequest
    portfolioImportRequest: ...,
  } satisfies ImportSteamInventoryRequest;

  try {
    const data = await api.importSteamInventory(body);
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
| **portfolioId** | `string` |  | [Defaults to `undefined`] |
| **portfolioImportRequest** | [PortfolioImportRequest](PortfolioImportRequest.md) |  | |

### Return type

[**PortfolioImportResult**](PortfolioImportResult.md)

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
| **403** | No linked Steam account. |  -  |
| **429** | Rate limit exceeded (burst or monthly quota). |  * Retry-After - Seconds to wait before retrying when present. <br>  * X-RateLimit-Tier - Authenticated caller tier code. <br>  * X-RateLimit-Limit - Request limit for the rate-limit window that was exceeded. <br>  * X-RateLimit-Remaining - Remaining requests in the rate-limit window that was exceeded. <br>  * X-RateLimit-Reset - Seconds until the rate-limit window resets. <br>  |
| **422** | Request validation failed. The detail list contains field-specific validation errors. |  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  |
| **404** | Portfolio not found. |  -  |
| **503** | Steam inventory unavailable. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listPortfolioItems

> Array&lt;PortfolioItemOut&gt; listPortfolioItems(portfolioId)

List Portfolio Items

List all items in a saved portfolio.

### Example

```ts
import {
  Configuration,
  PortfolioApi,
} from 'cs2cap';
import type { ListPortfolioItemsRequest } from 'cs2cap';

async function example() {
  console.log("🚀 Testing cs2cap SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PortfolioApi(config);

  const body = {
    // string
    portfolioId: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
  } satisfies ListPortfolioItemsRequest;

  try {
    const data = await api.listPortfolioItems(body);
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
| **portfolioId** | `string` |  | [Defaults to `undefined`] |

### Return type

[**Array&lt;PortfolioItemOut&gt;**](PortfolioItemOut.md)

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
| **404** | Portfolio not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listPortfolios

> PortfolioListResponse listPortfolios()

List Portfolios

List all named portfolios belonging to the authenticated user.

### Example

```ts
import {
  Configuration,
  PortfolioApi,
} from 'cs2cap';
import type { ListPortfoliosRequest } from 'cs2cap';

async function example() {
  console.log("🚀 Testing cs2cap SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PortfolioApi(config);

  try {
    const data = await api.listPortfolios();
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

[**PortfolioListResponse**](PortfolioListResponse.md)

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
| **403** | Access denied. |  -  |
| **429** | Rate limit exceeded (burst or monthly quota). |  * Retry-After - Seconds to wait before retrying when present. <br>  * X-RateLimit-Tier - Authenticated caller tier code. <br>  * X-RateLimit-Limit - Request limit for the rate-limit window that was exceeded. <br>  * X-RateLimit-Remaining - Remaining requests in the rate-limit window that was exceeded. <br>  * X-RateLimit-Reset - Seconds until the rate-limit window resets. <br>  |
| **422** | Request validation failed. The detail list contains field-specific validation errors. |  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listTransactions

> Array&lt;TransactionOut&gt; listTransactions(portfolioId)

List Transactions

List all transactions in a portfolio, newest first.

### Example

```ts
import {
  Configuration,
  PortfolioApi,
} from 'cs2cap';
import type { ListTransactionsRequest } from 'cs2cap';

async function example() {
  console.log("🚀 Testing cs2cap SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PortfolioApi(config);

  const body = {
    // string
    portfolioId: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
  } satisfies ListTransactionsRequest;

  try {
    const data = await api.listTransactions(body);
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
| **portfolioId** | `string` |  | [Defaults to `undefined`] |

### Return type

[**Array&lt;TransactionOut&gt;**](TransactionOut.md)

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
| **404** | Portfolio not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## portfolioValuation

> PortfolioResponse portfolioValuation(portfolioRequest)

Portfolio Valuation

Value an inventory of CS2 items at live market prices.  Send a list of &#x60;{item_id, quantity}&#x60; pairs and receive per-item valuation based on the best ask price across queried providers, plus a rolled-up total.  Maximum 100 distinct items per request.  All money values are in minor units of the requested currency (e.g. USD cents when &#x60;currency&#x3D;USD&#x60;). Divide by 100 for display.

### Example

```ts
import {
  Configuration,
  PortfolioApi,
} from 'cs2cap';
import type { PortfolioValuationRequest } from 'cs2cap';

async function example() {
  console.log("🚀 Testing cs2cap SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PortfolioApi(config);

  const body = {
    // PortfolioRequest
    portfolioRequest: ...,
  } satisfies PortfolioValuationRequest;

  try {
    const data = await api.portfolioValuation(body);
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
| **portfolioRequest** | [PortfolioRequest](PortfolioRequest.md) |  | |

### Return type

[**PortfolioResponse**](PortfolioResponse.md)

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


## removeItemFromPortfolio

> removeItemFromPortfolio(portfolioId, entryId)

Remove Item from Portfolio

Remove a specific item entry from a portfolio.

### Example

```ts
import {
  Configuration,
  PortfolioApi,
} from 'cs2cap';
import type { RemoveItemFromPortfolioRequest } from 'cs2cap';

async function example() {
  console.log("🚀 Testing cs2cap SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PortfolioApi(config);

  const body = {
    // string
    portfolioId: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
    // string
    entryId: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
  } satisfies RemoveItemFromPortfolioRequest;

  try {
    const data = await api.removeItemFromPortfolio(body);
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
| **portfolioId** | `string` |  | [Defaults to `undefined`] |
| **entryId** | `string` |  | [Defaults to `undefined`] |

### Return type

`void` (Empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | Successful Response |  -  |
| **401** | Missing or invalid authentication credentials. |  -  |
| **403** | Authenticated but not permitted to access this resource. |  -  |
| **429** | Rate limit exceeded (burst or monthly quota). |  * Retry-After - Seconds to wait before retrying when present. <br>  * X-RateLimit-Tier - Authenticated caller tier code. <br>  * X-RateLimit-Limit - Request limit for the rate-limit window that was exceeded. <br>  * X-RateLimit-Remaining - Remaining requests in the rate-limit window that was exceeded. <br>  * X-RateLimit-Reset - Seconds until the rate-limit window resets. <br>  |
| **422** | Request validation failed. The detail list contains field-specific validation errors. |  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  |
| **404** | Portfolio or item not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateTransaction

> TransactionOut updateTransaction(portfolioId, transactionId, transactionUpdateRequest)

Update Transaction

Partially update a transaction.

### Example

```ts
import {
  Configuration,
  PortfolioApi,
} from 'cs2cap';
import type { UpdateTransactionRequest } from 'cs2cap';

async function example() {
  console.log("🚀 Testing cs2cap SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PortfolioApi(config);

  const body = {
    // string
    portfolioId: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
    // string
    transactionId: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
    // TransactionUpdateRequest
    transactionUpdateRequest: ...,
  } satisfies UpdateTransactionRequest;

  try {
    const data = await api.updateTransaction(body);
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
| **portfolioId** | `string` |  | [Defaults to `undefined`] |
| **transactionId** | `string` |  | [Defaults to `undefined`] |
| **transactionUpdateRequest** | [TransactionUpdateRequest](TransactionUpdateRequest.md) |  | |

### Return type

[**TransactionOut**](TransactionOut.md)

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
| **404** | Portfolio or transaction not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## valueSavedPortfolio

> PortfolioResponse valueSavedPortfolio(portfolioId, currency, providers)

Value Saved Portfolio

Value all items in a saved portfolio at live market prices. Items without price data appear in &#x60;items_not_found&#x60;. All money values are in minor units (e.g. USD cents). Divide by 100 for display.

### Example

```ts
import {
  Configuration,
  PortfolioApi,
} from 'cs2cap';
import type { ValueSavedPortfolioRequest } from 'cs2cap';

async function example() {
  console.log("🚀 Testing cs2cap SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PortfolioApi(config);

  const body = {
    // string
    portfolioId: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
    // string | Target currency code. (optional)
    currency: currency_example,
    // Array<string> | Provider keys to include. Repeat to pass multiple, e.g. providers=steam&providers=skinport. Omit for all providers. (optional)
    providers: ...,
  } satisfies ValueSavedPortfolioRequest;

  try {
    const data = await api.valueSavedPortfolio(body);
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
| **portfolioId** | `string` |  | [Defaults to `undefined`] |
| **currency** | `string` | Target currency code. | [Optional] [Defaults to `&#39;USD&#39;`] |
| **providers** | `Array<string>` | Provider keys to include. Repeat to pass multiple, e.g. providers&#x3D;steam&amp;providers&#x3D;skinport. Omit for all providers. | [Optional] |

### Return type

[**PortfolioResponse**](PortfolioResponse.md)

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
| **404** | Portfolio not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

