---
title: 游戏王概率查表
published: 2024-06-18
description: ''
image: ''
tags: []
category: 'YGO'
draft: false 
---

# 游戏王概率查表

> 2023-06-18 补充概率表 1.5
>
> 2021-09-15 修复1.4公式错误(0A0B1+壶不成立)；补充概率表1.4
>
> 2021-09-12 表1.1嵌入1.3
>
> 2021-09-08 补充概率表 1.3
>
> 2021-08-22 补充概率表 1.1, 1.2; 修正1.2简化公式错误

最近有在吹逼游戏王相关，强互动的中速策略为主的环境比较能提起兴致，虽然新冠坐牢遥遥无期，但人还是要有梦想，没事做做环境分析。随风旅鸟这个策略从发售后就上位数寥寥，日本“权威”排表中稳定二线开外，必然是有其致命短板，第一直觉是系统安定性的问题（包含系统初动率和抗压两个维度），而初动率就达不到环境平均水平，抗压方面展开链条每个环节都吃无效系，没有单卡补点，只能依赖抹杀、月书这类系统外对抗牌，系统虽然不大（14张左右）但初动率补助依靠大量壶压缩卡组（系统能搭载所有种类壶是优点，但不得不投入就是缺点了，尤其对后手阻抗上手率毫无帮助反而挤占其卡位，已经不是Hoban的无脑3Upstart Goblin的时代了），系统外卡位相比环境其他中速策略并没有优势。就系统初动率的问题，台北提供了一个思路，压缩围绕场地的2卡combo相关组件，投入小世界现象补助知更单卡初动的思路，我觉得是有其先进性的。小世界能联结系统内和系统外形成一个新的卡片集群，作为新卡的可能性是尚待开发的。但小世界本质也是2卡combo，需要投入特定中介来扩展小世界的配对范围，有优化手牌结构的作用但cost1手的代价会影响其他战术目标的达成。光空口白话列举优劣是很难得出有效的结论的，还是需要将不同构筑投射到同一的测度空间进行直接比较，从点到面建构出一个更直观的认识。

## 1 概率表

先把一些常见的组合情况做个列举，后面案例分析时会引用。

### 1.1 起手单卡

> D = deck size，$40 \leq D \leq 60$
> 
> H = hand size，先手5，后手6

前提

- 一个目标卡片门类投入n张

P[起手1+] =

$$
\frac{\sum_{i=1}^{\min(n,H)}\binom{n}{i} \cdot \binom{D-n}{H-i}}{\binom{D}{H}}
$$

= 1 - P[起手0] =

$$
1 - \frac{\binom{n}{0} \cdot \binom{D-n}{H}}{\binom{D}{H}}
$$

| n   | prob   |
| --- | ------ |
| 1   | 12.50% |
| 2   | 23.72% |
| 3   | 33.76% |
| 4   | 42.71% |
| 5   | 50.66% |
| 6   | 57.71% |
| 7   | 63.93% |
| 8   | 69.40% |
| 9   | 74.18% |
| 10  | 78.34% |

### 1.2 起手2卡combo

前提

- 两个目标卡片门类（A和B），各投入n和m张

P[起手各1+] =

$$
\frac
  { {\color{blue}\sum}_{i=1}^{\min(n,H)} {\color{blue}(} \binom{n}{i} \cdot
      {\color{red}\sum}_{j=1}^{\min(m,H-i)} {\color{red}(}
          \binom{m}{j} \cdot \binom{D-n-m}{H-i-j}
      {\color{red})}
    {\color{blue})}
  }
  {\binom{D}{H}}
$$

= 1 - P[起手0A 1+B] - P[起手1+A 0B] - P[起手0A 0B]

暂不考虑$(D-n-m) < H$的情况

