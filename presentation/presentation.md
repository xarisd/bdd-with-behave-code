## BDD with behave
<p>&nbsp;</p>
<p class="fragment">An introduction to BDD for the Python developer</p>


## Who am I?

<p>&nbsp;</p>
<h3 class="fragment">
  Haris Dimitriou (<strong>xarisd</strong>)
</h3>
<p>&nbsp;</p>
<p class="fragment">
  Backend software engineer<span class="fragment">...among other things</span>
</p>
<p>&nbsp;</p>
<p class="fragment">
  <a href="http://github.com/xarisd">github.com/xarisd</a>
  <br>
  <a href="http://twitter.com/xarisd">twitter.com/xarisd</a>
  <br>
  <a href="http://xarisd.io">xarisd.io</a>
</p>

## Agenda

<p>&nbsp;</p>

* What is BDD?
* What is behave?
* Simple tutorial
* Examples


%!SLIDE down-open
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%

## What is BDD?


!SLIDE

> BDD is a second-generation, outside–in, pull-based, multiple-stakeholder, multiple-scale, high-automation, agile methodology. It describes a cycle of interactions with well-defined outputs, resulting in the delivery of working, tested software that matters.

Dan North


!SLIDE

> Behavior-driven development (or BDD) is an agile software development technique that encourages collaboration between developers, QA and non-technical or business participants in a software project.

([behave docs](http://pythonhosted.org/behave/philosophy.html))


## Why use it?

!SLIDE

> BDD focuses on obtaining a clear understanding of desired software behavior through discussion with stakeholders. It extends TDD by writing test cases in a natural language that non-programmers can read.

([behave docs](http://pythonhosted.org/behave/philosophy.html))


!SLIDE

Basically, you use it to DESCRIBE the behaviour from the business perspective


!SLIDE

> This allows the developers to focus on why the code should be created, rather than the technical details, and minimizes translation between the technical language in which the code is written and the domain language spoken by the business, users, stakeholders, project management, etc.

([behave docs](http://pythonhosted.org/behave/philosophy.html))


## What is `behave`?

!SLIDE

> behave is behaviour-driven development, Python style.

([behave docs](http://pythonhosted.org/behave/))

!SLIDE

It is a Python package :-)


## How do you use `behave`?

!SLIDE

1 - Install it

```
pip install behave
```

!SLIDE

2 - Create the minimum structure it needs inside your project

```
features/
features/my_example.feature
features/steps/
features/steps/steps.py
```


!SLIDE

3 - Edit your scenarios inside your `*.feature` files

i.e.

```
Feature: showing off behave

  Scenario: run a simple test
     Given we have behave installed
      when we implement a test
      then behave will test it for us!
```

!SLIDE

4 - Invoke it from command line

```
behave
```

!SLIDE

5 - It will complain!

```
Failing scenarios:
  features/my_example.feature:3  run a simple test

0 features passed, 1 failed, 0 skipped
0 scenarios passed, 1 failed, 0 skipped
0 steps passed, 0 failed, 0 skipped, 3 undefined
Took 0m0.000s

You can implement step definitions for undefined steps with these snippets:

@given(u'we have behave installed')
def step_impl(context):
    raise NotImplementedError(u'STEP: Given we have behave installed')

@when(u'we implement a test')
def step_impl(context):
    raise NotImplementedError(u'STEP: When we implement a test')

@then(u'behave will test it for us!')
def step_impl(context):
    raise NotImplementedError(u'STEP: Then behave will test it for us!')

```
<p class="fragment">But it will help you ^ </p>

!SLIDE

6 - Take the snippets and paste them inside the `steps.py`

```
@given(u'we have behave installed')
def step_impl(context):
    raise NotImplementedError(u'STEP: Given we have behave installed')

@when(u'we implement a test')
def step_impl(context):
    raise NotImplementedError(u'STEP: When we implement a test')

@then(u'behave will test it for us!')
def step_impl(context):
    raise NotImplementedError(u'STEP: Then behave will test it for us!')

```

!SLIDE

7 - Rerun it

```
behave
```

!SLIDE

8 - It will complain again

```
Feature: showing off behave # features/my_example.feature:1

  Scenario: run a simple test        # features/my_example.feature:3
    Given we have behave installed   # features/steps/steps.py:1 0.000s
      Traceback (most recent call last):
        File "/Users/xarisd/.virtualenvs/bdd-with-behave-code/lib/python3.6/site-packages/behave/model.py", line 1456, in run
          match.run(runner.context)
        File "/Users/xarisd/.virtualenvs/bdd-with-behave-code/lib/python3.6/site-packages/behave/model.py", line 1903, in run
          self.func(context, *args, **kwargs)
        File "features/steps/steps.py", line 3, in step_impl
          raise NotImplementedError(u'STEP: Given we have behave installed')
      NotImplementedError: STEP: Given we have behave installed

    When we implement a test         # None
    Then behave will test it for us! # None


Failing scenarios:
  features/my_example.feature:3  run a simple test

0 features passed, 1 failed, 0 skipped
0 scenarios passed, 1 failed, 0 skipped
0 steps passed, 1 failed, 2 skipped, 0 undefined
Took 0m0.000s
```

!SLIDE
In case you missed it: `NotImplementedError: STEP: Given we have behave installed`

!SLIDE
And it is right :-)

```
@given(u'we have behave installed')
def step_impl(context):
    raise NotImplementedError(u'STEP: Given we have behave installed')
```

!SLIDE

9 - So, go and implement it in Python!


!SLIDE

What we just saw :

<ul>
    <li class="fragment">We write some <code>.feature</code> files</li>
    <li class="fragment">We implement the <code>steps</code> in Python (inside <code>feature/steps</code>)</li>
    <li class="fragment">We run the <code>scenarios</code> inside <code>features</code> using <code>behave</code> cli</li>
</ul>


!SLIDE
Can I write whatever I want?

## NO!

<p class="fragment">But there is not TOO much to learn</p>

## Meet Gherkin

<p class="fragment">The language beneath :o </p>
<a class="fragment" href="http://pythonhosted.org/behave/gherkin.html#gherkin-feature-testing-language">http://pythonhosted.org/behave/gherkin.html</a>

!SLIDE
Let's do some `live coding!`

<p class="fragment">Please be gentle :-)</p>

## Examples and Links

- [Gherkin](http://pythonhosted.org/behave/gherkin.html)
- [Step Implementation](http://pythonhosted.org/behave/tutorial.html#python-step-implementations)
- [Django Testing Example](http://pythonhosted.org/behave/django.html)
    - [behave-django](https://pythonhosted.org/behave-django/index.html)
- [Relative software](http://pythonhosted.org/behave/related.html)
- [Comparison With Other Tools](http://pythonhosted.org/behave/comparison.html)
- ... I will post more when this goes online

## Thank you!
<p>&nbsp;</p>
<p class="fragment">Liked the presentation?</p>
<p class="fragment">
  Source: <a href="http://github.com/xarisd/bdd-with-behave-code.git">github.com/xarisd/bdd-with-behave-code.git</a>
</p>
<p>&nbsp;</p>
<p class="fragment">
  Have something to say?
</p>
<p class="fragment">
  Send me a tweet or DM: <a href="http://twitter.com/xarisd">@xarisd</a>
</p>
<p>&nbsp;</p>
<p class="fragment">Questions?</p>

