---
title: EnumerableExtensions
description: API reference for EnumerableExtensions in Vendr, the eCommerce solution for Umbraco v8+
---
## EnumerableExtensions

Extensions for enumerable sources

```csharp
public static class EnumerableExtensions
```

**Namespace**
* [Vendr.Core](../)

### Methods

#### Diff&lt;T&gt; (1 of 2)

```csharp
public static EnumerableDiff<T> Diff<T>(this IEnumerable<T> current, IEnumerable<T> previous)
```

---

#### Diff&lt;T&gt; (2 of 2)

```csharp
public static EnumerableDiff<T> Diff<T>(this IEnumerable<T> current, IEnumerable<T> previous, 
    Func<T, object> idAccessor, bool deep = false)
```


---

#### Diff&lt;TKey,TValue&gt;

```csharp
public static DictionaryDiff<TKey, TValue> Diff<TKey, TValue>(
    this IDictionary<TKey, TValue> current, IDictionary<TKey, TValue> previous, bool deep = false)
```


---

#### Extract&lt;T&gt;

```csharp
public static T Extract<T>(this List<T> list, Predicate<T> match)
```


---

#### Sum (1 of 3)

```csharp
public static Price Sum(this IEnumerable<AppliedDiscount> discounts, Guid currencyId)
```

---

#### Sum (2 of 3)

```csharp
public static Amount Sum(this IEnumerable<AppliedGiftCard> giftCards, Guid currencyId)
```

---

#### Sum (3 of 3)

```csharp
public static Amount Sum(this IEnumerable<Amount> amounts, Guid currencyId)
```


<!-- DO NOT EDIT: generated by xmldocmd for Vendr.Core.dll -->