| n \ m | 1                      | 2                      | 3                       | 4                       | 5                       | 6                       | 7                       | 8                       | 9                       | 10                      |
| ----- | ---------------------- | ---------------------- | ----------------------- | ----------------------- | ----------------------- | ----------------------- | ----------------------- | ----------------------- | ----------------------- | ----------------------- |
| 1     | $\color{blue}{1.28\%}$ | $2.46\%$               | $3.55\%$                | $4.54\%$                | $5.45\%$                | $6.28\%$                | $7.04\%$                | $7.72\%$                | $8.34\%$                | $8.89\%$                |
| 2     | $\color{blue}{2.46\%}$ | $\color{blue}{4.73\%}$ | $6.81\%$                | $8.71\%$                | $10.45\%$               | $12.03\%$               | $13.47\%$               | $14.77\%$               | $15.94\%$               | $17.00\%$               |
| 3     | $3.55\%$               | $\color{blue}{6.81\%}$ | $\color{blue}{9.80\%}$  | $12.53\%$               | $15.02\%$               | $17.29\%$               | $19.34\%$               | $21.20\%$               | $22.87\%$               | $24.37\%$               |
| 4     | $4.54\%$               | $8.71\%$               | $\color{blue}{12.53\%}$ | $\color{blue}{16.02\%}$ | $19.19\%$               | $22.08\%$               | $24.69\%$               | $27.04\%$               | $29.15\%$               | $31.05\%$               |
| 5     | $5.45\%$               | $10.45\%$              | $15.02\%$               | $\color{blue}{19.19\%}$ | $\color{blue}{22.99\%}$ | $26.42\%$               | $29.53\%$               | $32.33\%$               | $34.84\%$               | $37.08\%$               |
| 6     | $6.28\%$               | $12.04\%$              | $17.29\%$               | $22.08\%$               | $\color{blue}{26.43\%}$ | $\color{blue}{30.36\%}$ | $33.91\%$               | $37.11\%$               | $39.97\%$               | $42.52\%$               |
| 7     | $7.04\%$               | $13.47\%$              | $19.35\%$               | $24.69\%$               | $29.53\%$               | $\color{blue}{33.92\%}$ | $\color{blue}{37.86\%}$ | $41.40\%$               | $44.57\%$               | $47.39\%$               |
| 8     | $7.73\%$               | $14.78\%$              | $21.21\%$               | $27.05\%$               | $32.34\%$               | $37.11\%$               | $\color{blue}{41.41\%}$ | $\color{blue}{45.26\%}$ | $48.70\%$               | $51.75\%$               |
| 9     | $8.35\%$               | $15.96\%$              | $22.89\%$               | $29.17\%$               | $34.86\%$               | $39.98\%$               | $44.59\%$               | $\color{blue}{48.71\%}$ | $\color{blue}{52.38\%}$ | $55.63\%$               |
| 10    | $8.93\%$               | $17.04\%$              | $24.41\%$               | $31.09\%$               | $37.12\%$               | $42.55\%$               | $47.43\%$               | $51.78\%$               | $\color{blue}{55.65\%}$ | $\color{blue}{59.08\%}$ |

- 在同样卡位(n + m)的情况下，尽可能选择对角线上的组合( $| n - m | \leq 1$ )来最大化概率

### 1.3 壶补助单卡起手

前提

- 目标卡片门类投入n张

- 壶投入u张
  
  - 效果翻/抽V张

P[前H张中0目标卡1+壶，后V张中1+目标卡] =

$$
\frac
  { \binom{n}{0} \cdot {\color{blue}\sum}_{i=1}^{\min(u,H)} {\color{blue}(}
      \binom{u}{i} \cdot \binom{D-n-u}{H-i} \cdot {\color{red}\sum}_{j=1}^{\min(n,V)} {\color{red}(}
        \binom{n}{j} \cdot \binom{D-H-n}{V-j}
      {\color{red})}
    {\color{blue})}
  }
  {\binom{D}{H+V} \cdot \binom{H+V}{H} = \binom{D}{H} \cdot \binom{D-H}{V}}
$$

- 底数两种算法是一样的，所以用等号标注
  
  - 取(H+V)张，选其中H张为前H张，剩下自然为后V张
  
  - 先取H张，然后从剩余的(D-H)张中取V张

- 暂时想不出简化公式（懒

#### 1.3.1 强金/强贪 (v=2)

| n \ u | 0         | 1         | 2         | 3         |
| ----- | --------- | --------- | --------- | --------- |
| 1     | $12.50\%$ | $+0.64\%$ | $+1.21\%$ | $+1.73\%$ |
| 2     | $23.72\%$ | $+1.13\%$ | $+2.14\%$ | $+3.03\%$ |
| 3     | $33.76\%$ | $+1.49\%$ | $+2.81\%$ | $+3.99\%$ |
| 4     | $42.71\%$ | $+1.74\%$ | $+3.28\%$ | $+4.64\%$ |
| 5     | $50.66\%$ | $+1.90\%$ | $+3.57\%$ | $+5.04\%$ |
| 6     | $57.71\%$ | $+1.98\%$ | $+3.71\%$ | $+5.23\%$ |
| 7     | $63.93\%$ | $+1.99\%$ | $+3.74\%$ | $+5.26\%$ |
| 8     | $69.40\%$ | $+1.96\%$ | $+3.67\%$ | $+5.15\%$ |
| 9     | $74.18\%$ | $+1.89\%$ | $+3.53\%$ | $+4.94\%$ |
| 10    | $78.34\%$ | $+1.79\%$ | $+3.33\%$ | $+4.65\%$ |

#### 1.3.2 强谦/金谦 (v=3)

| n \ u | 0         | 1         | 2         | 3         |
| ----- | --------- | --------- | --------- | --------- |
| 1     | $12.50\%$ | $+0.96\%$ | $+1.82\%$ | $+2.59\%$ |
| 2     | $23.72\%$ | $+1.67\%$ | $+3.16\%$ | $+4.48\%$ |
| 3     | $33.76\%$ | $+2.17\%$ | $+4.09\%$ | $+5.80\%$ |
| 4     | $42.71\%$ | $+2.49\%$ | $+4.70\%$ | $+6.65\%$ |
| 5     | $50.66\%$ | $+2.68\%$ | $+5.04\%$ | $+7.11\%$ |
| 6     | $57.71\%$ | $+2.75\%$ | $+5.16\%$ | $+7.27\%$ |
| 7     | $63.93\%$ | $+2.73\%$ | $+5.12\%$ | $+7.20\%$ |
| 8     | $69.40\%$ | $+2.64\%$ | $+4.95\%$ | $+6.94\%$ |
| 9     | $74.18\%$ | $+2.51\%$ | $+4.69\%$ | $+6.56\%$ |
| 10    | $78.34\%$ | $+2.34\%$ | $+4.36\%$ | $+6.09\%$ |

