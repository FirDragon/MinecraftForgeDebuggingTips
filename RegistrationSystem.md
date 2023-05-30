> Crash when registering an item, showing that the registration system is frozen.

This usually means that you try to create a new item outside of the registered event. You can only register when the registration event comes. You have two better options:
1. Subscribe to the event RegisterEvent and check if event.getRegistryKey() is the registration type you want.
2. DeferredRegister.create
The code refers to other mods