---
tags:
  - C#
  - csharp
---

## SHA512
```csharp
using var sha = System.Security.Cryptography.SHA512.Create();
var utf8Bytes = Encoding.UTF8.GetBytes(value);
var hash = sha.ComputeHash(utf8Bytes);

var value = BitConverter.ToString(hash).Replace("-", string.Empty);
```