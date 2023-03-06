# Singleton

The singleton is a programming pattern useful for managing components that need have a whole-application lifetime and need just one instance of the script.

The singleton is useful for scripts like a [Game Manager](?TK)

## Benefits and Drawbacks

Benefits of the Singleton:

- **Globally accessible:** a singleton can be used to create a global access point to resources and services.
- **Control concurrency:** a singleton can be used to limit concurrent access to shared resources.

Drawbacks of the Singleton:

- **Unit testing:** if used multiple times in the same scene, the singleton pattern can turn [unit testing](?TK) hard to perform. This is because a manager will probably be dependent on another manager, which may or may not be set up in the scene, making unit testing impossible.
- **Laziness:**TK

## Snippets

- *Singleton class*

```csharp
public class Singleton<T> : Monobehaviour
		where T : Component
{
	
	private static T _instance;
	
	public static T Instance
	{
		get
		{
			if(_instance != null)
				return _instance;
			
			_instance = FindObjectOfType<T>();
			if(_instance != null)
				return _instance;
			
			GameObject obj = new GameObject(typeof(T).Name);
			_instance = obj.AddComponent<T>();
		}
	}
	
	public virtual void Awake()
	{
		if(_instance == null)
		{
			_instance = this as T;
			DontDestroyOnLoad(gameObject)
		}
		else
		{
			Destroy(gameObject);
		}
	}

}
```