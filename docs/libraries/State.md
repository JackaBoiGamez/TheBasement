Inheritable class with a `Enter` and `Exit` method:

!!! info "Inherited"

    State is a class that must be inherited by another class to be used!

## Example Class

```luau title="WalkingState Class"
local WalkingState = {}
WalkingState.__index = WalkingState

function WalkingState.new(): typeof(WalkingState)
    return setmetatable(State.new("Walking"),WalkingState)
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

## Methods

You can pass in any arguments into these methods

`State:Enter(...)`

`State:Exit(...)`
