# Conf

直接修改系統底層設定

並可撈出指定的即時系統運作資料

## Functions

### addProbe

設定要接收的系統資訊

接收到的資訊會直接在瀏覽器開發者頁面的 console 印出

可以連續設定多種不同過濾條件, 所有設定過的條件都會印出

##### 範例

```javascript
SrAPI.conf().addProbe({
    flag: "sys",
    level: "info",
    channelID: 1
})
```

- `flag: String` sys, channel, member, store, storeItem, fa, fr, feed, gaziru, tcp, udp, frsdb, baofeng, frRecord, pts, trigger, conf, h264player

- `level: String` all, debug, info, warn, error, fatal

- `channelID: Number` 除了 sys 以外, 其他都可用 channelID 區隔

---

### clearProbe

清除所有設定過要接收的系統資訊

##### 範例

```javascript
SrAPI.conf().clearProbe()
```

---

### getStore

取得設定檔 `./conf.json` 中的 store 資料

目前僅用於設定 POS 介面的預設咖啡按鈕

##### 範例

```javascript
SrAPI.conf().getStore()
```

##### 回應

```javascript
{
    coffee: {
        code: "coffee_0",
        name: "咖啡",
        price: 50
    }
}
```

---

### setStore

修改設定檔 `./conf.json` 中的 store 資料

目前僅用於設定 POS 介面的預設咖啡按鈕

##### 範例

```javascript
SrAPI.conf().setStore({
    coffee: {
        code: "coffee_0",
        name: "咖啡",
        price: 50
    }
})
```

- `code: String` 通常不會改, 除非連前端介面接收的參數一起改

- `name: String`

- `price: Number`


##### 回應

```javascript
{
    coffee: {
        code: "coffee_0",
        name: "咖啡",
        price: 50
    }
}
```

---

### getMember

取得設定檔 `./conf.json` 中的 member 資料

用於設定建檔時的預設資料

##### 範例

```javascript
SrAPI.conf().getMember()
```

##### 回應

```javascript
{
    defaultBalance: 168
}
```

---

### setStore

修改設定檔 `./conf.json` 中的 member 資料

用於設定建檔時的預設資料

##### 範例

```javascript
SrAPI.conf().setMember({
    defaultBalance: 168
})
```

- `defaultBalance: Number` 預設餘額


##### 回應

```javascript
{
    defaultBalance: 168
}
```

---

### getLog

取得設定檔 `./conf.json` 中的 logOpts 資料

這會決定保存及刪除 log 的設定

##### 範例

```javascript
SrAPI.conf().getLog()
```

##### 回應

```javascript
{
    keepDays: 7,
    delAtHour: 0,
    delAtMinute: 0
}
```

---

### setLog

修改設定檔 `./conf.json` 中的 logOpts 資料

這會決定保存及刪除 log 的設定

##### 範例

```javascript
SrAPI.conf().setLog({    // 設定值都不是必填
    keepDays: 7,
    delAtHour: 0,
    delAtMinute: 0
})
```

##### 回應

```javascript
{
    keepDays: 7,
    delAtHour: 0,
    delAtMinute: 0
}
```

---
