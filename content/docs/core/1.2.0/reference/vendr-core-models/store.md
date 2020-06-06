---
title: Store
description: API reference for Store in Vendr, the eCommerce solution for Umbraco v8+
---
## Store

```csharp
public class Store : StoreReadOnly
```

**Inheritance**

* class [StoreReadOnly](../storereadonly/)

**Namespace**
* [Vendr.Core.Models](../)

### Methods

#### Create (1 of 2)

```csharp
public static Store Create(IUnitOfWork uow, string alias, string name)
```

---

#### Create (2 of 2)

```csharp
public static Store Create(IUnitOfWork uow, Guid id, string alias, string name)
```


---

#### AddGiftCardPropertyAlias

```csharp
public Store AddGiftCardPropertyAlias(string alias)
```


---

#### AddProductPropertyAlias

```csharp
public Store AddProductPropertyAlias(string alias)
```


---

#### AddProductUniquenessPropertyAlias

```csharp
public Store AddProductUniquenessPropertyAlias(string alias)
```


---

#### AllowUser (1 of 2)

```csharp
public Store AllowUser(IUser user)
```

---

#### AllowUser (2 of 2)

```csharp
public Store AllowUser(string userId)
```


---

#### AllowUserRole

```csharp
public Store AllowUserRole(string role)
```


---

#### AllowUserRoles

```csharp
public Store AllowUserRoles(IEnumerable<string> roles)
```


---

#### AllowUsers (1 of 2)

```csharp
public Store AllowUsers(IEnumerable<IUser> users)
```

---

#### AllowUsers (2 of 2)

```csharp
public Store AllowUsers(IEnumerable<string> userIds)
```


---

#### ClearGiftCardPropertyAliases

```csharp
public Store ClearGiftCardPropertyAliases()
```


---

#### ClearProductPropertyAliases

```csharp
public Store ClearProductPropertyAliases()
```


---

#### ClearProductUniquenessPropertyAliases

```csharp
public Store ClearProductUniquenessPropertyAliases()
```


---

#### DisableCookies

```csharp
public Store DisableCookies()
```


---

#### DisallowUser (1 of 2)

```csharp
public Store DisallowUser(IUser user)
```

---

#### DisallowUser (2 of 2)

```csharp
public Store DisallowUser(string userId)
```


---

#### DisallowUserRole

```csharp
public Store DisallowUserRole(string role)
```


---

#### DisallowUserRoles

```csharp
public Store DisallowUserRoles(IEnumerable<string> roles)
```


---

#### DisallowUsers (1 of 2)

```csharp
public Store DisallowUsers(IEnumerable<IUser> users)
```

---

#### DisallowUsers (2 of 2)

```csharp
public Store DisallowUsers(IEnumerable<string> userIds)
```


---

#### EnableCookies

```csharp
public Store EnableCookies(TimeSpan cookieTimeout)
```


---

#### RemoveGiftCardPropertyAlias

```csharp
public Store RemoveGiftCardPropertyAlias(string alias)
```


---

#### RemoveProductPropertyAlias

```csharp
public Store RemoveProductPropertyAlias(string alias)
```


---

#### RemoveProductUniquenessPropertyAlias

```csharp
public Store RemoveProductUniquenessPropertyAlias(string alias)
```


---

#### SetAlias

```csharp
public Store SetAlias(string alias)
```


---

#### SetAllowedUserRoles

```csharp
public Store SetAllowedUserRoles(IEnumerable<string> roles, 
    SetBehavior setBehavior = SetBehavior.Merge)
```


---

#### SetAllowedUsers (1 of 2)

```csharp
public Store SetAllowedUsers(IEnumerable<IUser> users, SetBehavior setBehavior = SetBehavior.Merge)
```

---

#### SetAllowedUsers (2 of 2)

```csharp
public Store SetAllowedUsers(IEnumerable<string> userIds, 
    SetBehavior setBehavior = SetBehavior.Merge)
```


---

#### SetCartNumberTemplate

```csharp
public Store SetCartNumberTemplate(string template)
```


---

#### SetConfirmationEmailTemplate (1 of 2)

```csharp
public Store SetConfirmationEmailTemplate(EmailTemplateReadOnly emailTemplate)
```

---

#### SetConfirmationEmailTemplate (2 of 2)

```csharp
public Store SetConfirmationEmailTemplate(Guid? emailTemplateId)
```


---

#### SetDefaultCountry (1 of 2)

```csharp
public Store SetDefaultCountry(CountryReadOnly country)
```

---

#### SetDefaultCountry (2 of 2)

```csharp
public Store SetDefaultCountry(Guid? countryId)
```


---

#### SetDefaultGiftCardEmailTemplate (1 of 2)

```csharp
public Store SetDefaultGiftCardEmailTemplate(EmailTemplateReadOnly emailTemplate)
```

---

#### SetDefaultGiftCardEmailTemplate (2 of 2)

