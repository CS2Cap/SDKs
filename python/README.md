# cs2cap
CS2Cap aggregates and analyzes Counter-Strike 2 marketplace data across multiple providers via a unified REST API.

## Requirements.

Python 3.9+

## Installation

```sh
pip install cs2cap
```

Then import the package:
```python
import cs2cap
```

## Getting Started

Please follow the [installation procedure](#installation--usage) and then run the following:

```python

import cs2cap
from cs2cap.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to https://api.cs2c.app
# See configuration.py for a list of all supported configuration parameters.
configuration = cs2cap.Configuration(
    host = "https://api.cs2c.app"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization: BearerAuth
configuration = cs2cap.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)


# Enter a context with an instance of the API client
with cs2cap.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = cs2cap.AccountAPIKeysApi(api_client)
    child_api_key_create_request = cs2cap.ChildAPIKeyCreateRequest() # ChildAPIKeyCreateRequest | 

    try:
        # Create Sub Key
        api_response = api_instance.create_sub_key(child_api_key_create_request)
        print("The response of AccountAPIKeysApi->create_sub_key:\n")
        pprint(api_response)
    except ApiException as e:
        print("Exception when calling AccountAPIKeysApi->create_sub_key: %s\n" % e)

```

## Documentation for API Endpoints

All URIs are relative to *https://api.cs2c.app*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*AccountAPIKeysApi* | [**create_sub_key**](docs/AccountAPIKeysApi.md#create_sub_key) | **POST** /v1/account/sub-keys | Create Sub Key
*AccountAPIKeysApi* | [**delete_sub_key**](docs/AccountAPIKeysApi.md#delete_sub_key) | **DELETE** /v1/account/sub-keys/{key_id} | Delete Sub Key
*AccountAPIKeysApi* | [**get_sub_key**](docs/AccountAPIKeysApi.md#get_sub_key) | **GET** /v1/account/sub-keys/{key_id} | Get Sub Key
*AccountAPIKeysApi* | [**list_sub_keys**](docs/AccountAPIKeysApi.md#list_sub_keys) | **GET** /v1/account/sub-keys | List Sub Keys
*AccountAPIKeysApi* | [**reissue_sub_key**](docs/AccountAPIKeysApi.md#reissue_sub_key) | **POST** /v1/account/sub-keys/{key_id}/reissue | Reissue Sub Key
*AccountAPIKeysApi* | [**update_sub_key**](docs/AccountAPIKeysApi.md#update_sub_key) | **PATCH** /v1/account/sub-keys/{key_id} | Update Sub Key
*AccountAlertsApi* | [**create_alert**](docs/AccountAlertsApi.md#create_alert) | **POST** /v1/account/alerts | Create Alert
*AccountAlertsApi* | [**create_alerts_batch**](docs/AccountAlertsApi.md#create_alerts_batch) | **POST** /v1/account/alerts/batch | Create Alerts Batch
*AccountAlertsApi* | [**delete_alert**](docs/AccountAlertsApi.md#delete_alert) | **DELETE** /v1/account/alerts/{alert_id} | Delete Alert
*AccountAlertsApi* | [**list_alert_events**](docs/AccountAlertsApi.md#list_alert_events) | **GET** /v1/account/alerts/events | List Alert Events
*AccountAlertsApi* | [**list_alerts**](docs/AccountAlertsApi.md#list_alerts) | **GET** /v1/account/alerts | List Alerts
*AccountAlertsApi* | [**update_alert**](docs/AccountAlertsApi.md#update_alert) | **PATCH** /v1/account/alerts/{alert_id} | Update Alert
*AccountWatchlistApi* | [**create_watchlist_entries**](docs/AccountWatchlistApi.md#create_watchlist_entries) | **POST** /v1/account/watchlist | Create Watchlist Entries
*AccountWatchlistApi* | [**delete_watchlist_entry**](docs/AccountWatchlistApi.md#delete_watchlist_entry) | **DELETE** /v1/account/watchlist/{item_id} | Delete Watchlist Entry
*AccountWatchlistApi* | [**list_watchlist**](docs/AccountWatchlistApi.md#list_watchlist) | **GET** /v1/account/watchlist | List Watchlist
*AccountWebhooksApi* | [**create_webhook**](docs/AccountWebhooksApi.md#create_webhook) | **POST** /v1/account/webhooks | Create Webhook
*AccountWebhooksApi* | [**delete_webhook**](docs/AccountWebhooksApi.md#delete_webhook) | **DELETE** /v1/account/webhooks/{webhook_id} | Delete Webhook
*AccountWebhooksApi* | [**get_webhook_delivery**](docs/AccountWebhooksApi.md#get_webhook_delivery) | **GET** /v1/account/webhooks/deliveries/{delivery_id} | Get Webhook Delivery
*AccountWebhooksApi* | [**list_webhook_deliveries**](docs/AccountWebhooksApi.md#list_webhook_deliveries) | **GET** /v1/account/webhooks/deliveries | List Webhook Deliveries
*AccountWebhooksApi* | [**list_webhooks**](docs/AccountWebhooksApi.md#list_webhooks) | **GET** /v1/account/webhooks | List Webhooks
*AccountWebhooksApi* | [**rotate_webhook_secret**](docs/AccountWebhooksApi.md#rotate_webhook_secret) | **POST** /v1/account/webhooks/{webhook_id}/rotate-secret | Rotate Webhook Secret
*AccountWebhooksApi* | [**update_webhook**](docs/AccountWebhooksApi.md#update_webhook) | **PATCH** /v1/account/webhooks/{webhook_id} | Update Webhook
*BidsApi* | [**batch_bid_lookup**](docs/BidsApi.md#batch_bid_lookup) | **POST** /v1/bids/batch | Batch Bid Lookup
*BidsApi* | [**list_bids**](docs/BidsApi.md#list_bids) | **GET** /v1/bids | List Bids
*BidsApi* | [**stream_full_bids_snapshot**](docs/BidsApi.md#stream_full_bids_snapshot) | **POST** /v1/bids | Stream Full Bids Snapshot
*ForeignExchangeApi* | [**get_fx_rates**](docs/ForeignExchangeApi.md#get_fx_rates) | **GET** /v1/fx | Get Fx Rates
*ImagesApi* | [**list_game_images**](docs/ImagesApi.md#list_game_images) | **GET** /v1/images | List Game Images
*InventoryApi* | [**fetch_steam_inventory**](docs/InventoryApi.md#fetch_steam_inventory) | **GET** /v1/inventory/steam | Fetch Steam Inventory
*InventoryApi* | [**fetch_steam_inventory_by_steam_id**](docs/InventoryApi.md#fetch_steam_inventory_by_steam_id) | **GET** /v1/inventory/steam/lookup | Fetch Steam Inventory by Steam ID
*ItemsApi* | [**get_item_catalog_metadata**](docs/ItemsApi.md#get_item_catalog_metadata) | **GET** /v1/items/metadata | Get Item Catalog Metadata
*ItemsApi* | [**list_items**](docs/ItemsApi.md#list_items) | **GET** /v1/items | List Items
*MarketIntelligenceApi* | [**get_arbitrage_opportunities**](docs/MarketIntelligenceApi.md#get_arbitrage_opportunities) | **GET** /v1/market/arbitrage | Get Arbitrage Opportunities
*MarketIntelligenceApi* | [**get_deep_price_history_chart**](docs/MarketIntelligenceApi.md#get_deep_price_history_chart) | **GET** /v1/market/history/chart | Get Deep Price History Chart
*MarketIntelligenceApi* | [**get_indicators**](docs/MarketIntelligenceApi.md#get_indicators) | **GET** /v1/market/indicators | Get Indicators
*MarketIntelligenceApi* | [**get_item_analytics**](docs/MarketIntelligenceApi.md#get_item_analytics) | **GET** /v1/market/items/{item_id} | Get Item Analytics
*MarketIntelligenceApi* | [**get_market_analytics_snapshot**](docs/MarketIntelligenceApi.md#get_market_analytics_snapshot) | **GET** /v1/market/items | Get Market Analytics Snapshot
*MarketIntelligenceApi* | [**get_market_cap_indexes**](docs/MarketIntelligenceApi.md#get_market_cap_indexes) | **GET** /v1/market/indexes | Get Market Cap Indexes
*PortfolioApi* | [**add_item_to_portfolio**](docs/PortfolioApi.md#add_item_to_portfolio) | **POST** /v1/portfolio/{portfolio_id}/items | Add Item to Portfolio
*PortfolioApi* | [**add_transaction**](docs/PortfolioApi.md#add_transaction) | **POST** /v1/portfolio/{portfolio_id}/transactions | Add Transaction
*PortfolioApi* | [**create_portfolio**](docs/PortfolioApi.md#create_portfolio) | **POST** /v1/portfolio | Create Portfolio
*PortfolioApi* | [**delete_portfolio**](docs/PortfolioApi.md#delete_portfolio) | **DELETE** /v1/portfolio/{portfolio_id} | Delete Portfolio
*PortfolioApi* | [**delete_transaction**](docs/PortfolioApi.md#delete_transaction) | **DELETE** /v1/portfolio/{portfolio_id}/transactions/{transaction_id} | Delete Transaction
*PortfolioApi* | [**historical_saved_portfolio_valuation**](docs/PortfolioApi.md#historical_saved_portfolio_valuation) | **GET** /v1/portfolio/{portfolio_id}/history | Historical Saved Portfolio Valuation
*PortfolioApi* | [**import_steam_inventory**](docs/PortfolioApi.md#import_steam_inventory) | **POST** /v1/portfolio/{portfolio_id}/import | Import Steam Inventory
*PortfolioApi* | [**list_portfolio_items**](docs/PortfolioApi.md#list_portfolio_items) | **GET** /v1/portfolio/{portfolio_id}/items | List Portfolio Items
*PortfolioApi* | [**list_portfolios**](docs/PortfolioApi.md#list_portfolios) | **GET** /v1/portfolio | List Portfolios
*PortfolioApi* | [**list_transactions**](docs/PortfolioApi.md#list_transactions) | **GET** /v1/portfolio/{portfolio_id}/transactions | List Transactions
*PortfolioApi* | [**portfolio_valuation**](docs/PortfolioApi.md#portfolio_valuation) | **POST** /v1/portfolio/value | Portfolio Valuation
*PortfolioApi* | [**remove_item_from_portfolio**](docs/PortfolioApi.md#remove_item_from_portfolio) | **DELETE** /v1/portfolio/{portfolio_id}/items/{entry_id} | Remove Item from Portfolio
*PortfolioApi* | [**update_transaction**](docs/PortfolioApi.md#update_transaction) | **PATCH** /v1/portfolio/{portfolio_id}/transactions/{transaction_id} | Update Transaction
*PortfolioApi* | [**value_saved_portfolio**](docs/PortfolioApi.md#value_saved_portfolio) | **GET** /v1/portfolio/{portfolio_id}/value | Value Saved Portfolio
*PricesApi* | [**batch_price_lookup**](docs/PricesApi.md#batch_price_lookup) | **POST** /v1/prices/batch | Batch Price Lookup
*PricesApi* | [**list_prices**](docs/PricesApi.md#list_prices) | **GET** /v1/prices | List Prices
*PricesApi* | [**price_candles**](docs/PricesApi.md#price_candles) | **GET** /v1/prices/candles | Price Candles
*PricesApi* | [**price_history**](docs/PricesApi.md#price_history) | **GET** /v1/prices/history | Price History
*PricesApi* | [**stream_full_prices_snapshot**](docs/PricesApi.md#stream_full_prices_snapshot) | **POST** /v1/prices | Stream Full Prices Snapshot
*ProvidersApi* | [**list_providers**](docs/ProvidersApi.md#list_providers) | **GET** /v1/providers | List Providers
*SalesApi* | [**list_recent_sales**](docs/SalesApi.md#list_recent_sales) | **GET** /v1/sales | List Recent Sales


## Documentation For Models

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


<a id="documentation-for-authorization"></a>
## Documentation For Authorization


Authentication schemes defined for the API:
<a id="BearerAuth"></a>
### BearerAuth

- **Type**: Bearer authentication


## Author




