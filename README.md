# linglong-builder-action

使用github action构建玲珑

## 例子

```yaml
name: CI
on:
  push:
    branches: ["main"]
  pull_request:
    branches: ["main"]
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-24.04

    steps:
      - uses: actions/checkout@v4
        with:
          repository: linuxdeepin/linglong-builder-demo

      - name: ll-builder-build
        uses: myml/linglong-builder-action@main
      
      - uses: actions/upload-artifact@v4
        with:
          name: layers
          path: ./*.layer

```
