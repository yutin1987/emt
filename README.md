# emt

## 處置流程

基本

創傷

非創傷

火災

## 評估方式

### 初步評估

```mermaid
flowchart LR;
    安全-->防護
    subgraph 安全
        direction TB
        現1[現場安全]-->現大{{大量傷病患}}
        現1-->現2>呼叫支援]
        style 現2 stroke-dasharray: 5 5
    end
    subgraph 防護
        direction TB
        防1[戴手套, 口罩]-->防2>面罩, 防護衣]
        style 防2 stroke-dasharray: 5 5
    end
    防護-->自介{{自我介紹}}
    自介-->|創傷\n兒童, 新生兒, 急產, 溺水, 燒燙傷或無法判定|創傷[創傷 XABCDE]
    自介-->|非創傷|非創傷[非創傷 ABC]
    自介-->|特殊|特殊[特殊]
```

### 創傷流程

```mermaid
%%{init: {'flowchart' : {'curve' : 'linear'}}}%%
flowchart TB;
    subgraph 詢問[詢問]
        direction TB
        詢問1["
            主訴: 哪裡不舒服? 感覺怎樣? 多久?
            之前: 不舒服前在做什麼?
            吃過: 最近一次用餐時間?
            藥: 服用任何藥物?
            敏: 食物或藥物過敏?
            感: 其他不舒服?
        "]
        style 詢問1 text-align: left
    end
    subgraph 叫 ["叫 AVPU"]
        direction TB
        叫1[哪裡不舒服?]-->|沒反應| 叫2{{+ 拍肩}}
        叫2-->|沒反應| 叫3{{頸動脈}}
        叫3-->|沒脈搏| 叫4[[OHCA]]
    end
    叫-->A
    subgraph A
        direction TB
        A1[呼吸道]-->|"鼾聲、雜音"| A2>"暢通<sub>呼吸道</sub>"]
        A2-->A3{無改善}
        A3-->A4>鼻管]
        A3-->|痛無反應| A5>口咽]
        style A2 stroke-dasharray: 5 5
        style A4 stroke-dasharray: 5 5
        style A5 stroke-dasharray: 5 5
    end
    A-->B
    subgraph B
        direction TB
        B1[呼吸深淺快慢]-->|"≥ 24"| B2>"(Sample) Mask"]
        B1[呼吸深淺快慢]-->|"≥ 30 ≤ 10"| B3>NRM]
        style B2 stroke-dasharray: 5 5
        style B3 stroke-dasharray: 5 5
    end
    B-->C
    subgraph C ["C 循環"]
        direction LR
        C1["<sub>目視有無</sub>大出血"]
        C1-->C2[橈動脈對等]
        C2-->C3[CRT]
        C3-->C4[末端濕冷]
        C4-->C5[膚色蒼白 臉色發紺]
    end
    C-->D
    subgraph D ["D 失能"]
        direction LR
        D1["GCS"]
        D1-->D2["瞳孔"]
        D2-->D3["<sub>四肢</sub>感<sub>覺</sub>運<sub>動</sub>"]
    end
    D-->E
    subgraph E ["E 暴露"]
        direction LR
        E1["
            目視頭頸胸腹骨盆四隻是否有致命性傷口，必要時移除衣物
            頸: 氣管<sub>是否偏移</sub>
            頸: 頸靜脈<sub>是否怒張或塌陷</sub>
            頸: 頸椎<sub>是否壓痛</sub>
            胸: <sub>有無</sub>皮下氣腫
            股盆: 骨盆<sub>是否穩固</sub>
        "]
        style E1 text-align: left
    end
    E-->輔助
    subgraph 輔助
        direction LR
        輔助1["
            除非 OHCA: 血壓、血氧、體溫
            急性意識改變或頭部創傷: 瞳孔
            呼吸困難或胸部創傷: 聽診<sub>肺音</sub>
        "]
        style 輔助1 text-align: left
    end
    輔助-->危急{危急個案}
    危急-->二評
    subgraph 二評["二評 (BLS 非危急現場二評)"]
        direction LR
        二評1["[意<sub>識</sub>]、[呼<sub>吸</sub>]、脈<sub>搏</sub>、<sub>血</sub>壓、[瞳<sub>孔</sub>]、體<sub>溫</sub>、[膚<sub>色</sub>]、<sub>血</sub>氧"]
        二評2["
            頭: 額骨顴骨下顎骨<sub>是否穩固</sub>、<sub>是否</sub>耳漏鼻漏、熊貓眼耳後瘀青
            胸: 鎖骨上胸下胸<sub>是否穩固</sub>，起伏<sub>是否對等</sub>、<sub>聽診</sub>肺音
            腹: <sub>是否</sub>瘀青、傷口、腫脹、<sub>是否</sub>壓痛<sub>(四區)</sub>
            四肢: <sub>是否</sub>瘀青、傷口、腫脹、變形，<sub>是否</sub>對等
            紅疹紫斑
        "]
        style 二評2 text-align: left
    end
    二評-->救護車回報
```