#### 1.3.3 金谦 (v=6)

| n \ u | 0         | 1         | 2         | 3          |
| ----- | --------- | --------- | --------- | ---------- |
| 1     | $12.50\%$ | $+1.92\%$ | $+3.64\%$ | $+5.18\%$  |
| 2     | $23.72\%$ | $+3.19\%$ | $+6.03\%$ | $+8.56\%$  |
| 3     | $33.76\%$ | $+3.95\%$ | $+7.47\%$ | $+10.58\%$ |
| 4     | $42.71\%$ | $+4.35\%$ | $+8.20\%$ | $+11.60\%$ |
| 5     | $50.66\%$ | $+4.47\%$ | $+8.41\%$ | $+11.88\%$ |
| 6     | $57.71\%$ | $+4.40\%$ | $+8.26\%$ | $+11.65\%$ |
| 7     | $63.93\%$ | $+4.20\%$ | $+7.87\%$ | $+11.07\%$ |
| 8     | $69.40\%$ | $+3.91\%$ | $+7.32\%$ | $+10.27\%$ |
| 9     | $74.18\%$ | $+3.57\%$ | $+6.67\%$ | $+9.34\%$  |
| 10    | $78.34\%$ | $+3.22\%$ | $+5.99\%$ | $+8.36\%$  |

- 真滴强，3-3就能达到10%的补助，注意这不光是对单一战术目标的提升，而是全局buff
- 壶的共同弱点，后攻无法补助手坑上手率，但可以补助解场牌
- 目标卡投入量超过5时，补助效率开始衰减，要结合表1.1来看

### 1.4 壶补助2卡combo起手

前提

- 两个目标卡片门类（A和B），各投入n和m张

- 壶投入u张
  
  - 效果翻/抽V张

P[前H张中0A 1+B 1+壶，后V张中1+A] + P[前H张中1+A 0B 1+壶，后V张中1+B] =

$$
\frac
  { \binom{n}{0} \cdot {\color{blue}\sum}_{i=1}^{\min(u,H)} {\color{blue}(}
      \binom{u}{i} \cdot {\color{red}\sum}_{j=1}^{\min(m,H-i)} {\color{red}(}
        \binom{m}{j} \cdot \binom{D-n-m-u}{H-i-j} \cdot {\color{green}\sum}_{k=1}^{\min(n,V)} {\color{green}(}
          \binom{n}{k} \cdot \binom{D-H-n}{V-k}
        {\color{green})}
      {\color{red})}
    {\color{blue})}
  }
  {\binom{D}{H+V} \cdot \binom{H+V}{H} = \binom{D}{H} \cdot \binom{D-H}{V}} \\ +
\frac
  { \binom{m}{0} \cdot {\color{blue}\sum}_{i=1}^{\min(u,H)} {\color{blue}(}
      \binom{u}{i} \cdot {\color{red}\sum}_{j=1}^{\min(n,H-i)} {\color{red}(}
        \binom{n}{j} \cdot \binom{D-n-m-u}{H-i-j} \cdot {\color{green}\sum}_{k=1}^{\min(m,V)} {\color{green}(}
          \binom{m}{k} \cdot \binom{D-H-m}{V-k}
        {\color{green})}
      {\color{red})}
    {\color{blue})}
  }
  {\binom{D}{H+V} \cdot \binom{H+V}{H} = \binom{D}{H} \cdot \binom{D-H}{V}}
$$

- 两项仅仅交换了n和m的位置

- 暂时想不出简化公式（懒

#### 1.4.1 强金/强贪 (v=2)

##### 1.4.1.1 投入1枚 (u=1)

