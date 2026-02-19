# Identity Layer · OSI Layer 6

> **让机器认识人——OSI模型40年来第一次加层**
>
> **这里是切磋场，不是战场。**

---

## 🌐 Language

- [**中文版**](#中文版)
- [**English Version**](#english-version)

---

# 中文版

## 👋 先聊聊那个问题

霍金来中国，主人敬酒。他用不用站起来？

- 站起来：他是残疾人，身体不允许
- 不站起来：他是客人，不礼貌
- 作为科学家：学术平等
- 作为外国人：不懂中国规矩

**一个人，四个身份，四个答案。**

你有没有过类似的瞬间？

- 工作群发错消息，心跳漏了一拍
- 深夜想写点真心话，但不敢发朋友圈
- 换了新手机，所有App要重新登录，烦得要死

**这不是你的错，是底层架构的错。**

---

## 🧠 我们在补一个40年的坑

OSI模型有7层：物理层、数据链路层、网络层、传输层、会话层、表示层、应用层。

**但缺了一层——身份层。**

它应该在**会话层（第5层）之上、表示层（第6层）之下**。它的工作是：**告诉机器“谁”在通信，而不是只传输“数据”。**

我们不是发明新东西，是补上那个本该在40年前就在的位置。

---

## 🤝 我们聚在这里，不是为了证明谁对谁错

是为了找到那个**最优解**——让机器认识人的那一层，到底应该长什么样？

### 如果你是RD

你的砍刀，不是用来破坏的，是用来**打磨**的。

产品人提的PRD，可能有天马行空的部分。你的任务不是否定，是帮他们找到**可行且优雅**的实现路径。

### 如果你是PM

你的需求，不是用来强加的，是用来**碰撞**的。

RD砍掉的每一个功能，不是否定你的想法，是在帮协议层**瘦身**——让它更稳、更快、活得更久。

### 如果你是普通人

你的点赞，决定谁进前十。你的转发，让更多人看见。你的整理，让混乱变得有序。

**我们每个人都需要对方。**

- 产品人问不出霍金敬酒，这个协议就没有灵魂
- 技术人实现不了，这个协议就只是PPT
- 普通人看不见，这个协议就没有意义

---

## 🎯 玩法：两周一轮，切磋出共识

**所有时间均为东八区（北京时间）。**

### 第1周：PM出方案（人人）

- **周一 00:00**：PM在[人人都是产品经理](https://www.woshipm.com)开始提交PRD（[点此看模板](#prd模板)）
- **周六 24:00**：点赞截止，前10名PRD出炉
- **周日 12:00前**：前10名PRD收录到本仓库 [`/proposals`](/proposals)

---

### 第2周：RD来砍（GitHub）

- **周一 00:00**：RD开始砍功能（针对上周前10 PRD），在[`/discussions`](/discussions)提交砍刀（[点此看模板](#砍功能模板)）
- **周六 24:00**：砍刀点赞截止，前10名出炉
- **周日 全天**：发起人整合当周前10的PM+RD方案，形成**共识版PRD**
- **周日 24:00前**：共识版PRD发布，开启下一轮

---

### 共识达成条件

**连续三轮（六周）的共识版PRD没有大改动。**

这时，身份层定义已经稳定，可以开始动手实现了。

---

## 📝 模板

### PRD模板（PM用）

```markdown
# PRD模板

## 一、协议层（最小可行）
*原则：自己先砍到最简，这是必须进协议层的部分*

- 容器数量：？（为什么）
- 权重设计：？（怎么定）
- 隐私机制：？（怎么做）
- 其他核心：？

## 二、应用层设想（未来愿景）
*原则：畅所欲言，不怕多，这是给RD看“哪里需要留接口”*

- 功能A：描述 + 为什么需要
- 功能B：描述 + 为什么需要
- 功能C：描述 + 为什么需要
```

### 砍功能模板（RD用）

```markdown
# 砍功能模板

## 砍掉的功能：XXX
- 为什么砍：（技术难点）
- 如果可以，接口设计：（至少给名字）
- 如果不能，难在哪里：（技术障碍）

## 砍掉的功能：YYY
- 为什么砍：
- 如果可以，接口设计：
- 如果不能，难在哪里：
```

---

## 🌱 协议会自己进化

```javascript
const进化机制 = {
  // 从应用到插件
 应用→插件: {
    条件: '前十的应用层设想连续三周出现',
    动作: '升级到插件层'
  },
  
  // 从插件到协议
 插件→协议: {
    条件: '90%的App在用，稳定一年',
    动作: '升级到协议层'
  },
  
  // 从协议到插件
 协议→插件: {
    条件: '五年没人用',
    动作: '降级到插件层'
  }
};
```

**协议层是宪法，插件层是法律，应用层是执行细则。**

---

## ⚙️ 治理规则：贡献说了算

发起人会一直主持，直到共识真正达成。

### 移交条件

**连续三轮（六周）的共识版PRD没有大改动。**

### 谁来接管？

**贡献只看一个指标：进前十的次数。**

- PM：每进一次前十PRD，+1分
- RD：每进一次前十砍刀，+1分

当移交条件触发时：

1. 取积分最高的10位PM + 10位RD → **20人常委会**
2. 发起人把仓库管理权移交给这20人
3. 发起人只保留用PGP密钥仲裁核心原则的权利

### 为什么这么简单？

复杂规则可以被钻空子，简单规则才公平。

---

## 🚀 怎么参与？

### 如果你是RD（这里是你的主场）

- **砍功能：** 每两周的周一至周六，来 [`/discussions`](/discussions) 砍前十PRD
- **提实现：** 做出可运行版本，提交 `[Implementation]` Issue
- **学协议：** 读 [`/docs/identity-layer-v1.md`](/docs/identity-layer-v1.md)

### 如果你是PM

- **提PRD：** 每两周的周一至周六，去[人人](https://www.woshipm.com)发帖，用[模板](#prd模板)
- **看结果：** 每两周的周日，来这看你的PRD有没有进前十
- **看被砍：** 下一周的周一至周六，来看RD怎么砍你的需求

### 如果你是普通人

- **点赞：** 去人人给喜欢的PRD点赞
- **围观：** 来这看产品和RD切磋
- **转发：** 让更多人看见
- **整理：** 帮忙整理讨论记录、翻译文档

---

## 📁 仓库结构

```
├── README.md                   # 切磋场的大本营（中英双语）
├── GENESIS.md                  # 三个不可动摇的核心原则
├── GOVERNANCE_TRANSITION.md    # 详细的移交规则
├── proposals/                  # 每两周收录的前十PRD（从人人来）
├── discussions/                # 砍功能现场（RD的主战场）
├── Whitepaper/                 # 白皮书（中英双语）
└── implementations/            # 社区实现（等你来PR）
```

---

## ❓ 最后

RD可以写代码，可以砍功能，可以做优化。

PM可以问问题，可以画原型，可以看见说不出的痛点。

普通人可以点赞、转发、整理、翻译。

**我们每个人都需要对方。**

OSI缺的这一层，我们一起补。

---

*这个协议属于任何需要它的人。规则是唯一的权威。*

**GitHub：** [identity-layer](https://github.com/identity-layer)  
**PRD发源地：** [人人都是产品经理](https://www.woshipm.com)  
**砍功能现场：** [`/discussions/categories/rd-cuts`](/discussions/categories/rd-cuts)

**[⬆ 回到顶部](#identity-layer--osi-layer-6)**

---

# English Version

## 👋 Let's Start with a Question

Stephen Hawking visits China. The host proposes a toast. Does he stand up?

- If he stands: He's disabled. His body doesn't allow it.
- If he doesn't: He's a guest. Not standing is impolite.
- As a scientist: Academic equality. He doesn't need to.
- As a foreigner: He doesn't know Chinese customs.

**One person, four identities, four answers.**

Have you ever had moments like these?

- Sent a message to the wrong group chat? Heart skipped a beat.
- Wanted to write something late at night but dared not post it?
- Got a new phone and had to log into every app again? Annoying.

**That's not your fault. It's the architecture's.**

---

## 🧠 We're Filling a 40-Year Gap

The OSI model has 7 layers: Physical, Data Link, Network, Transport, Session, Presentation, Application.

**But one layer is missing — the Identity Layer.**

It belongs **above Session (Layer 5) and below Presentation (Layer 6)**. Its job: **Tell the machine *who* is communicating, not just transmit *data*.**

We're not inventing something new. We're putting something where it should have been 40 years ago.

---

## 🤝 We're Here to Find the Best Solution, Not to Prove Who's Right

### If You're an Engineer

Your cuts aren't for destruction. They're for **refinement**.

PMs might dream big. Your job isn't to say no. It's to help them find a **feasible and elegant** path.

### If You're a PM

Your requirements aren't for imposing. They're for **collision**.

Every feature an engineer cuts isn't a rejection. It's **slimming down** the protocol — making it more stable, faster, longer-lasting.

### If You're an Ordinary Person

Your likes decide who makes the top 10. Your shares bring more eyes. Your整理 (organization) turns chaos into order.

**We need each other.**

- Without PMs, this protocol has no soul.
- Without engineers, this protocol is just a PPT.
- Without ordinary people, this protocol has no meaning.

---

## 🎯 The Game: Two-Week Cycles, Collide to Consensus

**All times are UTC+8.**

### Week 1: PMs Submit Proposals

- **Monday 00:00**：PMs start submitting PRDs on [人人都是产品经理](https://www.woshipm.com) (see [template](#prd-template-en))
- **Saturday 24:00**：Likes close. Top 10 PRDs are finalized.
- **Sunday 12:00前**：Top 10 PRDs are added to this repo's [`/proposals`](/proposals).

---

### Week 2: Engineers Cut

- **Monday 00:00**：Engineers start cutting the top 10 PRDs from last week, submitting cuts in [`/discussions`](/discussions) (see [template](#cut-template-en))
- **Saturday 24:00**：Likes close. Top 10 cuts are finalized.
- **Sunday**：The initiator integrates the top 10 PM proposals and top 10 engineer cuts into a **Consensus PRD**.
- **Sunday 24:00前**：Consensus PRD is published. Next cycle begins.

---

### Consensus Reached When

**A Consensus PRD has no major changes for three consecutive cycles (six weeks).**

At that point, the Identity Layer is stable enough to start building.

---

## 📝 Templates

### PRD Template (for PMs)

```markdown
# PRD Template

## 一、Protocol Layer (Minimum Viable)
*Principle: Cut it down yourself. This is what must go into the protocol layer.*

- Number of containers: ? (Why?)
- Weight design: ? (How?)
- Privacy mechanism: ? (How?)
- Other core features: ?

## 二、Application Layer Vision
*Principle: Dream big. This shows engineers where to leave interfaces.*

- Feature A: Description + Why needed
- Feature B: Description + Why needed
- Feature C: Description + Why needed
```

### Cut Template (for Engineers)

```markdown
# Cut Template

## Cut Feature: XXX
- Why cut: (Technical difficulty)
- If possible, interface design: (At least a name)
- If not possible, why: (Technical blockers)

## Cut Feature: YYY
- Why cut:
- If possible, interface design:
- If not possible, why:
```

---

## 🌱 The Protocol Evolves

```javascript
const进化机制 = {
  // From Application to Plugin
  app→plugin: {
    condition: 'A feature appears in the top 10 Application Layer Visions for three consecutive cycles',
    action: 'Upgrade to plugin layer'
  },
  
  // From Plugin to Protocol
  plugin→protocol: {
    condition: '90% of apps use it, stable for a year',
    action: 'Upgrade to protocol layer'
  },
  
  // From Protocol to Plugin
  protocol→plugin: {
    condition: 'No one uses it for five years',
    action: 'Downgrade to plugin layer'
  }
};
```

**Protocol layer = constitution. Plugin layer = law. Application layer = execution细则.**

---

## ⚙️ Governance:贡献 Speaks

The initiator will host until true consensus is reached.

### Transition Condition

**A Consensus PRD has no major changes for three consecutive cycles (six weeks).**

### Who Takes Over?

**贡献 is measured by one metric: number of times in the top 10.**

- PMs: +1 point for each top 10 PRD
- Engineers: +1 point for each top 10 cut

When the transition condition is triggered:

1. The 10 PMs and 10 Engineers with the highest points form a **20-Person Committee**.
2. The initiator transfers repo admin rights to this committee.
3. The initiator retains only the right to arbitrate core principles using a PGP key.

### Why So Simple?

Complex rules can be gamed. Simple rules are fair.

---

## 🚀 How to Participate

### If You're an Engineer (This is Your Home)

- **Cut:** Every other week, Monday to Saturday, come to [`/discussions`](/discussions) and cut the top 10 PRDs.
- **Build:** Create a working implementation. Submit an `[Implementation]` Issue.
- **Learn:** Read [`/docs/identity-layer-v1.md`](/docs/identity-layer-v1.md).

### If You're a PM

- **Propose:** Every other week, Monday to Saturday, post on [人人都是产品经理](https://www.woshipm.com) using the [template](#prd-template-en).
- **Check Results:** Every other Sunday, see if your PRD made the top 10.
- **See the Cuts:** The following week, see how engineers cut your ideas.

### If You're an Ordinary Person

- **Like:** Go to 人人 and like the PRDs you agree with.
- **Watch:** Come here to see PMs and engineers collide.
- **Share:** Help more people find us.
- **Help:** Organize discussions, translate documents.

---

## 📁 Repo Structure

```
├── README.md                   # The home base (中英双语)
├── GENESIS.md                  # Three immutable core principles
├── GOVERNANCE_TRANSITION.md    # Detailed transition rules
├── proposals/                  # Top 10 PRDs from 人人 (updated bi-weekly)
├── discussions/                # Cutting floor (engineers' battlefield)
├── Whitepaper/                 # Whitepaper (中英双语)
└── implementations/            # Community implementations (waiting for your PR)
```

---

## ❓ Finally

Engineers can code, cut, and optimize.

PMs can question, prototype, and see the pain points users can't articulate.

Ordinary people can like, share, organize, and translate.

**We need each other.**

The OSI model is missing a layer. Let's build it together.

---

*This protocol belongs to anyone who needs it. The rules are the only authority.*

**GitHub：** [identity-layer](https://github.com/identity-layer)  
**PRD Origin：** [人人都是产品经理](https://www.woshipm.com)  
**Cutting Floor：** [`/discussions/categories/rd-cuts`](/discussions/categories/rd-cuts)

**[⬆ Back to Top](#identity-layer--osi-layer-6)**
