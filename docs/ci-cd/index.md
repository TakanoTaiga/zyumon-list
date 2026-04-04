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
      workflow_dispatch:
    permissions:
      contents: read
    concurrency:
      group: pages
      cancel-in-progress: true
    jobs:
      build:
        runs-on: ubuntu-latest
        permissions:
          contents: read
        steps:
          - uses: actions/checkout@v5
          - uses: actions/setup-python@v6
            with:
              python-version: "3.12"
          - uses: astral-sh/setup-uv@v7
            with:
              version: "0.9.18"
              enable-cache: true
          - uses: actions/configure-pages@v5
          - run: uv sync --frozen
          - run: uv run --no-sync mkdocs build
          - uses: actions/upload-pages-artifact@v4
            with:
              path: site
      deploy:
        runs-on: ubuntu-latest
        needs: build
        permissions:
          contents: read
          pages: write
          id-token: write
        environment:
          name: github-pages
          url: ${{ steps.deployment.outputs.page_url }}
        steps:
          - id: deployment
            uses: actions/deploy-pages@v4
    ```

    Repository Settings > Pages > Build and deployment > Source must be set to `GitHub Actions`.
