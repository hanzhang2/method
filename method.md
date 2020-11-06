# method

<font size=5>

## 1.结构体(数据库)设计

### 1.user

```go
type user struct{
    Uid string
    Name string
    Password string
    Phone string
    VxName string
    Credit string
    Email string
    Place string
    PhotoPlace string
}
```

---

### 2.product

```go
type user struct{
    Pid string
    Name string
    Price string
    Username string
    Condition string
    Sort string
    PublishTime string
    PhotoPlace string
}
```

## 2.uuid生成

```go
//纳秒级时间戳转换为md5去前10位
func MD5() {
    now:=time.Now()
    t1:=now.UnixNano()
    t2 := strconv.FormatInt(t1,10)

    ctx := md5.New()
    ctx.Write([]byte(t2))
    t2=hex.EncodeToString(ctx.Sum(nil))

    t2=t2[0:10]
    fmt.Println(t2)
}
```