---
title: OrderShippingCountryRegionChangedNotification
description: API reference for OrderShippingCountryRegionChangedNotification in Vendr, the eCommerce solution for Umbraco v8+
---
## OrderShippingCountryRegionChangedNotification

```csharp
public class OrderShippingCountryRegionChangedNotification : 
    OrderShippingCountryRegionChangeNotificationBase<OrderReadOnly>
```

**Inheritance**

* class [OrderShippingCountryRegionChangeNotificationBase&lt;TEntity&gt;](../ordershippingcountryregionchangenotificationbase-1/)

**Namespace**
* [Vendr.Core.Events.Notification](../)

### Constructors

#### OrderShippingCountryRegionChangedNotification

```csharp
public OrderShippingCountryRegionChangedNotification(OrderReadOnly order, 
    ChangingValue<Guid?> countryId, ChangingValue<Guid?> regionId)
```


<!-- DO NOT EDIT: generated by xmldocmd for Vendr.Core.dll -->