| n \ m | 1         | 2         | 3         | 4         | 5         | 6         | 7         | 8         | 9         | 10        |
| ----- | --------- | --------- | --------- | --------- | --------- | --------- | --------- | --------- | --------- | --------- |
| 1     | $+0.13\%$ | $+0.25\%$ | $+0.35\%$ | $+0.44\%$ | $+0.51\%$ | $+0.57\%$ | $+0.62\%$ | $+0.66\%$ | $+0.69\%$ | $+0.71\%$ |
| 2     | $+0.25\%$ | $+0.47\%$ | $+0.65\%$ | $+0.81\%$ | $+0.94\%$ | $+1.05\%$ | $+1.14\%$ | $+1.20\%$ | $+1.26\%$ | $+1.30\%$ |
| 3     | $+0.35\%$ | $+0.65\%$ | $+0.91\%$ | $+1.12\%$ | $+1.30\%$ | $+1.45\%$ | $+1.57\%$ | $+1.66\%$ | $+1.73\%$ | $+1.77\%$ |
| 4     | $+0.44\%$ | $+0.81\%$ | $+1.12\%$ | $+1.39\%$ | $+1.60\%$ | $+1.78\%$ | $+1.92\%$ | $+2.02\%$ | $+2.10\%$ | $+2.15\%$ |
| 5     | $+0.51\%$ | $+0.94\%$ | $+1.30\%$ | $+1.60\%$ | $+1.85\%$ | $+2.05\%$ | $+2.20\%$ | $+2.31\%$ | $+2.40\%$ | $+2.45\%$ |
| 6     | $+0.57\%$ | $+1.05\%$ | $+1.45\%$ | $+1.78\%$ | $+2.05\%$ | $+2.26\%$ | $+2.42\%$ | $+2.54\%$ | $+2.62\%$ | $+2.67\%$ |
| 7     | $+0.62\%$ | $+1.14\%$ | $+1.57\%$ | $+1.92\%$ | $+2.20\%$ | $+2.42\%$ | $+2.58\%$ | $+2.70\%$ | $+2.78\%$ | $+2.83\%$ |
| 8     | $+0.66\%$ | $+1.20\%$ | $+1.66\%$ | $+2.02\%$ | $+2.31\%$ | $+2.54\%$ | $+2.70\%$ | $+2.82\%$ | $+2.89\%$ | $+2.93\%$ |
| 9     | $+0.69\%$ | $+1.26\%$ | $+1.73\%$ | $+2.10\%$ | $+2.40\%$ | $+2.62\%$ | $+2.78\%$ | $+2.89\%$ | $+2.95\%$ | $+2.98\%$ |
| 10    | $+0.71\%$ | $+1.30\%$ | $+1.77\%$ | $+2.15\%$ | $+2.45\%$ | $+2.67\%$ | $+2.83\%$ | $+2.93\%$ | $+2.98\%$ | $+3.00\%$ |

##### 1.4.1.2 投入2枚 (u=2)

| n \ m | 1         | 2         | 3         | 4         | 5         | 6         | 7         | 8         | 9         | 10        |
| ----- | --------- | --------- | --------- | --------- | --------- | --------- | --------- | --------- | --------- | --------- |
| 1     | $+0.26\%$ | $+0.48\%$ | $+0.67\%$ | $+0.84\%$ | $+0.97\%$ | $+1.09\%$ | $+1.18\%$ | $+1.25\%$ | $+1.31\%$ | $+1.35\%$ |
| 2     | $+0.48\%$ | $+0.90\%$ | $+1.25\%$ | $+1.55\%$ | $+1.80\%$ | $+2.00\%$ | $+2.16\%$ | $+2.29\%$ | $+2.39\%$ | $+2.47\%$ |
| 3     | $+0.67\%$ | $+1.25\%$ | $+1.74\%$ | $+2.15\%$ | $+2.49\%$ | $+2.76\%$ | $+2.98\%$ | $+3.15\%$ | $+3.28\%$ | $+3.37\%$ |
| 4     | $+0.84\%$ | $+1.55\%$ | $+2.15\%$ | $+2.65\%$ | $+3.06\%$ | $+3.39\%$ | $+3.65\%$ | $+3.84\%$ | $+3.99\%$ | $+4.08\%$ |
| 5     | $+0.97\%$ | $+1.80\%$ | $+2.49\%$ | $+3.06\%$ | $+3.52\%$ | $+3.89\%$ | $+4.18\%$ | $+4.39\%$ | $+4.54\%$ | $+4.64\%$ |
| 6     | $+1.09\%$ | $+2.00\%$ | $+2.76\%$ | $+3.39\%$ | $+3.89\%$ | $+4.28\%$ | $+4.59\%$ | $+4.81\%$ | $+4.96\%$ | $+5.04\%$ |
| 7     | $+1.18\%$ | $+2.16\%$ | $+2.98\%$ | $+3.65\%$ | $+4.18\%$ | $+4.59\%$ | $+4.89\%$ | $+5.11\%$ | $+5.25\%$ | $+5.33\%$ |
| 8     | $+1.25\%$ | $+2.29\%$ | $+3.15\%$ | $+3.84\%$ | $+4.39\%$ | $+4.81\%$ | $+5.11\%$ | $+5.32\%$ | $+5.45\%$ | $+5.51\%$ |
| 9     | $+1.31\%$ | $+2.39\%$ | $+3.28\%$ | $+3.99\%$ | $+4.54\%$ | $+4.96\%$ | $+5.25\%$ | $+5.45\%$ | $+5.56\%$ | $+5.60\%$ |
| 10    | $+1.35\%$ | $+2.47\%$ | $+3.37\%$ | $+4.08\%$ | $+4.64\%$ | $+5.04\%$ | $+5.33\%$ | $+5.51\%$ | $+5.60\%$ | $+5.62\%$ |

##### 1.4.1.3 投入3枚 (u=3)

