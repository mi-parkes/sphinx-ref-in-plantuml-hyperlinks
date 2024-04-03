# Enhanced integration between Sphinx documentation and PlantUML diagrams

`sphinx_ref_in_plantuml_hyperlinks` is a [Sphinx](https://www.sphinx-doc.org/en/master/index.html) extension that automatically resolves references (links) created using the `std:ref:` syntax within [PlantUML](https://plantuml.com) diagrams. This allows you to link elements in your PlantUML diagrams to corresponding sections or elements in your Sphinx documentation, enhancing navigation and information flow.

![](https://mi-parkes.github.io/sphinx-ref-in-plantuml-hyperlinks/_images/refInPlantuml.png)

## Example of Use

    .. uml::
        :caption: PlantUML Caption with **bold** and *italic*
        :name: PlantUML Label2
    
        @startmindmap mindmap2
    
        *[#Orange] Example of clickable references
        **[#lightgreen] [[ ":ref:`plantuml label1`" Internal Page Reference1 ]]
        **[#lightblue] [[ ":ref:`N_00001`" Internal Page Reference2 on Sphinx-Needs ]]

        @endmindmap

## Installation

You can install [sphinx-ref-in-plantuml-hyperlinks](https://pypi.org/project/sphinx-ref-in-plantuml-hyperlinks/) with pip

```
pip install sphinx-ref-in-plantuml-hyperlinks
```

Alternatively (Linux)

    git clone https://github.com/mi-parkes/sphinx-ref-in-plantuml-hyperlinks.git
    cd sphinx-ref-in-plantuml-hyperlinks

    python3 -m venv .venv
    source .venv/bin/activate
    pip install -r doc/requirements.txt

    python3 -m build --wheel
    pip install dist/sphinx_ref_in_plantuml_hyperlinks*.whl

## Activation

In your conf.py configuration file, add `sphinx_ref_in_plantuml_hyperlinks` to your extensions list:

    extensions = [
      ...
      'sphinx_ref_in_plantuml_hyperlinks'
      ...
    ]

## List Labels:

    python3 -m sphinx.ext.intersphinx build/html/objects.inv
