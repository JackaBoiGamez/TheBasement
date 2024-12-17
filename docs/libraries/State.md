Inheritable class with a `Enter` and `Exit` method:

!!! info "Inherited"

    State is a class that must be inherited by another class to be used!

```luau title="Example State Class"
local WalkingState = {}
WalkingState.__index = WalkingState

function WalkingState.new(): typeof(WalkingState)
    local self = State.new()
    setmetatable(self, WalkingState)
    return self
end

-- Only using player as an example you can pass in other arguments
function WalkingState:Enter(player: Player)
    print(`{player.Name} Walking`)
end

function WalkingState:Exit(player: Player)
    print(`{player.Name} No Longer Walking`)
end

return WalkingState
```
