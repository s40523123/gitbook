# week5

### 上課內容:

### 利用 Python3 找出缺席名單

### 執行程式碼:

```
with open("cd_w5b.txt", "r", encoding="utf-8") as fh:
    # 逐行讀出檔案資料, 並放入數列中
    lines = fh.readlines()
    raw_data = lines[1:]
    #print(raw_data)
    # 設法用迴圈逐數列內容取出字串
    # k 為集合所有檔案中的學號字串, 先設為空字串
    k = []
    for i in range(len(raw_data)):
        # 利用 strip() 去除各行字串最末端的跳行符號
        raw_line = raw_data[i].strip()
        # 利用 split() 將以 \t 區隔的字串資料分離後納入 groups 字串
        groups = raw_line.split("\t")
        #print(groups)
        # 逐一進入各行中的各字串去除空字串
        for j in range(len(groups)):
            if groups[j] != "":
                # 除了空字串外, 其餘字串放入 k 數列中
                k.append(groups[j])
# 將 k 中只出現一次的字串印出, 即為缺席者名單
absent = [x for x in k if k.count(x) == 1]
print(absent)
```

### 執行結果:

```
cd w5 出席名單        ­修課名單
40123252        40123252
40523201        40523201
40523203        40523203
40523204        40523204
40523205        40523205
40523206        40523206
40523207        40523207
40523209        40523209
        40523210
40523210        40523211
40523211        40523212
40523213        40523213
40523214        40523214
40523215        40523215
        40523216
40523216        40523217
        40523218
40523218        40523219
40523219        40523220
40523220        40523222
        40523224
        40523226
        40523227
        40523230
        40523231
40523226        40523232
        40523233
        40523234
        40523236
40523230        40523237
        40523238
        40523239
40523233        40523240
        40523241
        40523242
40523236        40523243
40523237        40523244
40523238        40523245
40523239        40523246
40523240        40523248
40523241        40523249
40523242        40523250
40523243        
40523244        
40523245        
40523246        

40523248        
40523249        
40523250
```


