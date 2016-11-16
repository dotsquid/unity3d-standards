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

If you want to make your private field visible in Inspector and do not break encapsulation use *SerializeField* attribute:

```cs
public class Foo : MonoBehaviour
{
    [SerializeField]
    privare int number;
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
- Insert space between slash and text.
- Put dot at the end of a comment.
- Use shortcut keys to comment or uncomment multiple lines. It is way more faster than putting multiLine comments.
- Write comments only if they are useful. Do not comment everything.
- Write comments on something that is potentially confusing.
- Think about other developers who work with you. Is your code good enough to understand it without comment?

### Unused code
Delete unused code. Delete empty methods. If it is a Unity callback method like Start or Update it will be executed even if it is empty, this can slow the game down a bit.

### Animation events
If you have a method that is callback for some animation event then name it with prefix:
```cs
public class Foo
{
    private void AnimEvent_PlayVoiceSound()
    {
    }
}
```
It is a common situation when someone finds such kind of method without prefix in its name. He finds out that there are no references to this method and deletes it as unused code.

### Member ordering
A class should not look like this:
```cs
public class Foo : MonoBehaviour
{
    public int LifeAmount;
    public Transform Boss;
    bool working;
    public GameObject Ground;
    public int EnemyAmount;
    public Transform Sword, Helmet;
}
```
Group members together by their type and access modifier.
It should look like this:
```cs
public class Foo : MonoBehaviour
{
    public int LifeAmount;
    public int EnemyAmount;
    public Transform Boss;
    public Transform Sword;
    public Transform Helmet;
    public GameObject Ground;
    private bool working;
}
```
Use the following order when you have to write something inside one of my class:
- Enums
- Structs
- Classes
- Interfaces
- Delegates
- Constant Fields
- Events
- Fields
- Properties
- Indexers
- Constructors
- Methods

Within each of these groups order by access:
- public
- protected
- internal
- private
- protected internal

Within each of the access groups, order by static, then non-static:
- static
- non-static

Do not forget order by readonly, then non-readonly : 
- readonly
- non-readonly

Also do not declare several variables in one line.