| n \ m | 1         | 2         | 3         | 4         | 5         | 6         | 7         | 8         | 9         | 10        |
| ----- | --------- | --------- | --------- | --------- | --------- | --------- | --------- | --------- | --------- | --------- |
| 1     | $+0.37\%$ | $+0.69\%$ | $+0.97\%$ | $+1.20\%$ | $+1.39\%$ | $+1.56\%$ | $+1.69\%$ | $+1.79\%$ | $+1.87\%$ | $+1.93\%$ |
| 2     | $+0.69\%$ | $+1.29\%$ | $+1.79\%$ | $+2.22\%$ | $+2.57\%$ | $+2.86\%$ | $+3.09\%$ | $+3.28\%$ | $+3.41\%$ | $+3.51\%$ |
| 3     | $+0.97\%$ | $+1.79\%$ | $+2.49\%$ | $+3.08\%$ | $+3.56\%$ | $+3.95\%$ | $+4.26\%$ | $+4.49\%$ | $+4.67\%$ | $+4.79\%$ |
| 4     | $+1.20\%$ | $+2.22\%$ | $+3.08\%$ | $+3.79\%$ | $+4.37\%$ | $+4.83\%$ | $+5.20\%$ | $+5.47\%$ | $+5.67\%$ | $+5.80\%$ |
| 5     | $+1.39\%$ | $+2.57\%$ | $+3.56\%$ | $+4.37\%$ | $+5.02\%$ | $+5.55\%$ | $+5.95\%$ | $+6.24\%$ | $+6.45\%$ | $+6.58\%$ |
| 6     | $+1.56\%$ | $+2.86\%$ | $+3.95\%$ | $+4.83\%$ | $+5.55\%$ | $+6.10\%$ | $+6.52\%$ | $+6.83\%$ | $+7.03\%$ | $+7.15\%$ |
| 7     | $+1.69\%$ | $+3.09\%$ | $+4.26\%$ | $+5.20\%$ | $+5.95\%$ | $+6.52\%$ | $+6.95\%$ | $+7.25\%$ | $+7.44\%$ | $+7.54\%$ |
| 8     | $+1.79\%$ | $+3.28\%$ | $+4.49\%$ | $+5.47\%$ | $+6.24\%$ | $+6.83\%$ | $+7.25\%$ | $+7.54\%$ | $+7.71\%$ | $+7.78\%$ |
| 9     | $+1.87\%$ | $+3.41\%$ | $+4.67\%$ | $+5.67\%$ | $+6.45\%$ | $+7.03\%$ | $+7.44\%$ | $+7.71\%$ | $+7.85\%$ | $+7.89\%$ |
| 10    | $+1.93\%$ | $+3.51\%$ | $+4.79\%$ | $+5.80\%$ | $+6.58\%$ | $+7.15\%$ | $+7.54\%$ | $+7.78\%$ | $+7.89\%$ | $+7.91\%$ |

#### 1.4.2 强谦/金谦 (v=3)

##### 1.4.2.1 投入1枚 (u=1)

| n \ m | 1         | 2         | 3         | 4         | 5         | 6         | 7         | 8         | 9         | 10        |
| ----- | --------- | --------- | --------- | --------- | --------- | --------- | --------- | --------- | --------- | --------- |
| 1     | $+0.20\%$ | $+0.37\%$ | $+0.52\%$ | $+0.64\%$ | $+0.74\%$ | $+0.83\%$ | $+0.89\%$ | $+0.95\%$ | $+0.99\%$ | $+1.02\%$ |
| 2     | $+0.37\%$ | $+0.69\%$ | $+0.96\%$ | $+1.18\%$ | $+1.36\%$ | $+1.51\%$ | $+1.63\%$ | $+1.72\%$ | $+1.79\%$ | $+1.84\%$ |
| 3     | $+0.52\%$ | $+0.96\%$ | $+1.32\%$ | $+1.63\%$ | $+1.87\%$ | $+2.07\%$ | $+2.22\%$ | $+2.34\%$ | $+2.42\%$ | $+2.49\%$ |
| 4     | $+0.64\%$ | $+1.18\%$ | $+1.63\%$ | $+1.99\%$ | $+2.28\%$ | $+2.51\%$ | $+2.69\%$ | $+2.83\%$ | $+2.92\%$ | $+2.98\%$ |
| 5     | $+0.74\%$ | $+1.36\%$ | $+1.87\%$ | $+2.28\%$ | $+2.61\%$ | $+2.87\%$ | $+3.06\%$ | $+3.20\%$ | $+3.30\%$ | $+3.36\%$ |
| 6     | $+0.83\%$ | $+1.51\%$ | $+2.07\%$ | $+2.51\%$ | $+2.87\%$ | $+3.14\%$ | $+3.34\%$ | $+3.48\%$ | $+3.57\%$ | $+3.62\%$ |
| 7     | $+0.89\%$ | $+1.63\%$ | $+2.22\%$ | $+2.69\%$ | $+3.06\%$ | $+3.34\%$ | $+3.54\%$ | $+3.67\%$ | $+3.76\%$ | $+3.79\%$ |
| 8     | $+0.95\%$ | $+1.72\%$ | $+2.34\%$ | $+2.83\%$ | $+3.20\%$ | $+3.48\%$ | $+3.67\%$ | $+3.80\%$ | $+3.87\%$ | $+3.89\%$ |
| 9     | $+0.99\%$ | $+1.79\%$ | $+2.42\%$ | $+2.92\%$ | $+3.30\%$ | $+3.57\%$ | $+3.76\%$ | $+3.87\%$ | $+3.92\%$ | $+3.93\%$ |
| 10    | $+1.02\%$ | $+1.84\%$ | $+2.49\%$ | $+2.98\%$ | $+3.36\%$ | $+3.62\%$ | $+3.79\%$ | $+3.89\%$ | $+3.93\%$ | $+3.92\%$ |

##### 1.4.2.2 投入2枚 (u=2)

