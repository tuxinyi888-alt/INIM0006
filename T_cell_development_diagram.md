# T Cell Development in the Thymus — Flow Diagram

> 根据描述整理：T 细胞从骨髓前体到成熟 naive T 细胞输出的完整发育流程。

---

## 主流程图

```mermaid
flowchart TD
    A["骨髓前体细胞<br/>Bone Marrow Progenitors"] --> B["早期胸腺前体 ETP<br/>进入胸腺"]
    B --> C["DN 双阴性阶段<br/>CD4- CD8-<br/>（DN1 → DN2 → DN3）"]
    C -. "Notch 信号" .-> C1["T 系定向<br/>抑制 B 细胞命运"]

    C --> D["DN3：RAG 介导 V(D)J 重排<br/>生成 TCRβ 链"]
    D --> E{"TCRβ<br/>重排成功?"}
    E -- "否" --> X["凋亡"]
    E -- "是" --> F["pre-TCR 形成<br/>TCRβ + pre-Tα"]

    F --> G["β-selection<br/>• 存活信号<br/>• 增殖<br/>• 等位排斥<br/>• 推进到 DP"]
    G --> H["DP 双阳性阶段<br/>CD4+ CD8+"]
    H --> I["TCRα 重排<br/>形成完整 αβ TCR"]

    I --> J["皮质 Cortex<br/>cTEC 介导<br/>Positive Selection"]
    J --> K{"识别自身 MHC?"}
    K -- "完全不识别" --> Y["Death by neglect<br/>（忽视性死亡）"]
    K -- "弱/中等识别" --> L["存活<br/>建立 MHC 限制性"]

    L --> M{"识别哪类 MHC?"}
    M -- "MHC II" --> N["CD4 SP 谱系"]
    M -- "MHC I"  --> O["CD8 SP 谱系"]

    N --> P["髓质 Medulla<br/>mTEC + DC 介导<br/>Negative Selection"]
    O --> P
    P -. "AIRE 依赖/非依赖" .-> P1["呈递组织限制性抗原 TRA"]

    P --> Q{"对自身抗原<br/>反应强度?"}
    Q -- "强反应" --> R["克隆删除<br/>或 转化为 FoxP3+ Treg"]
    Q -- "弱/无反应" --> S["成熟 naive T 细胞"]

    S --> T["胸腺输出<br/>KLF2 / S1PR1 依赖"]
    T --> U["外周循环<br/>多样 TCR 库 + 自身耐受"]
```

---

## 关键节点速记表

| 阶段 | 位置 | 关键事件 | 关键分子 |
|---|---|---|---|
| 进入胸腺 | 骨髓 → 胸腺 | ETP 迁入 | — |
| DN1–DN3 | 皮质外缘 | T 系定向 | **Notch** |
| DN3 | 皮质 | TCRβ V(D)J 重排 | **RAG1/2** |
| β-selection | 皮质 | pre-TCR 信号 → 存活/增殖/等位排斥 | **pre-Tα + TCRβ** |
| DP | 皮质 | TCRα 重排，完整 αβ TCR | RAG |
| 阳性选择 | 皮质 | 弱/中识别 self-MHC → 存活；否则 death by neglect；建立 MHC 限制 | **cTEC** |
| 谱系决定 | 皮质 | MHC II → CD4 ；MHC I → CD8 | — |
| 阴性选择 | 髓质 | 强自反应性 → 删除 或 → Treg | **mTEC + DC，AIRE，FoxP3** |
| 输出 | 髓质 → 外周 | 胸腺出口 | **KLF2 → S1PR1** |

---

## 三大检查点（Three Checkpoints）

1. **β-selection（DN3 → DP）**：检查 TCRβ 重排是否成功 → 决定能否继续发育。
2. **Positive selection（皮质，DP）**：检查 TCR 是否能识别 self-MHC → 建立 **MHC 限制性**。
3. **Negative selection（髓质，SP）**：检查是否对 self-Ag 过度反应 → 建立 **中枢耐受**。

> 核心逻辑：**多样性（V(D)J 随机重排）→ 有用性（阳性选择）→ 安全性（阴性选择）**，最终输出既能识别外来抗原、又不攻击自身的成熟 T 细胞。
