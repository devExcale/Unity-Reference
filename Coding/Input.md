# Input

Player input is the base of every game. Without player control, there would be no game.

## Input Manager

Unity automatically sets up an **Input Manager** that helps the developer wire the player input to the player control logic. The Manager can be found in `Edit > Project Settings > Input Manager`.

In the Input Manager a single dropdown called **Axes** can be found. The Axes groups all the possible controls, giving them a canonical name that can be used on the code.

> [!quote] External Reference
> 
> [Unity's documentation](https://docs.unity3d.com/2019.4/Documentation/Manual/class-InputManager.html) on the Input Manager, containing all the properties of the axes.

### Axes

Axes represent not a single input, but rather a group of inputs that control a certain aspect of the gameplay. For example, two default axes are the `Horizontal` axis and the `Vertical` axis, which control both the left/right and up/down movements, respectively.

A single axis can
- map positive and negative buttons for an action (e.g. *`D` moves right, `A` moves opposite to right i.e. left*);
- define analog sensitivity;
- map alt buttons to a control.

Unity provides some default axes, which can be overwritten or deleted. The Axes dropdown is actually an array, so to add more axis the `Size` property can be modified to adjust the array to the developer's needs.

## Input Querying

Unity's **Input API** provides different methods to retrieve user input.

> [!danger] Attention
> 
> The following table isn't complete, it's just a reference for myself.


| Return Type | Method                | Parameters          | Description                                                                           |
| ----------- | --------------------- | ------------------- | ------------------------------------------------------------------------------------- |
| `float`     | `Input.GetAxis`       | `string axisName`   | Get the value of the control axis. `Bounded [-1, 1]`                                  |
| `float`     | `Input.GetAxisRaw`    | `string axisName`   | Get the value of the control axis, with no smoothing. `Bounded [-1, 1]`               |
| `bool`      | `Input.GetButton`     | `string buttonName` | Get the value of the button, true while the button is being held.                     |
| `bool`      | `Input.GetButtonDown` | `string buttonName` | Get the value of the button, true when a button is pressed (no holding persistence).  |
| `bool`      | `Input.GetButtonUp`   | `string buttonName` | Get the value of the button, true when a button is released.                          |
| `bool`      | `Input.GetKey`        | `string buttonName` | Get the value of a single key, true while the key is being held.                      |
| `bool`      | `Input.GetKeyDown`    | `string buttonName` | Get the value of a single key, true when the key is pressed (no holding persistence). |
| `bool`      | `Input.GetKeyUp`      | `string buttonName` | Get the value of a single key, true when the key is released.                         |

> [!tip] Buttons
> 
> Button is just another way to refer to a (*boolean*) control axis, `buttonName` refers to an axis' name.
