---

## .NET formatting rules

The formatting rules in this section apply to both C# and Visual Basic.

- [Organize usings](#organize-using-directives)
  - dotnet_sort_system_directives_first

### Organize using directives

These formatting rules concern the sorting and display of `using` directives and `Imports` statements.

Example *.editorconfig* file:

```ini
# .NET formatting rules
[*.{cs,vb}]
dotnet_sort_system_directives_first = true
```

#### dotnet\_sort\_system\_directives_first

|Property|Value|
|-|-|
| **Option name** | dotnet_sort_system_directives_first |
| **Applicable languages** | C# and Visual Basic |
| **Introduced version** | Visual Studio 2017 version 15.3 |
| **Option values** | `true` - Sort `System.*` `using` directives alphabetically, and place them before other using directives.<br /><br />`false` - Do not place `System.*` `using` directives before other `using` directives. |

Code examples:

```csharp
// dotnet_sort_system_directives_first = true
using System.Collections.Generic;
using System.Threading.Tasks;
using Octokit;

// dotnet_sort_system_directives_first = false
using System.Collections.Generic;
using Octokit;
using System.Threading.Tasks;
```

## C# formatting rules

The formatting rules in this section apply only to C# code.

- [Newline options](#new-line-options)
  - csharp_new_line_before_open_brace
  - csharp_new_line_before_else
  - csharp_new_line_before_catch
  - csharp_new_line_before_finally
  - csharp_new_line_before_members_in_object_initializers
  - csharp_new_line_before_members_in_anonymous_types
  - csharp_new_line_between_query_expression_clauses
- [Indentation options](#indentation-options)
  - csharp_indent_case_contents
  - csharp_indent_switch_labels
  - csharp_indent_labels
  - csharp_indent_block_contents
  - csharp_indent_braces
- [Spacing options](#spacing-options)
  - csharp_space_after_keywords_in_control_flow_statements
  - csharp_space_around_binary_operators
  - csharp_space_after_comma
  - csharp_space_after_dot
  - csharp_space_before_dot
  - csharp_space_after_semicolon_in_for_statement
  - csharp_space_around_declaration_statements
- [Wrap options](#wrap-options)
  - csharp_preserve_single_line_statements
  - csharp_preserve_single_line_blocks
- [Using directive options](#using-directive-options)
  - csharp_using_directive_placement
- [Namespace options](#namespace-options)
  - csharp_style_namespace_declarations

### New-line options

These formatting rules concern the use of new lines to format code.

Example *.editorconfig* file:

```ini
# CSharp formatting rules:
[*.cs]
csharp_new_line_before_open_brace = methods, properties, control_blocks, types
csharp_new_line_before_else = true
csharp_new_line_before_catch = true
csharp_new_line_before_finally = true
csharp_new_line_before_members_in_object_initializers = true
csharp_new_line_before_members_in_anonymous_types = true
csharp_new_line_between_query_expression_clauses = true
```

#### csharp\_new\_line\_before\_open_brace

This rule concerns whether an open brace `{` should be placed on the same line as the preceding code, or on a new line. For this rule, you specify **all**, **none**, or one or more code elements such as **methods** or **properties**, to define when this rule should be applied. To specify multiple code elements, separate them with a comma (,).

|Property|Value|
|-|-|
| **Option name** | csharp_new_line_before_open_brace |
| **Applicable languages** | C# |
| **Introduced version** | Visual Studio 2017 version 15.3 |
| **Option values** | `all` - Require braces to be on a new line for all expressions ("Allman" style).<br /><br />`none` - Require braces to be on the same line for all expressions ("K&R").<br /><br />`accessors`, `anonymous_methods`, `anonymous_types`, `control_blocks`, `events`, `indexers`, `lambdas`, `local_functions`, `methods`, `object_collection_array_initializers`, `properties`, `types` - Require braces to be on a new line for the specified code element ("Allman" style). |

Code examples:

```csharp
// csharp_new_line_before_open_brace = all
void MyMethod()
{
    if (...)
    {
        ...
    }
}

// csharp_new_line_before_open_brace = none
void MyMethod() {
    if (...) {
        ...
    }
}
```

#### csharp\_new\_line\_before_else

|Property|Value|
|-|-|
| **Option name** | csharp_new_line_before_else |
| **Applicable languages** | C# |
| **Introduced version** | Visual Studio 2017 version 15.3 |
| **Option values** | `true` - Place `else` statements on a new line.<br /><br />`false` - Place `else` statements on the same line. |

Code examples:

```csharp
// csharp_new_line_before_else = true
if (...) {
    ...
}
else {
    ...
}

// csharp_new_line_before_else = false
if (...) {
    ...
} else {
    ...
}
```

#### csharp\_new\_line\_before_catch

|Property|Value|
|-|-|
| **Option name** | csharp_new_line_before_catch |
| **Applicable languages** | C# |
| **Introduced version** | Visual Studio 2017 version 15.3 |
| **Option values** | `true` - Place `catch` statements on a new line.<br /><br />`false` - Place `catch` statements on the same line. |

Code examples:

```csharp
// csharp_new_line_before_catch = true
try {
    ...
}
catch (Exception e) {
    ...
}

// csharp_new_line_before_catch = false
try {
    ...
} catch (Exception e) {
    ...
}
```

#### csharp\_new\_line\_before_finally

|Property|Value|
|-|-|
| **Option name** | csharp_new_line_before_finally |
| **Applicable languages** | C# |
| **Introduced version** | Visual Studio 2017 version 15.3 |
| **Option values** | `true` - Require `finally` statements to be on a new line after the closing brace.<br /><br />`false` - Require `finally` statements to be on the same line as the closing brace. |

Code examples:

```csharp
// csharp_new_line_before_finally = true
try {
    ...
}
catch (Exception e) {
    ...
}
finally {
    ...
}

// csharp_new_line_before_finally = false
try {
    ...
} catch (Exception e) {
    ...
} finally {
    ...
}
```

#### csharp\_new\_line\_before\_members\_in\_object_initializers

|Property|Value|
|-|-|
| **Option name** | csharp_new_line_before_members_in_object_initializers |
| **Applicable languages** | C# |
| **Introduced version** | Visual Studio 2017 version 15.3 |
| **Option values** | `true` - Require members of object initializers to be on separate lines<br /><br />`false` - Require members of object initializers to be on the same line |

Code examples:

```csharp
// csharp_new_line_before_members_in_object_initializers = true
var z = new B()
{
    A = 3,
    B = 4
}

// csharp_new_line_before_members_in_object_initializers = false
var z = new B()
{
    A = 3, B = 4
}
```

#### csharp\_new\_line\_before\_members\_in\_anonymous_types

|Property|Value|
|-|-|
| **Option name** | csharp_new_line_before_members_in_anonymous_types |
| **Applicable languages** | C# |
| **Introduced version** | Visual Studio 2017 version 15.3 |
| **Option values** | `true` - Require members of anonymous types to be on separate lines<br /><br />`false` - Require members of anonymous types to be on the same line |

Code examples:

```csharp
// csharp_new_line_before_members_in_anonymous_types = true
var z = new
{
    A = 3,
    B = 4
}

// csharp_new_line_before_members_in_anonymous_types = false
var z = new
{
    A = 3, B = 4
}
```

#### csharp_new_line_between_query_expression_clauses

|Property|Value|
|-|-|
| **Option name** | csharp_new_line_between_query_expression_clauses |
| **Applicable languages** | C# |
| **Introduced version** | Visual Studio 2017 version 15.3 |
| **Option values** | `true` - Require elements of query expression clauses to be on separate lines<br /><br />`false` - Require elements of query expression clauses to be on the same line |

Code examples:

```csharp
// csharp_new_line_between_query_expression_clauses = true
var q = from a in e
        from b in e
        select a * b;

// csharp_new_line_between_query_expression_clauses = false
var q = from a in e from b in e
        select a * b;
```

### Indentation options

These formatting rules concern the use of indentation to format code.

Example *.editorconfig* file:

```ini
# CSharp formatting rules:
[*.cs]
csharp_indent_case_contents = true
csharp_indent_switch_labels = true
csharp_indent_block_contents = true
csharp_indent_braces = false
```

#### csharp\_indent\_case_contents

|Property|Value|
|-|-|
| **Option name** | csharp_indent_case_contents |
| **Applicable languages** | C# |
| **Introduced version** | Visual Studio 2017 version 15.3 |
| **Option values** | `true` - Indent `switch` case contents<br /><br />`false` - Do not indent `switch` case contents |

Code examples:

```csharp
// csharp_indent_case_contents = true
switch(c) {
    case Color.Red:
        Console.WriteLine("The color is red");
        break;
    case Color.Blue:
        Console.WriteLine("The color is blue");
        break;
    default:
        Console.WriteLine("The color is unknown.");
        break;
}

// csharp_indent_case_contents = false
switch(c) {
    case Color.Red:
    Console.WriteLine("The color is red");
    break;
    case Color.Blue:
    Console.WriteLine("The color is blue");
    break;
    default:
    Console.WriteLine("The color is unknown.");
    break;
}
```

#### csharp\_indent\_switch_labels

|Property|Value|
|-|-|
| **Option name** | csharp_indent_switch_labels |
| **Applicable languages** | C# |
| **Introduced version** | Visual Studio 2017 version 15.3 |
| **Option values** | `true` - Indent `switch` labels<br /><br />`false` - Do not indent `switch` labels |

Code examples:

```csharp
// csharp_indent_switch_labels = true
switch(c) {
    case Color.Red:
        Console.WriteLine("The color is red");
        break;
    case Color.Blue:
        Console.WriteLine("The color is blue");
        break;
    default:
        Console.WriteLine("The color is unknown.");
        break;
}

// csharp_indent_switch_labels = false
switch(c) {
case Color.Red:
    Console.WriteLine("The color is red");
    break;
case Color.Blue:
    Console.WriteLine("The color is blue");
    break;
default:
    Console.WriteLine("The color is unknown.");
    break;
}
```

#### csharp\_indent_labels

|Property|Value|
|-|-|
| **Option name** | csharp_indent_labels |
| **Applicable languages** | C# |
| **Introduced version** | Visual Studio 2017 version 15.3 |
| **Option values** | `flush_left` - Labels are placed at the leftmost column<br /><br />`one_less_than_current` - Labels are placed at one less indent to the current context<br /><br />`no_change` - Labels are placed at the same indent as the current context |

Code examples:

```csharp
// csharp_indent_labels= flush_left
class C
{
    private string MyMethod(...)
    {
        if (...) {
            goto error;
        }
error:
        throw new Exception(...);
    }
}

// csharp_indent_labels = one_less_than_current
class C
{
    private string MyMethod(...)
    {
        if (...) {
            goto error;
        }
    error:
        throw new Exception(...);
    }
}

// csharp_indent_labels= no_change
class C
{
    private string MyMethod(...)
    {
        if (...) {
            goto error;
        }
        error:
        throw new Exception(...);
    }
}
```

#### csharp_indent_block_contents

|Property|Value|
|-|-|
| **Option name** | csharp_indent_block_contents |
| **Applicable languages** | C# |
| **Option values** | `true` - <br /><br />`false` -  |

Code examples:

```csharp
// csharp_indent_block_contents = true
static void Hello()
{
    Console.WriteLine("Hello");
}

// csharp_indent_block_contents = false
static void Hello()
{
Console.WriteLine("Hello");
}
```

#### csharp_indent_braces

|Property|Value|
|-|-|
| **Option name** | csharp_indent_braces |
| **Applicable languages** | C# |
| **Option values** | `true` - <br /><br />`false` -  |

Code examples:

```csharp
// csharp_indent_braces = true
static void Hello()
    {
    Console.WriteLine("Hello");
    }

// csharp_indent_braces = false
static void Hello()
{
    Console.WriteLine("Hello");
}
```

### Spacing options

These formatting rules concern the use of space characters to format code.

Example *.editorconfig* file:

```ini
# CSharp formatting rules:
[*.cs]
csharp_space_after_keywords_in_control_flow_statements = true
csharp_space_around_binary_operators = before_and_after
csharp_space_after_comma = true
csharp_space_after_dot = false
csharp_space_before_dot = false
csharp_space_after_semicolon_in_for_statement = true
csharp_space_around_declaration_statements = false
```

#### csharp_space_after_keywords_in_control_flow_statements

|Property|Value|
|-|-|
| **Option name** | csharp_space_after_keywords_in_control_flow_statements |
| **Applicable languages** | C# |
| **Introduced version** | Visual Studio 2017 version 15.3 |
| **Option values** | `true` - Place a space character after a keyword in a control flow statement such as a `for` loop<br /><br />`false` - Remove space after a keyword in a control flow statement such as a `for` loop |

Code examples:

```csharp
// csharp_space_after_keywords_in_control_flow_statements = true
for (int i;i<x;i++) { ... }

// csharp_space_after_keywords_in_control_flow_statements = false
for(int i;i<x;i++) { ... }
```

#### csharp\_space\_around\_binary_operators

|Property|Value|
|-|-|
| **Option name** | csharp_space_around_binary_operators |
| **Applicable languages** | C# |
| **Introduced version** | Visual Studio 2017 version 15.7 |
| **Option values** | `before_and_after` - Insert space before and after the binary operator<br /><br />`none` - Remove spaces before and after the binary operator<br /><br />`ignore` - Ignore spaces around binary operators |

If you omit this rule, or use a value other than `before_and_after`, `none`, or `ignore`, the setting is not applied.

Code examples:

```csharp
// csharp_space_around_binary_operators = before_and_after
return x * (x - y);

// csharp_space_around_binary_operators = none
return x*(x-y);

// csharp_space_around_binary_operators = ignore
return x  *  (x-y);
```

#### csharp_space_after_comma

|Property|Value|
|-|-|
| **Option name** | csharp_space_after_comma |
| **Applicable languages** | C# |
| **Option values** | `true` - Insert space after a comma<br /><br />`false` - Remove space after a comma |

Code examples:

```csharp
// csharp_space_after_comma = true
int[] x = new int[] { 1, 2, 3, 4, 5 };

// csharp_space_after_comma = false
int[] x = new int[] { 1,2,3,4,5 }
```

#### csharp_space_after_dot

|Property|Value|
|-|-|
| **Option name** | csharp_space_after_dot |
| **Applicable languages** | C# |
| **Option values** | `true` - Insert space after a dot<br /><br />`false` - Remove space after a dot |

Code examples:

```csharp
// csharp_space_after_dot = true
this. Goo();

// csharp_space_after_dot = false
this.Goo();
```

#### csharp_space_before_dot

|Property|Value|
|-|-|
| **Option name** | csharp_space_before_dot |
| **Applicable languages** | C# |
| **Option values** | `true` - Insert space before a dot <br /><br />`false` - Remove space before a dot |

Code examples:

```csharp
// csharp_space_before_dot = true
this .Goo();

// csharp_space_before_dot = false
this.Goo();
```

#### csharp_space_after_semicolon_in_for_statement

|Property|Value|
|-|-|
| **Option name** | csharp_space_after_semicolon_in_for_statement |
| **Applicable languages** | C# |
| **Option values** | `true` - Insert space after each semicolon in a `for` statement<br /><br />`false` - Remove space after each semicolon in a `for` statement |

Code examples:

```csharp
// csharp_space_after_semicolon_in_for_statement = true
for (int i = 0; i < x.Length; i++)

// csharp_space_after_semicolon_in_for_statement = false
for (int i = 0;i < x.Length;i++)
```

#### csharp_space_around_declaration_statements

|Property|Value|
|-|-|
| **Option name** | csharp_space_around_declaration_statements |
| **Applicable languages** | C# |
| **Option values** | `ignore` - Don't remove extra space characters in declaration statements<br /><br />`false` - Remove extra space characters in declaration statements |

Code examples:

```csharp
// csharp_space_around_declaration_statements = ignore
int    x    =    0   ;

// csharp_space_around_declaration_statements = false
int x = 0;
```

### Wrap options

These formatting rules concern the use of single lines versus separate lines for statements and code blocks.

Example *.editorconfig* file:

```ini
# CSharp formatting rules:
[*.cs]
csharp_preserve_single_line_statements = true
csharp_preserve_single_line_blocks = true
```

#### csharp_preserve_single_line_statements

|Property|Value|
|-|-|
| **Option name** | csharp_preserve_single_line_statements |
| **Applicable languages** | C# |
| **Introduced version** | Visual Studio 2017 version 15.3 |
| **Option values** | `true` - Leave statements and member declarations on the same line<br /><br />`false` - Leave statements and member declarations on different lines |

Code examples:

```csharp
//csharp_preserve_single_line_statements = true
int i = 0; string name = "John";

//csharp_preserve_single_line_statements = false
int i = 0;
string name = "John";
```

#### csharp_preserve_single_line_blocks

|Property|Value|
|-|-|
| **Option name** | csharp_preserve_single_line_blocks |
| **Applicable languages** | C# |
| **Introduced version** | Visual Studio 2017 version 15.3 |
| **Option values** | `true` - Leave code block on single line<br /><br />`false` - Leave code block on separate lines |

Code examples:

```csharp
//csharp_preserve_single_line_blocks = true
public int Foo { get; set; }

//csharp_preserve_single_line_blocks = false
public int MyProperty
{
    get; set;
}
```

### Using directive options

This formatting rule concerns the use of using directives being placed inside versus outside a namespace.

Example *.editorconfig* file:

```ini
# 'using' directive preferences
[*.cs]
csharp_using_directive_placement = outside_namespace
csharp_using_directive_placement = inside_namespace
```

#### csharp_using_directive_placement

|Property|Value|
|-|-|
| **Option name** | csharp_using_directive_placement |
| **Applicable languages** | C# |
| **Introduced version** | Visual Studio 2019 version 16.1 |
| **Option values** | `outside_namespace` - Leave using directives outside namespace<br /><br />`inside_namespace` - Leave using directives inside namespace |

Code examples:

```csharp
// csharp_using_directive_placement = outside_namespace
using System;

namespace Conventions
{

}

// csharp_using_directive_placement = inside_namespace
namespace Conventions
{
    using System;
}
```

### Namespace options

These formatting rules concern styling and naming constraints for namespace declarations.

Example *.editorconfig* file:

```ini
# CSharp formatting rules:
[*.cs]
csharp_style_namespace_declarations = file_scoped
```

#### csharp_style_namespace_declarations

|Property|Value|
|-|-|
| **Option name** | csharp_style_namespace_declarations |
| **Applicable languages** | C# |
| **Introduced version** | Visual Studio 2019 version 16.10 |
| **Option values** | `block_scoped` - Namespace declarations should use block scopes for declaration.<br /><br />`file_scoped` - Namespace declarations should be file scoped. For more information, see the [file-scoped namespaces specification](/dotnet/csharp/language-reference/proposals/csharp-10.0/file-scoped-namespaces). |

```csharp
// csharp_style_namespace_declarations = block_scoped
using System;

namespace Convention
{
    class C
    {
    }
}

// csharp_style_namespace_declarations = file_scoped
using System;

namespace Convention;
class C
{
}
```

##### Project items

`dotnet_style_namespace_match_folder` requires the analyzer to have access to project properties to function correctly.

For projects that target .NET Core 3.1 or an earlier version, you must manually add the following items to your project file. (They're added automatically for .NET 5 and higher.)

```xml
  <ItemGroup>
    <CompilerVisibleProperty Include="RootNamespace" />
    <CompilerVisibleProperty Include="ProjectDir" />
  </ItemGroup>
```

## See also

- [Language rules](language-rules.md)
- [Naming rules](naming-rules.md)
- [.NET code style rules reference](index.md)
