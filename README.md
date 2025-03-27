# Autodocx

**Autodocx** is a documentation generator for Python projects, built on top of **Autodoc2**. It enhances **Autodoc2** by fixing certain docstring rendering issues, particularly when using Google-style docstrings with **Sphinx** and **MyST** Markdown.

## Features

- 📝 **Built on Autodoc2**, with improved docstring rendering
- 🔍 **Automatically generates API documentation** from Python source code
- 📖 **MyST Markdown support** for rich and flexible documentation
- ⚡ **Minimal configuration required** to get started
- 🎨 **Uses the Furo theme** for modern and responsive documentation

## Installation

You can install Autodocx via pip:

```sh
pip install autodocx
```

## Quick Start

1. **Initialize your Sphinx project** if you haven't already:

```sh
sphinx-quickstart
```

2. **Install Autodocx** and required dependencies:

```sh
git clone https://github.com/digreatbrian/autodocx.git
cd autodocx
pip install .
```

3. **Modify your `conf.py` to include Autodocx**:

```py
# No need to add sphinx.ext.napoleon, autoapi, autodoc and autodoc2
extensions = [
    "autodocx",
    "myst_parser"
]
```

4. **Generate documentation**:

Refer to [Sphinx Documentation](https://sphinx-doc.org) for full steps and documentation.

```sh
make html
```

Your documentation will be available in `build/html`.

## Configuration

You can customize Autodocx by adding the following options in your `conf.py`:

```py
napoleon_config = {
    "use_google_docstrings": True,  # Enable Google style docstrings
    "use_numpy_docstrings": False,  # Disable Numpy-style docstrings (set to True if needed)
    "include_private_with_doc": True,  # Include private members with docstrings
    "include_special_with_doc": True,  # Include special methods (e.g., __init__) with docstrings
    "use_ivar": True,  # Use 'ivar' for instance variables
    "use_param": True,  # Use 'param' for function parameters in Google style
    "use_rtype": True,  # Use 'rtype' for return type in Google style
    "preprocess_types": True,  # Automatically process type annotations
    "attr_annotations": True,  # Enable attribute annotations for class properties
    "use_admonition_for_examples": True  # Use admonitions for 'Examples' sections
}

autodoc2_output_dir = "api"
autodoc2_render_plugin = "myst"
autodoc2_include_private = True
autodoc2_include_special = True
autodoc2_sort_names = True
autodoc2_show_if_no_docstring = True
```

## Example Docstring

Here’s an example of a properly formatted Google-style docstring:

```py
def add_numbers(a: int, b: int) -> int:
    """
    Adds two numbers.

    Args:
        a (int): The first number.
        b (int): The second number.

     Returns:
         int: The sum of the two numbers.
    """
    return a + b
```

## License

This project is licensed under the **MIT License**. See [LICENSE](LICENSE) for details.

## Author

Developed by **Brian Musakwa**  
📧 [digreatbrian@gmail.com](mailto:digreatbrian@gmail.com)  
🌍 [brianmusakwa.link](https://brianmusakwa.link)

## Contributing

Contributions are welcome! Feel free to submit issues or pull requests via [GitHub](https://github.com/digreatbrian/autodocx).

## Acknowledgements

- Built on **Autodoc2**, with enhancements for better docstring rendering.
- Special thanks to **Guido van Rossum** for creating Python.
- Thanks to the **Sphinx** and **MyST** teams for their fantastic tools.
