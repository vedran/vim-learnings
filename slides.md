# Vim
- Don't forget to record


# Vim


# Vim
- What is Vim?
- What problem does it solve?
- How it works
- Examples of Vim magic
- Q&A
 
 
Ask questions at any time!


# What  is  Vim?

"How to exit the Vim editor" has made up about .005% of question traffic
That is, one out of every 20,000 visits to Stack Overflow questions.
- Stack Overflow, 2017

Solution: <escape>:qa!


# What  is  Vim?

- Vim is a text editor based on the original vi editor that came out in 1976
- Ships with most linux systems
- Most popular editors (Eclipse, IntelliJ, Visual Studio, VSCode) have a Vim mode or plugin.
- Many many features, we'll just cover some very basics + my favourites today


# Why?
- Why do people still use an editor that came out the same year as Rocky I?
- Isn't nano / gedit / notepad / vscode / eclipse good enough??


# Why?
 
Text Navigation tools
 

Mouse:
- Mostly used for navigation
- Good for selection
- Not great for quick precision
- Slow
 
Keyboard:
- Mostly used for inserting text
- Great at precision (exception some MBP)
- Most keys are for insertions, not navigation
- Fast
 
Can we leverage the speed and precision of the keyboard for navigation?


# Modal  editing

- Vim is a "modal editor"
- Analogy of Ctrl-V
- Toggle the "mode" of the editor to use keyboard for both navigation and insertion
- Vim's three main modes are called insert, visual, and normal
- Insert mode is what normal text editors are like
- Visual mode is the keyboard equivalent of highlighting text
- Normal mode "secret sauce" in Vim.


# Navigation

Navigation Challenge!

Example #1:

```html
<div><span class="change-me" onclick="handler(state, props)">I love HTML</span></div>
```

-
 

Navigate to...
 
- The "change-me" class
- The closing angle bracket of <span>
- The opening angle bracket of <span>
- The "I" of "I love HTML"
 


# Normal  Mode

[F]ind command

```html
<div><span class="change-me" onclick="handler(state, props)">I love HTML</span></div>
```

-

Navigate to the following in under 3 keystrokes:
 
- The "change-me" class: f"
- The closing angle bracket of <span>: f>
- The opening angle bracket of <span> F<
- The "I" of "I love HTML": fI


# Normal  Mode

[C]hange command

```html
<div><span class="change-me" onclick="handler(state, [props, otherProps])">I love HTML</span></div>
```

-

Make the following changes

- Change the class name: ci"
- Change "HTML" to "XML": fHcwXML
- Replace content of the list in the click handler: f[ci[
- Replace all arguments in the click handler: f(ci(
- Replace all content inside of the div: ^cit


# Normal  Mode

[D]elete command

```python
# This is a standalone comment

# This is a
# long comment
# across several lines
# above a function
def a():
    func1("A seven nation army couldn't hold me back")
    func2("Don't want to hear about it. Every single one's got a story to tell")
```

-

Make the following changes

- Delete the standalone comment: dd
- Delete the 4 lines of comments: 4dd
- Delete the argument passed into func1: di(
- Delete the first sentence of the argument in func2: d)


# Favourites
- Repeating actions
- Column editing
- Find & Replace
- Inserting lines
- Command line vim


# Repeating  actions

Record macros with 'q' and a letter to save the macro to.
Run the macro with @<letter name>.

Example

From:

```javascript
properties = {
    "first_name": first_name,
    "last_name": last_name,
    "email": email,
}
```
-
To:

```javascript
properties = {}

if (my_condition) {
    properties["first_name"] = first_name
    properties["last_name"] = last_name
    properties["email"] = email
}
```


# Repeating  actions

Use macros to quickly add leading numbers to a list

Example:

 
From:

Mia
Ema
Ana
Ivan
Marko
Filip
Matea

To:

1. Mia
2. Ema
3. Ana
4. Ivan
5. Marko
6. Filip
7. Matea


# Column  Editing

Visual block mode to add 'event_' prefix to all variables

```javascript
name = event.get('event_name', None)
date = event.get('event_date', None)
time = event.get('event_time', None)
author = event.get('event_author', None)
source = event.get('event_source', None)
location = event.get('event_location', None)
```



# Find  &  replace

Use visual mode and find/replace to change the word "date" to "day"

From:

```javascript
if (matches) {
    new_date = '2018'
    old_date = '2017'
    birth_date = '2019'
}
```
-
 
To:

```javascript
if (matches) {
    new_day = '2018'
    old_day = '2017'
    birth_day = '2019'
}
```


# Joining  lines

Use 'J' to join lines together

```javascript
const {
    a,
    b,
    c,
} = d;
```


# Inserting  lines

Use 'O' and 'o' to insert a new line before and after current line

```javascript
if(a === b) {
    func1();
}
```
-
 
- Add func2() call after func1();
- Add func0() call before func1();


# Command  line

- Enable in bash with "set -o vi"
- Many normal mode features are available

Example:

```
> curl -XPOST "https://api.mixpanel.com/track/" -d '{"event": "$create_alias", "properties": { "distinct_id": "bd92a702655fef31", "alias": "ALIAS_TEST", "token": "MY_TOKEN" } }'

- Change "$create_alias" to "$identify"
- Change "distinct_id" to "distinct_ids"
```


# Q  &  A

- Thanks!
- Any questions?
- Feedback: https://forms.gle/xpBkw3ZyuTSRmn2r7
- Slides: https://github.com/vedran/vim-learnings
