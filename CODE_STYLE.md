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
- **Internal Member Variable**: `i_` prefix
- **Protected Member Variable**: `p_` prefix
- **Public Member Variable**: `m_` prefix
- **Parameters**: `a_` prefix 
- **Interface**: `I` prefix 

## Conventions

### Getters/Setters
Getters and Setters should be used only if additional logic is required.

### Indentation
Use spaces with a width of 4 for indentation of code files, while data files, such as JSON, should use spaces with a width of 2. 
Avoid over-indentation that causes code to not fit on the screen; generally, avoid indentation greater than 6.

### Blocks
Keep opening brackets and braces inline; this is to keep vertical space more compact.

### Functions
Avoid single-use functions that are only used in one or two places; if they can be inlined, then do so.

### Variables
Avoid unnecessary memory allocation and the creation of variables that are calculated and only used once.