### 非創流程

```mermaid
%%{init: {'flowchart' : {'curve' : 'linear'}}}%%
flowchart TB;
    subgraph 詢問[詢問]
        direction TB
        詢問1["
            主訴: 哪裡不舒服? 感覺怎樣? 多久?
            之前: 不舒服前在做什麼?
            吃過: 最近一次用餐時間?
            藥: 服用任何藥物?
            敏: 食物或藥物過敏?
            感: 其他不舒服?
        "]
        style 詢問1 text-align: left, stroke-dasharray: 5 5
    end
    詢問-->|胸痛|胸痛
    subgraph 胸痛[OPQRST]
        胸痛1["
            O: 突然? 慢慢?
            P: 緩解? 加劇?
            Q: 壓迫緊縮?悶痛?刺痛?撕裂痛?
            R: <sub>有無</sub>轉移?
            S: 程度1~10?
            T: 多久?
            其他症狀?
        "]
        style 胸痛1 text-align: left, stroke-dasharray: 5 5
    end
    subgraph 叫 ["叫 AVPU"]
        direction TB
        叫1[哪裡不舒服?]-->|沒反應| 叫2{{+ 拍肩}}
        叫2-->|沒反應| 叫3{{頸動脈}}
        叫3-->|沒脈搏| 叫4[[OHCA]]
    end
    叫-->A
    subgraph A
        direction TB
        A1[呼吸道]-->|"鼾聲、雜音"| A2>"暢通<sub>呼吸道</sub>"]
        A2-->A3{無改善}
        A3-->A4>鼻管]
        A3-->|痛無反應| A5>口咽]
        style A2 stroke-dasharray: 5 5
        style A4 stroke-dasharray: 5 5
        style A5 stroke-dasharray: 5 5
    end
    A-->B
    subgraph B
        direction TB
        B1[呼吸深淺快慢]-->|"≥ 24"| B2>"(Sample) Mask"]
        B1[呼吸深淺快慢]-->|"≥ 30 ≤ 10"| B3>NRM]
        style B2 stroke-dasharray: 5 5
        style B3 stroke-dasharray: 5 5
    end
    B-->C
    subgraph C ["C 循環"]
        direction LR
        C1[橈動脈對等]
        C1-->C2[CRT]
        C2-->C3[末端濕冷]
        C3-->C4[膚色蒼白 臉色發紺]
    end
    C-->輔助
    subgraph 輔助
        direction LR
        輔助1["
            除非 OHCA: 血壓、血氧、體溫
            混亂、冒冷汗、虛弱、顫抖、嚴重脫水、低體溫、糖尿病、肝硬化: 血糖
            急性意識改變: 血糖、GCS
            呼吸困難: 聽診、血糖
            胸痛: 聽診
            毒藥物中毒: 瞳孔
            腦中風: G-FAST(眼動、微笑 舉手 說你好)、瞳孔、血糖
        "]
        style 輔助1 text-align: left
    end
    輔助-->危急{危急個案}
    危急-->二評
    subgraph 二評["二評 (BLS 非危急現場二評)"]
        direction LR
        二評1["[意<sub>識</sub>]、[呼<sub>吸</sub>]、脈<sub>搏</sub>、<sub>血</sub>壓、[瞳<sub>孔</sub>]、體<sub>溫</sub>、[膚<sub>色</sub>]、<sub>血</sub>氧"]
        二評2["
            頸: 氣管<sub>是否偏移</sub>、頸靜脈<sub>是否怒張或塌陷</sub>
            胸: <sub>是否</sub>紅疹紫斑、起伏<sub>是否對等</sub>、<sub>聽診</sub>肺音
            腹: <sub>是否</sub>腫脹、<sub>是否</sub>壓痛<sub>(四區)</sub>
            四肢: <sub>是否</sub>紅疹紫斑、針孔、水腫、浮腫
            紅疹紫斑
        "]
        style 二評2 text-align: left
    end
    二評-->救護車回報
```

