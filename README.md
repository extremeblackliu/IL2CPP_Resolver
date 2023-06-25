## IL2CPP Resolver(Old)
A run-time API resolver for IL2CPP Unity.

Since IL2CPP_Resolver is being rewrite to single-header, this branch is maintaining for saving old codestyle. will still keep updating

[External Version](https://github.com/extremeblackliu/IL2CPP_Resolver_External)

### Quick Example
```cpp
#include "Main.hpp"

void SomeFunction()
{
    IL2CPP::Initialize(); // This needs to be called once!

    Unity::CGameObject* pLocal = Unity::GameObject::Find("LocalPlayer");
    Unity::CComponent* pLocalData = pLocal->GetComponent("PlayerData");
    pLocalData->SetMemberValue<bool>("CanFly", true);
}
```

### Registering OnUpdate Callback
```cpp
void OurUpdateFunction()
{
    // Your special code...
}

void OnLoad()
{
    IL2CPP::Initialize();

    IL2CPP::Callback::Initialize();
    IL2CPP::Callback::OnUpdate::Add(OurUpdateFunction);
}
```

More: https://sneakyevil.gitbook.io/il2cpp-resolver/
