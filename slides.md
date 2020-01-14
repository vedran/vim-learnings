# Vim with Vedran


# Vim with Vedran
- What is Vim?
- Why does anyone use it?
- What is Modal Editing?
- What are Text Objects?
- Examples
- Q&A


# What is Vim?
- Vim is a text editor based on the original vi editor that came out in 1976
- Ships with most linux systems
- Most popular editors (Eclipse, IntelliJ, Visual Studio, VSCode) have a Vim mode or plugin.
- Many many features, we'll just cover some very basics today


# Why?
- Why do people still an editor that came out the same year as Rocky I?
- What's wrong with regular (non-modal) text editors?


# Text Editing
Mouse:
- Mostly used for navigation
- Good for selection
- Not great for quick precision
- Slow
 
Keyboard:
- Mostly used for inserting text
- Great at precision
- Most keys are for insertions, not navigation
- Fast
 
What if we could use the speed and precision of the keyboard for navigation?


# Modal editing

- Vim is a "modal editor"
- Toggle the "mode" of the editor to use keyboard for both navigation and insertion
- Non-modal editors are always in "insert" mode. Anything you type is inserted directly
- Three main modes are insert, command, and visual 


# Insert mode


# Command mode


# Visual mode


# Text objects

- Most editors treat text as strings of characters. But we group strings of characters into words, sentences, paragraphs, code blocks, etc.
- IDEs can give semantic meanings to these characters, but usually just for highlighting and and some refactoring, not much for navigation.


# Modal navigation

- Combine modal editing and text objects
- Navigate through the file by words, paragraphs, code blocks
- Text as objects, commands can be considered as verbs
- Some examples

# Change "verb"

```html
<div><span class="change-me" onclick="handler(state, props)">I love html</span></div>
```

- Change the class name
- Change the content inside of the span
- Replace all content inside of the div
- Replace all arguments in the click handler

# TODO: Other verb examples


# Bonus
- Macros
- Column editing
- Find & Replace
- command line vim

# Repeated actions (1)

From

```javascript
properties = {
    "first_name": first_name,
    "last_name": last_name,
    "email": email,
}
```
To

```javascript
properties = {}

if (my_condition) {
    properties["first_name"] = first_name
    properties["last_name"] = last_name
    properties["email"] = email
}
```


# Repeated actions (2)

From

```
Mia
Lucija
Ema
Ana
Nika
Ivan
Matej
Marko
Filip
Matea
```

to

```
1. Mia
2. Lucija
3. Ema
4. Ana
5. Nika
6. Ivan
7. Matej
8. Marko
9. Filip
10. Matea
```


## Column Editing

```
event_name = event.get('event_name', None)
event_date = event.get('event_date', None)
event_time = event.get('event_time', None)
event_author = event.get('event_author', None)
event_source = event.get('event_source', None)
event_location = event.get('event_location', None)
```




# Find & replace

```
if (has_date) {
    new_date = '2018'
    old_date = '2017'
    birth_date = '2019';
}
```

to

```
if (has_date) {
    new_day = '2018'
    old_day = '2017'
    birth_day = '2019';
}
```

