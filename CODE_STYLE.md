# Darthsae's Official Unofficial Personal Code Style and Architectural Style Guide

This is my personal style.

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
- **Private Member Variable/Function**: `_` prefix, if this is reserved in the language, use the `m_` prefix
- **Static Member Variable/Function**: `s_` prefix
- **Internal Member Variable**: `i_` prefix
- **Protected Member Variable**: `p_` prefix
- **Global Variable**: `g_` prefix
- **Parameters**: `a_` prefix 
- **Interface**: `I` prefix 

## Conventions

### Typing
Use static typing, or type hints; avoid type inferences when possible.

**BAD**

C#

```csharp
for (var a in intArrayObject) {
}
```

Python

```python
variable = 3
```

**GOOD**

C#

```csharp
for (int a in intArrayObject)  {
}
```

Python

```python
variable: int = 3
```

### Getters/Setters
Getters and setters should be used only if additional logic is required; this includes auto-generated getters and setters.
The usage of language-specific generation of getters and setters is allowed if getters and setters are required.

### Indentation
Use spaces with a width of 4 for indentation of code files, while data files, such as JSON, should use spaces with a width of 2. 
Avoid over-indentation that causes code to not fit on the screen; generally, avoid indentation greater than 6.

### Line Length
Avoid having lines that go off the screen; this is generally around 120 characters.

### Blocks
Keep opening brackets and braces inline; this is to keep vertical space more compact. 
Always have explicit flow control bodies.

### Functions
Avoid single-use functions that are only used in one or two places; if they can be inlined, then do so; logic hidden behind function calls is not clarity.

### Variables
Avoid unnecessary memory allocation and the creation of variables that are calculated and only used once.

### White Space
Use operator spacing for operators, and a space between opening braces and the parentheses of flow control statements.

```c
if (a < 4) {
    a++;
}
```

### Errors
Prefer the use of errors as values instead of exceptions.
Exceptions should only be used for states that are irrecoverable due to something *crucial* failing.

### Abstraction
Abstraction is not the ultimate goal; it is a tool to be used; do not make code more broken up just to abstract when it provides no benefit.

## Documentation

### Comments
Avoid comments about the function of code generally; this is best seen from the code, as comments become outdated.
Only if the code is too complex to understand on its own should comments be used.

### Code Documentation
You should have documentation for your code, via tools such as doxygen, XML, or docstrings.

#### General Guidelines
- **Be consistent** with documentation across files, classes, methods, and variables.
- **Be clear and concise** with descriptions, only use longer descriptions when necessary.

---

#### File Headers
Each file should include a header comment describing the file's purpose and what is in it.

---

#### Namespaces
Namespaces should have a description to clarify their purpose, what belongs in them, and their scope.

---

#### Classes/Structs
Classes and structs should be documented with a summary of their purpose, along with detailed descriptions for constructors, methods, and member variables.

---

#### Type Aliasing
Provide clear descriptions of type alias declarations.

---

#### Variables
Global variables and public members should be documented as to their purpose and the data they hold.
This should include any important information relating to its use.

---

#### Functions / Methods
Every function or method must include a description of its parameters, return values, and the purpose of the function.

---

#### Enums
Each enumerator in an enum should be documented.

---

#### Templates/Generics
Template parameters should be described in detail.

---

## EXAMPLES

### C++

```cpp
/**
 * @file MyClass.h
 * @brief Header file for the MyClass class.
 *
 * Detailed description of the file, including purpose and usage details if necessary.
 */

/**
 * @namespace MyNamespace
 * @brief Brief description of the namespace.
 */
namespace MyNamespace {
    /**
     * @class MyClass
     * @brief Brief description of the class.
     *
     * Detailed description of the class, including purpose and design notes.
     */
    class MyClass {
    public:
        /**
         * @brief Constructs a new MyClass object.
         * @param a_value The value to initialize.
         */
        MyClass(int a_value);
    
        /**
         * @brief Retrieves the stored value.
         * @return The current value.
         */
        int GetValue() const;
    
    private:
        int m_value; ///< Brief description of the member variable.
    };

    /**
     * @struct MyStruct
     * @brief Brief description of the struct.
     *
     * Detailed description of the struct, including purpose and design notes.
     */
    struct MyStruct {
        int valueOne; ///< Brief description of the member variable.
        int valueTwo; ///< Brief description of the member variable.
    };
}
```

### C#

```csharp
/// <summary>
/// Brief description of the namespace.
/// </summary>
namespace MyNamespace {
    /// <summary>
    /// Detailed description of the enum.
    /// </summary>
    public enum MyEnum {
        STATE_ONE = 0,  //
        STATE_TWO = 1,  //
        STATE_THREE = 2 //
    }


    /// <summary>
    /// Detailed description of the interface.
    /// </summary>
    public interface IMyInterface {
        /// <summary>
        /// Detailed description of the function.
        /// </summary>
        /// <returns>
        /// Brief description of the return.
        /// </returns>
        public int GetValue();
    }


    /// <summary>
    /// Detailed description of the class.
    /// </summary>
    public class MyClass : IMyInterface {
        protected int p_value;

        /// <summary>
        /// Detailed description of the class.
        /// </summary>
		/// <param name="a_value">
        /// Brief description of the parameter.
        /// </param>
        public MyClass(int a_value = 24) {
            p_value = a_value;
        }

        /// <summary>
        /// Detailed description of the function.
        /// </summary>
        /// <returns>
        /// Brief description of the return.
        /// </returns>
        public int GetValue() {
            return p_value;
        }
    }
}
```

### Python

```python
class MyEnum(Enum):
    """Brief description of the enum.
	"""

    VALUE_ONE = 0
    """Brief description of the enumerator."""
    VALUE_TWO = 1
    """Brief description of the enumerator."""
    VALUE_THREE = 2
    """Brief description of the enumerator."""

class MyClass:
    """Brief description of the class.
    """

    s_EnumTypes: list[MyEnum] = []
    """Brief description of the static variable."""

    def __init__(self, a_amount: float):
        """Brief description of the constructor.

        Args:
            a_amount (float): Brief description of the parameter.
        """

        self._amount = a_amount
        """Brief description of the member variable.
        """

    def SetAmount(self, a_amount: float) -> None:
        """Brief description of the function.

        Args:
            a_amount (float): Brief description of the parameter.
        """

        self._amount = self._amount * len(MyClass.EnumTypes) / (self._amount - a_amount)

    def GetAmount(self) -> float:
        """Brief description of the function.

        Returns:
            float: Description of the return.
        """

        return self._amount * 4
```
