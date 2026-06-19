# cs2cap@2.0.0

A TypeScript SDK client for the CS2Cap API.

## Usage

First, install the SDK from npm.

```bash
npm install cs2cap --save
```

Next, try it out.


```ts
import {
  Configuration,
  AccountAPIKeysApi,
} from 'cs2cap';
import type { CreateSubKeyRequest } from 'cs2cap';

async function example() {
  console.log("🚀 Testing cs2cap SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AccountAPIKeysApi(config);

  const body = {
    // ChildAPIKeyCreateRequest
    childAPIKeyCreateRequest: ...,
  } satisfies CreateSubKeyRequest;

  try {
    const data = await api.createSubKey(body);
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

// Run the test
example().catch(console.error);
```


## Documentation

### API Endpoints

All URIs are relative to *https://api.cs2c.app*

| Class | Method | HTTP request | Description
| ----- | ------ | ------------ | -------------
*AccountAPIKeysApi* | [**createSubKey**](docs/AccountAPIKeysApi.md#createsubkey) | **POST** /v1/account/sub-keys | Create Sub Key
*AccountAPIKeysApi* | [**deleteSubKey**](docs/AccountAPIKeysApi.md#deletesubkey) | **DELETE** /v1/account/sub-keys/{key_id} | Delete Sub Key
*AccountAPIKeysApi* | [**getSubKey**](docs/AccountAPIKeysApi.md#getsubkey) | **GET** /v1/account/sub-keys/{key_id} | Get Sub Key
*AccountAPIKeysApi* | [**listSubKeys**](docs/AccountAPIKeysApi.md#listsubkeys) | **GET** /v1/account/sub-keys | List Sub Keys
*AccountAPIKeysApi* | [**reissueSubKey**](docs/AccountAPIKeysApi.md#reissuesubkey) | **POST** /v1/account/sub-keys/{key_id}/reissue | Reissue Sub Key
*AccountAPIKeysApi* | [**updateSubKey**](docs/AccountAPIKeysApi.md#updatesubkey) | **PATCH** /v1/account/sub-keys/{key_id} | Update Sub Key
*AccountAlertsApi* | [**createAlert**](docs/AccountAlertsApi.md#createalert) | **POST** /v1/account/alerts | Create Alert
*AccountAlertsApi* | [**createAlertsBatch**](docs/AccountAlertsApi.md#createalertsbatch) | **POST** /v1/account/alerts/batch | Create Alerts Batch
*AccountAlertsApi* | [**deleteAlert**](docs/AccountAlertsApi.md#deletealert) | **DELETE** /v1/account/alerts/{alert_id} | Delete Alert
*AccountAlertsApi* | [**listAlertEvents**](docs/AccountAlertsApi.md#listalertevents) | **GET** /v1/account/alerts/events | List Alert Events
*AccountAlertsApi* | [**listAlerts**](docs/AccountAlertsApi.md#listalerts) | **GET** /v1/account/alerts | List Alerts
*AccountAlertsApi* | [**updateAlert**](docs/AccountAlertsApi.md#updatealert) | **PATCH** /v1/account/alerts/{alert_id} | Update Alert
*AccountWatchlistApi* | [**createWatchlistEntries**](docs/AccountWatchlistApi.md#createwatchlistentries) | **POST** /v1/account/watchlist | Create Watchlist Entries
*AccountWatchlistApi* | [**deleteWatchlistEntry**](docs/AccountWatchlistApi.md#deletewatchlistentry) | **DELETE** /v1/account/watchlist/{item_id} | Delete Watchlist Entry
*AccountWatchlistApi* | [**listWatchlist**](docs/AccountWatchlistApi.md#listwatchlist) | **GET** /v1/account/watchlist | List Watchlist
*AccountWebhooksApi* | [**createWebhook**](docs/AccountWebhooksApi.md#createwebhook) | **POST** /v1/account/webhooks | Create Webhook
*AccountWebhooksApi* | [**deleteWebhook**](docs/AccountWebhooksApi.md#deletewebhook) | **DELETE** /v1/account/webhooks/{webhook_id} | Delete Webhook
*AccountWebhooksApi* | [**getWebhookDelivery**](docs/AccountWebhooksApi.md#getwebhookdelivery) | **GET** /v1/account/webhooks/deliveries/{delivery_id} | Get Webhook Delivery
*AccountWebhooksApi* | [**listWebhookDeliveries**](docs/AccountWebhooksApi.md#listwebhookdeliveries) | **GET** /v1/account/webhooks/deliveries | List Webhook Deliveries
*AccountWebhooksApi* | [**listWebhooks**](docs/AccountWebhooksApi.md#listwebhooks) | **GET** /v1/account/webhooks | List Webhooks
*AccountWebhooksApi* | [**rotateWebhookSecret**](docs/AccountWebhooksApi.md#rotatewebhooksecret) | **POST** /v1/account/webhooks/{webhook_id}/rotate-secret | Rotate Webhook Secret
*AccountWebhooksApi* | [**updateWebhook**](docs/AccountWebhooksApi.md#updatewebhook) | **PATCH** /v1/account/webhooks/{webhook_id} | Update Webhook
*BidsApi* | [**batchBidLookup**](docs/BidsApi.md#batchbidlookup) | **POST** /v1/bids/batch | Batch Bid Lookup
*BidsApi* | [**listBids**](docs/BidsApi.md#listbids) | **GET** /v1/bids | List Bids
*BidsApi* | [**streamFullBidsSnapshot**](docs/BidsApi.md#streamfullbidssnapshot) | **POST** /v1/bids | Stream Full Bids Snapshot
*ForeignExchangeApi* | [**getFxRates**](docs/ForeignExchangeApi.md#getfxrates) | **GET** /v1/fx | Get Fx Rates
*ImagesApi* | [**listGameImages**](docs/ImagesApi.md#listgameimages) | **GET** /v1/images | List Game Images
*InventoryApi* | [**fetchSteamInventory**](docs/InventoryApi.md#fetchsteaminventory) | **GET** /v1/inventory/steam | Fetch Steam Inventory
*InventoryApi* | [**fetchSteamInventoryBySteamId**](docs/InventoryApi.md#fetchsteaminventorybysteamid) | **GET** /v1/inventory/steam/lookup | Fetch Steam Inventory by Steam ID
*ItemsApi* | [**getItemCatalogMetadata**](docs/ItemsApi.md#getitemcatalogmetadata) | **GET** /v1/items/metadata | Get Item Catalog Metadata
*ItemsApi* | [**listItems**](docs/ItemsApi.md#listitems) | **GET** /v1/items | List Items
*MarketIntelligenceApi* | [**getArbitrageOpportunities**](docs/MarketIntelligenceApi.md#getarbitrageopportunities) | **GET** /v1/market/arbitrage | Get Arbitrage Opportunities
*MarketIntelligenceApi* | [**getDeepPriceHistoryChart**](docs/MarketIntelligenceApi.md#getdeeppricehistorychart) | **GET** /v1/market/history/chart | Get Deep Price History Chart
*MarketIntelligenceApi* | [**getIndicators**](docs/MarketIntelligenceApi.md#getindicators) | **GET** /v1/market/indicators | Get Indicators
*MarketIntelligenceApi* | [**getItemAnalytics**](docs/MarketIntelligenceApi.md#getitemanalytics) | **GET** /v1/market/items/{item_id} | Get Item Analytics
*MarketIntelligenceApi* | [**getMarketAnalyticsSnapshot**](docs/MarketIntelligenceApi.md#getmarketanalyticssnapshot) | **GET** /v1/market/items | Get Market Analytics Snapshot
*MarketIntelligenceApi* | [**getMarketCapIndexes**](docs/MarketIntelligenceApi.md#getmarketcapindexes) | **GET** /v1/market/indexes | Get Market Cap Indexes
*PortfolioApi* | [**addItemToPortfolio**](docs/PortfolioApi.md#additemtoportfolio) | **POST** /v1/portfolio/{portfolio_id}/items | Add Item to Portfolio
*PortfolioApi* | [**addTransaction**](docs/PortfolioApi.md#addtransaction) | **POST** /v1/portfolio/{portfolio_id}/transactions | Add Transaction
*PortfolioApi* | [**createPortfolio**](docs/PortfolioApi.md#createportfolio) | **POST** /v1/portfolio | Create Portfolio
*PortfolioApi* | [**deletePortfolio**](docs/PortfolioApi.md#deleteportfolio) | **DELETE** /v1/portfolio/{portfolio_id} | Delete Portfolio
*PortfolioApi* | [**deleteTransaction**](docs/PortfolioApi.md#deletetransaction) | **DELETE** /v1/portfolio/{portfolio_id}/transactions/{transaction_id} | Delete Transaction
*PortfolioApi* | [**historicalSavedPortfolioValuation**](docs/PortfolioApi.md#historicalsavedportfoliovaluation) | **GET** /v1/portfolio/{portfolio_id}/history | Historical Saved Portfolio Valuation
*PortfolioApi* | [**importSteamInventory**](docs/PortfolioApi.md#importsteaminventory) | **POST** /v1/portfolio/{portfolio_id}/import | Import Steam Inventory
*PortfolioApi* | [**listPortfolioItems**](docs/PortfolioApi.md#listportfolioitems) | **GET** /v1/portfolio/{portfolio_id}/items | List Portfolio Items
*PortfolioApi* | [**listPortfolios**](docs/PortfolioApi.md#listportfolios) | **GET** /v1/portfolio | List Portfolios
*PortfolioApi* | [**listTransactions**](docs/PortfolioApi.md#listtransactions) | **GET** /v1/portfolio/{portfolio_id}/transactions | List Transactions
*PortfolioApi* | [**portfolioValuation**](docs/PortfolioApi.md#portfoliovaluation) | **POST** /v1/portfolio/value | Portfolio Valuation
*PortfolioApi* | [**removeItemFromPortfolio**](docs/PortfolioApi.md#removeitemfromportfolio) | **DELETE** /v1/portfolio/{portfolio_id}/items/{entry_id} | Remove Item from Portfolio
*PortfolioApi* | [**updateTransaction**](docs/PortfolioApi.md#updatetransaction) | **PATCH** /v1/portfolio/{portfolio_id}/transactions/{transaction_id} | Update Transaction
*PortfolioApi* | [**valueSavedPortfolio**](docs/PortfolioApi.md#valuesavedportfolio) | **GET** /v1/portfolio/{portfolio_id}/value | Value Saved Portfolio
*PricesApi* | [**batchPriceLookup**](docs/PricesApi.md#batchpricelookup) | **POST** /v1/prices/batch | Batch Price Lookup
*PricesApi* | [**listPrices**](docs/PricesApi.md#listprices) | **GET** /v1/prices | List Prices
*PricesApi* | [**priceCandles**](docs/PricesApi.md#pricecandles) | **GET** /v1/prices/candles | Price Candles
*PricesApi* | [**priceHistory**](docs/PricesApi.md#pricehistory) | **GET** /v1/prices/history | Price History
*PricesApi* | [**streamFullPricesSnapshot**](docs/PricesApi.md#streamfullpricessnapshot) | **POST** /v1/prices | Stream Full Prices Snapshot
*ProvidersApi* | [**listProviders**](docs/ProvidersApi.md#listproviders) | **GET** /v1/providers | List Providers
*SalesApi* | [**listRecentSales**](docs/SalesApi.md#listrecentsales) | **GET** /v1/sales | List Recent Sales


### Models

- [APIKeyInfo](docs/APIKeyInfo.md)
- [AccountMutationResponse](docs/AccountMutationResponse.md)
- [AlertBatchCreateRequest](docs/AlertBatchCreateRequest.md)
- [AlertBatchCreateResponse](docs/AlertBatchCreateResponse.md)
- [AlertBatchCreateResult](docs/AlertBatchCreateResult.md)
- [AlertCreateRequest](docs/AlertCreateRequest.md)
- [AlertDefinition](docs/AlertDefinition.md)
- [AlertDeliverySummary](docs/AlertDeliverySummary.md)
- [AlertEventSummary](docs/AlertEventSummary.md)
- [AlertEventsResponse](docs/AlertEventsResponse.md)
- [AlertItemSummary](docs/AlertItemSummary.md)
- [AlertListResponse](docs/AlertListResponse.md)
- [AlertUpdateRequest](docs/AlertUpdateRequest.md)
- [AllProviders](docs/AllProviders.md)
- [BatchBidItem](docs/BatchBidItem.md)
- [BatchBidQuote](docs/BatchBidQuote.md)
- [BatchBidsMeta](docs/BatchBidsMeta.md)
- [BatchBidsRequest](docs/BatchBidsRequest.md)
- [BatchBidsResponse](docs/BatchBidsResponse.md)
- [BatchPriceItem](docs/BatchPriceItem.md)
- [BatchPriceQuote](docs/BatchPriceQuote.md)
- [BatchPricesMeta](docs/BatchPricesMeta.md)
- [BatchPricesRequest](docs/BatchPricesRequest.md)
- [BatchPricesResponse](docs/BatchPricesResponse.md)
- [BidsResponse](docs/BidsResponse.md)
- [BuyOrderItem](docs/BuyOrderItem.md)
- [BuyOrderProvider](docs/BuyOrderProvider.md)
- [CharmInfo](docs/CharmInfo.md)
- [ChildAPIKeyCreateRequest](docs/ChildAPIKeyCreateRequest.md)
- [ChildAPIKeyCreateResponse](docs/ChildAPIKeyCreateResponse.md)
- [ChildAPIKeyDetailResponse](docs/ChildAPIKeyDetailResponse.md)
- [ChildAPIKeyListResponse](docs/ChildAPIKeyListResponse.md)
- [ChildAPIKeyUpdateRequest](docs/ChildAPIKeyUpdateRequest.md)
- [CursorPaginationMeta](docs/CursorPaginationMeta.md)
- [ErrorResponse](docs/ErrorResponse.md)
- [FXRatesResponse](docs/FXRatesResponse.md)
- [IndicatorDataCoverage](docs/IndicatorDataCoverage.md)
- [IndicatorMomentum](docs/IndicatorMomentum.md)
- [IndicatorSignals](docs/IndicatorSignals.md)
- [IndicatorVolatility](docs/IndicatorVolatility.md)
- [IndicatorVolume](docs/IndicatorVolume.md)
- [InspectInfo](docs/InspectInfo.md)
- [ItemOut](docs/ItemOut.md)
- [ItemsCatalogSummary](docs/ItemsCatalogSummary.md)
- [ItemsFilterMetadata](docs/ItemsFilterMetadata.md)
- [ItemsMetadataResponse](docs/ItemsMetadataResponse.md)
- [ItemsPaginatedResponseItemOut](docs/ItemsPaginatedResponseItemOut.md)
- [ItemsPaginationMeta](docs/ItemsPaginationMeta.md)
- [LocInner](docs/LocInner.md)
- [MarketArbitrageData](docs/MarketArbitrageData.md)
- [MarketArbitrageItem](docs/MarketArbitrageItem.md)
- [MarketArbitrageMeta](docs/MarketArbitrageMeta.md)
- [MarketArbitrageResponse](docs/MarketArbitrageResponse.md)
- [MarketHistoryChartMeta](docs/MarketHistoryChartMeta.md)
- [MarketHistoryChartPoint](docs/MarketHistoryChartPoint.md)
- [MarketHistoryChartResponse](docs/MarketHistoryChartResponse.md)
- [MarketHistoryChartSeries](docs/MarketHistoryChartSeries.md)
- [MarketIndexGroup](docs/MarketIndexGroup.md)
- [MarketIndexesData](docs/MarketIndexesData.md)
- [MarketIndexesMeta](docs/MarketIndexesMeta.md)
- [MarketIndexesResponse](docs/MarketIndexesResponse.md)
- [MarketIndicatorsItemData](docs/MarketIndicatorsItemData.md)
- [MarketIndicatorsItemResponse](docs/MarketIndicatorsItemResponse.md)
- [MarketIndicatorsMeta](docs/MarketIndicatorsMeta.md)
- [MarketItem](docs/MarketItem.md)
- [MarketItemAnalyticsCoverage](docs/MarketItemAnalyticsCoverage.md)
- [MarketItemAnalyticsData](docs/MarketItemAnalyticsData.md)
- [MarketItemAnalyticsProvider](docs/MarketItemAnalyticsProvider.md)
- [MarketItemAnalyticsResponse](docs/MarketItemAnalyticsResponse.md)
- [MarketItemAnalyticsSummary](docs/MarketItemAnalyticsSummary.md)
- [MarketItemsSnapshotData](docs/MarketItemsSnapshotData.md)
- [MarketItemsSnapshotItem](docs/MarketItemsSnapshotItem.md)
- [MarketItemsSnapshotResponse](docs/MarketItemsSnapshotResponse.md)
- [MarketMeta](docs/MarketMeta.md)
- [MarketTimeWindowMeta](docs/MarketTimeWindowMeta.md)
- [PaginationMeta](docs/PaginationMeta.md)
- [PhaseName](docs/PhaseName.md)
- [PortfolioAddItemRequest](docs/PortfolioAddItemRequest.md)
- [PortfolioCreate](docs/PortfolioCreate.md)
- [PortfolioData](docs/PortfolioData.md)
- [PortfolioHistoryMeta](docs/PortfolioHistoryMeta.md)
- [PortfolioHistoryPage](docs/PortfolioHistoryPage.md)
- [PortfolioHistoryPoint](docs/PortfolioHistoryPoint.md)
- [PortfolioImportRequest](docs/PortfolioImportRequest.md)
- [PortfolioImportResult](docs/PortfolioImportResult.md)
- [PortfolioItemOut](docs/PortfolioItemOut.md)
- [PortfolioLineItem](docs/PortfolioLineItem.md)
- [PortfolioListResponse](docs/PortfolioListResponse.md)
- [PortfolioMeta](docs/PortfolioMeta.md)
- [PortfolioOut](docs/PortfolioOut.md)
- [PortfolioRequest](docs/PortfolioRequest.md)
- [PortfolioRequestItem](docs/PortfolioRequestItem.md)
- [PortfolioResponse](docs/PortfolioResponse.md)
- [PriceCandleItem](docs/PriceCandleItem.md)
- [PriceCandlesMeta](docs/PriceCandlesMeta.md)
- [PriceCandlesPage](docs/PriceCandlesPage.md)
- [PriceHistoryFiltersMeta](docs/PriceHistoryFiltersMeta.md)
- [PriceHistoryMeta](docs/PriceHistoryMeta.md)
- [PriceSnapshot](docs/PriceSnapshot.md)
- [PriceSnapshotPage](docs/PriceSnapshotPage.md)
- [PricesFilterMeta](docs/PricesFilterMeta.md)
- [PricesMeta](docs/PricesMeta.md)
- [PricesPaginatedResponseMarketItem](docs/PricesPaginatedResponseMarketItem.md)
- [ProviderFeatures](docs/ProviderFeatures.md)
- [ProviderFees](docs/ProviderFees.md)
- [ProviderHealth](docs/ProviderHealth.md)
- [ProviderInfo](docs/ProviderInfo.md)
- [Providers](docs/Providers.md)
- [RecentSalesProvider](docs/RecentSalesProvider.md)
- [SaleRecordDetail](docs/SaleRecordDetail.md)
- [SalesFiltersMeta](docs/SalesFiltersMeta.md)
- [SalesHistoryResponse](docs/SalesHistoryResponse.md)
- [SalesMeta](docs/SalesMeta.md)
- [SteamInventoryItem](docs/SteamInventoryItem.md)
- [SteamInventoryResponse](docs/SteamInventoryResponse.md)
- [StickerInfo](docs/StickerInfo.md)
- [TransactionCreateRequest](docs/TransactionCreateRequest.md)
- [TransactionOut](docs/TransactionOut.md)
- [TransactionUpdateRequest](docs/TransactionUpdateRequest.md)
- [ValidationErrorItem](docs/ValidationErrorItem.md)
- [ValidationErrorResponse](docs/ValidationErrorResponse.md)
- [WatchlistBatchCreateResponse](docs/WatchlistBatchCreateResponse.md)
- [WatchlistCreateBatchRequest](docs/WatchlistCreateBatchRequest.md)
- [WatchlistCreateRequest](docs/WatchlistCreateRequest.md)
- [WatchlistCreateResponse](docs/WatchlistCreateResponse.md)
- [WatchlistCreateSingleRequest](docs/WatchlistCreateSingleRequest.md)
- [WatchlistItem](docs/WatchlistItem.md)
- [WatchlistResponse](docs/WatchlistResponse.md)
- [WebhookCreateRequest](docs/WebhookCreateRequest.md)
- [WebhookDeliveriesResponse](docs/WebhookDeliveriesResponse.md)
- [WebhookDeliveryAttemptSummary](docs/WebhookDeliveryAttemptSummary.md)
- [WebhookDeliveryDetail](docs/WebhookDeliveryDetail.md)
- [WebhookDeliverySummary](docs/WebhookDeliverySummary.md)
- [WebhookEndpointSummary](docs/WebhookEndpointSummary.md)
- [WebhookEndpointsResponse](docs/WebhookEndpointsResponse.md)
- [WebhookSecretResponse](docs/WebhookSecretResponse.md)
- [WebhookUpdateRequest](docs/WebhookUpdateRequest.md)

### Authorization


Authentication schemes defined for the API:
<a id="BearerAuth"></a>
#### BearerAuth


- **Type**: HTTP Bearer Token authentication

## About

This TypeScript SDK client supports the [Fetch API](https://fetch.spec.whatwg.org/)
and is automatically generated by the
[OpenAPI Generator](https://openapi-generator.tech) project:

- API version: `1.0.0`
- Package version: `2.0.0`
- Generator version: `7.20.0`
- Build package: `org.openapitools.codegen.languages.TypeScriptFetchClientCodegen`

The generated npm module supports the following:

- Environments
  * Node.js
  * Webpack
  * Browserify
- Language levels
  * ES5 - you must have a Promises/A+ library installed
  * ES6
- Module systems
  * CommonJS
  * ES6 module system


## Development

### Building

To build the TypeScript source code, you need to have Node.js and npm installed.
After cloning the repository, navigate to the project directory and run:

```bash
npm install
npm run build
```

### Publishing

Once you've built the package, you can publish it to npm:

```bash
npm publish
```

## License

[]()
