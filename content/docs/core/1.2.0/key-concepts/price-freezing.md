---
title: Price Freezing
description: Freezing prices for shopping carts in Vendr, the eCommerce solution for Umbraco v8+
---

Price Freezing in Vendr is the ability to freeze prices for products that are added to the shopping cart. Once an item is added to a cart, Vendr will take a snapshot of the products price and ensure that this price is honored for the life of the shopping cart. By freezing prices in this way it prevents a customers shopping cart suddenly changing in value should a price change occur whilst their cart session is in progress.

By default a product's price is Frozen from the point a product is added to the current Order, and only for the current Currency of the Order. Should the Customer change the Currency of their Order, then a new snapshot of the product price will be taken for that Currency.

## Controlling Price Freezing

There are times when you may wish to control when a frozen price should expire, such as if a product was incorrectly priced, or if you have some pre-defined rules as to how long an Order session should be allowed to maintain a frozen price for.

In these occasions you can force frozen prices to expire by using the `IFrozenPriceService` and its `Thaw` method.

All frozen prices have an `OrderId` property and a `Key` that uniquely identifies them. For product prices, this key consists of a generated token of the following format `{StoreId}_{OrderId}_{ProductReference}`. In addition, the product prices Currency and date of the freeze are also tracked. It is important to know these details as we can use all of these attributes to target which prices we wish to thaw.

For example, to thaw all prices for a product with the reference `c0296b75-1764-4f62-b59c-7005c2348fdd` we could call:

````csharp
_frozenPriceService.Thaw(partialKey: "c0296b75-1764-4f62-b59c-7005c2348fdd");
````

Or to thaw all prices for a given Currency that are greater than 30 days old we could call:

````csharp
_frozenPriceService.Thaw(currencyId: currency.Id, olderThan: DateTime.Now.AddDays(-30));
````
