# FA

---

## getStats

取得 FA 統計資料

#### 範例

```
SrAPI.fa(channelID).getStats({
    inSeconds: 3600,        // 這些全都是選擇性參數, 若都不下, 就只會用預設條件查   
    pseudodata: {
        headCount: true,
        mask: true
    }
})
```

- `channelID: Number`

- `inSeconds: Number` 取得距目前時間前多少秒內的統計資料. 預設 3600.

- `pseudodata: Object` 設定為 true 的子項目, 會回傳模擬資料. 可以設的有 headCount, watchTime, age, smile, glasses, mask. 另外有個 all, 如果設了就會全部用模擬資料. 預設不使用模擬資料.


#### 回應

```
{
    channelID: channelID,
    headCount: headCount,
    watchTime: watchTime,
    age: age,
    smile: smile,
    glasses: glasses,
    mask: mask
}

// 以下是各組資料細節

headCount = {
    male: 0,
    female: 0,
}

watchTime = {
    male: 0,
    female: 0,
}

age = {
    male: {
        _10: 0,
        _10_20: 0,
        _20_30: 0,
        _30_40: 0,
        _40_50: 0,
        _50_60: 0,
        _60: 0,
    },
    female: {
        _10: 0,
        _10_20: 0,
        _20_30: 0,
        _30_40: 0,
        _40_50: 0,
        _50_60: 0,
        _60: 0,
    },
}

smile = {
    male: {
        yes: 0,
        no: 0,
    },
    female: {
        yes: 0,
        no: 0,
    },
}

glasses = {
    male: {
        yes: 0,
        no: 0,
    },
    female: {
        yes: 0,
        no: 0,
    },
}

mask = {
    male: {
        yes: 0,
        no: 0,
    },
    female: {
        yes: 0,
        no: 0,
    },
}
```

---

## 即時資料

接收用來刷新前端介面的即時資料

> TODO: 連結到 monitor 收即時資料的章節