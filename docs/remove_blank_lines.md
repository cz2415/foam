# 去重

**linux 下删除重复的行**

1. grep 

```shell
grep -v '^[[:space:]]*$' sample.txt
```
![grep](../attachments/img/remove_blank_lines-20220318150247.png)

2.  sed 

```shell
sed '/^$/d' sample.txt
```
![sed](../attachments/img/remove_blank_lines-20220318150254.png)

3. awk

```shell
awk '{if(NF>0) {print $0}}' sample.txt
```
![awk](../attachments/img/remove_blank_lines-20220318150301.png)