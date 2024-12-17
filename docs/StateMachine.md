Class made to contain and switch between States:

!!! info "States"

    A table of classes that inherit the State class.

Will require States to pass into the constructor.

```lua title="States Table"
# States Table Example
local States: {[string]: typeof(State)} = {
    ["Walking"] = LoadingState.new(),
    ["Running"] = RunningState.new()
}

# Example Object Creation
local stateMachine = StateMachine.new(States)
```