```csharp
public Store SetDefaultGiftCardEmailTemplate(Guid? emailTemplateId)
```


---

#### SetDefaultOrderStatus (1 of 2)

```csharp
public Store SetDefaultOrderStatus(OrderStatusReadOnly orderStatus)
```

---

#### SetDefaultOrderStatus (2 of 2)

```csharp
public Store SetDefaultOrderStatus(Guid? orderStatusId)
```


---

#### SetDefaultTaxClass (1 of 2)

```csharp
public Store SetDefaultTaxClass(TaxClassReadOnly taxClass)
```

---

#### SetDefaultTaxClass (2 of 2)

```csharp
public Store SetDefaultTaxClass(Guid? taxClassId)
```


---

#### SetErrorEmailTemplate (1 of 2)

```csharp
public Store SetErrorEmailTemplate(EmailTemplateReadOnly emailTemplate)
```

---

#### SetErrorEmailTemplate (2 of 2)

```csharp
public Store SetErrorEmailTemplate(Guid? emailTemplateId)
```


---

#### SetErrorOrderStatus (1 of 2)

```csharp
public Store SetErrorOrderStatus(OrderStatusReadOnly orderStatus)
```

---

#### SetErrorOrderStatus (2 of 2)

```csharp
public Store SetErrorOrderStatus(Guid? orderStatusId)
```


---

#### SetGiftCardActivationMethod

```csharp
public Store SetGiftCardActivationMethod(GiftCardActivationMethod activationMethod)
```


---

#### SetGiftCardActivationOrderStatus (1 of 2)

```csharp
public Store SetGiftCardActivationOrderStatus(OrderStatusReadOnly orderStatus)
```

---

#### SetGiftCardActivationOrderStatus (2 of 2)

```csharp
public Store SetGiftCardActivationOrderStatus(Guid? orderStatusId)
```


---

#### SetGiftCardCodeLength

```csharp
public Store SetGiftCardCodeLength(int length)
```


---

#### SetGiftCardCodeTemplate

```csharp
public Store SetGiftCardCodeTemplate(string codeTemplate)
```


---

#### SetGiftCardPropertyAliases

```csharp
public Store SetGiftCardPropertyAliases(IEnumerable<string> aliases, 
    SetBehavior setBehavior = SetBehavior.Merge)
```


---

#### SetGiftCardValidityTimeframe

```csharp
public Store SetGiftCardValidityTimeframe(int numberOfDays)
```


---

#### SetName (1 of 2)

```csharp
public Store SetName(string name)
```

---

#### SetName (2 of 2)

```csharp
public Store SetName(string name, string alias)
```


---

#### SetNotificationEmailTemplates (1 of 2)

```csharp
public Store SetNotificationEmailTemplates(EmailTemplateReadOnly confirmationEmailTemplate, 
    EmailTemplateReadOnly errorEmailTemplate)
```

---

#### SetNotificationEmailTemplates (2 of 2)

```csharp
public Store SetNotificationEmailTemplates(Guid? confirmationEmailTemplateId, 
    Guid? errorEmailTemplateId)
```


---

#### SetOrderEditorConfig

```csharp
public Store SetOrderEditorConfig(string configPath)
```


---

#### SetOrderNumberTemplate

```csharp
public Store SetOrderNumberTemplate(string template)
```


---

#### SetOrderNumberTemplates

```csharp
public Store SetOrderNumberTemplates(string cartNumberTemplate, string orderNumberTemplate)
```


---

#### SetOrderStatuses (1 of 2)

```csharp
public Store SetOrderStatuses(OrderStatusReadOnly defaultOrderStatus, 
    OrderStatusReadOnly errorOrderStatus)
```

---

#### SetOrderStatuses (2 of 2)

```csharp
public Store SetOrderStatuses(Guid? defaultOrderStatusId, Guid? errorOrderStatusId)
```


---

#### SetPriceTaxInclusivity

```csharp
public Store SetPriceTaxInclusivity(bool pricesIncludeTax)
```


---

#### SetProductPropertyAliases

```csharp
public Store SetProductPropertyAliases(IEnumerable<string> aliases, 
    SetBehavior setBehavior = SetBehavior.Merge)
```


---

#### SetProductUniquenessPropertyAliases

```csharp
public Store SetProductUniquenessPropertyAliases(IEnumerable<string> aliases, 
    SetBehavior setBehavior = SetBehavior.Merge)
```


---

#### SetSortOrder

```csharp
public Store SetSortOrder(int order)
```


---

#### ShareStockFrom (1 of 2)

```csharp
public Store ShareStockFrom(StoreReadOnly store)
```

---

#### ShareStockFrom (2 of 2)

```csharp
public Store ShareStockFrom(Guid storeId)
```


---

#### StopSharingStock

```csharp
public Store StopSharingStock()
```


<!-- DO NOT EDIT: generated by xmldocmd for Vendr.Core.dll -->
