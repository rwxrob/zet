# Docker Desktop Fatal .NET Error

No surprise here. The GUI killed it. I'm never using Docker Desktop
again, ever. It has permanently lost my trust. I'm going to miss
deadlines because of all the screwing around with getting WSL2 to work
with AnyConnect and then installing Docker into it.

Here's the error:

```
See the end of this message for details on invoking
just-in-time (JIT) debugging instead of this dialog box.

************** Exception Text **************
System.Threading.Tasks.TaskCanceledException: Cancellation token triggered before we finished reading from the stream.
   at HttpOverStream.ByLineReader.<ReadLineAsync>d__0.MoveNext()
--- End of stack trace from previous location where exception was thrown ---
   at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
   at System.Runtime.CompilerServices.TaskAwaiter.ThrowForNonSuccess(Task task)
   at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
   at HttpOverStream.Client.DialMessageHandler.<SendAsync>d__9.MoveNext()
--- End of stack trace from previous location where exception was thrown ---
   at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
   at System.Runtime.CompilerServices.TaskAwaiter.ThrowForNonSuccess(Task task)
   at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
   at Docker.Core.IPC.Client.<SendAsync>d__4.MoveNext() in C:\workspaces\PR-16024\src\github.com\docker\pinata\win\src\Docker.Core\IPC\Client.cs:line 41
--- End of stack trace from previous location where exception was thrown ---
   at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
   at System.Runtime.CompilerServices.TaskAwaiter.ThrowForNonSuccess(Task task)
   at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
   at System.Net.Http.HttpClient.<FinishSendAsyncBuffered>d__58.MoveNext()
--- End of stack trace from previous location where exception was thrown ---
   at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
   at System.Runtime.CompilerServices.TaskAwaiter.ThrowForNonSuccess(Task task)
   at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
   at Docker.ApiServices.LifecycleClient.<DockerStartAsync>d__4.MoveNext() in C:\workspaces\PR-16024\src\github.com\docker\pinata\win\src\Docker.ApiServices\LifecycleClient.cs:line 84
--- End of stack trace from previous location where exception was thrown ---
   at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
   at System.Runtime.CompilerServices.TaskAwaiter.ThrowForNonSuccess(Task task)
   at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
   at Docker.LinuxkitDaemonStartup.<StartAsync>d__5.MoveNext() in C:\workspaces\PR-16024\src\github.com\docker\pinata\win\src\Docker.Desktop\LinuxkitDaemonStartup.cs:line 30
--- End of stack trace from previous location where exception was thrown ---
   at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
   at System.Runtime.CompilerServices.TaskAwaiter.ThrowForNonSuccess(Task task)
   at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
   at Docker.Engines.WSL2.LinuxWSL2Engine.<DoStartAsync>d__26.MoveNext() in C:\workspaces\PR-16024\src\github.com\docker\pinata\win\src\Docker.Desktop\Engines\WSL2\LinuxWSL2Engine.cs:line 178
--- End of stack trace from previous location where exception was thrown ---
   at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
   at System.Runtime.CompilerServices.TaskAwaiter.ThrowForNonSuccess(Task task)
   at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
   at Docker.ApiServices.StateMachines.TaskExtensions.<WrapAsyncInCancellationException>d__0.MoveNext() in C:\workspaces\PR-16024\src\github.com\docker\pinata\win\src\Docker.ApiServices\StateMachines\TaskExtensions.cs:line 20
--- End of stack trace from previous location where exception was thrown ---
   at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
   at System.Runtime.CompilerServices.TaskAwaiter.ThrowForNonSuccess(Task task)
   at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
   at Docker.ApiServices.StateMachines.StartTransition.<DoRunAsync>d__5.MoveNext() in C:\workspaces\PR-16024\src\github.com\docker\pinata\win\src\Docker.ApiServices\StateMachines\StartTransition.cs:line 29
--- End of stack trace from previous location where exception was thrown ---
   at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
   at Docker.ApiServices.StateMachines.StartTransition.<DoRunAsync>d__5.MoveNext() in C:\workspaces\PR-16024\src\github.com\docker\pinata\win\src\Docker.ApiServices\StateMachines\StartTransition.cs:line 38
--- End of stack trace from previous location where exception was thrown ---
   at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
   at System.Runtime.CompilerServices.TaskAwaiter.ThrowForNonSuccess(Task task)
   at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
   at Docker.ApiServices.StateMachines.EngineStateMachine.<StartAsync>d__14.MoveNext() in C:\workspaces\PR-16024\src\github.com\docker\pinata\win\src\Docker.ApiServices\StateMachines\EngineStateMachine.cs:line 69
--- End of stack trace from previous location where exception was thrown ---
   at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
   at System.Runtime.CompilerServices.TaskAwaiter.ThrowForNonSuccess(Task task)
   at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
   at Docker.Engines.Engines.<StartAsync>d__21.MoveNext() in C:\workspaces\PR-16024\src\github.com\docker\pinata\win\src\Docker.Desktop\Engines\Engines.cs:line 114
--- End of stack trace from previous location where exception was thrown ---
   at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
   at System.Runtime.CompilerServices.TaskAwaiter.ThrowForNonSuccess(Task task)
   at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
   at Docker.Core.TaskExtension.<Forget>d__0.MoveNext() in C:\workspaces\PR-16024\src\github.com\docker\pinata\win\src\Docker.Core\Extensions.cs:line 30
--- End of stack trace from previous location where exception was thrown ---
   at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()


************** Loaded Assemblies **************
mscorlib
    Assembly Version: 4.0.0.0
    Win32 Version: 4.8.4360.0 built by: NET48REL1LAST_C
    CodeBase: file:///C:/Windows/Microsoft.NET/Framework64/v4.0.30319/mscorlib.dll
----------------------------------------
Docker Desktop
    Assembly Version: 1.0.0.0
    Win32 Version: 3.5.1.66090
    CodeBase: file:///C:/Program%20Files/Docker/Docker/Docker%20Desktop.exe
----------------------------------------
Docker.Core
    Assembly Version: 1.0.0.0
    Win32 Version: 3.5.1.66090
    CodeBase: file:///C:/Program%20Files/Docker/Docker/Docker.Core.DLL
----------------------------------------
Docker.WPF
    Assembly Version: 1.0.0.0
    Win32 Version: 3.5.1.66090
    CodeBase: file:///C:/Program%20Files/Docker/Docker/Docker.WPF.DLL
----------------------------------------
PresentationFramework
    Assembly Version: 4.0.0.0
    Win32 Version: 4.8.4360.0
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/PresentationFramework/v4.0_4.0.0.0__31bf3856ad364e35/PresentationFramework.dll
----------------------------------------
WindowsBase
    Assembly Version: 4.0.0.0
    Win32 Version: 4.8.4360.0 built by: NET48REL1LAST_C
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/WindowsBase/v4.0_4.0.0.0__31bf3856ad364e35/WindowsBase.dll
----------------------------------------
System.Core
    Assembly Version: 4.0.0.0
    Win32 Version: 4.8.4360.0 built by: NET48REL1LAST_C
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Core/v4.0_4.0.0.0__b77a5c561934e089/System.Core.dll
----------------------------------------
System
    Assembly Version: 4.0.0.0
    Win32 Version: 4.8.4360.0 built by: NET48REL1LAST_C
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System/v4.0_4.0.0.0__b77a5c561934e089/System.dll
----------------------------------------
PresentationCore
    Assembly Version: 4.0.0.0
    Win32 Version: 4.8.4360.0 built by: NET48REL1LAST_C
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_64/PresentationCore/v4.0_4.0.0.0__31bf3856ad364e35/PresentationCore.dll
----------------------------------------
System.Xaml
    Assembly Version: 4.0.0.0
    Win32 Version: 4.8.4360.0 built by: NET48REL1LAST_C
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Xaml/v4.0_4.0.0.0__b77a5c561934e089/System.Xaml.dll
----------------------------------------
Docker.ApiServices
    Assembly Version: 1.0.0.0
    Win32 Version: 3.5.1.66090
    CodeBase: file:///C:/Program%20Files/Docker/Docker/Docker.ApiServices.DLL
----------------------------------------
Docker.HttpApi
    Assembly Version: 1.0.0.0
    Win32 Version: 3.5.1.66090
    CodeBase: file:///C:/Program%20Files/Docker/Docker/Docker.HttpApi.DLL
----------------------------------------
System.Windows.Forms
    Assembly Version: 4.0.0.0
    Win32 Version: 4.8.4341.0 built by: NET48REL1LAST_C
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Windows.Forms/v4.0_4.0.0.0__b77a5c561934e089/System.Windows.Forms.dll
----------------------------------------
System.Drawing
    Assembly Version: 4.0.0.0
    Win32 Version: 4.8.4084.0 built by: NET48REL1
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Drawing/v4.0_4.0.0.0__b03f5f7f11d50a3a/System.Drawing.dll
----------------------------------------
System.Net.Http
    Assembly Version: 4.2.0.0
    Win32 Version: 4.6.26011.01
    CodeBase: file:///C:/Program%20Files/Docker/Docker/System.Net.Http.DLL
----------------------------------------
HttpOverStream.NamedPipe
    Assembly Version: 1.0.0.0
    Win32 Version: 1.0.0.0
    CodeBase: file:///C:/Program%20Files/Docker/Docker/HttpOverStream.NamedPipe.DLL
----------------------------------------
NLog
    Assembly Version: 4.0.0.0
    Win32 Version: 4.5.10.8381
    CodeBase: file:///C:/Program%20Files/Docker/Docker/NLog.DLL
----------------------------------------
System.Configuration
    Assembly Version: 4.0.0.0
    Win32 Version: 4.8.4190.0 built by: NET48REL1LAST_B
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Configuration/v4.0_4.0.0.0__b03f5f7f11d50a3a/System.Configuration.dll
----------------------------------------
System.Xml
    Assembly Version: 4.0.0.0
    Win32 Version: 4.8.4084.0 built by: NET48REL1
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Xml/v4.0_4.0.0.0__b77a5c561934e089/System.Xml.dll
----------------------------------------
Newtonsoft.Json
    Assembly Version: 11.0.0.0
    Win32 Version: 11.0.2.21924
    CodeBase: file:///C:/Program%20Files/Docker/Docker/Newtonsoft.Json.DLL
----------------------------------------
System.Numerics
    Assembly Version: 4.0.0.0
    Win32 Version: 4.8.4084.0 built by: NET48REL1
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Numerics/v4.0_4.0.0.0__b77a5c561934e089/System.Numerics.dll
----------------------------------------
System.Runtime.Serialization
    Assembly Version: 4.0.0.0
    Win32 Version: 4.8.4250.0 built by: NET48REL1LAST_C
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Runtime.Serialization/v4.0_4.0.0.0__b77a5c561934e089/System.Runtime.Serialization.dll
----------------------------------------
System.Data
    Assembly Version: 4.0.0.0
    Win32 Version: 4.8.4270.0 built by: NET48REL1LAST_C
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_64/System.Data/v4.0_4.0.0.0__b77a5c561934e089/System.Data.dll
----------------------------------------
System.ServiceModel
    Assembly Version: 4.0.0.0
    Win32 Version: 4.8.4250.0 built by: NET48REL1LAST_C
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.ServiceModel/v4.0_4.0.0.0__b77a5c561934e089/System.ServiceModel.dll
----------------------------------------
BITSReference5_0
    Assembly Version: 1.0.0.0
    Win32 Version: 1.0.0.0
    CodeBase: file:///C:/Program%20Files/Docker/Docker/BITSReference5_0.DLL
----------------------------------------
HttpOverStream
    Assembly Version: 1.0.0.0
    Win32 Version: 1.0.0.0
    CodeBase: file:///C:/Program%20Files/Docker/Docker/HttpOverStream.DLL
----------------------------------------
System.Threading.Tasks.Extensions
    Assembly Version: 4.2.0.1
    Win32 Version: 4.6.27818.01
    CodeBase: file:///C:/Program%20Files/Docker/Docker/System.Threading.Tasks.Extensions.DLL
----------------------------------------
System.Web.Http
    Assembly Version: 5.2.7.0
    Win32 Version: 5.2.61128.0
    CodeBase: file:///C:/Program%20Files/Docker/Docker/System.Web.Http.DLL
----------------------------------------
HttpOverStream.Client
    Assembly Version: 1.0.0.0
    Win32 Version: 1.0.0.0
    CodeBase: file:///C:/Program%20Files/Docker/Docker/HttpOverStream.Client.DLL
----------------------------------------
netstandard
    Assembly Version: 2.0.0.0
    Win32 Version: 4.8.4084.0
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/netstandard/v4.0_2.0.0.0__cc7b13ffcd2ddd51/netstandard.dll
----------------------------------------
System.ValueTuple
    Assembly Version: 4.0.3.0
    Win32 Version: 4.6.26515.06
    CodeBase: file:///C:/Program%20Files/Docker/Docker/System.ValueTuple.DLL
----------------------------------------
Bugsnag
    Assembly Version: 2.2.0.0
    Win32 Version: 2.2.0.0
    CodeBase: file:///C:/Program%20Files/Docker/Docker/Bugsnag.DLL
----------------------------------------
PresentationFramework.Aero2
    Assembly Version: 4.0.0.0
    Win32 Version: 4.8.4084.0 built by: NET48REL1
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/PresentationFramework.Aero2/v4.0_4.0.0.0__31bf3856ad364e35/PresentationFramework.Aero2.dll
----------------------------------------
Anonymously Hosted DynamicMethods Assembly
    Assembly Version: 0.0.0.0
    Win32 Version: 4.8.4360.0 built by: NET48REL1LAST_C
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_64/mscorlib/v4.0_4.0.0.0__b77a5c561934e089/mscorlib.dll
----------------------------------------
Microsoft.Toolkit.Uwp.Notifications
    Assembly Version: 1.5.1.0
    Win32 Version: 1.5.1.0
    CodeBase: file:///C:/Program%20Files/Docker/Docker/Microsoft.Toolkit.Uwp.Notifications.DLL
----------------------------------------
System.Runtime
    Assembly Version: 4.1.2.0
    Win32 Version: 4.6.25714.01
    CodeBase: file:///C:/Program%20Files/Docker/Docker/System.Runtime.DLL
----------------------------------------
Windows.UI
    Assembly Version: 255.255.255.255
    Win32 Version: 10.0.10011.16384
    CodeBase: file:///C:/WINDOWS/system32/WinMetadata/Windows.UI.winmd
----------------------------------------
Windows.Foundation
    Assembly Version: 255.255.255.255
    Win32 Version: 10.0.10011.16384
    CodeBase: file:///C:/WINDOWS/system32/WinMetadata/Windows.Foundation.winmd
----------------------------------------
System.Runtime.InteropServices.WindowsRuntime
    Assembly Version: 4.0.0.0
    Win32 Version: 4.8.4084.0
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Runtime.InteropServices.WindowsRuntime/v4.0_4.0.0.0__b03f5f7f11d50a3a/System.Runtime.InteropServices.WindowsRuntime.dll
----------------------------------------
Windows.Data
    Assembly Version: 255.255.255.255
    Win32 Version: 10.0.10011.16384
    CodeBase: file:///C:/WINDOWS/system32/WinMetadata/Windows.Data.winmd
----------------------------------------
System.Collections
    Assembly Version: 4.0.11.0
    Win32 Version: 4.6.25714.01
    CodeBase: file:///C:/Program%20Files/Docker/Docker/System.Collections.DLL
----------------------------------------
System.Runtime.CompilerServices.Unsafe
    Assembly Version: 4.0.4.1
    Win32 Version: 4.6.26919.02
    CodeBase: file:///C:/Program%20Files/Docker/Docker/System.Runtime.CompilerServices.Unsafe.DLL
----------------------------------------
Microsoft.Owin
    Assembly Version: 4.1.0.0
    Win32 Version: 4.1.81112.127
    CodeBase: file:///C:/Program%20Files/Docker/Docker/Microsoft.Owin.DLL
----------------------------------------
Owin
    Assembly Version: 1.0.0.0
    Win32 Version: 1.0
    CodeBase: file:///C:/Program%20Files/Docker/Docker/Owin.DLL
----------------------------------------
HttpOverStream.Server.Owin
    Assembly Version: 1.0.0.0
    Win32 Version: 1.0.0.0
    CodeBase: file:///C:/Program%20Files/Docker/Docker/HttpOverStream.Server.Owin.DLL
----------------------------------------
Microsoft.Owin.Hosting
    Assembly Version: 4.1.0.0
    Win32 Version: 4.1.81112.127
    CodeBase: file:///C:/Program%20Files/Docker/Docker/Microsoft.Owin.Hosting.DLL
----------------------------------------
System.Web.Http.Owin
    Assembly Version: 5.2.7.0
    Win32 Version: 5.2.61128.0
    CodeBase: file:///C:/Program%20Files/Docker/Docker/System.Web.Http.Owin.DLL
----------------------------------------
System.Net.Http.Formatting
    Assembly Version: 5.2.7.0
    Win32 Version: 5.2.61128.0
    CodeBase: file:///C:/Program%20Files/Docker/Docker/System.Net.Http.Formatting.DLL
----------------------------------------
SMDiagnostics
    Assembly Version: 4.0.0.0
    Win32 Version: 4.8.4250.0 built by: NET48REL1LAST_C
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/SMDiagnostics/v4.0_4.0.0.0__b77a5c561934e089/SMDiagnostics.dll
----------------------------------------
System.ServiceProcess
    Assembly Version: 4.0.0.0
    Win32 Version: 4.8.4084.0 built by: NET48REL1
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.ServiceProcess/v4.0_4.0.0.0__b03f5f7f11d50a3a/System.ServiceProcess.dll
----------------------------------------
UIAutomationProvider
    Assembly Version: 4.0.0.0
    Win32 Version: 4.8.4360.0 built by: NET48REL1LAST_C
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/UIAutomationProvider/v4.0_4.0.0.0__31bf3856ad364e35/UIAutomationProvider.dll
----------------------------------------
UIAutomationTypes
    Assembly Version: 4.0.0.0
    Win32 Version: 4.8.4360.0 built by: NET48REL1LAST_C
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/UIAutomationTypes/v4.0_4.0.0.0__31bf3856ad364e35/UIAutomationTypes.dll
----------------------------------------
System.Security
    Assembly Version: 4.0.0.0
    Win32 Version: 4.8.4261.0 built by: NET48REL1LAST_B
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Security/v4.0_4.0.0.0__b03f5f7f11d50a3a/System.Security.dll
----------------------------------------
Accessibility
    Assembly Version: 4.0.0.0
    Win32 Version: 4.8.4084.0 built by: NET48REL1
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/Accessibility/v4.0_4.0.0.0__b03f5f7f11d50a3a/Accessibility.dll
----------------------------------------
System.Data.SqlXml
    Assembly Version: 4.0.0.0
    Win32 Version: 4.8.4084.0 built by: NET48REL1
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Data.SqlXml/v4.0_4.0.0.0__b77a5c561934e089/System.Data.SqlXml.dll
----------------------------------------
System.ServiceModel.Internals
    Assembly Version: 4.0.0.0
    Win32 Version: 4.8.4250.0 built by: NET48REL1LAST_C
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.ServiceModel.Internals/v4.0_4.0.0.0__31bf3856ad364e35/System.ServiceModel.Internals.dll
----------------------------------------
System.Transactions
    Assembly Version: 4.0.0.0
    Win32 Version: 4.8.4084.0 built by: NET48REL1
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_64/System.Transactions/v4.0_4.0.0.0__b77a5c561934e089/System.Transactions.dll
----------------------------------------
System.IdentityModel
    Assembly Version: 4.0.0.0
    Win32 Version: 4.8.4250.0 built by: NET48REL1LAST_C
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.IdentityModel/v4.0_4.0.0.0__b77a5c561934e089/System.IdentityModel.dll
----------------------------------------
Microsoft.Transactions.Bridge
    Assembly Version: 4.0.0.0
    Win32 Version: 4.8.4084.0 built by: NET48REL1
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/Microsoft.Transactions.Bridge/v4.0_4.0.0.0__b03f5f7f11d50a3a/Microsoft.Transactions.Bridge.dll
----------------------------------------
System.EnterpriseServices
    Assembly Version: 4.0.0.0
    Win32 Version: 4.8.4084.0 built by: NET48REL1
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_64/System.EnterpriseServices/v4.0_4.0.0.0__b03f5f7f11d50a3a/System.EnterpriseServices.dll
----------------------------------------
System.Messaging
    Assembly Version: 4.0.0.0
    Win32 Version: 4.8.4084.0 built by: NET48REL1
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Messaging/v4.0_4.0.0.0__b03f5f7f11d50a3a/System.Messaging.dll
----------------------------------------
System.Runtime.DurableInstancing
    Assembly Version: 4.0.0.0
    Win32 Version: 4.8.4084.0 built by: NET48REL1
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Runtime.DurableInstancing/v4.0_4.0.0.0__31bf3856ad364e35/System.Runtime.DurableInstancing.dll
----------------------------------------
System.Web.Services
    Assembly Version: 4.0.0.0
    Win32 Version: 4.8.4084.0 built by: NET48REL1
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Web.Services/v4.0_4.0.0.0__b03f5f7f11d50a3a/System.Web.Services.dll
----------------------------------------
System.Runtime.WindowsRuntime
    Assembly Version: 4.0.0.0
    Win32 Version: 4.8.4084.0 built by: NET48REL1
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Runtime.WindowsRuntime/v4.0_4.0.0.0__b77a5c561934e089/System.Runtime.WindowsRuntime.dll
----------------------------------------
System.Numerics.Vectors
    Assembly Version: 4.1.4.0
    Win32 Version: 4.6.26515.06
    CodeBase: file:///C:/Program%20Files/Docker/Docker/System.Numerics.Vectors.DLL
----------------------------------------
Windows.Graphics
    Assembly Version: 255.255.255.255
    Win32 Version: 10.0.10011.16384
    CodeBase: file:///C:/WINDOWS/system32/WinMetadata/Windows.Graphics.winmd
----------------------------------------
Windows.System
    Assembly Version: 255.255.255.255
    Win32 Version: 10.0.10011.16384
    CodeBase: file:///C:/WINDOWS/system32/WinMetadata/Windows.System.winmd
----------------------------------------
Windows.Devices
    Assembly Version: 255.255.255.255
    Win32 Version: 10.0.10011.16384
    CodeBase: file:///C:/WINDOWS/system32/WinMetadata/Windows.Devices.winmd
----------------------------------------
Windows.Gaming
    Assembly Version: 255.255.255.255
    Win32 Version: 10.0.10011.16384
    CodeBase: file:///C:/WINDOWS/system32/WinMetadata/Windows.Gaming.winmd
----------------------------------------
Windows.ApplicationModel
    Assembly Version: 255.255.255.255
    Win32 Version: 10.0.10011.16384
    CodeBase: file:///C:/WINDOWS/system32/WinMetadata/Windows.ApplicationModel.winmd
----------------------------------------
Windows.Storage
    Assembly Version: 255.255.255.255
    Win32 Version: 10.0.10011.16384
    CodeBase: file:///C:/WINDOWS/system32/WinMetadata/Windows.Storage.winmd
----------------------------------------
Windows.Web
    Assembly Version: 255.255.255.255
    Win32 Version: 10.0.10011.16384
    CodeBase: file:///C:/WINDOWS/system32/WinMetadata/Windows.Web.winmd
----------------------------------------
Windows.Media
    Assembly Version: 255.255.255.255
    Win32 Version: 10.0.10011.16384
    CodeBase: file:///C:/WINDOWS/system32/WinMetadata/Windows.Media.winmd
----------------------------------------
Windows.Security
    Assembly Version: 255.255.255.255
    Win32 Version: 10.0.10011.16384
    CodeBase: file:///C:/WINDOWS/system32/WinMetadata/Windows.Security.winmd
----------------------------------------
System.Configuration.Install
    Assembly Version: 4.0.0.0
    Win32 Version: 4.8.4084.0 built by: NET48REL1
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Configuration.Install/v4.0_4.0.0.0__b03f5f7f11d50a3a/System.Configuration.Install.dll
----------------------------------------
System.Xml.Linq
    Assembly Version: 4.0.0.0
    Win32 Version: 4.8.4084.0 built by: NET48REL1
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Xml.Linq/v4.0_4.0.0.0__b77a5c561934e089/System.Xml.Linq.dll
----------------------------------------
System.ComponentModel.DataAnnotations
    Assembly Version: 4.0.0.0
    Win32 Version: 4.8.4084.0
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.ComponentModel.DataAnnotations/v4.0_4.0.0.0__31bf3856ad364e35/System.ComponentModel.DataAnnotations.dll
----------------------------------------
System.Net.IPNetwork
    Assembly Version: 2.1.2.0
    Win32 Version: 2.1.2.0
    CodeBase: file:///C:/Program%20Files/Docker/Docker/System.Net.IPNetwork.DLL
----------------------------------------

************** JIT Debugging **************
To enable just-in-time (JIT) debugging, the .config file for this
application or computer (machine.config) must have the
jitDebugging value set in the system.windows.forms section.
The application must also be compiled with debugging
enabled.

For example:

<configuration>
    <system.windows.forms jitDebugging="true" />
</configuration>

When JIT debugging is enabled, any unhandled exception
will be sent to the JIT debugger registered on the computer
rather than be handled by this dialog box.
```
