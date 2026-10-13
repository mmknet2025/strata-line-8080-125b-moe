# 本地推理生产线③：Strata 125B MoE 线

- **角色**：双卡 layer-split 跑 Qwen3.8-Flash-Next 125B/A6B MoE（大模型线，按需启动）。
- **模型工件（未包含在本仓）**：`~/src/Strata-data`（≈133 GB，权重/数据，**不在本仓**）。
- **生产配置**：端口 `8080`，ctx `262144`，双卡 layer-split，systemd user 单元 `strata-swift-iq3s`；与单卡线**资源互斥**（需先释放显存/内存）。
- **本仓内容**：引擎源码快照（**不含**编译产物；二进制 68 MB 不进仓）。仓内已有的 `data/draft_vocab*.bin`、`data/experimental-speed-projection/*.gguf`（0.5 MB）是上游自带的实验数据，非模型权重，原样保留。
- **来源与许可**：fork 自 `Niko1221/Strata`（公开，**MIT**，见 `LICENSE`）。
- **快照点**：分支 `main` @ `a0116b2`（2026-10-12）。
