# IChatGptClient.DeleteConversationAsync method

Deletes a chat conversation, clearing all the history.

```csharp
public Task DeleteConversationAsync(Guid conversationId, bool preserveSetup = false, 
    CancellationToken cancellationToken = default)
```

| parameter | description |
| --- | --- |
| conversationId | The unique identifier of the conversation. |
| preserveSetup | `true` to maintain the system message that has been specified with the [`SetupAsync`](./SetupAsync.md) method. |
| cancellationToken | The token to monitor for cancellation requests. |

## Return Value

The Task corresponding to the asynchronous operation.

## See Also

* method [SetupAsync](./SetupAsync.md)
* interface [IChatGptClient](../IChatGptClient.md)
* namespace [ChatGptNet](../../ChatGptNet.md)

<!-- DO NOT EDIT: generated by xmldocmd for ChatGptNet.dll -->
