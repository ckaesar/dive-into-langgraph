# Python 环境说明（Conda）

本项目使用 Conda 创建并管理 Python 环境，以下为已创建环境及使用说明。

## 环境概览
- 环境名称：`dive-langgraph-py311`
- Python 版本：`3.11.14`
- 运行架构：`64bit`

## 创建与激活
- 创建环境（Python 3.11，64 位）：
  ```bash
  conda create -y -n dive-langgraph-py311 python=3.11
  ```
- 激活环境：
  ```bash
  conda activate dive-langgraph-py311
  ```

## 安装依赖
- 在项目根目录安装 `requirements.txt` 依赖：
  ```bash
  pip install -r requirements.txt
  ```
  或未激活环境时：
  ```bash
  conda run -n dive-langgraph-py311 pip install -r requirements.txt
  ```

## 验证环境与依赖
- 验证位数与 Python 版本：
  ```bash
  conda run -n dive-langgraph-py311 python -c "import platform, sys; print(platform.architecture()[0]); print(sys.version)"
  ```
  预期输出：
  ```
  64bit
  3.11.14 (main, Oct 21 2025, 18:31:21) [GCC 11.2.0]
  ```

- 依赖健康检查：
  ```bash
  conda run -n dive-langgraph-py311 pip check
  ```
  预期输出：
  ```
  No broken requirements found.
  ```

## 使用建议
- 运行脚本（未激活环境时）：
  ```bash
  conda run -n dive-langgraph-py311 python your_script.py
  ```
- 列出当前环境包：
  ```bash
  conda run -n dive-langgraph-py311 pip list
  ```

## 备注
- 若提示 Conda 有新版本，可在基础环境更新：
  ```bash
  conda update -n base -c defaults conda
  ```
- 若以 `root` 用户运行 `pip` 出现警告，可忽略或通过在已激活环境内执行 `pip` 来避免该提示。
