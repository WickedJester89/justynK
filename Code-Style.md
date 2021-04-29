# Formatting

We have set up a [`.clang-format`](https://github.com/diasurgical/devilutionX/blob/master/Source/.clang-format) definition that should be used for automatically formatting the code to the project code style. The formatting is based on [WebKit-code style](https://webkit.org/code-style-guidelines/), with some adjustments to better fit what has been found to be the original code style. Note that we only follow the formatting part of the WebKit style (i.e. everything `clang-format` automatically cleans up).

To avoid uninitialized variables local variable declarations should happen at the first statment. See the example below:

*good*:
```c
int f() {
	int x = 5;
	return x;
}
```

*bad*:
```c
int f() {
	int x;

	x = 5;
	return x;
}
```

# Data types

In general, you should use SDL or C++ types.

Some globals and parameters are using a hungarian notation specifying the type. The ones we've identified for now are the following:

```cpp
Uint8 bLen;
bool isEnabled;
Uint16 wLen;
Uint32 dwLen;
size_t nLen;
static bool sgbSomeFlag;
static Uint32 sgdwSomeDword;
```

## Booleans

`true`/`false` should be used in any case as boolean literals.

## Unsigned integers

* Use `Uint8`, `Uint16`, `Uint32`, size_t, or `Uint64`

## Signed integers

Avoid `char` as it can be signed or unsigned depending on the platform, use `Sint8` unless it's a C-string.

Use `Sint8`, `Sint16`, `Sint32`, `Sint64`

# Rules

## Pointers

Null-pointers should use `nullptr` instead of `0` to stand out more between numeric values.

## Increments and decrements

* Avoid all increments/decrements used as expressions and try to write the code to include them as statements unless it'd contradict with other information we have (like all local variable names).

  Avoid:
  ```cpp
  foo[++count] = 0;
  ```

  Prefer:
  ```cpp
  count++;
  foo[count] = 0;
  ```

* Avoid pre-increments/-decrements whenever possible. The default should be `foo++`/`foo--`.

## Conditions/checks (esp. zero/falsy checks)

* Booleans: Use the expression itself: `if (!condition)`
* Pointers: Use explicit comparisons with `nullptr`: `if (ptr == nullptr)`
* Integers: Use explicit comparisons with `0`: `if (count == 0)`

*Reasoning*: Comparing with the literals of the right type makes the intent of the check clearer in many cases.

# Comments

* Use Doxygen style for documentation of the code