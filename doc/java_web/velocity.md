





#if使用：

1. 单一判断

```
#if($value!="")
```

2. 两个或多个判断

```
#if($value != "" && $value != 0)
```

3. 为空判断（网上说 #if($value) 就代表不为空，我没试过）

```
#if($value != $null)   // 注意 null 前面必须要有$符号
```

4. 判断中用到函数

```
#if(${value.length()}>0)
#if(${value.indexOf("xxx")}!=-1)
```