# 深度学习学习工具文档

### **1. 基础工具安装**（Basic Tools）
- **必装软件**  
  - Python/Conda环境配置（附常用包清单）  
  - PyTorch/TensorFlow的GPU版安装指南（含CUDA版本对照表）  
  - VS Code/Pycharm/Cursor远程开发配置（SSH连接服务器教程）  
  - 科学上网工具（简要说明代理设置，不涉及敏感细节）  

- **效率工具**  
  - Git基础命令（克隆、提交、分支管理）  
  - GitHub协作流程（Fork→PR→Code Review）  
  - 截图软件 pixpin
  - 电脑文件查询 listary
  - markdown编辑器 

---

### **2. 实验与代码管理**（exp）

- **实验记录**  
  - 实验日志模板（日期、模型、数据集、关键参数、结果）  
  - 结果保存规范（统一命名如 `实验名_日期_版本`）  

- **代码规范**  
  - 基础代码结构（示例：`/data`、`/models`、`/utils`目录）  
  - 模型训练脚本模板（含参数解析和日志输出）  

---

### **3. 服务器使用**（server）

- **基础命令**  
  - 常用Linux命令（`tmux`保活、`nvidia-smi`看GPU）  
  - 文件传输（`scp`/`rsync`示例）  

- **资源监控**  
  - 查看CPU/GPU/内存占用（`htop`、`gpustat`）  
  - 清理缓存和临时文件（简单脚本示例）  

---

### **4. 协作与学习**（paper）

- **论文相关**  
  - 论文复现Checklist（数据+模型+结果对比）  
  - 文献管理（Zotero共享库链接）  
- **问题速查**  
  - 常见报错解决（如CUDA out of memory、导入错误）  
  - 外部资源链接（Colab、Kaggle、PyTorch官方教程）  

---

### **5. 数据集管理**（dataset）

#### **1. 数据集获取与存储**  
- **公开数据集**  
  - 常用深度学习数据集（如ImageNet、COCO、MNIST）的下载链接与官方文档  
  - 医学/金融/遥感等专业领域数据集资源（附实验室推荐来源）  

- **存储规范**  
  - 统一存储路径（如 `/data/dataset_name/`，避免散放）  
  - 大数据集压缩与分卷存储（如 `tar + split` 或使用 `zip -r -s 2G`）  

#### **2. 数据预处理与标注**  
- **预处理脚本模板**  
  - 常见数据增强方法（PyTorch/TensorFlow代码示例）  
  - 数据集划分（训练/验证/测试集，比例建议8:1:1）  

- **标注规范**（如果涉及人工标注）  
  - 标注工具推荐（LabelImg、CVAT、Prodigy）  
  - 标注文件格式（COCO JSON/YOLO TXT/VOC XML的转换脚本）  

#### **3. 数据版本控制**  
- **命名规则**  
  - 版本号格式（如 `dataset_v1.0`，重大更新时升级主版本号）  
  - 变更记录（记录数据增减或修正，如 `README.md` 中说明）  

- **轻量级管理工具**  
  - 使用 `DVC`（Data Version Control）跟踪数据变更（类似Git，但针对大文件）  
  - 或简单维护一个 `data_versions.csv`，记录数据集哈希值/更新时间  

#### **4. 数据安全与备份**  
- **敏感数据**  
  - 加密存储（如 `7-zip` 密码压缩或使用 `gpg`）  
  - 访问权限控制（仅限项目组成员访问）  

- **定期备份**  
  - 重要数据集至少备份到两个位置（如实验室NAS + 云存储）  
  - 自动化备份脚本示例（`rsync` 或 `rclone` 到云盘）  

---

### **附：数据集管理示例结构**
```plaintext
/data/
├── coco/                  # 数据集目录
│   ├── images/            # 原始图像
│   ├── annotations/       # 标注文件
│   └── README.md          # 数据说明（来源、版本、格式）
├── preprocess_scripts/    # 预处理代码
│   └── resize_and_split.py
└── dataset_versions.csv   # 版本记录（可选）
```

---

### **维护建议**

- **文档格式**：用Markdown编写，存到GitHub仓库或共享网盘  
- **更新规则**：遇到新问题就补充，每学期整理一次  
