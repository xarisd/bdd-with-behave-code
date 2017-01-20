
## Installing behave


Easy way :
```
pip install behave
```

- Other ways : http://pythonhosted.org/behave/install.html
- Behave-Django: https://pythonhosted.org/behave-django/

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
    - TODO : Make it work locally nad document the gotchas




