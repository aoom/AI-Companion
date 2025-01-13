# AI-Companion

## Project Structure

```
ai-companion/
├── hardware/              # 硬件设计文件
│   ├── 3d-models/        # 3D 打印模型
│   ├── circuits/         # 电路设计
│   └── components/       # 组件清单
│
├── firmware/             # 嵌入式系统代码
│   ├── main/
│   └── modules/
│
├── cloud/                # 云服务后端
│   ├── api/
│   └── ai-services/
│
├── mobile-app/          # 配套手机应用
│   ├── ios/
│   └── android/
│
└── docs/                # 文档
```

## AI-Companion 项目简介

- 产品定位：3-12岁儿童的智能玩伴
- 核心功能：
  - 语音交互和情感识别
  - 教育性游戏和故事讲述
  - 安全监控和家长控制
  - 个性化学习和成长
- 预期目标：2025年Q1发布第一个原型

## 团队结构和职责

1. 硬件团队
   - 工业设计师：外观设计✅
   - 电子工程师：电路设计✅🎡
   - 机械工程师：结构设计

2. 固件团队
   - 嵌入式系统工程师✅
   - IoT专家
   - 音频处理工程师🎡

3. AI团队
   - 机器学习工程师🎡
   - NLP专家🎡
   - 语音识别专家✅

4. 应用开发团队
   - 后端开发者
   - iOS开发者
   - Android开发者

5. 产品团队
   - 产品经理
   - UI/UX设计师✅
   - 儿童教育专家

## 安全和隐私要求

1. 数据安全
   - 所有用户数据加密存储
   - 遵守COPPA规范
   - 实施最小权限原则

2. 设备安全
   - 固件加密
   - 安全启动
   - 远程更新机制

3. 通信安全
   - 所有API使用HTTPS✅
   - WebSocket加密✅
   - 实时数据传输加密✅

## 团队沟通规范

1. 例会安排
   - 每日站会: 9:00 AM (UTC+8)
   - 周会: 每周一 10:00 AM
   - 月度回顾: 每月最后一个周五

2. 文档更新
   - 每周五更新进度文档
   - 实时更新技术文档
   - 及时记录问题和解决方案


## 技术规格

### 硬件平台
- 主控: ESP32-C3-MINI-1
  - 架构: RISC-V 32位单核处理器
  - 主频: 160MHz
  - RAM: 400KB SRAM
  - Flash: 4MB
  - 支持 Wi-Fi 和 Bluetooth LE 5.0
- 外设配置:
  - 麦克风阵列: ICS-43434 MEMS数字麦克风 (4个)
    - SNR: 65dB
    - 灵敏度: -26dBFS
  - 扬声器: MAX98357A I2S 3W D类功放
    - THD+N: 0.013%
    - SNR: 98dB
  - 显示: ST7789V 2.4寸 IPS LCD
    - 分辨率: 240x320
    - SPI接口
  - 传感器:
    - BME280 温湿度气压传感器
    - APDS-9960 环境光/手势传感器
    - MPU6050 6轴姿态传感器

### AI模型 (EchoMind)
- 基础模型: Qwen-0.5B
- 优化方案:
  - 模型量化: 
    - INT8动态量化
    - KL散度优化
    - 稀疏化处理
  - 特定领域微调:
    - 儿童教育对话: 基于COPA和COMET数据集
    - 情感识别: 基于MELD和EmpatheticDialogues
    - 安全内容过滤: 基于TextSafety数据集
  - 推理优化:
    - ONNX Runtime加速
    - TensorRT Edge优化
- 训练数据规划:
  - 儿童教育对话:
    - 来源: CommonCrawl筛选、维基童书、教育网站爬取
    - 规模: 初期50万对话对
  - 情感标注:
    - 来源: 人工标注+半监督学习扩充
    - 规模: 初期10万情感标记样本
  - 安全审核:
    - 来源: 内容审核数据库、人工构建
    - 规模: 初期20万正负样本对

## 近期开发计划
1. 硬件原型
   - [🎡] ESP32-C3-MINI-1性能测试与功耗优化
   - [ ] 麦克风阵列波束形成算法验证
   - [ ] 音频前端信号处理电路设计
   - [ ] 电源管理方案设计

2. AI模型
   - [✅] Qwen-0.5B INT8量化基准测试
   - [ ] 对话数据爬虫框架搭建
   - [🎡] 数据清洗与标注流程建立
   - [ ] 模型剪枝与压缩实验
