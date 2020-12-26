# Демонстрация классификации примитивов с помощью PyTorch Geometric

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/KernelA/made-ml-demo-app.git/master?urlpath=%2Fvoila%2Frender%2Fdemo.ipynb)

## Описание

Проект демонстрирует возможность применения [PyTorch Geometric](https://github.com/rusty1s/pytorch_geometric), а также других технологий для создания простого демо с классификаций 3D примитивов.

Оригинальный репозиторий с обучением модели [находится здесь](https://github.com/KernelA/made-ml-demo-app-model)

Используемые технологии:
* [Voila для создания web-приложения](https://github.com/voila-dashboards/voila)
* [Jupyter Widgets для создания основного интерфейса](https://jupyter.org/widgets)
* [BinderHub для запуска примера](https://github.com/jupyterhub/binderhub)

Также используется репозиторий [с примером замены внешнего вида интерфейса Voila](https://github.com/voila-dashboards/voila-material)

## Требования для запуска

1. Python 3.7 или выше.
2. Anaconda
3. Git LFS (все данные для модели хранятся в LFS)

## Как запустить

Создать окружение:
```
conda env create -n 3d-cls-demo --file ./environment.yml
conda activate 3d-cls-demo
```

Для запуска приложения в Voila:
```
python ./setup.py develop
```

Файлы со из директории `share` должны попасть в нужную директорию, иначе будет ошибка при запуске Voila. Для Anaconda:
```
jupyter --paths
```

Возможный вывод под Windows:
```
data:
    D:\...\3d-cls-demo\share\jupyter
```

Структура директорий в ` D:\...\3d-cls-demo\share\jupyter` должны быть такая:
```
├───nbconvert
│   └───templates
│       ├───asciidoc
│       ├───base
│       ├───basic
│       ├───classic
│       │   └───static
│       ├───compatibility
│       ├───html
│       ├───lab
│       │   └───static
│       ├───latex
│       ├───markdown
│       ├───material
│       │   └───static
│       ├───python
│       ├───reveal
│       │   └───static
│       ├───rst
│       └───script
└───voila
    └───templates
        ├───base
        │   └───static
        ├───classic
        │   └───static
        ├───lab
        └───material
            └───templates
```

Обратите внимание на название `material`. Это директория, которая содержит нужные файлы с настройками внешнего вида. Соотв. директорий в репозитории и в окружении не однозначное, поэтому нужные директории необходимо скопировать самостоятельно. С работой `setup.py` под Windows и Anaconda были проблемы.

После этого необходимо выполнить команду:
```
voila ./demo.ipynb --template material
```

