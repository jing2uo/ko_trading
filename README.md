# Quant Base

此仓库提供基础的 Python 代码，用于使用 [tdx2db](github.com/jing2uo/tdx2db) 处理后 DuckDB 中的数据，并提供额外功能：

- 查询股票数据
- 更新和查询申万行业分类信息
- 更新和查询指数成分股数据

## 项目结构

```
├── database
│   ├── base.py         # 数据库核心操作
│   ├── index.py        # 指数成分股数据处理
│   ├── shenwan.py      # 申万行业分类数据
│   └── stock.py        # 读取 tdx2db 保存的股票数据
├── example.ipynb       # 使用示例笔记本
├── req.txt             # 依赖项
└── utils
    ├── download.py     # 文件下载工具
    └── log.py          # 日志记录工具
```

## 开始使用

### 前提条件

- Python 3.13 （在此版本上开发，其他版本可自行尝试）
- 使用 `tdx2db` 转换生成的 DuckDB 数据库
- 安装 `req.txt` 中列出的依赖项：
  ```bash
  pip install -r req.txt
  ```

### 使用方法

1. **设置数据库**：确保 `tdx2db` 转换生成的 DuckDB 数据库可用
2. **配置环境变量**：修改`.env` 中的 DBPATH 变量，请自行确认编辑器会正确读取 `.env` ，也可以使用全局变量
3. **执行示例**：运行 `example.ipynb` 中的示例代码理解工作流程

在 vscode 下开发，依赖 python 和 jupyter 插件，使用 vscode 调试跑起来的坑可能不多~

### 项目扩展

您可以基于本仓库添加自定义模块，例如：

- 基于技术指标的选股逻辑。
- 使用复权数据执行策略回测。
