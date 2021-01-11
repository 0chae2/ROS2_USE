
[pyenv 설명](http://taewan.kim/post/python_virtual_env/)
- pyenv versions
- pyenv global {version}
- pyenv local {version}
- pyenv activate {version}

[jupyter notebook 가상환경 커널 추가](https://somjang.tistory.com/entry/Python-Jupyter-Notebook-%EC%97%90-%EA%B0%80%EC%83%81%ED%99%98%EA%B2%BD-%EC%BB%A4%EB%84%90-%EC%B6%94%EA%B0%80%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95)

$ pip install ipykernel
$ python -m ipykernel install --user --name myvenv --display-name "PythonHome_p36"
$ python -m ipykernel install --user --name [virtualEnv] --display-name "[displayKenrelName]"
