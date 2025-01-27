# 项目结构
# my-awesome-project
# ├── README.md
# ├── .github/
# │   └── workflows/
# │       └── main.yml
# └── app.py

# 1. README.md
# 在这里写仓库的简单介绍
README_CONTENT = """
# My Awesome Project

这是一个简单的 GitHub 示例项目，用于展示如何创建和管理一个 GitHub 仓库。

## 功能
- 输出欢迎信息
- 包含基本的 GitHub Actions 设置

## 如何运行

确保已安装 Python，然后在项目根目录运行：

```bash
python app.py
```

## GitHub Actions

本仓库包含一个简单的 GitHub Action 配置文件，当你提交代码或创建拉取请求时，会自动运行并输出 "Hello, GitHub Actions!"。
"""

with open("README.md", "w", encoding="utf-8") as readme_file:
    readme_file.write(README_CONTENT)


# 2. .github/workflows/main.yml
# GitHub Action 配置文件
github_workflow_content = """
name: CI Pipeline

on:   :
  push:
    branches:   分支:
      - main   ——主要
  pull_request:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest   上运行:ubuntu-latest

    steps:
    - uses: actions/checkout@v3
    - name: Set up Python
      uses: actions/setup-python@v4用途:行动/ setup-python@v4
      with:   :
        python-version: '3.x'
    - name: Run Python script
      run: |
        python app.py
"""

import os   进口的
os.makedirs(".github/workflows", exist_ok=True)
with open(".github/workflows/main.yml", "w", encoding="utf-8") as workflow_file:张开(“.github /工作流/主要。Yml ", "w", encoding="utf-8")作为workflow_file：
    workflow_file.write(github_workflow_content)


# 3. app.py
# 一个简单的 Python 脚本
python_script = """
print("Hello, GitHub! Welcome to my awesome project.")
"""

with open("app.py", "w", encoding="utf-8") as app_file:
    app_file.write(python_script)
