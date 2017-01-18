## What is BDD?

https://en.wikipedia.org/wiki/Behavior-driven_development

From http://pythonhosted.org/behave/philosophy.html

>> Behavior-driven development (or BDD) is an agile software development technique that encourages collaboration between developers, QA and non-technical or business participants in a software project.

It was originally named in 2003 by Dan North as a response to test-driven development (TDD), including acceptance test or customer test driven development practices as found in extreme programming.

Another link : https://forums.pragprog.com/forums/95/topics/3035


From Dan North (lately) on "How to sell BDD to the business" [https://skillsmatter.com/skillscasts/923-how-to-sell-bdd-to-the-business]:

>> BDD is a second-generation, outside–in, pull-based, multiple-stakeholder, multiple-scale, high-automation, agile methodology. It describes a cycle of interactions with well-defined outputs, resulting in the delivery of working, tested software that matters.


Philosophy : http://pythonhosted.org/behave/philosophy.html

>> BDD focuses on obtaining a clear understanding of desired software behavior through discussion with stakeholders. It extends TDD by writing test cases in a natural language that non-programmers can read. Behavior-driven developers use their native language in combination with the ubiquitous language of domain-driven design to describe the purpose and benefit of their code. This allows the developers to focus on why the code should be created, rather than the technical details, and minimizes translation between the technical language in which the code is written and the domain language spoken by the business, users, stakeholders, project management, etc.


https://dannorth.net/whats-in-a-story/
https://lizkeogh.com/2007/06/13/bdd-tdd-done-well/


## What is behave?

behave is behaviour-driven development, Python style.
behave uses tests written in a natural language style, backed up by Python code.


## Installing behave


Easy way :
```
pip install behave
```

Other ways : http://pythonhosted.org/behave/install.html

## How do I get started?

http://pythonhosted.org/behave/

```
Once you’ve installed behave, we recommend reading the
- tutorial first and then
- feature test setup,
- behave API and
- related software (things that you can combine with behave)
- finally: how to use and configure the behave tool.
```

## Useful plugins for SublimeText

- https://packagecontrol.io/packages/Behave%20Toolkit
    - Docs: http://behavetoolkit.readthedocs.io/en/latest/
    - Getting Started:  http://behavetoolkit.readthedocs.io/en/latest/gettingstarted.html
    - Commands: http://behavetoolkit.readthedocs.io/en/latest/commands.html
    - Configuration (IMPORTANT) : http://behavetoolkit.readthedocs.io/en/latest/configuration.html

        ```
        Exception: behave could not be found. Is it installed?
        ```

        1. Run `which behave` to find out the path
        2. Add this inside your project's `.sublime-project` file

            ```
                ...

                "settings": {
                    ...
                    "behave_command": ["/Users/xarisd/.virtualenvs/bdd-with-behave-code/bin/behave"]
                    ...
                }
                ...
            ```


- https://packagecontrol.io/packages/Behave%20Step%20Finder



