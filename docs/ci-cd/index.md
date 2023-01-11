# CI/CD

- ROS2 Build test
    [TakanoTaiga/ros2-ci](https://github.com/TakanoTaiga/ros2-ci)

    ```yaml
    name: Build test
    on:
    pull_request:
        branches: [ main ]
    push:
        branches: [ main ]
    jobs:
    build-and-test:
        runs-on: ubuntu-latest
        steps:
        - name: Checking out
            uses: actions/checkout@v2.3.4
        - name: Building and testing
            uses: TakanoTaiga/ros2-ci@v1.0.1
    ```

- MkDocs
    ```yaml
    name: publish-pages 
    on:
    push:
        branches:
        - master 
        - main
    permissions:
    contents: write
    jobs:
    deploy:
        runs-on: ubuntu-latest
        steps:
        - uses: actions/checkout@v3
        - uses: actions/setup-python@v4
            with:
            python-version: 3.x
        - run: pip3 install -U wheel
        - run: pip3 install fontawesome_markdown markdown mdx_truly_sane_lists mkdocs mkdocs-awesome-pages-plugin mkdocs-exclude mkdocs-macros-plugin mkdocs-material mkdocs-same-dir mkdocs-static-i18n mike plantuml-markdown pymdown-extensions python-markdown-math
        - run: pip3 install -U git+https://github.com/jimporter/mike
        - run: pip3 install mkdocs-material 
        - run: mkdocs gh-deploy --force
    ```