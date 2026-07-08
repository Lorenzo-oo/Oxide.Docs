---
title: Permissions
after: index
---

# Permissions

## Registering a permission

Before you're able to use a permission for your plugin, you first need to register the permission so that you're able to assign it to players or groups. By convention the permission name should start with the plugin's exact name (e.g. `myfirstplugin.use`). This isn't strictly enforced, but registering a permission without that prefix logs a warning, so always include it.

```csharp
namespace Oxide.Plugins
{
    [Info("MyFirstPlugin", "Author Name", "1.0.0")]
    public class MyFirstPlugin : RustPlugin
    {
        void Init() => permission.RegisterPermission("myfirstplugin.use", this);
    }
}
```

## Checking a player for a permission

To check if a player has a specific permission, you must first make sure the permission is registered, and both the registered permission and permission you're checking for are the same.

```csharp
namespace Oxide.Plugins;

[Info("MyFirstPlugin", "Author Name", "1.0.0")]
public class MyFirstPlugin : RustPlugin
{
    void Init() => permission.RegisterPermission("myfirstplugin.use", this);

    [ChatCommand("hello")]
    private void HelloCommand(BasePlayer player, string command, string[] args)
    {
        if(!permission.UserHasPermission(player.UserIDString, "myfirstplugin.use"))
        {
            PrintToChat(player, "You don't have permission to use this command!");
            return;
        }

        PrintToChat(player, "Hello, you have permission to use this command!");
    }
}
```