### 危急個案

- 生命徵象
    - GCS < 14
    - 呼吸次數(RR) ≥ 5 OR < 1.6666 / 10s
    - 脈搏 > 150 OR < 50
    - 收縮壓 > 200 OR < 90 mmHg
    - 微血管充填時間(CRT) > 2s
    - 體溫(BT) > 41 OR < 32°C
    - 血氧(SPO2) < 90%
- 創傷部位
    - 體表面積 >25% 或顏面、會陰之 2 度或 3 度燒灼傷
    - 重大的電（雷）擊傷
    - 化學性、吸入性燒灼傷
    - 頭頸軀幹及肘膝處以上肢體之穿刺傷
    - 大量皮下氣腫
    - 氣管支氣管損傷
    - 內臟外露
    - 手腕或腳踝以上之截肢
    - 兩處以上大腿及上臂處長骨骨折、骨盆腔骨折、頭骨開放或凹陷性骨折
    - 肢體脈搏摸不到
    - 癱瘓、壓碎傷或嚴重撕裂傷
- 創傷機轉
    - 高處墜落 > 6 公尺（OR > 2 層樓高）或小兒 > 3 公尺（OR > 身高 2 倍）
    - 脫困時間 > 20 分鐘
    - 身體被車輛輾過(遠端肢體除外)
    - 從車輛中被拋出、同車有死亡者或其他有高能量撞擊
- 特殊情況
    - 血糖 < 60mg/dl 或 ≥ 500mg/dl
    - 疑似急性腦中風或缺血性胸痛
    - 當病患連續抽搐超過 5 分鐘，或在 5 分鐘內有2次發作且意識未能恢復（癲癇重積，應立刻請求支援）
    - 中毒可能危及生命
    - 小兒評估三角異常者
    - 急產或已經完成接生
    - 毒蛇咬傷
    - 溺水

### 燒燙傷
成人：頭上肢 9%、前後軀幹及下肢 18%、外陰 1%
兒童：頭 18%、下肢 14%

### GCS

```mermaid
flowchart TD;
    A1[名字? 是誰? 哪裡?]
    A1-->|YES| A2[手舉一下?]
    A2-->|YES| A3[15: E4 V5 M6]
    
    B1[名字? 是誰? 哪裡?]
    B1-->|NO| B2[名字? + 拍肩]
    B2-->|YES| B3[手舉一下?]
    B3-->|YES| B4[14: E3 V5 M6]

    D1[名字? 是誰? 哪裡?]
    D1-->|NO| D2[名字? + 拍肩]
    D2-->|NO| D3[捏肩疼痛測試]
    D3-->|定位| D3M5[8: E1 V2 M5]
    D3-->|無法定位| D3M4[7: E1 V2 M4]
    D3-->|病態屈曲| D3M3[6: E1 V2 M3]
    D3-->|四隻僵直| D3M2[5: E1 V2 M2]

    E1[名字? 是誰? 哪裡?]
    E1-->|NO| E2[名字? + 拍肩]
    E2-->|NO| E3[捏肩疼痛測試]
    E3-->|NO| E4[3: E1 V1 M1]
```
- 語言：錯誤 V4、單詞 V3、聲音 V2
- ≦ 8? 7? 意識昏迷

## 單項處置技術