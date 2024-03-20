# Release instructions 

> setup `pip install --upgrade pip build`

Using twine : https://twine.readthedocs.io/en/latest/ 

1. Update the `__version__` in `mtdata/__init__.py`  
   Clear `rm -r build dist *.egg-info`   if those dir exist.
2. Build :: `$  python -m build --no-isolation  --sdist --wheel -o dist `   
3.  Make docs: `docs/make-docs.sh`
4. Upload to **testpypi** ::  `$ twine upload -r testpypi dist/*`
5. Upload to **pypi** ::  `$ twine upload -r pypi dist/*`


### The `.pypirc` file

The rc file `~/.pypirc` should have something like this 
```ini
[distutils]
index-servers =
    pypi
    testpypi

[pypi]
repository: https://upload.pypi.org/legacy/
username:Thamme.Gowda
password:<password_here>


[testpypi]
repository: https://test.pypi.org/legacy/
username:Thamme.Gowda
password:<password_here>
```
