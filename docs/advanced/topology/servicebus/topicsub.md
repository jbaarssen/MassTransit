# Topic Subscriptions

To create a topic subscription which will forward messages to the receive endpoint:

```
cfg.ReceiveEndpoint(host, "input-queue", e =>
{
    e.Subscribe("topic-name");
    e.Subscribe<MessageType>();
})
```

The properties of the topic subscription may also be configured:

```
cfg.ReceiveEndpoint(host, "input-queue", e =>
{
    e.Subscribe("topic-name", x =>
    {
        x.AutoDeleteOnIdle = TimeSpan.FromMinutes(60);
    });
})
```

