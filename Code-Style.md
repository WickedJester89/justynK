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

# Adding notes for translators

If you create a new string visible to the user please make sure to include a note for translators if the context isn't clear. As we are using an automated process to export the strings please follow this style:

* Short notes can be done inline: `_( /* TRANSLATORS: New UI Element showing foo bar */ "foo bar"),`
* For more complex explanations please use `// TRANSLATORS:` as comment before printing the message.

Example: 
```
// TRANSLATORS: This here is the new UI function a player can toggle via the diablo.ini. %s will be the player name %i the players level. [...]
sprintf(msg, _("%s is level %i.")
```

*Note*: Poedit will look for the Tags `_`, `N_` and `ngettext` to export a string for translation. The useage of ` TRANSLATORS: ` will export the text as a note for translators. Other comments will be ignored. 

# Comments

* Use Doxygen style for documentation of the code