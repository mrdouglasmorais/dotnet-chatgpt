# IChatGptBuilderExtensions.WithCache&lt;TImplementation&gt; method

Defines a custom cache implementation for conversation handling.

```csharp
public static IChatGptBuilder WithCache<TImplementation>(this IChatGptBuilder builder, 
    ServiceLifetime lifetime = ServiceLifetime.Singleton)
    where TImplementation : class, IChatGptCache
```

| parameter | description |
| --- | --- |
| TImplementation | The implementation of [`IChatGptCache`](../IChatGptCache.md) to use. |
| builder | The [`IChatGptBuilder`](../IChatGptBuilder.md) object to configure. |
| lifetime | The ServiceLifetime of the service. |

## Return Value

The [`IChatGptBuilder`](../IChatGptBuilder.md) to further customize ChatGPT.

## See Also

* interface [IChatGptBuilder](../IChatGptBuilder.md)
* interface [IChatGptCache](../IChatGptCache.md)
* class [IChatGptBuilderExtensions](../IChatGptBuilderExtensions.md)
* namespace [ChatGptNet](../../ChatGptNet.md)

<!-- DO NOT EDIT: generated by xmldocmd for ChatGptNet.dll -->
