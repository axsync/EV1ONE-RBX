# EV1ONE API Documentation
**Written by ChatGPT - Im lazy ok?**

**EV1ONE** is an advanced wrapper around the Xeno executor framework, designed for interfacing with Roblox client processes. This API is built for automation, client management, and script execution with robust version control and attachment routines.

## Features
- Remote script execution
- Client process discovery
- Automatic update and dependency management
- Process attachment with focus control
- Version hijack for `identifyexecutor()`
- Virtual detachment mode

## Initialization
The API loads and initializes the `EV1ONE.dll` wrapper with optional console output.

```csharp
API.AttachAPI(bool console = false);
```

This checks for required files, downloads missing components, validates version integrity, and performs the attach routine if everything is valid.

## Client Management
### List attached clients:
```csharp
List<API.ClientInfo> clients = API.GetClientsList();
```

### Check if attached:
```csharp
bool status = API.IsAttached();
```

### Detach from Roblox:
```csharp
API.Detach();
API.DetachVirtually();
```

### Get current client PID:
```csharp
string pid = API.GetAttachedClientPID();
```

## Roblox Process Utilities
### Launch Roblox:
```csharp
API.LaunchRoblox();
```

### Kill all Roblox processes:
```csharp
API.KillRoblox();
```

### Check if Roblox is running:
```csharp
bool isRunning = API.IsRobloxOpen();
```

## Update Management
Automatically handled during `AttachAPI()`.

Manual checks:
```csharp
bool updating = API.IsUpdating();
bool failed = API.GetAttachFailed();
```

## Executor Identity
Override display name and version for identify spoofing:
```csharp
API.SetExecutorName("EV1ONE", "v1.0");
```

### Get current API version:
```csharp
string ver = API.GetAPIVersion();
```

## Build Requirements
- .NET Framework 4.8

## License
MIT License - Refer to `LICENSE` file.
