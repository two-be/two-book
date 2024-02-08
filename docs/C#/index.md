---
tags:
  - C#
  - csharp
---

## Check a string property for null
```csharp
var user = new UserInfo();

Console.WriteLine(user.Username is { }); // false
Console.WriteLine(string.IsNullOrWhiteSpace(user.Username)); // true
Console.WriteLine(user.Username is { Length: > 0 }); // false
Console.WriteLine(user.Username is not null); // false
```

## SHA512
```csharp
using var sha = System.Security.Cryptography.SHA512.Create();
var utf8Bytes = Encoding.UTF8.GetBytes(value);
var hash = sha.ComputeHash(utf8Bytes);

var value = BitConverter.ToString(hash).Replace("-", string.Empty);
```