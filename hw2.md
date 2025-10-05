```mermaid
gantt
    title 專案甘特圖
    dateFormat  YYYY-MM-DD
    axisFormat  %m/%d

    section 規劃階段
    研擬計畫          :a1, 2025-10-01, 1d
    任務分配          :a2, after a1, 4d

    section 硬體作業
    取得硬體          :a3, after a1, 17d
    安裝硬體          :a5, after a3, 10d

    section 軟體開發
    程式開發          :a4, after a2, 70d
    程式測試          :a6, after a4, 30d
    系統測試          :a9, after a6, 25d

    section 文件與訓練
    撰寫使用手冊      :a7, after a5, 25d
    轉換檔案          :a8, after a5, 20d
    使用者訓練        :a10, after a7 a8, 20d
    使用者測試        :a11, after a9 a10, 25d
```


```mermaid
flowchart LR
    A1([1 研擬計畫<br>1天]) --> A2([2 任務分配<br>4天])
    A2 --> A4([4 程式開發<br>70天])
    A4 --> A6([6 程式測試<br>30天])
    A6 --> A9([9 系統測試<br>25天])
    A9 --> A11([11 使用者測試<br>25天])

    %% 標註開始與結束
    start([開始]) --> A1
    A11 --> end([結束])

    %% 標示關鍵路徑
    classDef critical fill=#f66,stroke=#333,stroke-width=2px,color=white;
    class start,end,A1,A2,A4,A6,A9,A11 critical;
```
