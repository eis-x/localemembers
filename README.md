### Structure of the Project

```
localemembers/
├── localemembers/
│   ├── __init__.py
│   ├── locale_members.py
├── tests/
│   ├── __init__.py
│   └── test_locale_members.py
├── .gitignore
├── LICENSE
├── localemembers.tr
├── main.py
├── README.md
├── requirements.txt
└── setup.py
```

### File `setup.py`

```python
from setuptools import setup, find_packages

setup(
    name='localemembers',
    version='1.0.0',
    author='Your Name',
    author_email='your.email@example.com',
    description='A Python module to detect and format system localization information.',
    long_description=open('README.md').read(),
    long_description_content_type='text/markdown',
    url='https://github.com/yourusername/localemembers',
    packages=find_packages(),
    classifiers=[
        'Programming Language :: Python :: 3',
        'License :: OSI Approved :: MIT License',
        'Operating System :: OS Independent',
    ],
    python_requires='>=3.6',
    install_requires=[
        # List of dependencies
    ],
    entry_points={
        'console_scripts': [
            'localemembers=localemembers.locale_members:main',
        ],
    },
)
```

### File `README.md`

```markdown
# Localemembers

A Python module to detect and format system localization information.

## Installation

You can install the package using pip:

```bash
pip install localemembers
```

## Usage

Here's an example of how to use the `localemembers` module:

```python
import localemembers

print(f"System Locale: {localemembers.system_locale}")
print(f"Locale Encoding: {localemembers.locale_encoding}")
print(f"Friendly Language: {localemembers.friendly_language}")
print(f"Locale Country: {localemembers.locale_country}")
print(f"Short Language Code: {localemembers.language_code}")
print(f"Short Country Code: {localemembers.country_code}")
print(f"Formatted Language Code: {localemembers.formatted_language_code}")
```

## Contributing

Contributions are welcome! Please open an issue or submit a pull request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
```

### File `LICENSE`

```plaintext
MIT License

Copyright (c) 2024 Your Name

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

### File `.gitignore`

```plaintext
# Byte-compiled / optimized / DLL files
__pycache__/
*.py[cod]
*$py.class

# Distribution / packaging
.Python
build/
develop-eggs/
dist/
downloads/
eggs/
.eggs/
lib/
lib64/
parts/
sdist/
var/
wheels/
share/python-wheels/
*.egg-info/
.installed.cfg
*.egg

# PyInstaller
*.manifest
*.spec

# Installer logs
pip-log.txt
pip-delete-this-directory.txt

# Unit test / coverage reports
htmlcov/
.tox/
.nox/
.coverage
.coverage.*
.cache
nosetests.xml
coverage.xml
*.cover
.hypothesis/
.pytest_cache/
cover/

# Translations
*.mo
*.pot

# Django stuff:
*.log
local_settings.py
db.sqlite3

# Flask stuff:
instance/
.webassets-cache

# Scrapy stuff:
.scrapy

# Sphinx documentation
docs/_build/

# PyBuilder
target/

# Jupyter Notebook
.ipynb_checkpoints

# IPython
profile_default/
ipython_config.py

# pyenv
.python-version

# celery beat schedule file
celerybeat-schedule

# dotenv
.env
.venv
env/
venv/
ENV/
env.bak/
venv.bak/

# Spyder project settings
.spyderproject
.spyproject

# Rope project settings
.ropeproject

# mkdocs documentation
/site

# mypy
.mypy_cache/
.dmypy.json
dmypy.json

# Pyre type checker
.pyre/
```

### File `localemembers/__init__.py`

```python
from .locale_members import *
```

### File `localemembers/locale_members.py`

```python
from locale import getlocale

# Global variables to store localization information
system_locale = None
locale_encoding = None
friendly_language = None
locale_country = None
language_code = None
country_code = None
formatted_language_code = None

# Function to detect and format system localization information
def detect_system_friendly_language():
    global system_locale, locale_encoding, friendly_language, locale_country, language_code, country_code, formatted_language_code
    system_locale = getlocale()
    if system_locale[0] and system_locale[1]:
        locale_value = system_locale[0]
        locale_encoding = system_locale[1]
        friendly_language = locale_value.split("_")[0]
        locale_country = locale_value.split("_")[1]
        language_code = friendly_language[:2].lower()
        country_code = locale_country[:2].upper()
        formatted_language_code = f"{language_code}_{country_code}"
    else:
        system_locale = None
        locale_encoding = None
        friendly_language = None
        locale_country = None
        language_code = None
        country_code = None
        formatted_language_code = None

# Call the function to initialize the variables
detect_system_friendly_language()

def main():
    # Example usage
    print()
    print(f"System Locale: {system_locale}")
    print(f"Locale Encoding: {locale_encoding}")
    print(f"Friendly Language: {friendly_language}")
    print(f"Locale Country: {locale_country}")
    print(f"Short Language Code: {language_code}")
    print(f"Short Country Code: {country_code}")
    print(f"Formatted Language Code: {formatted_language_code}")
    print()

if __name__ == '__main__':
    main()
```

### File `tests/test_locale_members.py`

```python
import unittest
import localemembers

class TestLocaleMembers(unittest.TestCase):

    def test_locale_members(self):
        self.assertIsNotNone(localemembers.system_locale)
        self.assertIsNotNone(localemembers.locale_encoding)
        self.assertIsNotNone(localemembers.friendly_language)
        self.assertIsNotNone(localemembers.locale_country)
        self.assertIsNotNone(localemembers.language_code)
        self.assertIsNotNone(localemembers.country_code)
        self.assertIsNotNone(localemembers.formatted_language_code)

if __name__ == '__main__':
    unittest.main()
```

### Instructions

1. **Installation** :
   ```bash
   pip install .
   ```

2. **Usage** :
   ```python
   import localemembers

   print(f"System Locale: {localemembers.system_locale}")
   print(f"Locale Encoding: {localemembers.locale_encoding}")
   print(f"Friendly Language: {localemembers.friendly_language}")
   print(f"Locale Country: {localemembers.locale_country}")
   print(f"Short Language Code: {localemembers.language_code}")
   print(f"Short Country Code: {localemembers.country_code}")
   print(f"Formatted Language Code: {localemembers.formatted_language_code}")
   ```

3. **Tests** :
   ```bash
   pytest
   ```

### Publishing on GitHub

1. **Initialize a Git repository** :
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   ```

2. **Create a new repository on GitHub** and add it as a remote:
   ```bash
   git remote add origin https://github.com/yourusername/localemembers.git
   git push -u origin master
   ```

### Publishing on PyPI

1. **Install `twine`** if you haven't already:
   ```bash
   pip install twine
   ```

2. **Create a distribution** :
   ```bash
   python setup.py sdist bdist_wheel
   ```

3. **Upload the distribution to PyPI** :
   ```bash
   twine upload dist/*
   ```