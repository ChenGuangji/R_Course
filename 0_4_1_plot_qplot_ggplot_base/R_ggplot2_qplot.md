# ��R�Ļ�����ͼϵͳ��ggplot2������ͼ
�������ǻ���R�����еĻ�����ͼϵͳ��ggplot2�е�qplot�Լ�ggplot��������ͼ��
�������漸�ֳ�����ͼ��
* ɢ��ͼ
* ��ͼ
* ����ͼ
* ֱ��ͼ,���ܶ�ͼ
* ����ͼ
* ��ͼ
* ����ͼ
������ͼ�εĴ��붼���������վ�
http://docs.ggplot2.org/current/

## ���ݼ�
ĳ�ֶ����������峤

```r
dugong = read.table("dugongs.txt", header = TRUE)
```


## ggplot2�İ�װ,������

```r
# install.packages('ggplot2')
library(ggplot2)
```


## ɢ��ͼ 

```r
plot(dugong$Age, dugong$Length, col = "red")
```

![plot of chunk unnamed-chunk-3](figure/unnamed-chunk-3.png) 

```r

# colour������ɫ
qplot(Age, Length, data = data, geom = "point", colour = "red")
```

```
## Error: ggplot2 doesn't know how to deal with data of class function
```

```r

qplot(data$Age, data$Length, geom = "point", colour = "red")
```

```
## Error: ���Ϊ'closure'�Ķ��󲻿���ȡ�Ӽ�
```

```r

ggplot(data, aes(x = Age, y = Length)) + geom_point()
```

```
## Error: ggplot2 doesn't know how to deal with data of class function
```

# ��ͼ

```r
plot(dugong$Age, dugong$Length, type = "l")
# ��������ӵ�
points(dugong$Age, dugong$Length)
dugong$Length1 = dugong$Length * 0.9
# ���һ����
lines(dugong$Age, dugong$Length1, col = "red")
points(dugong$Age, dugong$Length1)
# ���ƽ������
lines(spline(dugong$Age, dugong$Length, n = 201), col = 454, lwd = 2)
lines(spline(dugong$Age, dugong$Length1, n = 201), col = 454, lwd = 2)
```

![plot of chunk unnamed-chunk-4](figure/unnamed-chunk-4.png) 

```r

qplot(Age, Length, data = data, geom = "line")
```

```
## Error: ggplot2 doesn't know how to deal with data of class function
```

```r
qplot(Age, Length, data = data, geom = c("line", "point"))
```

```
## Error: ggplot2 doesn't know how to deal with data of class function
```

```r
qplot(Age, Length, data = data, geom = c("line", "point"))
```

```
## Error: ggplot2 doesn't know how to deal with data of class function
```

```r
qplot(Age, Length, data = data, geom = c("line", "point", "smooth"))
```

```
## Error: ggplot2 doesn't know how to deal with data of class function
```

```r



ggplot(data, aes(x = Age, y = Length)) + geom_line()
```

```
## Error: ggplot2 doesn't know how to deal with data of class function
```

```r
ggplot(data, aes(x = Age, y = Length)) + geom_line() + geom_point() + geom_smooth()
```

```
## Error: ggplot2 doesn't know how to deal with data of class function
```

## ����ͼ

```r
dugong
```

```
##     Age Length Length1
## 1   1.0   1.80   1.620
## 2   1.5   1.85   1.665
## 3   1.5   1.87   1.683
## 4   1.5   1.77   1.593
## 5   2.5   2.02   1.818
## 6   4.0   2.27   2.043
## 7   5.0   2.15   1.935
## 8   5.0   2.26   2.034
## 9   7.0   2.35   2.115
## 10  8.0   2.47   2.223
## 11  8.5   2.19   1.971
## 12  9.0   2.26   2.034
## 13  9.5   2.40   2.160
## 14  9.5   2.39   2.151
## 15 10.0   2.41   2.169
## 16 12.0   2.50   2.250
## 17 12.0   2.32   2.088
## 18 13.0   2.43   2.187
## 19 13.0   2.47   2.223
## 20 14.5   2.56   2.304
## 21 15.5   2.65   2.385
## 22 15.5   2.47   2.223
## 23 16.5   2.64   2.376
## 24 17.0   2.56   2.304
## 25 22.5   2.70   2.430
## 26 29.0   2.72   2.448
## 27 31.5   2.57   2.313
```

```r
# ��ʾ27��Age
barplot(dugong$Age)
```

![plot of chunk unnamed-chunk-5](figure/unnamed-chunk-51.png) 

```r
barplot(dugong$Length)
```

![plot of chunk unnamed-chunk-5](figure/unnamed-chunk-52.png) 

```r
# ggplot��bar������ͬ
```

## ֱ��ͼ-���ܶ�ͼ


## ����ͼ


## ��ͼ


## ����ͼ


