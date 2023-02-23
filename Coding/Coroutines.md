# Coroutines

Coroutines are a way to multitask between multiple jobs and to span tasks over time, without the need to bloat the [Update](?TK) method with checks every frame.

 Coroutines are a way to stop execution of a portion of code and to resume it at a later arbitrary time (frame count, engine time or real time).

> [!warning] Coroutines != Multithreading
> As the title says, coroutines aren't equivalent to and are not able of *multithreading*. Coroutines are executed on the thread that has started it.

> [!info] Coroutines and Unity
> Coroutines are implemented by the Unity framework, and are not native to C# / .NET framework.

## Handling Coroutines

Coroutines are handles with the methods `StartCoroutine` TK

## External Resources

> [!quote] Video Explanation
> [Unity Coroutines - What? Why? How?](https://www.youtube.com/watch?v=t4m8pmahbzY)
> 
> *This is an excellent video explaining what coroutines are, how to use them and how they work.*
