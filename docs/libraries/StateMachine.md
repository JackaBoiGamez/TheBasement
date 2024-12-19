Class made to contain and switch between States:

!!! info "States"

    A table of classes that inherit the State class.

Will require States to pass into the constructor.

```luau title="States Table"
-- States Table Example
local States: {[string]: typeof(State)} = {
    ["Walking"] = LoadingState.new(),
    ["Running"] = RunningState.new()
}

-- Example Object Creation
local stateMachine = StateMachine.new(States)
```

You can switch states by simply calling `:ChangeState("StateName", arguments)`

```luau title="Switch State Example"
stateMachine:ChangeState("Running", player)
```

You can connect to the `OnStateChange` signal for event based scripts.

```luau title="OnStateChange Example"
stateMachine.OnStateChange:Connect(function(newState, currentState)
    if currentState.name ~= "Running" or newState.name ~= "Walking" return end
    print("Player Slowed Down :(")
end)
```
