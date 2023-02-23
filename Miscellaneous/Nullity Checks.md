# Nullity Checks

Sometimes, when a variable is equal to `null`, it actually might not be `null`. For example, when a variable isn't initialized in the inspector, Unity assigns to it a *dummy object*, which is equivalent to `null`.

This dummy object can help the developer find bugs and discover unset variables, because it isn't a pure null but it can provide debugging information.

> [!tip] MissingReferenceException
> 
> When a variable isn't set in the Unity Editor, the exception that will show up if trying to access the variable is `MissingReferenceException`, not `NullReferenceException`.

## Nullity check in Constructor

During the constructor, a non-initialized serial variable will *ALWAYS* be a pure `null`. This is because all variables initialized from the Editor will be set after the object's construction, meaning that all non-initialized serial variables won't hold any object.

> [!warning] Serial Assignment
> 
> As a consequence, editor assignment can't be checked in the constructor, but rather in another method (e.g. `Start`, `OnEnable`).

> [!example] External Resources
> 
> [Custom == operator, should we keep it?](https://blog.unity.com/technology/custom-operator-should-we-keep-it)
> 
> *Unity's blog (quite old) on the equals [operator override](/Miscellaneous/Operators%20Override.md) and nullity checks.*
