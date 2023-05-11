# Source 2013 imgui

This repo contains an imgui implementation for Source 2013 based on the one we developed for Strata Source (Portal 2: Community Edition, Momentum Mod, etc.)

## Integrating

1. Add this repo as a submodule to your Source mod
2. Include the VPC file in your client\_base.vpc
3. Add the following code to cdll\_client\_int.cpp

At the top of the file:
```cpp
#include "imgui/imgui_system.h"
```

Towards the end of `CHLClient::Init`:
```cpp
g_pImguiSystem->Init();
```

At the start of `CHLClient::Shutdown`:
```cpp
g_pImguiSystem->Shutdown();
```

4. That's it!

## Limitations

* Interop with vgui isn't the greatest, as we need to intercept input from vgui itself and redirect it to imgui. An invisible popup panel is used for this purpose.

## See Also

For an example of a standalone app in Source with imgui, [see this](https://github.com/ozxybox/Source-2013-Example-ImGui-App)

