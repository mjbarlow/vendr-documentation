---
title: Events
description: Listening for changes within Vendr, the eCommerce solution for Umbraco v8+
---

Much like the standard events system in .NET, Vendr also has an events system to notify you when certain things happen within the application, however Vendr differs slightly in the types of events that are fired and how you register your event handlers.

Events in Vendr are registered using Umbraco's [dependency injection](../dependency-injection/) interface, rather than via static event delegates. This has a number of advantages, such as being able to control the order of when event handlers are fired and it also allows us to inject dependencies into the event handlers making it a much more decoupled approach to eventing. 

In Vendr, there are two main types of events you can create handlers for, and these are:

## Validation events

Validation events are events that fire immediately before a change is about to be made to an entity and allow you to inject your own logic to decide whether an action should be possible or not. We already have a number of validation handlers built in to maintain the consistency of your data, however Validation events allow you to extend this behavior with your own rules.

### Example Validation event handler

An example of a Validation event handler would look something like this:

````csharp
public class MyOrderProductAddValidationHandler : ValidationEventHandlerBase<ValidateOrderProductAdd>
{
    public override void Validate(ValidateOrderProductAdd evt)
    {
        if (evt.ProductReference == "MyProductRef" && evt.Quantity % 10 == 0)
            evt.Fail("This product can only be purchased in increments of 10");
    }
}

````

All Validation event handlers inherit from a base class `ValidationEventHandlerBase<TEvent>` where `TEvent` is the Type of the event the handler is for. They then have a `Validate` method which accepts an instance of the event type, and inside which you can perform your custom logic. If the event fails the validation logic, you can call `evt.Fail("Your message here")` to block the related action from happening and have a `ValidationException` be thrown that can be captured in the front end to display a friendly error message.

### Registering a Validation event handler

Validation event handlers are [registered via a Composer](../dependency-injection/#registering-dependencies) using the `WithValidationEvent<TEvent>()` composition extension method to identify the event you want to handle and then calling the `RegisterHandler<THandler>()` method to register your handler(s) for that event.


````csharp
public void Compose(Composition composition)
{
    composition.WithValidationEvent<ValidateOrderProductAdd>()
        .RegisterHandler<MyOrderProductAddValidationHandler>();
}
````

You can also control the order of when Validation event handlers run, before or after another Validation event handler, by registering them via the `RegisterHandlerBefore<THandler>()` or `RegisterHandlerAfter<THandler>()` methods respectively.

````csharp
public void Compose(Composition composition)
{
    // Register MyOrderProductAddValidationHandler to execute before the SomeOtherValidationHandler handler
    composition.WithValidationEvent<ValidateOrderProductAdd>()
        .RegisterHandlerBefore<SomeOtherValidationHandler, MyOrderProductAddValidationHandler>();

    // Register MyOrderProductAddValidationHandler to execute after the SomeOtherValidationHandler handler
    composition.WithValidationEvent<ValidateOrderProductAdd>()
        .RegisterHandlerAfter<SomeOtherValidationHandler, MyOrderProductAddValidationHandler>();
}
````

## Notification events


Notification events are events that fire, often immediately before and immediately after an action is about to be or has been executed, providing  you a means to run custom logic to react to that action occurring. This is useful for scenarios such as sending emails when an Order is finalized, or allowing you synchronize stock updates with an external system.

Notification events won't allow you to change the behavior of how Vendr runs, but they do provide you with an effective means of reacting to when changes occur.

### Example Notification event handler

An example of a Notification event handler would look something like this:

````csharp
public class MyOrderFinalizedHandler : NotificationEventHandlerBase<OrderFinalizedNotification>
{
    public override void Handle(OrderFinalizedNotification evt)
    {
        // Implement your custom logic here
    }
}

````

All Notification event handlers inherit from a base class `NotificationEventHandlerBase<TEvent>` where `TEvent` is the Type of the event the handler is for. They then have a `Handle` method which accepts an instance of the event type, and inside which you can perform your custom logic. 

### Registering a Notification event handler

Notification event handlers are [registered via a Composer](../dependency-injection/#registering-dependencies) using the `WithNotificationEvent<TEvent>()` composition extension method to identify the event you want to handle and then calling the `RegisterHandler<THandler>()` method to register your handler(s) for that event.


````csharp
public void Compose(Composition composition)
{
    composition.WithNotificationEvent<OrderFinalizedNotification>()
        .RegisterHandler<MyOrderFinalizedHandler>();
}
````

You can also control the order of when Notification event handlers run, before or after another Notification event handler, by registering them via the `RegisterHandlerBefore<THandler>()` or `RegisterHandlerAfter<THandler>()` methods respectively.

````csharp
public void Compose(Composition composition)
{
    // Register MyOrderFinalizedHandler to execute before the SomeOtherNotificationHandler handler
    composition.WithNotificationEvent<OrderFinalizedNotification>()
        .RegisterHandlerBefore<SomeOtherNotificationHandler, MyOrderFinalizedHandler>();

    // Register MyOrderFinalizedHandler to execute after the SomeOtherNotificationHandler handler
    composition.WithNotificationEvent<OrderFinalizedNotification>()
        .RegisterHandlerAfter<SomeOtherNotificationHandler, MyOrderFinalizedHandler>();
}
````