| n \ m | 1         | 2         | 3         | 4         | 5         | 6         | 7         | 8         | 9         | 10        |
| ----- | --------- | --------- | --------- | --------- | --------- | --------- | --------- | --------- | --------- | --------- |
| 1     | $+0.39\%$ | $+0.72\%$ | $+1.00\%$ | $+1.23\%$ | $+1.42\%$ | $+1.58\%$ | $+1.70\%$ | $+1.80\%$ | $+1.88\%$ | $+1.94\%$ |
| 2     | $+0.72\%$ | $+1.33\%$ | $+1.83\%$ | $+2.26\%$ | $+2.60\%$ | $+2.88\%$ | $+3.10\%$ | $+3.27\%$ | $+3.40\%$ | $+3.49\%$ |
| 3     | $+1.00\%$ | $+1.83\%$ | $+2.53\%$ | $+3.10\%$ | $+3.57\%$ | $+3.94\%$ | $+4.23\%$ | $+4.45\%$ | $+4.61\%$ | $+4.72\%$ |
| 4     | $+1.23\%$ | $+2.26\%$ | $+3.10\%$ | $+3.80\%$ | $+4.35\%$ | $+4.79\%$ | $+5.12\%$ | $+5.37\%$ | $+5.54\%$ | $+5.66\%$ |
| 5     | $+1.42\%$ | $+2.60\%$ | $+3.57\%$ | $+4.35\%$ | $+4.97\%$ | $+5.45\%$ | $+5.81\%$ | $+6.07\%$ | $+6.25\%$ | $+6.35\%$ |
| 6     | $+1.58\%$ | $+2.88\%$ | $+3.94\%$ | $+4.79\%$ | $+5.45\%$ | $+5.96\%$ | $+6.33\%$ | $+6.59\%$ | $+6.75\%$ | $+6.84\%$ |
| 7     | $+1.70\%$ | $+3.10\%$ | $+4.23\%$ | $+5.12\%$ | $+5.81\%$ | $+6.33\%$ | $+6.70\%$ | $+6.95\%$ | $+7.10\%$ | $+7.16\%$ |
| 8     | $+1.80\%$ | $+3.27\%$ | $+4.45\%$ | $+5.37\%$ | $+6.07\%$ | $+6.59\%$ | $+6.95\%$ | $+7.18\%$ | $+7.30\%$ | $+7.33\%$ |
| 9     | $+1.88\%$ | $+3.40\%$ | $+4.61\%$ | $+5.54\%$ | $+6.25\%$ | $+6.75\%$ | $+7.10\%$ | $+7.30\%$ | $+7.39\%$ | $+7.39\%$ |
| 10    | $+1.94\%$ | $+3.49\%$ | $+4.72\%$ | $+5.66\%$ | $+6.35\%$ | $+6.84\%$ | $+7.16\%$ | $+7.33\%$ | $+7.39\%$ | $+7.35\%$ |

##### 1.4.2.3 投入3枚 (u=3)

| n \ m | 1         | 2         | 3         | 4         | 5         | 6         | 7          | 8          | 9          | 10         |
| ----- | --------- | --------- | --------- | --------- | --------- | --------- | ---------- | ---------- | ---------- | ---------- |
| 1     | $+0.56\%$ | $+1.03\%$ | $+1.43\%$ | $+1.76\%$ | $+2.04\%$ | $+2.26\%$ | $+2.44\%$  | $+2.58\%$  | $+2.69\%$  | $+2.77\%$  |
| 2     | $+1.03\%$ | $+1.90\%$ | $+2.63\%$ | $+3.23\%$ | $+3.73\%$ | $+4.12\%$ | $+4.43\%$  | $+4.67\%$  | $+4.85\%$  | $+4.98\%$  |
| 3     | $+1.43\%$ | $+2.63\%$ | $+3.63\%$ | $+4.45\%$ | $+5.11\%$ | $+5.63\%$ | $+6.04\%$  | $+6.34\%$  | $+6.57\%$  | $+6.72\%$  |
| 4     | $+1.76\%$ | $+3.23\%$ | $+4.45\%$ | $+5.43\%$ | $+6.22\%$ | $+6.83\%$ | $+7.30\%$  | $+7.65\%$  | $+7.89\%$  | $+8.04\%$  |
| 5     | $+2.04\%$ | $+3.73\%$ | $+5.11\%$ | $+6.22\%$ | $+7.09\%$ | $+7.77\%$ | $+8.28\%$  | $+8.64\%$  | $+8.88\%$  | $+9.01\%$  |
| 6     | $+2.26\%$ | $+4.12\%$ | $+5.63\%$ | $+6.83\%$ | $+7.77\%$ | $+8.48\%$ | $+9.00\%$  | $+9.36\%$  | $+9.58\%$  | $+9.69\%$  |
| 7     | $+2.44\%$ | $+4.43\%$ | $+6.04\%$ | $+7.30\%$ | $+8.28\%$ | $+9.00\%$ | $+9.52\%$  | $+9.86\%$  | $+10.05\%$ | $+10.12\%$ |
| 8     | $+2.58\%$ | $+4.67\%$ | $+6.34\%$ | $+7.65\%$ | $+8.64\%$ | $+9.36\%$ | $+9.86\%$  | $+10.17\%$ | $+10.32\%$ | $+10.35\%$ |
| 9     | $+2.69\%$ | $+4.85\%$ | $+6.57\%$ | $+7.89\%$ | $+8.88\%$ | $+9.58\%$ | $+10.05\%$ | $+10.32\%$ | $+10.43\%$ | $+10.41\%$ |
| 10    | $+2.77\%$ | $+4.98\%$ | $+6.72\%$ | $+8.04\%$ | $+9.01\%$ | $+9.69\%$ | $+10.12\%$ | $+10.35\%$ | $+10.41\%$ | $+10.34\%$ |

