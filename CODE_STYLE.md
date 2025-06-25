This is just my general style.

## Naming Conventions

### Cases
- **Functions**: `PascalCase`
- **Classes/Structs**: `PascalCase`
- **Namespaces**: `PascalCase`
- **Folders**: `PascalCase`
- **File Names**: `PascalCase`
- **Variables**: `camelCase`
- **Constant Variables**: `MACRO_CASE`
- **Static Variables**: `PascalCase`
- **Template Parameters**: `PascalCase`
- **Function Parameters**: `camelCase`
- **Lambdas**: `camelCase`
- **Aliases**: `PascalCase`
- **Guards/Macros**: `MACRO_CASE`
- **Enum Type Names**: `PascalCase`
- **Enum Value Names**: `MACRO_CASE`

### Hungarian Notation
- **Private Member Variable/Function**: `_` prefix
- **Static Member Variable/Function**: `s_` prefix
- **Internal Member Variable**: `i_` prefix
- **Protected Member Variable**: `p_` prefix
- **Global Variable**: `g_` prefix
- **Parameters**: `a_` prefix 
- **Interface**: `I` prefix 

## Conventions

### Static Typing
Use static typing, or type hints.

### Getters/Setters
Getters and setters should be used only if additional logic is required; this includes auto-generated getters and setters.
Usage of language-specific methods of auto-generation of getters and setters is allowed if getters and setters are needed.

### Indentation
Use spaces with a width of 4 for indentation of code files, while data files, such as JSON, should use spaces with a width of 2. 
Avoid over-indentation that causes code to not fit on the screen; generally, avoid indentation greater than 6.

### Line Length
Avoid having lines that go off the screen; this is generally around 120 characters.

### Blocks
Keep opening brackets and braces inline; this is to keep vertical space more compact, and avoid using implicit if statement bodies.

### Functions
Avoid single-use functions that are only used in one or two places; if they can be inlined, then do so.

### Variables
Avoid unnecessary memory allocation and the creation of variables that are calculated and only used once.

### White Space
Use operator spacing for operators, and a space between opening braces and the parentheses of flow control statements.

## Documentation

### Comments
Avoid comments about the function of code generally; this is best seen from the code, as comments become outdated.
If the code is too complex to understand, then the usage of comments is advised, but ensure they are kept up to date.

## EXAMPLES

### C++

```cpp
class MyClass {
public:
    MyClass(int a_param1, double a_param2);

    int MyMethod(int a_value) const;

private:
    int _privateMemberVariable;
};

struct MyStruct {
    int m_x;
    int m_y;
};
```

### C#

```csharp
namespace MyNamespace {
    public enum MyEnum {
        STATE_ONE = 0,
        STATE_TWO = 1,
        STATE_THREE = 2
    }

    public interface IMyInterface {
        public int GetValue();
    }

    public class MyClass : IMyInterface {
        protected int p_value;

        public MyClass(int a_value = 24) {
            p_value = a_value;
        }

        public int GetValue() {
            return p_value;
        }
    }
}
```

### Python

```python
class MyEnum(Enum):
    VALUE_ONE = 0
    VALUE_TWO = 1
    VALUE_THREE = 2

class MyClass:
    EnumTypes: list[MyEnum] = []

    def __init__(self, a_amount: float):
        self._amount = a_amount

    def SetAmount(self, a_amount: float) -> None:
        self._amount = self._amount * len(MyClass.EnumTypes) / (self._amount - a_amount)

    def GetAmount(self) -> float:
        return self._amount * 4
```
