# EV1ONE API Documentation
**Documentation written by ChatGPT - Im lazy ok?**

**EV1ONE** is an advanced wrapper around the Xeno executor framework, designed for interfacing with Roblox client processes. This API is built for automation, client management, and script execution with robust version control and attachment routines.

## Features
- Remote script execution
- Client process discovery
- Automatic update and dependency management
- Process attachment with focus control
- Identity spoofing for `identifyexecutor` & `User Agent`

## Initialization
Add the reference to your project and append this at the top of your code

```csharp
using EV1ONE;
```

Call this before using any methods, on Form Load or after InitializeComponent()

```csharp
Main.Initialize();
```

The API loads with optional xeno console window

```csharp
API.Attach(bool console = false);
```

This checks for required files, downloads missing components, validates version integrity, and performs the attach routine if everything is valid

## Execution
```csharp
API.Execute(string script);
```

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
```

### Get current client PID:
```csharp
string pid = API.GetAttachedClientPID();
```

### Launch Roblox | Bloxstrap | Fishstrap:
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
Automatically handled during `Attach()`

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
- Release | x64
- .NET Framework 4.8

## License
**Protected under EV1ONE License**  
**TAMPERING IS NOT ALLOWED | YOU CAN SKID BUT GIVE CREDITS**
