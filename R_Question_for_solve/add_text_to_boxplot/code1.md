
```r
library(reshape)
```

```
## Loading required package: plyr
## 
## Attaching package: 'reshape'
## 
## ���ж���������from 'package:plyr':
## 
##     rename, round_any
```

```r
data.FZY = read.table("a.csv", sep = ",", header = TRUE)
data.RenShu = read.table("b.csv", sep = ",", header = TRUE)
names_city = names(data.RenShu)
data.FZY2011 = subset(data.FZY, ��� == 2011)
for (i in 3:length(names_city)) {
    name = names_city[i]
    data.FZY2011[, name] = data.FZY2011[, name]/data.RenShu[1, name]
}
data.FZY2011_1 = melt(data.FZY2011, id = c("X", "�·�", "���", "װ�ƻ����"))
value = boxplot(value ~ variable, data = data.FZY2011_1, varwidth = TRUE, notch = TRUE, 
    col = rainbow(16))$stats
```

```
## Warning: 'mbcsToSbcs'��ת��'全省'����<e5>������dot
## Warning: 'mbcsToSbcs'��ת��'全省'����<85>������dot
## Warning: 'mbcsToSbcs'��ת��'全省'����<a8>������dot
## Warning: 'mbcsToSbcs'��ת��'全省'����<e7>������dot
## Warning: 'mbcsToSbcs'��ת��'全省'����<9c>������dot
## Warning: 'mbcsToSbcs'��ת��'全省'����<81>������dot
## Warning: 'mbcsToSbcs'��ת��'全省'����<e5>������dot
## Warning: 'mbcsToSbcs'��ת��'全省'����<85>������dot
## Warning: 'mbcsToSbcs'��ת��'全省'����<a8>������dot
## Warning: 'mbcsToSbcs'��ת��'全省'����<e7>������dot
## Warning: 'mbcsToSbcs'��ת��'全省'����<9c>������dot
## Warning: 'mbcsToSbcs'��ת��'全省'����<81>������dot
## Warning: 'mbcsToSbcs'��ת��'南京'����<e5>������dot
## Warning: 'mbcsToSbcs'��ת��'南京'����<8d>������dot
## Warning: 'mbcsToSbcs'��ת��'南京'����<97>������dot
## Warning: 'mbcsToSbcs'��ת��'南京'����<e4>������dot
## Warning: 'mbcsToSbcs'��ת��'南京'����<ba>������dot
## Warning: 'mbcsToSbcs'��ת��'南京'����<ac>������dot
## Warning: 'mbcsToSbcs'��ת��'无锡'����<e6>������dot
## Warning: 'mbcsToSbcs'��ת��'无锡'����<97>������dot
## Warning: 'mbcsToSbcs'��ת��'无锡'����<a0>������dot
## Warning: 'mbcsToSbcs'��ת��'无锡'����<e9>������dot
## Warning: 'mbcsToSbcs'��ת��'无锡'����<94>������dot
## Warning: 'mbcsToSbcs'��ת��'无锡'����<a1>������dot
## Warning: 'mbcsToSbcs'��ת��'无锡'����<e6>������dot
## Warning: 'mbcsToSbcs'��ת��'无锡'����<97>������dot
## Warning: 'mbcsToSbcs'��ת��'无锡'����<a0>������dot
## Warning: 'mbcsToSbcs'��ת��'无锡'����<e9>������dot
## Warning: 'mbcsToSbcs'��ת��'无锡'����<94>������dot
## Warning: 'mbcsToSbcs'��ת��'无锡'����<a1>������dot
## Warning: 'mbcsToSbcs'��ת��'镇江'����<e9>������dot
## Warning: 'mbcsToSbcs'��ת��'镇江'����<95>������dot
## Warning: 'mbcsToSbcs'��ת��'镇江'����<87>������dot
## Warning: 'mbcsToSbcs'��ת��'镇江'����<e6>������dot
## Warning: 'mbcsToSbcs'��ת��'镇江'����<b1>������dot
## Warning: 'mbcsToSbcs'��ת��'镇江'����<9f>������dot
## Warning: 'mbcsToSbcs'��ת��'苏州'����<e8>������dot
## Warning: 'mbcsToSbcs'��ת��'苏州'����<8b>������dot
## Warning: 'mbcsToSbcs'��ת��'苏州'����<8f>������dot
## Warning: 'mbcsToSbcs'��ת��'苏州'����<e5>������dot
## Warning: 'mbcsToSbcs'��ת��'苏州'����<b7>������dot
## Warning: 'mbcsToSbcs'��ת��'苏州'����<9e>������dot
## Warning: 'mbcsToSbcs'��ת��'苏州'����<e8>������dot
## Warning: 'mbcsToSbcs'��ת��'苏州'����<8b>������dot
## Warning: 'mbcsToSbcs'��ת��'苏州'����<8f>������dot
## Warning: 'mbcsToSbcs'��ת��'苏州'����<e5>������dot
## Warning: 'mbcsToSbcs'��ת��'苏州'����<b7>������dot
## Warning: 'mbcsToSbcs'��ת��'苏州'����<9e>������dot
## Warning: 'mbcsToSbcs'��ת��'南�<U+393C><U+3E61>'����<e5>������dot
## Warning: 'mbcsToSbcs'��ת��'南�<U+393C><U+3E61>'����<8d>������dot
## Warning: 'mbcsToSbcs'��ת��'南�<U+393C><U+3E61>'����<97>������dot
## Warning: 'mbcsToSbcs'��ת��'南�<U+393C><U+3E61>'����<e9>������dot
## Warning: 'mbcsToSbcs'��ת��'南�<U+393C><U+3E61>'����<80>������dot
## Warning: 'mbcsToSbcs'��ת��'南�<U+393C><U+3E61>'����<9a>������dot
## Warning: 'mbcsToSbcs'��ת��'扬州'����<e6>������dot
## Warning: 'mbcsToSbcs'��ת��'扬州'����<89>������dot
## Warning: 'mbcsToSbcs'��ת��'扬州'����<ac>������dot
## Warning: 'mbcsToSbcs'��ת��'扬州'����<e5>������dot
## Warning: 'mbcsToSbcs'��ת��'扬州'����<b7>������dot
## Warning: 'mbcsToSbcs'��ת��'扬州'����<9e>������dot
## Warning: 'mbcsToSbcs'��ת��'扬州'����<e6>������dot
## Warning: 'mbcsToSbcs'��ת��'扬州'����<89>������dot
## Warning: 'mbcsToSbcs'��ת��'扬州'����<ac>������dot
## Warning: 'mbcsToSbcs'��ת��'扬州'����<e5>������dot
## Warning: 'mbcsToSbcs'��ת��'扬州'����<b7>������dot
## Warning: 'mbcsToSbcs'��ת��'扬州'����<9e>������dot
## Warning: 'mbcsToSbcs'��ת��'盐城'����<e7>������dot
## Warning: 'mbcsToSbcs'��ת��'盐城'����<9b>������dot
## Warning: 'mbcsToSbcs'��ת��'盐城'����<90>������dot
## Warning: 'mbcsToSbcs'��ת��'盐城'����<e5>������dot
## Warning: 'mbcsToSbcs'��ת��'盐城'����<9f>������dot
## Warning: 'mbcsToSbcs'��ת��'盐城'����<8e>������dot
## Warning: 'mbcsToSbcs'��ת��'徐州'����<e5>������dot
## Warning: 'mbcsToSbcs'��ת��'徐州'����<be>������dot
## Warning: 'mbcsToSbcs'��ת��'徐州'����<90>������dot
## Warning: 'mbcsToSbcs'��ת��'徐州'����<e5>������dot
## Warning: 'mbcsToSbcs'��ת��'徐州'����<b7>������dot
## Warning: 'mbcsToSbcs'��ת��'徐州'����<9e>������dot
## Warning: 'mbcsToSbcs'��ת��'徐州'����<e5>������dot
## Warning: 'mbcsToSbcs'��ת��'徐州'����<be>������dot
## Warning: 'mbcsToSbcs'��ת��'徐州'����<90>������dot
## Warning: 'mbcsToSbcs'��ת��'徐州'����<e5>������dot
## Warning: 'mbcsToSbcs'��ת��'徐州'����<b7>������dot
## Warning: 'mbcsToSbcs'��ת��'徐州'����<9e>������dot
## Warning: 'mbcsToSbcs'��ת��'淮安'����<e6>������dot
## Warning: 'mbcsToSbcs'��ת��'淮安'����<b7>������dot
## Warning: 'mbcsToSbcs'��ת��'淮安'����<ae>������dot
## Warning: 'mbcsToSbcs'��ת��'淮安'����<e5>������dot
## Warning: 'mbcsToSbcs'��ת��'淮安'����<ae>������dot
## Warning: 'mbcsToSbcs'��ת��'淮安'����<89>������dot
## Warning: 'mbcsToSbcs'��ת��'连云渐�<U+3E66>'����<e8>������dot
## Warning: 'mbcsToSbcs'��ת��'连云渐�<U+3E66>'����<bf>������dot
## Warning: 'mbcsToSbcs'��ת��'连云渐�<U+3E66>'����<9e>������dot
## Warning: 'mbcsToSbcs'��ת��'连云渐�<U+3E66>'����<e4>������dot
## Warning: 'mbcsToSbcs'��ת��'连云渐�<U+3E66>'����<ba>������dot
## Warning: 'mbcsToSbcs'��ת��'连云渐�<U+3E66>'����<91>������dot
## Warning: 'mbcsToSbcs'��ת��'连云渐�<U+3E66>'����<e6>������dot
## Warning: 'mbcsToSbcs'��ת��'连云渐�<U+3E66>'����<b8>������dot
## Warning: 'mbcsToSbcs'��ת��'连云渐�<U+3E66>'����<af>������dot
## Warning: 'mbcsToSbcs'��ת��'连云渐�<U+3E66>'����<e8>������dot
## Warning: 'mbcsToSbcs'��ת��'连云渐�<U+3E66>'����<bf>������dot
## Warning: 'mbcsToSbcs'��ת��'连云渐�<U+3E66>'����<9e>������dot
## Warning: 'mbcsToSbcs'��ת��'连云渐�<U+3E66>'����<e4>������dot
## Warning: 'mbcsToSbcs'��ת��'连云渐�<U+3E66>'����<ba>������dot
## Warning: 'mbcsToSbcs'��ת��'连云渐�<U+3E66>'����<91>������dot
## Warning: 'mbcsToSbcs'��ת��'连云渐�<U+3E66>'����<e6>������dot
## Warning: 'mbcsToSbcs'��ת��'连云渐�<U+3E66>'����<b8>������dot
## Warning: 'mbcsToSbcs'��ת��'连云渐�<U+3E66>'����<af>������dot
## Warning: 'mbcsToSbcs'��ת��'常州'����<e5>������dot
## Warning: 'mbcsToSbcs'��ת��'常州'����<b8>������dot
## Warning: 'mbcsToSbcs'��ת��'常州'����<b8>������dot
## Warning: 'mbcsToSbcs'��ת��'常州'����<e5>������dot
## Warning: 'mbcsToSbcs'��ת��'常州'����<b7>������dot
## Warning: 'mbcsToSbcs'��ת��'常州'����<9e>������dot
## Warning: 'mbcsToSbcs'��ת��'泰州'����<e6>������dot
## Warning: 'mbcsToSbcs'��ת��'泰州'����<b3>������dot
## Warning: 'mbcsToSbcs'��ת��'泰州'����<b0>������dot
## Warning: 'mbcsToSbcs'��ת��'泰州'����<e5>������dot
## Warning: 'mbcsToSbcs'��ת��'泰州'����<b7>������dot
## Warning: 'mbcsToSbcs'��ת��'泰州'����<9e>������dot
## Warning: 'mbcsToSbcs'��ת��'泰州'����<e6>������dot
## Warning: 'mbcsToSbcs'��ת��'泰州'����<b3>������dot
## Warning: 'mbcsToSbcs'��ת��'泰州'����<b0>������dot
## Warning: 'mbcsToSbcs'��ת��'泰州'����<e5>������dot
## Warning: 'mbcsToSbcs'��ת��'泰州'����<b7>������dot
## Warning: 'mbcsToSbcs'��ת��'泰州'����<9e>������dot
## Warning: 'mbcsToSbcs'��ת��'宿迁'����<e5>������dot
## Warning: 'mbcsToSbcs'��ת��'宿迁'����<ae>������dot
## Warning: 'mbcsToSbcs'��ת��'宿迁'����<bf>������dot
## Warning: 'mbcsToSbcs'��ת��'宿迁'����<e8>������dot
## Warning: 'mbcsToSbcs'��ת��'宿迁'����<bf>������dot
## Warning: 'mbcsToSbcs'��ת��'宿迁'����<81>������dot
```

```r
text(1:14, t(value), sprintf("%.2f", t(value)))
```

![plot of chunk unnamed-chunk-1](figure/unnamed-chunk-1.png) 

