---
title: Settings Objects
description: Strongly typed Settings objects in Vendr, the eCommerce solution for Umbraco v8+
---

## Settings Objects

There are a number of places in Vendr where you can uses Settings Objects to pass configuration to a Provider, such as Discount Rule Providers, Reward Providers and Payment Providers.

The settings objects have a number of responsibilities.

* **Typed Settings Model** - The type represents a strongly typed settings model the given Provider accepts. Any stored settings in the database will be deserialized to this type before being passed to the Provider for processing. This provides strongly typed access to the relevant configuration settings.

* **UI Scaffold** - The settings object defines meta data on its properties via an Attribute implementing `VendrSettingAttribute`, each Provider type has their own attribute type in case they require additional config, for example `DiscountRewardProviderSettingAttribute`, `DiscountRuleProviderSettingAttribute` or `PaymentProviderSettingAttribute`. The attributes are used to dynamically build the AngularJS based UI for the given Providers configuration. See the [UI Scaffolding](#ui-scaffolding) section below for more information on UI Scaffolding.
</message-box>

* **JavaScript Settings Model** - The settings object also defines the JavaScript settings model passed to the Provider editor UI, using either the settings Property name as the object property key, or using the `key` property of the Setting Attribute declared on the given Property.

### UI Scaffolding

An important element of the Settings object is UI Scaffolding. UI Scaffolding is where Vendr reads a series of Settings Attributes defined on your Settings object properties in order to dynamically build a User Interface for that Providers settings.

An example of a Discount Reward Settings Object might look something like this:

````csharp
public class MyDiscountRewardProviderSettings
{
    [DiscountRewardProviderSetting(Key = "nodeId",
        Name = "Product Node",
        Description = "The product to discount the price of",
        View = "contentpicker",
        Config = "{ startNodeId: -1, multiPicker: false, idType: 'udi' }")]
    public Udi NodeId { get; set; }

    ...
}
````

Attributes define a property `key`, `name`, `description` to display in the UI as well as an optional `view` and `config` option to define the Umbraco property editor to use to edit the given property with. If no view is defined, one will attempt to automatically be chosen based on the properties value type.

An example of a generated UI built from these properties would look something like this:

![Discount Rule UI](~/assets/images/screenshots/discount_rule_ui.png)