#### 1.4.3 金谦 (v=6)

##### 1.4.3.1 投入1枚 (u=1)

| n \ m | 1         | 2         | 3         | 4         | 5         | 6         | 7         | 8         | 9         | 10        |
| ----- | --------- | --------- | --------- | --------- | --------- | --------- | --------- | --------- | --------- | --------- |
| 1     | $+0.40\%$ | $+0.73\%$ | $+1.00\%$ | $+1.21\%$ | $+1.38\%$ | $+1.52\%$ | $+1.63\%$ | $+1.71\%$ | $+1.78\%$ | $+1.83\%$ |
| 2     | $+0.73\%$ | $+1.32\%$ | $+1.79\%$ | $+2.16\%$ | $+2.46\%$ | $+2.69\%$ | $+2.86\%$ | $+3.00\%$ | $+3.10\%$ | $+3.18\%$ |
| 3     | $+1.00\%$ | $+1.79\%$ | $+2.41\%$ | $+2.90\%$ | $+3.28\%$ | $+3.57\%$ | $+3.78\%$ | $+3.95\%$ | $+4.06\%$ | $+4.14\%$ |
| 4     | $+1.21\%$ | $+2.16\%$ | $+2.90\%$ | $+3.47\%$ | $+3.90\%$ | $+4.22\%$ | $+4.45\%$ | $+4.62\%$ | $+4.73\%$ | $+4.80\%$ |
| 5     | $+1.38\%$ | $+2.46\%$ | $+3.28\%$ | $+3.90\%$ | $+4.36\%$ | $+4.69\%$ | $+4.93\%$ | $+5.08\%$ | $+5.17\%$ | $+5.22\%$ |
| 6     | $+1.52\%$ | $+2.69\%$ | $+3.57\%$ | $+4.22\%$ | $+4.69\%$ | $+5.02\%$ | $+5.24\%$ | $+5.38\%$ | $+5.44\%$ | $+5.46\%$ |
| 7     | $+1.63\%$ | $+2.86\%$ | $+3.78\%$ | $+4.45\%$ | $+4.93\%$ | $+5.24\%$ | $+5.44\%$ | $+5.55\%$ | $+5.58\%$ | $+5.57\%$ |
| 8     | $+1.71\%$ | $+3.00\%$ | $+3.95\%$ | $+4.62\%$ | $+5.08\%$ | $+5.38\%$ | $+5.55\%$ | $+5.62\%$ | $+5.62\%$ | $+5.57\%$ |
| 9     | $+1.78\%$ | $+3.10\%$ | $+4.06\%$ | $+4.73\%$ | $+5.17\%$ | $+5.44\%$ | $+5.58\%$ | $+5.62\%$ | $+5.59\%$ | $+5.50\%$ |
| 10    | $+1.83\%$ | $+3.18\%$ | $+4.14\%$ | $+4.80\%$ | $+5.22\%$ | $+5.46\%$ | $+5.57\%$ | $+5.57\%$ | $+5.50\%$ | $+5.38\%$ |

##### 1.4.3.2 投入2枚 (u=2)

| n \ m | 1         | 2         | 3         | 4         | 5         | 6          | 7          | 8          | 9          | 10         |
| ----- | --------- | --------- | --------- | --------- | --------- | ---------- | ---------- | ---------- | ---------- | ---------- |
| 1     | $+0.78\%$ | $+1.41\%$ | $+1.91\%$ | $+2.32\%$ | $+2.64\%$ | $+2.90\%$  | $+3.11\%$  | $+3.27\%$  | $+3.40\%$  | $+3.49\%$  |
| 2     | $+1.41\%$ | $+2.53\%$ | $+3.43\%$ | $+4.14\%$ | $+4.69\%$ | $+5.13\%$  | $+5.46\%$  | $+5.72\%$  | $+5.91\%$  | $+6.05\%$  |
| 3     | $+1.91\%$ | $+3.43\%$ | $+4.62\%$ | $+5.54\%$ | $+6.26\%$ | $+6.80\%$  | $+7.21\%$  | $+7.51\%$  | $+7.72\%$  | $+7.87\%$  |
| 4     | $+2.32\%$ | $+4.14\%$ | $+5.54\%$ | $+6.62\%$ | $+7.43\%$ | $+8.04\%$  | $+8.47\%$  | $+8.78\%$  | $+8.98\%$  | $+9.10\%$  |
| 5     | $+2.64\%$ | $+4.69\%$ | $+6.26\%$ | $+7.43\%$ | $+8.30\%$ | $+8.93\%$  | $+9.36\%$  | $+9.64\%$  | $+9.81\%$  | $+9.89\%$  |
| 6     | $+2.90\%$ | $+5.13\%$ | $+6.80\%$ | $+8.04\%$ | $+8.93\%$ | $+9.54\%$  | $+9.95\%$  | $+10.19\%$ | $+10.30\%$ | $+10.32\%$ |
| 7     | $+3.11\%$ | $+5.46\%$ | $+7.21\%$ | $+8.47\%$ | $+9.36\%$ | $+9.95\%$  | $+10.30\%$ | $+10.49\%$ | $+10.54\%$ | $+10.50\%$ |
| 8     | $+3.27\%$ | $+5.72\%$ | $+7.51\%$ | $+8.78\%$ | $+9.64\%$ | $+10.19\%$ | $+10.49\%$ | $+10.61\%$ | $+10.60\%$ | $+10.49\%$ |
| 9     | $+3.40\%$ | $+5.91\%$ | $+7.72\%$ | $+8.98\%$ | $+9.81\%$ | $+10.30\%$ | $+10.54\%$ | $+10.60\%$ | $+10.52\%$ | $+10.34\%$ |
| 10    | $+3.49\%$ | $+6.05\%$ | $+7.87\%$ | $+9.10\%$ | $+9.89\%$ | $+10.32\%$ | $+10.50\%$ | $+10.49\%$ | $+10.34\%$ | $+10.10\%$ |

