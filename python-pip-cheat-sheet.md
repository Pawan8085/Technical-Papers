
# Python PIP Cheat Sheet

## What is PIP?

- PIP is Python's package installer.
- It is used to install, upgrade, and uninstall Python packages.
- Packages can be installed from the Python Package Index (PyPI).
- We generally use pip inside a virtual environment to manage project dependencies.

Example: Installing Flask in a project.

```bash
pip install flask
```

## Useful PIP Commands

### 1. Check PIP Version

```bash
pip --version
```

Displays the installed pip version and its Python installation path.

### 2. Install a Package

```bash
pip install requests
```

Installs the latest available version of a package.

### 3. Install a Specific Version

```bash
pip install requests==2.31.0
```

Installs the specified package version.

### 4. Upgrade a Package

```bash
pip install --upgrade requests
```

Upgrades an installed package to the latest compatible version.

### 5. Uninstall a Package

```bash
pip uninstall requests
```

Removes the specified package.

### 6. List Installed Packages

```bash
pip list
```

Displays all packages installed in the current Python environment.

### 7. Show Package Information

```bash
pip show requests
```

Displays package details such as version, location, and dependencies.

### 8. Check Outdated Packages

```bash
pip list --outdated
```

Displays packages that have newer versions available.

### 9. Generate requirements.txt

```bash
pip freeze > requirements.txt
```

Saves installed packages and their versions into a file.

Example:

```text
requests==2.31.0
flask==3.0.0
```

### 10. Install Packages from requirements.txt

```bash
pip install -r requirements.txt
```

Installs all packages listed in the requirements file.

### 11. Upgrade PIP

```bash
python -m pip install --upgrade pip
```

Upgrades pip itself.

### 12. Check PIP Configuration

```bash
pip config list
```

Displays the current pip configuration.

---

## Quick Revision

| Command | Purpose |
|---|---|
| `pip --version` | Check pip version |
| `pip install package` | Install package |
| `pip install package==version` | Install specific version |
| `pip install --upgrade package` | Upgrade package |
| `pip uninstall package` | Uninstall package |
| `pip list` | List installed packages |
| `pip show package` | Show package information |
| `pip list --outdated` | Check outdated packages |
| `pip freeze` | Display installed packages with versions |
| `pip freeze > requirements.txt` | Save dependencies |
| `pip install -r requirements.txt` | Install dependencies |
| `python -m pip install --upgrade pip` | Upgrade pip |
| `pip config list` | View pip configuration |

## Important Notes

- Activate your virtual environment before installing project dependencies.
- `pip freeze` shows packages installed in the current environment.
- `requirements.txt` helps other developers install the same project dependencies.
- Prefer `python -m pip` when you want to ensure pip runs with a particular Python interpreter.

