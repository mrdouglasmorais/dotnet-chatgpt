# ChatGptMessage.Name property

Gets or sets the name of the author of this message.

```csharp
public string? Name { get; set; }
```

## Remarks

This property is required if role is function, and it should be the name of the function whose response is in the content. May contain a-z, A-Z, 0-9, and underscores, with a maximum length of 64 characters.

## See Also

* class [ChatGptRoles](../ChatGptRoles.md)
* class [ChatGptMessage](../ChatGptMessage.md)
* namespace [ChatGptNet.Models](../../ChatGptNet.md)

<!-- DO NOT EDIT: generated by xmldocmd for ChatGptNet.dll -->