##### 1.4.3.3 投入3枚 (u=3)

| n \ m | 1         | 2         | 3          | 4          | 5          | 6          | 7          | 8          | 9          | 10         |
| ----- | --------- | --------- | ---------- | ---------- | ---------- | ---------- | ---------- | ---------- | ---------- | ---------- |
| 1     | $+1.12\%$ | $+2.02\%$ | $+2.75\%$  | $+3.33\%$  | $+3.79\%$  | $+4.16\%$  | $+4.45\%$  | $+4.68\%$  | $+4.85\%$  | $+4.99\%$  |
| 2     | $+2.02\%$ | $+3.64\%$ | $+4.92\%$  | $+5.93\%$  | $+6.72\%$  | $+7.34\%$  | $+7.81\%$  | $+8.17\%$  | $+8.44\%$  | $+8.63\%$  |
| 3     | $+2.75\%$ | $+4.92\%$ | $+6.62\%$  | $+7.94\%$  | $+8.95\%$  | $+9.72\%$  | $+10.29\%$ | $+10.71\%$ | $+11.00\%$ | $+11.20\%$ |
| 4     | $+3.33\%$ | $+5.93\%$ | $+7.94\%$  | $+9.47\%$  | $+10.62\%$ | $+11.47\%$ | $+12.08\%$ | $+12.50\%$ | $+12.78\%$ | $+12.94\%$ |
| 5     | $+3.79\%$ | $+6.72\%$ | $+8.95\%$  | $+10.62\%$ | $+11.85\%$ | $+12.73\%$ | $+13.33\%$ | $+13.71\%$ | $+13.93\%$ | $+14.03\%$ |
| 6     | $+4.16\%$ | $+7.34\%$ | $+9.72\%$  | $+11.47\%$ | $+12.73\%$ | $+13.59\%$ | $+14.14\%$ | $+14.47\%$ | $+14.61\%$ | $+14.63\%$ |
| 7     | $+4.45\%$ | $+7.81\%$ | $+10.29\%$ | $+12.08\%$ | $+13.33\%$ | $+14.14\%$ | $+14.63\%$ | $+14.88\%$ | $+14.93\%$ | $+14.86\%$ |
| 8     | $+4.68\%$ | $+8.17\%$ | $+10.71\%$ | $+12.50\%$ | $+13.71\%$ | $+14.47\%$ | $+14.88\%$ | $+15.03\%$ | $+14.99\%$ | $+14.81\%$ |
| 9     | $+4.85\%$ | $+8.44\%$ | $+11.00\%$ | $+12.78\%$ | $+13.93\%$ | $+14.61\%$ | $+14.93\%$ | $+14.99\%$ | $+14.85\%$ | $+14.57\%$ |
| 10    | $+4.99\%$ | $+8.63\%$ | $+11.20\%$ | $+12.94\%$ | $+14.03\%$ | $+14.63\%$ | $+14.86\%$ | $+14.81\%$ | $+14.57\%$ | $+14.21\%$ |

### 1.5 满编卡上手复数

前提

- 有n种类卡片满编投入（3张）

P[前H张中任意种类上手2或3的概率] =

$$
\frac{\sum_{i=2}^3{\binom{n}{1} \cdot \binom{3}{i} \cdot \binom{D - 3}{H - i} }}{\binom{D}{H}}
$$

| n \ H | 5 (先手) | 6 (后手) |
| ----- | ------ | ------ |
| 1     | 3.64%  | 5.36%  |
| 2     | 7.29%  | 10.73% |
| 3     | 10.93% | 16.09% |
| 4     | 14.57% | 21.46% |
| 5     | 18.22% | 26.82% |
| 6     | 21.86% | 32.19% |
| 7     | 25.51% | 37.55% |
| 8     | 29.15% | 42.91% |
| 9     | 32.79% | 48.28% |
| 10    | 36.44% | 53.64% |
