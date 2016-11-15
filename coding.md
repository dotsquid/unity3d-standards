## C# code formatting guidelines

### Private members
This convention remains unchanged from standard C#. ALWAYS put the private keyword. It is way more readable:
```cs
public class Foo
{
	privare int number;

	private void Bar()
	{
	}
}
```

### Braces
By default Unity makes a new script look like this:
```cs
public class Foo : MonoBehaviour {

        // Use this for initialization
	void Start () {
	}
}
```
Always place open braces on new lines:
```cs
public class Foo : MonoBehaviour
{
        // Use this for initialization
	void Start ()
	{	
	}
}
```
### Comments
Use XML documentation comments everywhere except a method scope. Use single line comments inside methods.
```cs
///<summary>
/// XML documentation comment.
///</summary>
public class Foo
{
	///<summary>
	/// XML documentation comment.
	///</summary>
	public void Bar()
	{
	    // Single line comment.
	    int number = 0;
	}
}
```
Some rules about comments:
- insert space between slash and text;
- put dot at the end of a comment;
- use shortcut keys to comment or uncomment multiple lines. It is way more faster than putting multiLine comments;
- put comments only if they are useful. Do not comment everything;
- put comments on something that is potentially confusing;
- think about other developers who work on the same project. Is your code good enough to understand it without comment?
