___
- Not all Windows APIs are documented on MSDN.
- The documented APIs we used so far operate in user mode.
- When calling a user mode API, we eventually end up in kernel mode.
- Windows APIs are an abstraction layer over the native API.
- These native API calls we are interested in, are defined in NTDLL.

