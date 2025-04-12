# Package Management Tools

This guide provides an overview of different Python package management tools and their usage.

## 1. PIP (Python Package Installer)

PIP is the standard package manager for Python. It allows you to install and manage Python packages from the Python Package Index (PyPI).

### Installation:
```bash
# On Windows
python -m ensurepip --upgrade

# On macOS/Linux
python3 -m ensurepip --upgrade

# Verify installation
pip --version
```

### Basic Commands:
```bash
# Install a package
pip install package_name

# Install a specific version
pip install package_name==1.0.0

# Install from requirements.txt
pip install -r requirements.txt

# List installed packages
pip list

# Create requirements.txt
pip freeze > requirements.txt
```

## 2. Anaconda

Anaconda is a distribution of Python and R for scientific computing and data science. It includes conda, a powerful package and environment manager.

### Installation:
1. Download Anaconda from [https://www.anaconda.com/download](https://www.anaconda.com/download)
2. Run the installer:
   - Windows: Double-click the .exe file
   - macOS: Double-click the .pkg file
   - Linux: Run `bash Anaconda3-2023.09-0-Linux-x86_64.sh`
3. Follow the installation prompts
4. Verify installation:
```bash
conda --version
```

### Basic Commands:
```bash
# Create a new environment
conda create --name myenv python=3.9

# Activate environment
conda activate myenv

# Install packages
conda install numpy pandas

# List installed packages
conda list

# Export environment
conda env export > environment.yml
```

## 3. Poetry

Poetry is a modern dependency management tool that handles project dependencies, packaging, and publishing.

### Installation:
```bash
# On Windows (PowerShell)
(Invoke-WebRequest -Uri https://install.python-poetry.org -UseBasicParsing).Content | python -

# On macOS/Linux
curl -sSL https://install.python-poetry.org | python3 -

# Verify installation
poetry --version

# Add Poetry to PATH (if not automatically added)
# Windows: Add %APPDATA%\Python\Scripts to PATH
# macOS/Linux: Add ~/.local/bin to PATH
```

### Basic Commands:
```bash
# Initialize a new project
poetry new my-project

# Add dependencies
poetry add package_name

# Install dependencies
poetry install

# Update dependencies
poetry update

# Run a script
poetry run python script.py
```

## 4. UV

UV is a fast Python package installer and resolver, written in Rust. It's designed to be a drop-in replacement for pip.

### Installation:
```bash
# Using pip
pip install uv

# Using curl (macOS/Linux)
curl -LsSf https://astral.sh/uv/install.sh | sh

# Using PowerShell (Windows)
irm https://astral.sh/uv/install.ps1 | iex

# Verify installation
uv --version
```

### Basic Commands:
```bash
# Install a package
uv pip install package_name

# Install from requirements.txt
uv pip install -r requirements.txt

# Create a virtual environment
uv venv --python 3.12 .venv

# Install with specific Python version
uv pip install --python 3.9 package_name
```

## Best Practices

1. Always use virtual environments to isolate project dependencies
2. Keep your requirements files up to date
3. Specify exact versions for production environments
4. Regularly update your dependencies to get security patches
5. Document your package management choices in your project's README