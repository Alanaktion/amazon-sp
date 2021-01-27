# Amazon SP

The Selling Partner API for Orders helps you programmatically retrieve order information. These APIs let you develop fast, flexible, custom applications in areas like order synchronization, order research, and demand-based decision support tools.

This PHP package is automatically generated by the [Swagger Codegen](https://github.com/swagger-api/swagger-codegen) project:

- API version: v0
- Build package: io.swagger.codegen.v3.generators.php.PhpClientCodegen
For more information, please visit [https://sellercentral.amazon.com/gp/mws/contactus.html](https://sellercentral.amazon.com/gp/mws/contactus.html)

To generate this package:

```bash
swagger-codegen generate -l php -i https://github.com/amzn/selling-partner-api-models/raw/main/models/orders-api-model/ordersV0.json --model-package Orders --invoker-package AmazonSP
```

If someone is actually using this for something that requires anything beyond the Orders API, it's fairly trivial to add additional endpoints, and I'll accept valid PRs.

## Requirements

PHP 5.5 and later

## Installation & Usage

### Composer

To install the bindings via [Composer](http://getcomposer.org/), add the following to `composer.json`:

```json
{
  "repositories": [
    {
      "type": "git",
      "url": "https://github.com/Alanaktion/amazon-sp.git"
    }
  ],
  "require": {
    "alanaktion/amazon-sp": "*@dev"
  }
}
```

Then run `composer install`

### Manual Installation

Download the files and include `autoload.php`:

```php
require_once('/path/to/amazon-sp/vendor/autoload.php');
```

## Tests

To run the unit tests:

```bash
composer install
./vendor/bin/phpunit
```

## Getting Started

Please follow the [installation procedure](#installation--usage) and then run the following:

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new AmazonSP\Api\OrdersV0Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$order_id = "order_id_example"; // string | An Amazon-defined order identifier, in 3-7-7 format.

try {
    $result = $apiInstance->getOrder($order_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OrdersV0Api->getOrder: ', $e->getMessage(), PHP_EOL;
}

$apiInstance = new AmazonSP\Api\OrdersV0Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$order_id = "order_id_example"; // string | An orderId is an Amazon-defined order identifier, in 3-7-7 format.

try {
    $result = $apiInstance->getOrderAddress($order_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OrdersV0Api->getOrderAddress: ', $e->getMessage(), PHP_EOL;
}

$apiInstance = new AmazonSP\Api\OrdersV0Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$order_id = "order_id_example"; // string | An orderId is an Amazon-defined order identifier, in 3-7-7 format.

try {
    $result = $apiInstance->getOrderBuyerInfo($order_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OrdersV0Api->getOrderBuyerInfo: ', $e->getMessage(), PHP_EOL;
}

$apiInstance = new AmazonSP\Api\OrdersV0Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$order_id = "order_id_example"; // string | An Amazon-defined order identifier, in 3-7-7 format.
$next_token = "next_token_example"; // string | A string token returned in the response of your previous request.

try {
    $result = $apiInstance->getOrderItems($order_id, $next_token);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OrdersV0Api->getOrderItems: ', $e->getMessage(), PHP_EOL;
}

$apiInstance = new AmazonSP\Api\OrdersV0Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$order_id = "order_id_example"; // string | An Amazon-defined order identifier, in 3-7-7 format.
$next_token = "next_token_example"; // string | A string token returned in the response of your previous request.

try {
    $result = $apiInstance->getOrderItemsBuyerInfo($order_id, $next_token);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OrdersV0Api->getOrderItemsBuyerInfo: ', $e->getMessage(), PHP_EOL;
}

$apiInstance = new AmazonSP\Api\OrdersV0Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$marketplace_ids = array("marketplace_ids_example"); // string[] | A list of MarketplaceId values. Used to select orders that were placed in the specified marketplaces.
$created_after = "created_after_example"; // string | A date used for selecting orders created after (or at) a specified time. Only orders placed after the specified time are returned. Either the CreatedAfter parameter or the LastUpdatedAfter parameter is required. Both cannot be empty. The date must be in ISO 8601 format.
$created_before = "created_before_example"; // string | A date used for selecting orders created before (or at) a specified time. Only orders placed before the specified time are returned. The date must be in ISO 8601 format.
$last_updated_after = "last_updated_after_example"; // string | A date used for selecting orders that were last updated after (or at) a specified time. An update is defined as any change in order status, including the creation of a new order. Includes updates made by Amazon and by the seller. The date must be in ISO 8601 format.
$last_updated_before = "last_updated_before_example"; // string | A date used for selecting orders that were last updated before (or at) a specified time. An update is defined as any change in order status, including the creation of a new order. Includes updates made by Amazon and by the seller. The date must be in ISO 8601 format.
$order_statuses = array("order_statuses_example"); // string[] | A list of OrderStatus values used to filter the results. Possible values: PendingAvailability (This status is available for pre-orders only. The order has been placed, payment has not been authorized, and the release date of the item is in the future.); Pending (The order has been placed but payment has not been authorized); Unshipped (Payment has been authorized and the order is ready for shipment, but no items in the order have been shipped); PartiallyShipped (One or more, but not all, items in the order have been shipped); Shipped (All items in the order have been shipped); InvoiceUnconfirmed (All items in the order have been shipped. The seller has not yet given confirmation to Amazon that the invoice has been shipped to the buyer.); Canceled (The order has been canceled); and Unfulfillable (The order cannot be fulfilled. This state applies only to Multi-Channel Fulfillment orders.).
$fulfillment_channels = array("fulfillment_channels_example"); // string[] | A list that indicates how an order was fulfilled. Filters the results by fulfillment channel. Possible values: FBA (Fulfillment by Amazon); SellerFulfilled (Fulfilled by the seller).
$payment_methods = array("payment_methods_example"); // string[] | A list of payment method values. Used to select orders paid using the specified payment methods. Possible values: COD (Cash on delivery); CVS (Convenience store payment); Other (Any payment method other than COD or CVS).
$buyer_email = "buyer_email_example"; // string | The email address of a buyer. Used to select orders that contain the specified email address.
$seller_order_id = "seller_order_id_example"; // string | An order identifier that is specified by the seller. Used to select only the orders that match the order identifier. If SellerOrderId is specified, then FulfillmentChannels, OrderStatuses, PaymentMethod, LastUpdatedAfter, LastUpdatedBefore, and BuyerEmail cannot be specified.
$max_results_per_page = 56; // int | A number that indicates the maximum number of orders that can be returned per page. Value must be 1 - 100. Default 100.
$easy_ship_shipment_statuses = array("easy_ship_shipment_statuses_example"); // string[] | A list of EasyShipShipmentStatus values. Used to select Easy Ship orders with statuses that match the specified  values. If EasyShipShipmentStatus is specified, only Amazon Easy Ship orders are returned.Possible values: PendingPickUp (Amazon has not yet picked up the package from the seller). LabelCanceled (The seller canceled the pickup). PickedUp (Amazon has picked up the package from the seller). AtOriginFC (The packaged is at the origin fulfillment center). AtDestinationFC (The package is at the destination fulfillment center). OutForDelivery (The package is out for delivery). Damaged (The package was damaged by the carrier). Delivered (The package has been delivered to the buyer). RejectedByBuyer (The package has been rejected by the buyer). Undeliverable (The package cannot be delivered). ReturnedToSeller (The package was not delivered to the buyer and was returned to the seller). ReturningToSeller (The package was not delivered to the buyer and is being returned to the seller).
$next_token = "next_token_example"; // string | A string token returned in the response of your previous request.
$amazon_order_ids = array("amazon_order_ids_example"); // string[] | A list of AmazonOrderId values. An AmazonOrderId is an Amazon-defined order identifier, in 3-7-7 format.

try {
    $result = $apiInstance->getOrders($marketplace_ids, $created_after, $created_before, $last_updated_after, $last_updated_before, $order_statuses, $fulfillment_channels, $payment_methods, $buyer_email, $seller_order_id, $max_results_per_page, $easy_ship_shipment_statuses, $next_token, $amazon_order_ids);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OrdersV0Api->getOrders: ', $e->getMessage(), PHP_EOL;
}
?>
```

## Documentation for API Endpoints

All URIs are relative to *https://sellingpartnerapi-na.amazon.com/*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*OrdersV0Api* | [**getOrder**](docs/Api/OrdersV0Api.md#getorder) | **GET** /orders/v0/orders/{orderId} |
*OrdersV0Api* | [**getOrderAddress**](docs/Api/OrdersV0Api.md#getorderaddress) | **GET** /orders/v0/orders/{orderId}/address |
*OrdersV0Api* | [**getOrderBuyerInfo**](docs/Api/OrdersV0Api.md#getorderbuyerinfo) | **GET** /orders/v0/orders/{orderId}/buyerInfo |
*OrdersV0Api* | [**getOrderItems**](docs/Api/OrdersV0Api.md#getorderitems) | **GET** /orders/v0/orders/{orderId}/orderItems |
*OrdersV0Api* | [**getOrderItemsBuyerInfo**](docs/Api/OrdersV0Api.md#getorderitemsbuyerinfo) | **GET** /orders/v0/orders/{orderId}/orderItems/buyerInfo |
*OrdersV0Api* | [**getOrders**](docs/Api/OrdersV0Api.md#getorders) | **GET** /orders/v0/orders |

## Documentation For Models

- [Address](docs/Model/Address.md)
- [BuyerCustomizedInfoDetail](docs/Model/BuyerCustomizedInfoDetail.md)
- [BuyerTaxInfo](docs/Model/BuyerTaxInfo.md)
- [Error](docs/Model/Error.md)
- [ErrorList](docs/Model/ErrorList.md)
- [FulfillmentInstruction](docs/Model/FulfillmentInstruction.md)
- [GetOrderAddressResponse](docs/Model/GetOrderAddressResponse.md)
- [GetOrderBuyerInfoResponse](docs/Model/GetOrderBuyerInfoResponse.md)
- [GetOrderItemsBuyerInfoResponse](docs/Model/GetOrderItemsBuyerInfoResponse.md)
- [GetOrderItemsResponse](docs/Model/GetOrderItemsResponse.md)
- [GetOrderResponse](docs/Model/GetOrderResponse.md)
- [GetOrdersResponse](docs/Model/GetOrdersResponse.md)
- [Money](docs/Model/Money.md)
- [Order](docs/Model/Order.md)
- [OrderAddress](docs/Model/OrderAddress.md)
- [OrderBuyerInfo](docs/Model/OrderBuyerInfo.md)
- [OrderItem](docs/Model/OrderItem.md)
- [OrderItemBuyerInfo](docs/Model/OrderItemBuyerInfo.md)
- [OrderItemBuyerInfoList](docs/Model/OrderItemBuyerInfoList.md)
- [OrderItemList](docs/Model/OrderItemList.md)
- [OrderItemsBuyerInfoList](docs/Model/OrderItemsBuyerInfoList.md)
- [OrderItemsList](docs/Model/OrderItemsList.md)
- [OrderList](docs/Model/OrderList.md)
- [OrdersList](docs/Model/OrdersList.md)
- [PaymentExecutionDetailItem](docs/Model/PaymentExecutionDetailItem.md)
- [PaymentExecutionDetailItemList](docs/Model/PaymentExecutionDetailItemList.md)
- [PaymentMethodDetailItemList](docs/Model/PaymentMethodDetailItemList.md)
- [PointsGrantedDetail](docs/Model/PointsGrantedDetail.md)
- [ProductInfoDetail](docs/Model/ProductInfoDetail.md)
- [PromotionIdList](docs/Model/PromotionIdList.md)
- [TaxClassification](docs/Model/TaxClassification.md)
- [TaxCollection](docs/Model/TaxCollection.md)