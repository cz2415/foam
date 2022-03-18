# 去重

## grep 

```shell
grep -v '^[[:space:]]*$' sample.txt
```
![](../assets/img/remove_blank_lines-20220318150247.png)

## sed 

```shell
sed ‘/^$/d’ sample.txt
```
![](../assets/img/remove_blank_lines-20220318150254.png)

## awk

```shell
awk ‘{if(NF>0) {print $0}}’ sample.txt
```
![](../assets/img/remove_blank_lines-20220318150301.png)