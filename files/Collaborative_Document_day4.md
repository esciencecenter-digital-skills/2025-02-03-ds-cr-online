![](https://i.imgur.com/iywjz8s.png)


# Collaborative Document

2025-02-03-ds-cr Good Practices in Research Software Development - Day 4

Welcome to The Workshop Collaborative Document.

This Document is synchronized as you type, so that everyone viewing this page sees the same text. This allows you to collaborate seamlessly on documents.

----------------------------------------------------------------------------

This is the Document for today: https://edu.nl/4ynkp

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

## 👩‍💻👩‍💼👨‍🔬🧑‍🔬🧑‍🚀🧙‍♂️🔧 Roll Call + Mood Checker!
Name/ pronouns (optional) / job, role / social media (twitter, github, ...) / background or interests (optional) / city
 

## 🗓️ Agenda
|  Time | Topic                  |
| -----:|:---------------------- |
| 09:00	| Welcome and icebreaker |
| 09:15	| Introduction to testing|
| 10:15	| Coffee break|
| 10:30	| Introduction to Continuous Integration| 
| 11:30	| Coffee break |
| 11:45	| Continuous Integration Exercise |
| 12:45	| Wrap-up|
| 13:00	| END              |

## 🔧 Exercises

## Test-Driven Development: FizzBuzz Function (15 min)

The function `fizz_buzz()` takes an integer argument and returns it, BUT:

- Fails on zero or negative numbers.
- Instead returns "Fizz" on multiples of 3.
- Instead returns "Buzz" on multiples of 5.
- Instead returns "FizzBuzz" on multiples of 3 and 5.

Create an empty function `fizz_buzz()` and go through the conditions listed above, one by one:

1. Write a test for the condition.
2. Edit the `fizz_buzz()` function until the test passes.

Then discuss together the different solutions.



# Solutions

Room 1

```python
import pytest

def fizz_buzz(a):
	if(not isinstance(a,int)):
		raise TypeError("Error: Please input an integer")

	if(a<1):
		raise ValueError("Error: Please input a positive integer")

	response = "";

	if(a%3 == 0): response += "Fizz"
	if(a%5 == 0): response += "Buzz"
	if(response == ""): return a

	return response

def test_fizz_buzz_non_integer():
	with pytest.raises(TypeError):
		fizz_buzz("nan")
	with pytest.raises(TypeError):
		fizz_buzz(3.14)

def test_fizz_buzz_non_positive():
	with pytest.raises(ValueError):
		fizz_buzz(-1)
	with pytest.raises(ValueError):
		fizz_buzz(0)

def test_fizz_buzz_positive():
	assert fizz_buzz(1) == 1
	assert fizz_buzz(3) == "Fizz"
	assert fizz_buzz(4) == 4
	assert fizz_buzz(5) == "Buzz"
	assert fizz_buzz(15) == "FizzBuzz"
	assert fizz_buzz(27) == "Fizz"
```

Room 2
```
def fizzbuzz(n):
    if not isinstance(n, int):
        return "Input must be an integer"
    if n <= 0:
        return "Input must be a positive integer"
    if n % 3 == 0 and n % 5 == 0:
        return "FizzBuzz"
    elif n % 3 == 0:
        return "Fizz"
    elif n % 5 == 0:
        return "Buzz"
    else:
        return n

def test_fizz():
	assert fizzbuzz(3) == "Fizz"

def test_buzz():
	assert fizzbuzz(5) == "Buzz"

def test_fizzbuzz():
	assert fizzbuzz(15) == "FizzBuzz"	
	assert fizzbuzz(30) == "FizzBuzz"	

def test_self():
	assert fizzbuzz(2) == 2

def test_positive_integer():
	assert fizzbuzz(0) == "Input must be a positive integer"

def test_float():
	assert fizzbuzz(2.5) == "Input must be an integer"
```

Room 3
```python                                                               
import pytest

def fizz_buzz(i):
    
    is_zero_neg = check_zero_or_negative(i)
    is_multiple_three = check_multiple_three(i)
    is_multiple_five = check_multiple_five(i)

    try:
        check_zero_or_negative(i)
    except:
        raise ValueError

    if (is_multiple_three and is_multiple_five):
        return "FizzBuzz"
    elif (is_multiple_three):
        return "Fizz"
    elif (is_multiple_five):
        return "Buzz"
    else:
        return i

def check_zero_or_negative(i):
    if (i<=0):
        raise ValueError("negative or zero")

def check_multiple_three(i):
    if (i % 3 == 0):
        return True
    else:
        return False

def check_multiple_five(i):
    if (i % 5 == 0):
        return True
    else:
        return False

def fizz_buzz_error():
    with pytest.raises(ValueError):
        fizz_buzz(-1)
    with pytest.raises(ValueError):
        fizz_buzz(0)


def test_fizz_buzz():
    assert fizz_buzz( 1) == 1 
    assert fizz_buzz( 9) == "Fizz"
    assert fizz_buzz(15) == "FizzBuzz"
    assert fizz_buzz(25) == "Buzz"

    
# Room Eric et al (forgot the number)
def FizzBuzz(number):
    if number <= 0:
        raise ValueError("Input is a negative integer, please revise")
    elif number % 3 == 0 and n % 5 ==0:
        return("FizzBuzz")
    elif number % 3 ==0:
        return "Fizz"
    elif number % 5 ==0:
        return "Buzz"
    else: 
        return number
    
def test_FizzBuzz_number():
    assert isinstance(number ,int)

def test_FizzBuzz_negative_and_zero_number():
    try:
        fizzbuzz(0)
            except ValueError as e:
                assert str(e) == "Input must be a positive integer"
    try:
        fizzbuzz(-1)
            except ValueError as e:
                assert str(e) == "Input must be a positive integer"

def test_FizzBuzz_multiple_3():
    assert(3) == "FIzz"
    assert(6) == "Fizz"
    assert(9) == "FIzz"

def test_FizzBuzz_multiple_5():
    assert(5) == "Buzzz"
    assert(10) == "Buzz"

def test_FizzBuzz_both():
    assert(15) == "FizzBUzz"
    assert(30) == "FizzBuzz"

def test_FizzBuzz_other():
    assert(1) == 1
    assert(2) == 2
    assert(4) == 4
```

Room ? (doesn't work yet hahah)
```python
import pytest

def _is_correct_type(num):
    if(type(num) != int):
        raise TypeError("Must be integer")
    if(num < 1):
        raise ValueError("Must be positive")
    return True

def _multiple_of_3(num):
    return num%3 == 0

def _multiple_of_5(num):
    return num%5 == 0

def fizz_buzz(num):
    _is_correct_type(num)
    output = ""
    if(_multiple_of_3(num)):
        output = "Fizz"
    if(_multiple_of_5(num)):
        output += "Buzz"
    if(not (_multiple_of_3(num) and _multiple_of_5(num))):
        output = num
    return output

print(fizz_buzz(21))

print(_multiple_of_3(21))

def test_is_correct_type():
    with pytest.raises(TypeError):
        _is_correct_type("hello")

def test_id_positive_0():
    with pytest.raises(ValueError):
        _is_correct_type(0)

def test_id_positive__3():
    with pytest.raises(ValueError):
        _is_correct_type(-3)

def test_fizz_buzz_10():
    assert fizz_buzz(10) == "Buzz"

def test_fizz_buzz_21():
    assert fizz_buzz(21) == "Fizz"

def test_fizz_buzz_30():
    assert fizz_buzz(30) == "FizzBuzz"

def test_fizz_buzz_7():
    assert fizz_buzz(7) == 7

```

### Solution

```python
import pytest 


def fizz_buzz(x):
    if x <= 0:
        raise ValueError('Negative or zero input not allowed') 
    if x % 3 == 0 and x % 5 == 0:
        return 'FizzBuzz'
    elif x % 3 == 0:
        return 'Fizz'
    elif x % 5 == 0:
        return 'Buzz'
    return x


def test_fizz_buzz_returns_input_value():
    assert fizz_buzz(1) == 1
    assert fizz_buzz(2) == 2
    assert fizz_buzz(4) == 4


def test_fizz_buzz_fails():
    with pytest.raises(ValueError):
         fizz_buzz(0)
    with pytest.raises(ValueError):
         fizz_buzz(-1)


def test_fizz_buzz_returns_fizz():
    assert fizz_buzz(3) == "Fizz"
    assert fizz_buzz(6) == "Fizz"
    assert fizz_buzz(9) == "Fizz"


def test_fizz_buzz_returns_buzz():
    assert fizz_buzz(5) == "Buzz"
    assert fizz_buzz(10) == "Buzz"
    assert fizz_buzz(20) == "Buzz"


def test_fizz_buzz_returns_fizzbuzz():
    assert fizz_buzz(15) == "FizzBuzz"
    assert fizz_buzz(30) == "FizzBuzz"
    assert fizz_buzz(45) == "FizzBuzz"

```

## Collaborative CI Exercise

[Collaborative CI Exercise](https://esciencecenter-digital-skills.github.io/good-practices-lesson/4-ci.html#full-cycle-collaborative-workflow)

## 🧠 Collaborative Notes

### Introduction to Testing

#### Basics of Testing
The mindset behind testing is that mistakes and bugs will happen. So when we code, we should be pro-active against them. The more complex the code, the harder it is to keep an eye on things.

Safeguards can be build against problems:
- Throwing exceptions
- Logging (intermediate) results
- Writing tests <- this is what we will be covering today

Why Test?
- Preserve functionality
    - Detect new errors early: especially when adding new features
    - Avoid unexpected outputs: make sure that output is the same after a code change
- Help users
    - Verify correct installation: when a user installs, if all tests pass it means it is running correctly
    - Ensure reproducibility
- Enable developers
    - Manage complexity:
    - Simplify refactoring: 
    - Facilitate collaboration: You have a standard for implementing functionality and can make sure that PRs don't introduce errors. 

#### Test types
- Exceptions in the code base
    - Intended to handle "expected problems"
    - Sound an alarm as soon as the problem arises
    - Provide clear feedback to the user: make sure that the message is descriptive of the problem so the user can rectify easily.
- Unit testing:
    - Smallest possible unit (module): Simplify the testing of a complex problem into small chunks
    - No dependency on outside code: (if you cannot replace everything, then you can use mocks, stubs etc.) 
- Integration testing:
    - Test interactions between units: sequences of functions etc 
    - Can be on small scales or system wide. 

#### Testing frameworks
Most modern languages have good options for testing
- Python: [Pytest](https://docs.pytest.org/en/stable/)
- R: [testthat](https://testthat.r-lib.org/) (Blog: https://www.tidyverse.org/tags/testthat/)
- Julia: [Test](https://docs.julialang.org/en/v1/stdlib/Test/)
- Fortran: [Funit](https://fortranwiki.org/fortran/show/FUnit), [Fortuno](https://github.com/fortuno-repos/fortuno), [FRUIT](https://sourceforge.net/projects/fortranxunit/)

#### Testing Metrics
- Coverage:
    - Proportion of code that is executed 
    - Target >= 80%
- Ratio (lines of code: lines of test)

These metrics can be misleading because they do not measure the quality of your tests -> You might have written a bad test or one that doesn't cover all possibilities. So don't get blindsided by hitting targets. 

#### What are the benefits of unit testing if you have integration testing? 
- You may have the right results for the wrong reasons
- Unit testing is more helpful when debugging as it will point you to the part of the code where the error is occurring. 

#### Setting up Pytest

With Conda: 
```Python
conda activate myenv # with name of your env
conda install -c conda-forge pytest
pytest --version
```

With pip:
```Python
source venv/bin/activate # with name of your env
pip install pytest
pytest --version
```

### Writing Tests

Let's create a new directory with a new file in it. Here we use vim but you can use your preferred editor:
```shell
mkdir pytest-example
cd pytest-example/
vi example.py
```

Create a function and function to test it: 

```Python
def add(a,b):
    return a + b
    
def test_add():
    assert add(2,3) == 5
```

Save and exit, then run the test:

```shell
pytest example.py
```

You should see that 1 test was run and that 1 passed. Now let's add another test to our file:

```Python
def add(a,b):
    return a + b
    
def test_add_two_numbers():
    assert add(2,3) == 5
    
def test_add_two_strings():
    assert add("space","ship") == "spaceship"
```

Run the test again. Now you can see that pytest found 2 tests and that both tests passed again. Now lets change our function:

```Python
def add(a,b):
    return a - b
    
def test_add_two_numbers():
    assert add(2,3) == 5
    
def test_add_two_strings():
    assert add("space","ship") == "spaceship"
```

Now when we run the pytest again, both tests fail. The output shows us the line where the error occurs and what type of error we are getting. 

Usually, you would separate out the functions and test functions, with the tests functions in a separate directory (often called tests). If you only run `pytest`, it will look for all files that begin with `test_` and all functions within those files that begin with `test_`

### Continuous Integration (CI)
What if you want to automate some of these processes? But there are a lot of other things that can be done. 

--> This includes automated testing!

- Testing
- Building & compiling
- Code, documentation
- Deploying automatically
- Code analysis: linting, formatting, quality
- Security analysis
- Send messages: slack, discord, email etc

There are different providers for this:
- GitHub actions
- GitLab CI
- Jenkins
- etc..

They are all similar, so check what your team uses and use that. Today we will be using GitHub Actions. 

#### Setting up CI

1. Go to GitHub and create a new repository
2. Make sure your virtual environment is activated. 
3. In your terminal, clone the repository & create a new file
```shell
git clone git@github.com:[your-repo]
cd [your-repo]
vi example.py
```

```Python
def power(a, b):
    return a**b

def root(a, n):
    return a**(1 / n)
```
4. Create a a file testing your functions
```shell
vi test_example.py
```
```Python
from example import power, root

def test_power():
    assert power(2,2) == 4
    
def test_root():
    assert root(4,2) == 3
```
5. Let's commit these changes
```shell
git status
git add example.py test_example.py
git commit -m "Add function and test"
```
6. Now add CI in GitHub Actions:
- In your repository go to the "Actions" tab, you will see that there are many options. 
- Choose the "Python Application" option under "Continuous Integration"
- This will open a "pyhton-app.yml" file under ".github/workflows" in your repo. 
- This file contains all the information for what the CI will do, under different sections. From the file we can see that it will:
    - Run for "ubuntu-latest" and "Python3.10"
    - Install dependencies
    - Lint the code with "flake8"
    - Test the code with "pytest"
7. Now lets push the code
```shell
git push origin main
```
8. We can check the progress of the actions under the "Actions" tab. This will give you the same information that pytest would give you when running on your local machine. One of the tests should fail since we introduced an error on purpose earlier. 

We can fix this error and repeat the process again. 
```Python
from example import power, root

def test_power():
    assert power(2,2) == 4
    
def test_root():
    assert root(4,2) == 2
```

And now the CI should pass!

## 📚 Resources

- [Slides (on all topics)](https://esciencecenter-digital-skills.github.io/digital-skills-slides/modules/good-practices-lesson)
- [Pytest documentation](https://docs.pytest.org/en/stable/)
- [Fortran testing frameworks](https://fortranwiki.org/fortran/show/Unit+testing+frameworks)
- [Pytest assertions](https://docs.pytest.org/en/7.1.x/how-to/assert.html)
- [GitHub Actions](https://docs.github.com/en/actions/about-github-actions/understanding-github-actions)
- [pytest book](https://www.oreilly.com/library/view/python-testing-with/9781680502848/)
## ❓ Questions?
- Random question for the wrap-up, what is the business model of github? Because they host code, run test, host wiki, etc. All that stuff will cost them money, right?
    - They charge money for more features (or if you want a large organisation): https://github.com/account/enterprises/new . Additionally only open source projects have Actions for free, so companies etc would need to pay for it. The compute for actions is also limited, so if you need more heavy actions, you will also need to pay even if it is an open source project. Also, GitHub is also owned by Microsoft so it is not a small company. 
    
...

## 📢 Feedback 

[Post-workshop survey](https://www.surveymonkey.com/r/9Y6STB6)