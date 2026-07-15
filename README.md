# 等高线战术推演 · Contour Line Wargame

> Trae AI 创造力大赛 · 生活娱乐 / 造点新花样

---

## 这是什么

一张随机生成的等高线地形图。你在上面部署部队、画路径、打包围战。
没有六角格、没有 3D 模型——只有等高线和兵牌。

A randomly generated topographic contour map. Deploy units, draw movement paths, and execute encirclements. No hex grids, no 3D models — just contour lines and military counters.

---

## 设计理念

1824 年普鲁士军官 von Reisswitz 发明 Kriegsspiel，用等高线地图做兵棋推演。
200 年来没有人把它做成电子游戏。这个 Demo 是第一次尝试。

In 1824, Prussian officer von Reisswitz invented Kriegsspiel using contour maps for war gaming. For 200 years, no one has turned it into a video game. This demo is the first attempt.

**核心机制：**

- 等高线密集 = 陡坡（行军减速），稀疏 = 平地（快速机动）
- 高地对低地有攻击加成，山脊背侧是天然伏击位
- 切断敌军四周补给线 → 触发包围 → 士气崩溃
- 四种剧本：斯大林格勒（城市废墟战）、巴赫穆特（绞肉机）、硫磺岛（抢滩登陆）、默认野战

---

## 怎么玩

1. **观察地形**：等高线密度告诉你哪里是山、哪里是谷
2. **选中兵牌**：点击蓝色单位选中，再点击目标位置移动
3. **路径部署**：旗帜光标时点击放置路点，单位按序移动
4. **支援技能**：底部四张简报卡片（炮火支援 / 空中打击 / 战场侦察 / 增援部队），悬浮抬起、点击发出
5. **执行推演**：部署完毕点击红色「执行推演」按钮，观看实时战斗演绎
6. **滚轮缩放**，拖拽平移地图

---

## 技术栈

纯 HTML5 Canvas + Vanilla JavaScript，单文件，零外部依赖。

- **地形生成**：Simplex Noise 噪声场 → 高度图 → 等高线渲染
- **多层 Canvas**：地形层 / 阴影层 / 标记层 / 单位层 / 粒子层 / 光照层 / 天气层
- **动态天气系统**：雨、雪、雾实时粒子效果
- **昼夜循环**：光照层随时间渐变，夜间单位周围有视野光圈
- **性能优化**：阴影预渲染缓存、光照层缓存、粒子数量上限控制

---

## 文件结构

```
├── index.html          # 游戏主文件（单文件，含全部 CSS/JS）
├── README.md           # 本说明文档
└── 演示图片/            # 游戏截图
```

---

## 本地运行

直接用浏览器打开 `index.html` 即可，无需安装任何依赖。

---

## 关于作者

数学专业本科生，AI 工具重度用户。
本项目由 Trae IDE + AI 协作开发。
