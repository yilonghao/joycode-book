# JQ命令

日常工作经常需要跟 json 格式的数据打交道，推荐一个解析 json 格式数据的[在线工具](https://www.json.cn/)。

此外可以在开发机上安装 jq 工具，便于快速解析 json 格式的数据，下面几个例子简单的记录了 jq 命令的用法。其中 task_feature_file 中的每一行都是一个 json 格式的数据。

## 解析 json 格式的数据
```shell
cat task_feature_file | jq .
```

## 根据 key 获取 value
```shell
cat task_feature_file | jq '.cms_data'
```

## 根据 key 获取 value(嵌套提取)
```shell
cat task_feature_file | jq '.cms_data.res_id'
```
## 提取所有 key
```shell
cat task_feature_file | jq 'keys'
```

## 提取所有 key(嵌套提取)
```shell
cat task_feature_file | jq '.cms_data' | jq 'keys'
```

## 判断是否有某个 key
```shell
cat task_feature_file | jq 'has("cms_data")'
```
