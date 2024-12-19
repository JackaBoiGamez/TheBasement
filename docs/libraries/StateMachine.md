Class made to contain and switch between States:

## Constructor

??? info "States"

    A table of classes that inherit the State class.

Requires Name of Inital State and a Table of States

```luau title="States Table"
-- States Table Example
local States: {[string]: typeof(State)} = {
    ["Walking"] = LoadingState.new(),
    ["Running"] = RunningState.new()
}

-- Example Object Creation
local stateMachine = StateMachine.new("Walking", States, ...)
```

## Methods

You can switch states by simply calling `:ChangeState("StateName", ...)`

```luau title="Switch State Example"
stateMachine:ChangeState("Running", player)
```

## Signals

You can connect to the `OnStateChange` signal for event based scripts.

```luau title="OnStateChange Example"
stateMachine.OnStateChange:Connect(function(newState, currentState)
    if currentState.name ~= "Running" or newState.name ~= "Walking" return end
    print("Player Slowed Down :(")
end)
```
