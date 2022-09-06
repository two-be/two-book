---
tags:
  - .NET Framework
  - ASP.NET
---

## JSON camelCase
```csharp
public static class WebApiConfig
{
    public static void Register(HttpConfiguration config)
    {
        // ..

        config.Formatters.JsonFormatter.SerializerSettings = new JsonSerializerSettings
        {
            ContractResolver = new CamelCasePropertyNamesContractResolver(),
            // Formatting = Formatting.Indented,
            // ReferenceLoopHandling = ReferenceLoopHandling.Ignore,
        };

        // ..
    }
}
```

## Return JSON Instead of XML
```csharp
public static class WebApiConfig
{
    public static void Register(HttpConfiguration config)
    {
        // ..

        config.Formatters.JsonFormatter.SupportedMediaTypes.Add(new MediaTypeHeaderValue("text/html"));

        // ..
    }
}
```