Inheritable class with a `Enter` and `Exit` method:

!!! info "States"

    A table of classes that inherit the State class.

Will require States to pass into the constructor.

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
