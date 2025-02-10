![](https://i.imgur.com/iywjz8s.png)


# Collaborative Document

2025-02-03-ds-cr Good Practices in Research Software Development - Day 3

Welcome to The Workshop Collaborative Document.

This Document is synchronized as you type, so that everyone viewing this page sees the same text. This allows you to collaborate seamlessly on documents.

----------------------------------------------------------------------------

This is the Document for today: https://edu.nl/epqkf

Collaborative Document day 1: https://edu.nl/r84aa

Collaborative Document day 2: https://edu.nl/ca6g7

Collaborative Document day 3: https://edu.nl/epqkf

Collaborative Document day 4: https://edu.nl/4ynkp

##  🫱🏽‍🫲🏻 Code of Conduct

Participants are expected to follow these guidelines:
* Use welcoming and inclusive language.
* Be respectful of different viewpoints and experiences.
* Gracefully accept constructive criticism.
* Focus on what is best for the community.
* Show courtesy and respect towards other community members.
 
## 🎓 Certificate of attendance

If you attend the full workshop you can request a certificate of attendance by emailing to training@esciencecenter.nl.
Please request your certificate within 8 months after the workshop, as we will delete all personal identifyable information after this period.

## ⚖️ License

All content is publicly available under the Creative Commons Attribution License: [creativecommons.org/licenses/by/4.0/](https://creativecommons.org/licenses/by/4.0/).

## 🙋Getting help

To ask a question, raise your hand in zoom. Click on the icon labeled "Reactions" in the toolbar on the bottom center of your screen,
then click the button 'Raise Hand ✋'. For urgent questions, just unmute and speak up!

You can also ask questions or type 'I need help' in the chat window and helpers will try to help you.
Please note it is not necessary to monitor the chat - the helpers will make sure that relevant questions are addressed in a plenary way.
(By the way, off-topic questions will still be answered in the chat)


## 🖥 Workshop website

[link](https://esciencecenter-digital-skills.github.io/2025-02-03-ds-cr-online/)

🛠 Setup

Day 1 and 2: [link](https://carpentries-incubator.github.io/collaborative-git-and-github-lesson/)

Day 3 and 4: [link](https://esciencecenter-digital-skills.github.io/good-practices-lesson/#software-setup)

## 👩‍🏫👩‍💻🎓 Instructors

Olga Lyashevska, Francesco Nattino

## 🧑‍🙋 Helpers

Ole Mussmann, Claire Donnelly  

## 👩‍💻👩‍💼👨‍🔬🧑‍🔬🧑‍🚀🧙‍♂️🔧 Roll Call
Name/ pronouns (optional) / job, role / social media (twitter, github, ...) / background or interests (optional) / city

## 🗓️ Agenda
|  Time | Topic                  |     |     |
| -----:|:---------------------- | --- | --- |
| 09:00 | Welcome and icebreaker |     |     |
| 09:15 | Writing modular code   |     |     |
| 10:15 | Coffee break           |     |     |
| 10:30 | Writing modular code   |     |     |
| 11:00 | Documentation          |     |     |
| 11:30 | Coffee break           |     |     |
| 11:45 | Documentation          |     |     |
| 12:45 | Wrap-up                |     |     |
| 13:00 | END                    |     |     |

## ❄️ Icebreaker
What is your favorite food on vacation? 


## 🔧 Exercises

- You are making changes to t]he input array itself, the second time your input will be different (it will be the outptut from the first time)
- impure function example 1: converted_temps not initialized
- I forgot if Python has global vars. It does :) I see.
- The second call you get both the original output + the new output, right?

## Modularity (20 min)

Carefully review the following code snippet:

```python
def convert_temperature(temperature, unit):
    if unit == "F":
        # Convert Fahrenheit to Celsius
        celsius = (temperature - 32) * (5 / 9)
        if celsius < -273.15:
            # Invalid temperature, below absolute zero
            return "Invalid temperature"
        else:
            # Convert Celsius to Kelvin
            kelvin = celsius + 273.15
            if kelvin < 0:
                # Invalid temperature, below absolute zero
                return "Invalid temperature"
            else:
                fahrenheit = (celsius * (9 / 5)) + 32
                if fahrenheit < -459.67:
                    # Invalid temperature, below absolute zero
                    return "Invalid temperature"
                else:
                    return celsius, kelvin
    elif unit == "C":
        # Convert Celsius to Fahrenheit
        fahrenheit = (temperature * (9 / 5)) + 32
        if fahrenheit < -459.67:
            # Invalid temperature, below absolute zero
            return "Invalid temperature"
        else:
            # Convert Celsius to Kelvin
            kelvin = temperature + 273.15
            if kelvin < 0:
                # Invalid temperature, below absolute zero
                return "Invalid temperature"
            else:
                return fahrenheit, kelvin
    elif unit == "K":
        # Convert Kelvin to Celsius
        celsius = temperature - 273.15
        if celsius < -273.15:
            # Invalid temperature, below absolute zero
            return "Invalid temperature"
        else:
            # Convert Celsius to Fahrenheit
            fahrenheit = (celsius * (9 / 5)) + 32
            if fahrenheit < -459.67:
                # Invalid temperature, below absolute zero
                return "Invalid temperature"
            else:
                return celsius, fahrenheit
    else:
        return "Invalid unit"
```

Refactor the code by extracting functions without altering its functionality.

- What functions did you create?
- What strategies did you use to identify them?

Share your answers in the collaborative document.

### Answers
- Room 4 suggestions:

def fahrenheit_to_celsius(fahrenheit):
    return (fahrenheit - 32) * (5 / 9)

def celsius_to_fahrenheit(celsius):
    return (celsius * (9 / 5)) + 32

def celsius_to_kelvin(celsius):
    return celsius + 273.15

def kelvin_to_celsius(kelvin):
    return kelvin - 273.15

def is_valid_temp(temperature, unit):
    if unit == 'C':
        return temperature >= -273.15
    if unit == 'F':
        return temperature >= -459.67
    if unit == 'K':
        return temperature >= 0
    return False  # Invalid unit

def convert_temperature(temperature, unit):
    if not is_valid_temp(temperature, unit):
        return "Invalid temperature"
    if unit == "F":
        celsius = fahrenheit_to_celsius(temperature)
        kelvin = celsius_to_kelvin(celsius)
        return celsius, kelvin
    elif unit == "C":
        fahrenheit = celsius_to_fahrenheit(temperature)
        kelvin = celsius_to_kelvin(temperature)
        return fahrenheit, kelvin
    elif unit == "K":
        celsius = kelvin_to_celsius(temperature)
        fahrenheit = celsius_to_fahrenheit(celsius)
        return celsius, fahrenheit
    return "Invalid unit"  # Should never reach here due to validation


Room 8 suggestions:
Seprate the tasks inside the main function into:
    - 1 function to check input unit validity
    - 1 function to check temperature validity (e.g. if celsius < -273.15 return False)
    - 1 function to convert from C to K and F
    - 1 function to convert from K to F and C
    - 1 function to convert from F to K and C

Room 2 suggestion:
- Split up conversion work into 6 conversion functions (F to C, C to K,  etc.). Or maybe fewer if you don't mind using them sequentially.
- Make one check function to check if below absolute zero.
- Make main function always return consistent sequence of three values (e.g. {F, C, K}).

We've mostly been looking at repetitions and nesting.

Room 3 suggestion:
- Make 2 new functions:
    - Test if unit is one of the valid ones
    - Test if temperature is above absolute 0

```
def _test_absolute_zero(temperature, unit):
    if ((unit == "C" and temperature < -273.15) or (unit == "F" and temperature < -459.67) or (unit == "K" and temperature < 0)):
        print("Invalid temperature, below absolute zero")
        return -1

def _test_temperature_unit(unit):
    if (unit == "F" or unit == "C" or unit == "K"):
        return 0
    else:
        print("Invalid unit (please choose C, F or K)")
        return -1


def convert_temperature(temperature, unit):
    if(_test_temperature_unit(unit) == -1): return ;

    if(_test_absolute_zero(temperature, unit) == -1) : return ;


    if unit == "F":
        celsius = (temperature - 32) * (5 / 9)
        kelvin = celsius + 273.15

        return celsius, temperature, kelvin

    elif unit == "C":
        fahrenheit = (temperature * (9 / 5)) + 32
        kelvin = temperature + 273.15

        return temperature, fahrenheit, kelvin
    else:
        celsius = temperature - 273.15
        fahrenheit = (celsius * (9 / 5)) + 32
        
        return celsius, fahrenheit, temperature

```


Room 6:

issue: do calcs twice if invalid temp is found.
```
def _invalid_temperature_check_kelvin(temperature):

    if temperature < 0:
        # Invalid temperature, below absolute zero
        return "Invalid temperature"
    else:
        return temperature

def _invalid_temperature_check_celsius(temperature):
    if temperature < -273.15:
        # Invalid temperature, below absolute zero
        return "Invalid temperature"
    else:
        return temperature


def _invalid_temperature_check_fahrenheit(temperature):
    if temperature < -459.67:
        # Invalid temperature, below absolute zero
        return "Invalid temperature"
    else:
        return temperature


def convert_temperature(temperature, unit):
    if unit not in ["F", "C", "K"]:
        return "Invalid unit"
    elif unit == "F":
        # Convert Fahrenheit to Celsius
        celsius = (temperature - 32) * (5 / 9)

        # Convert Celsius to Kelvin
        kelvin = celsius + 273.15
        celsius = _invalid_temperature_check_celsius(celsius)
        kelvin = _invalid_temperature_check_kelvin(kelvin)

        return celsius, kelvin

    elif unit == "C":
        # Convert Celsius to Fahrenheit
        fahrenheit = (temperature * (9 / 5)) + 32
        # Convert Celsius to Kelvin
        kelvin = temperature + 273.15
        fahrenheit = _invalid_temperature_check_fahrenheit(fahrenheit)
        kelvin = _invalid_temperature_check_kelvin(kelvin)

        return fahrenheit, kelvin

    elif unit == "K":
        # Convert Kelvin to Celsius
        celsius = temperature - 273.15


            # Convert Celsius to Fahrenheit
        fahrenheit = (celsius * (9 / 5)) + 32
        celsius = _invalid_temperature_check_celsius(celsius)
        fahrenheit = _invalid_temperature_check_fahrenheit(fahrenheit)

        return celsius, fahrenheit
```

Room 2:

```
def convert_temperature_2(temperature, unit):

    if unit == "F":
        # Convert Fahrenheit to Celsius
        celsius = F_to_C(temperature)
        # Convert Celsius to Kelvin
        kelvin = C_to_K(celsius)
        return celsius, kelvin
    
    elif unit == "C":
        # Convert Celsius to Fahrenheit
        fahrenheit = C_to_F(temperature)
        # Convert Celsius to Kelvin
        kelvin = C_to_K(temperature)
        return fahrenheit, kelvin

    elif unit == "K":
        # Convert Kelvin to Celsius
        celsius = K_to_C(temperature)
        # Convert Celsius to Fahrenheit
        fahrenheit = C_to_F(celsius)
        return celsius, fahrenheit

    else:
        raise Exception("Invalid unit")
    
def F_to_C(temp_F):
    temp_C = (temp_F - 32) * (5 / 9)
    _check_below_absolute_zero(temp_C, -273.15)
    return temp_C

def C_to_K(temp_C):
    temp_K = temp_C + 273.15
    _check_below_absolute_zero(temp_K, 0)
    return temp_K

def C_to_F(temp_C):
    temp_F = (temp_C * (9 / 5)) + 32
    _check_below_absolute_zero(temp_F, -459.67)
    return temp_F

def K_to_C(temp_K):
    temp_C = temp_K - 273.15
    _check_below_absolute_zero(temp_C, -273.15)
    return temp_C

def _check_below_absolute_zero(temp, abs_zero):
    if temp < abs_zero:
        # Invalid temperature, below absolute zero
        raise Exception("Invalid temperature")
```

ROOM Anne Floor & Stefan
```
def convert_temperature(temperature, unit):
    if unit == "F":
        return convert_fahrenheit(temperature)
    elif unit == "C":
        return convert_celsius(temperature)
    elif unit == "K":
        return convert_kelvin(temperature)
    else:
        return "Invalid unit"
    

def convert_fahrenheit(fahrenheit):
    # Convert Fahrenheit to Celsius
    celsius = _fahrenheit_to_celsius(fahrenheit)

    # Check if the celsius temperature is below absolute zero
    _unit_check("C", celsius)
    
    # Convert Celsius to Kelvin
    kelvin = _celsius_to_kelvin(celsius)

    # Check if the kelvin temperature is below zero
    _unit_check("K", kelvin)
    return celsius, kelvin


def convert_celsius(celsius):
    # Convert Celsius to Fahrenheit
    fahrenheit = _celsius_to_fahrenheit(celsius)

    # Check if the fahrenheit temperature is below absolute zero
    _unit_check("F", fahrenheit)

    # Convert Celsius to Kelvin
    kelvin = _celsius_to_kelvin(celsius)

    # Check if the kelvin temperature is below zero
    _unit_check("K", kelvin)
    return fahrenheit, kelvin


def convert_kelvin(kelvin):
    # Convert Kelvin to Celsius
    celsius = _kelvin_to_celsius(kelvin)

    # Check if the celsius temperature is below absolute zero
    _unit_check("C", celsius)

    # Convert Celsius to Fahrenheit
    fahrenheit = _celsius_to_fahrenheit(celsius)

    # Check if the fahrenheit temperature is below absolute zero
    _unit_check("F", fahrenheit)
    return celsius, fahrenheit


def _celsius_to_fahrenheit(celsius):
    return (celsius * (9 / 5)) + 32


def _celsius_to_kelvin(celsius):
    return celsius + 273.15


def _kelvin_to_celsius(kelvin):
    return kelvin - 273.15


def _fahrenheit_to_celsius(fahrenheit):
    return (fahrenheit - 32) * (5 / 9)


def _unit_check(unit, temperature):
    if unit == "F":
        _fahrenheit_check(temperature)
    elif unit == "C":
        _celsius_check(temperature)
    elif unit == "K":
        _kelvin_check(temperature)


def _celsius_check(celsius):
    if celsius < -273.15:
        # Invalid temperature, below absolute zero
        return "Invalid temperature"


def _kelvin_check(kelvin):
    if kelvin < 0:
        # Invalid temperature, below absolute zero
        return "Invalid temperature"


def _fahrenheit_check(fahrenheit):
    if fahrenheit < -459.67:
        # Invalid temperature, below absolute zero
        return "Invalid temperature"
```  

Room 1:
```
def _kelvin_to_celsius(temperature):
    return temperature - 273.15

def _celsius_to_kelvin(temperature):
    return temperature + 273.15

def _celsius_to_fahrenheit(temperature):
    return (temperature * (9 / 5)) + 32 

def _fahrenheit_to_celsius(temperature):
    return (temperature - 32) * (5 / 9)

def _fahrenheit_to_kelvin(temperature):
    return _celsius_to_kelvin(_fahrenheit_to_celsius(temperature))

def _kelvin_to_fahrenheit(temperature):
    return _celsius_to_fahrenheit(_kelvin_to_celsius(temperature))

def _validate_unit(unit):
    if unit not in ["K", "C", "F"]:
        raise ValueError("Invalid unit")

def _validate_temp(temperature, unit):
    valid_temp = {"K": 0, "C": -273.15, "F": -459.67}
    return temperature >= valid_temp[unit]

def _validate_input(temperature, unit):
    _validate_unit(unit)
    return _validate_temp(temperature, unit)

def convert_temperature(temperature, unit):
    if not _validate_input(temperature, unit):
        raise ValueError("Invalid temperature")
    result = {"Fahrenheit":0, "Celsius":0, "Kelvin":0}
    result[unit] = temperature
    if unit == "F":
        result["Celsius"] = _fahrenheit_to_celsius(temperature)
        result["Kelvin"] = _fahrenheit_to_kelvin(temperature)
    elif unit == "C":
        result["Fahrenheit"] = _celsius_to_fahrenheit(temperature)
        result["Kelvin"] = _celsius_to_kelvin(temperature)
    elif unit == "K":
        result["Fahrenheit"] = _kelvin_to_fahrenheit(temperature)
        result["Celsius"] = _kelvin_to_celsius(temperature)
    return result
    
```

- Room 9
```
def convert_temperature(temperature, unit):
    if unit == "F":
        celsius = _fahrenheit2celsius(temperature)
        kelvin = _celsius2kelvin(celsius)
        if(_below0(kelvin)): 
            return "Invalid temperature"
        else:
            return celsius, kelvin
    elif unit == "C":
        fahrenheit = _celsius2fahrenheit(temperature)
        kelvin = _celsius2kelvin(temperature)
        if(_below0(kelvin)): 
            return "Invalid temperature"
        else:
            return fahrenheit, kelvin
    elif unit == "K":
        celsius = _kelvin2celsius(temperature)
        fahrenheit = _celsius2fahrenheit(celsius)
        if(_below0(temperature)): 
            return "Invalid temperature"
        else:
            return celsius, fahrenheit
    else:
        return "Invalid unit"

def _fahrenheit2celsius(fahrenheit):
    celsius = (fahrenheit - 32) * (5 / 9)
    return celsius

def _celsius2kelvin(celsius):
    kelvin = celsius + 273.15 
    return kelvin

def _kelvin2celsius(kelvin):
    celsius = kelvin - 273.15
    return celsius

def _celsius2fahrenheit(celsius):
    fahrenheit = (9 / 5) * celsius + 32
    return fahrenheit

def _below0(kelvin):
    #if T<0K return logical
    below0 = kelvin < 0
    return below0    
```

SOLUTION

```
def celsius_to_fahrenheit(celsius):
    """
    Converts a temperature from Celsius to Fahrenheit.

    Args:
        celsius (float): The temperature in Celsius.

    Returns:
        float: The temperature in Fahrenheit.
    """
    return (celsius * (9 / 5)) + 32


def fahrenheit_to_celsius(fahrenheit):
    """
    Converts a temperature from Fahrenheit to Celsius.

    Args:
        fahrenheit (float): The temperature in Fahrenheit.

    Returns:
        float: The temperature in Celsius.
    """
    return (fahrenheit - 32) * (5 / 9)


def celsius_to_kelvin(celsius):
    """
    Converts a temperature from Celsius to Kelvin.

    Args:
        celsius (float): The temperature in Celsius.

    Returns:
        float: The temperature in Kelvin.
    """
    return celsius + 273.15


def kelvin_to_celsius(kelvin):
    """
    Converts a temperature from Kelvin to Celsius.

    Args:
        kelvin (float): The temperature in Kelvin.

    Returns:
        float: The temperature in Celsius.
    """
    return kelvin - 273.15


def check_temperature_validity(temperature, unit):
    """
    Checks if a temperature is valid for a given unit.

    Args:
        temperature (float): The temperature to check.
        unit (str): The unit of the temperature. Must be "C", "F", or "K".

    Returns:
        bool: True if the temperature is valid, False otherwise.
    """
    abs_zero = {"C": -273.15, "F": -459.67, "K": 0}
    if temperature < abs_zero[unit]:
        return False
    return True


def check_unit_validity(unit):
    """
    Checks if a unit is valid.

    Args:
        unit (str): The unit to check. Must be "C", "F", or "K".

    Returns:
        bool: True if the unit is valid, False otherwise.
    """
    if not unit in ["C", "F", "K"]:
        return False
    return True


def convert_temperature(temperature, unit):
    """
    Converts a temperature from one unit to another.

    Args:
        temperature (float): The temperature to convert.
        unit (str): The unit of the temperature. Must be "C", "F", or "K".

    Returns:
        tuple: A tuple containing the converted temperature in Celsius and Kelvin units.

    Raises:
        ValueError: If the unit is not "C", "F", or "K".
        ValueError: If the temperature is below absolute zero for the given unit.

    Examples:
        >>> convert_temperature(32, "F")
        (0.0, 273.15)
        >>> convert_temperature(0, "C")
        (32.0, 273.15)
        >>> convert_temperature(273.15, "K")
        (0.0, -459.67)
    """
    if not check_unit_validity(unit):
        raise ValueError("Invalid unit")
    if not check_temperature_validity(temperature, unit):
        raise ValueError("Invalid temperature")
    if unit == "F":
        celsius = fahrenheit_to_celsius(temperature)
        kelvin = celsius_to_kelvin(celsius)
        return celsius, kelvin
    if unit == "C":
        fahrenheit = celsius_to_fahrenheit(temperature)
        kelvin = celsius_to_kelvin(temperature)
        return fahrenheit, kelvin
    if unit == "K":
        celsius = kelvin_to_celsius(temperature)
        fahrenheit = celsius_to_fahrenheit(celsius)
        return celsius, fahrenheit

if __name__ == "__main__":
    print(convert_temperature(0, "C"))
    print(convert_temperature(0, "F"))
    print(convert_temperature(0, "K"))
    print(convert_temperature(-500, "K"))
    print(convert_temperature(-500, "C"))
    print(convert_temperature(-500, "F"))
    print(convert_temperature(-500, "B"))
    
```

### Examples of Good & Bad Documentation

- I like the [screeps API](https://docs.screeps.com/api/) (screeps is a real time strategy game where you program your own AI in javascript) 


### Exercise README: Draft or improve a README for one of your recent projects (in breakout rooms)

Try to draft a brief README or review a README which you have written for one of your projects.

You can work individually, but you could also discuss whether anything can be improved on your neighbour's README file(s).

Think about the user (which can be a future you) of your project, what does this user need to know to use or contribute to the project? And how do you make your project attractive to use or contribute to?

(Optional): Try the https://hemingwayapp.com/ to analyse your README file and make your writing bold and clear.


## 🧠 Collaborative Notes

### Developing Modular Code

Software can be built from smaller blocks/elements that are self-contained and independent. Each element has a specific task. This makes it easier to understand and debug the code. 

#### What are these blocks/elements (going from small to big)? 
- functions
- classes
- modules
- libraries/packages

#### Why write modular code? 
- Increase robustness of your code
    - When code is well-written, it can be tested
    - Keeps the code-base organised and bug-free
- Easier to maintain
    - Readable and understandable
    - Modules can be debugged separately
    - Modules only need to be improved/optimised once
- Allow reusability
    - A module can live independently of its original context
    - Can be used in multiple projects
- Facilitate scalability
- Create opportunity for innovation
    - Easier to add new features
- To save time:
    - Although there is an initial time investment, you save time in the future


#### What is a good module?
A good module performs limited and clearly defined tasks
Name your module something clear:
- be descriptive and clear
- focus on human intelligibility
- follow language specific conventions
- avoid abbreviations

Your code should be readable
- More readable code does not mean shorter code. 

#### Pure vs Impure functions
Impure functions fo not always give the same answer or affects code outside of the function - known as side effects. 
- Don't reassign variables and pay attention to global variables

#### Identifying opportunities for modularisation

- Readable code: Code is read more than it is written or someone outside of the project cannot understand what the code does.
- Repetition: If you find that you are copy-pasting code to make slight changed
    - Don't Repeat Yourself (DRY), place reused code into a function
    - Identify functions by their action
- Nested code: for example for loops within for loops etc
    - You can split these into multiple functions. For example, into the separate actions. 
- Let tests help you: If you can easily write a test for your function, then it is probably good. 
    - Is the input/output clear?

### Documentation

Documentation helps others, including your future self, understand what your code is doing. 

#### Types of documentation:
- <b>README files</b>: this is what is immediately displayed on the landing page of your repository. It is one of the first things people will see. A good README file includes the following:
    - Motivation: What is the purpose of this software
    - Authors and how to reach them 
    - Installation guide
    - Links to tutorials/examples etc
    - Table of contents
    - DOI reference: citation information
    - Licence
    - Sample input/output
    - Contribution guidelines
    - Badges: a unified way to present condensed pieces of information about your projects. A badge consists of a small image and a URL that the image points to. For example: code coverage, pypi link, DOI. 
    - good example: https://github.com/pandas-dev/pandas

- <b>In-code documentation</b>: Makes code more understandable and explains decisions were made. 
    - Comments: You shouldn't use comments when the code is already self-explanatory or to replace good coding practices. Also do not use it replace version control or keeping old code. 
    - Docstrings: a specific kind of comment that describes a function/class. It becomes available as part of the code (shows up when using "help"). Can be used to generate API documentation. There are different conventions for docstrings. Choose one and stick to it. 
- <b>API documentation</b>: Application Programming Interface: it works as a reference for every function in the code, describing what goes in and what goes out. This is generally only for projects that are little bit larger with multiple users. 
- <b>Tutorials</b>: Examples, typical use cases etc (e.g. "Getting Started")
 
### Tools for automatic documentation generation:
- [Sphinx (documentation generator)](https://www.sphinx-doc.org/en/master/_)
    - Creates HTML pages out of .md or .rst files
    - Programming language independent
- [Github pages (deploy your documentation)](https://pages.github.com/)
- [MkDocs (documentation generator)](https://www.mkdocs.org/)
- [Roxygen (for R users)](https://roxygen2.r-lib.org/)


## 📚 Resources
- [Pure vs Impure functions](https://www.freecodecamp.org/news/pure-function-vs-impure-function/)
- [Slides on Modular Code](https://esciencecenter-digital-skills.github.io/digital-skills-slides/modules/good-practices-lesson/modular-code-slides#/26/0/2)
- [Generating badges for your code](https://shields.io/)
- [Choosing a docstrings style](https://joshdimella.com/blog/python-docstring-formats-best-practices)
- [Read the docs (deployment platform for documentation)](https://about.readthedocs.com/)
- [Roxygen to github pages with `usethis`](https://usethis.r-lib.org/reference/use_github_pages.html)

## 📢 Feedback 

### What went well?

- I liked the explanation on what makes good modular code and the exercise
- nice exercise on making code more modular, nice to see all the different solutions as well
- I really liked the block about making modular code. I learned some good points of attention to keep in mind when coding.
- Great content! I have a lot of food for thought
- the modular code exercise was nice!

### What could be improved?

- For the exercise on modular code, I personally would prefer it individually and not in breakout rooms because then everyone has their own pace. Showing different approaches later in the collab document was good though.
- I don't think it's necessary to let people work out the entire code for the modularity exercise, because it's more about the conceptual stuff anyway. 
- maybe add a bit where you can add docstrings to your temperature functions as an exercise. -> Good one
- The part about documentation seemed a bit abstract to me, but perhaps that is because documentation needs vary so much with the kind of project you're in.
- perhaps (if possible) a short example of a very simple project where you would go step by step on implementing documentation in Python, then use Sphinx to create html, and then upload to GitHub pages. But I guess that would take too much time... -> Agreed that it would be nice to see the entire workflow once, even if not in too much detail.

- The idea behind the modular code and documentation is understandable. But i also feel that it is not, it is something that you need to keep up to date and takes time along the way ,but if you can make it into one of those pretty html pages in the end for the next user it is quite worth it and saves the next user so much time. Coding is in some way quite "whatever your taste is", but as this is a good practices course, might be nice to have some more examples of how to or how not to do it? The philosophy behind everything is something that might require some mindshift, and it might be nice to have it a little bit more on the nose sometimes? i hope you get what I mean, cause you're doing an amazing job anyhow. 

- I think in some way even though it was mentioned a little in the course description, it was highly python. I think it might be nice to have the examples of a few other languages ready to go or just a link or the options. I noticed we were switchign a lot between R and Python meaning many of the people are working there, might be something to ask in one of the icebreakers on the first day which languages you know/code mostely in. 

- the adapt your read me file felt a bit like you had to fill the time? why not get ar andom one/ask if someone wants to share one, and go through that with feedback together? or how to otherwise structure it? is there a nice way to set up a read me? (general - how to run - environemnt or setup enviornment - how to run), like is there an order to it . or do this again in breakout rooms (just 2-3 people would be fine but it ujusts adds the discussion)

## ❓ Questions

