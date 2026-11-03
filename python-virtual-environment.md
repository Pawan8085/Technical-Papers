
# Python Virtual Environment (venv)

## 1. What is a Virtual Environment?

- A virtual environment is an isolated Python environment for a project.
- It has its own Python interpreter and installed packages.
- Packages installed inside one virtual environment do not affect other project environments.

## 2. Why Do We Need a Virtual Environment?

Consider two Python projects:

- Project A requires Django 4.2.
- Project B requires Django 5.0.

If we install both packages in the same global Python environment, managing their versions can become difficult.

A virtual environment solves this problem.

### Benefits

1. **Dependency Isolation:** Each project can have its own packages.
2. **Version Management:** Different projects can use different package versions.
3. **Avoid Conflicts:** Package changes in one project do not affect another.
4. **Clean Development Environment:** Keeps project dependencies separate from global Python packages.
5. **Easy Setup:** Dependencies can be shared through a `requirements.txt` file.

## 3. How to Create a Virtual Environment in Python

### Step 1: Create a Project Directory

```bash
mkdir my-python-project
cd my-python-project
```

### Step 2: Create a Virtual Environment

```bash
python3 -m venv venv
```

- `python3`: Runs the Python interpreter.
- `-m`: Runs a Python module as a script.
- `venv`: Python's built-in virtual environment module.
- `venv`: Name of the directory where the environment will be created.

You can use another directory name, such as `.venv`.

```bash
python3 -m venv .venv
```

### Step 3: Activate the Virtual Environment

**Linux / macOS:**

```bash
source venv/bin/activate
```

**Windows (Command Prompt):**

```cmd
venv\Scripts\activate.bat
```

**Windows (PowerShell):**

```powershell
.\venv\Scripts\Activate.ps1
```

After activation, the environment name appears in the terminal:

```bash
(venv) user@ubuntu:~/my-python-project$
```

### Step 4: Install Packages

```bash
pip install requests
```

The package will be installed inside the active virtual environment.

### Step 5: Check Installed Packages

```bash
pip list
```

### Step 6: Deactivate the Virtual Environment

```bash
deactivate
```

This returns you to your normal terminal environment.

---

## 4. Project Structure

After creating the virtual environment, the project may look like this:

```text
my-python-project/
│
├── venv/
│   ├── bin/
│   ├── include/
│   ├── lib/
│   └── pyvenv.cfg
│
└── main.py
```


