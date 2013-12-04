R ���Ի�ͼ�Ļ�������
=======================
# ��
## �������
����������Ϊ pch��ÿһ�ַ��Ŷ�Ӧһ�����ֱ��

```r
# ����25�֣�Ϊ��չʾ25�ֵ�
x = 1:25
y = 1:25
x
```

```
##  [1]  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23
## [24] 24 25
```

```r
plot(x, x, pch = x)
# ��ͼ��������ӵ�
lines(10, 15, type = "b", pch = 5)
```

![plot of chunk unnamed-chunk-1](figure/unnamed-chunk-11.png) 

```r
# type�ĺ���
plot(x, y, type = "p", pch = x)  #point ����������
```

![plot of chunk unnamed-chunk-1](figure/unnamed-chunk-12.png) 

```r
plot(x, y, type = "l", pch = x)  #line ����������
```

![plot of chunk unnamed-chunk-1](figure/unnamed-chunk-13.png) 

```r
plot(x, y, type = "b", pch = x)  #both ͬʱ��������,ע���o������,û�и���
```

![plot of chunk unnamed-chunk-1](figure/unnamed-chunk-14.png) 

```r
plot(x, y, type = "c", pch = x)  #  �����ߣ����ǵ����ڵ�λ��Ϊ��
```

![plot of chunk unnamed-chunk-1](figure/unnamed-chunk-15.png) 

```r
plot(x, y, type = "o", pch = x)  #overlap  �������ߣ��߸��ǵ�
```

![plot of chunk unnamed-chunk-1](figure/unnamed-chunk-16.png) 

```r
plot(x, y, type = "s", pch = x)  #step  ̨��
```

![plot of chunk unnamed-chunk-1](figure/unnamed-chunk-17.png) 

```r
plot(x, y, type = "h", pch = x)  #hist  ����ֱ��ͼ
```

![plot of chunk unnamed-chunk-1](figure/unnamed-chunk-18.png) 

```r
plot(x, y, type = "n", pch = x)  #none  һ���հ�
```

![plot of chunk unnamed-chunk-1](figure/unnamed-chunk-19.png) 

```r

```

## ��Ĵ�С
��Ĵ�С�Ĳ���Ϊcex

```r
plot(x, x, pch = x, cex = x)
```

![plot of chunk unnamed-chunk-2](figure/unnamed-chunk-2.png) 

# ��
## �ߵ�����
�ߵ��������Ϊlty

```r
# ������һ���Ƚϼ򵥵�����
a = c(1, 10)
plot(a, a, type = "b", lty = 1)
```

![plot of chunk unnamed-chunk-3](figure/unnamed-chunk-31.png) 

```r
plot(a, a, type = "b", lty = 2)
# 6���ߣ��ֱ��Ӧlty = 1��2��3��4��5��6
# ͨ����ͼ����Ӳο�������ʶһ���������� ��Ӳο��ߵĺ���Ϊabline ?abline()
b = 1:6
abline(h = b, lty = b)
abline(v = b, lty = b)
abline(a = 4, b = 5, lty = b)
abline(a = 0, b = 5, lty = b)
```

![plot of chunk unnamed-chunk-3](figure/unnamed-chunk-32.png) 

## �ߵĴ�ϸ
�ߵĴ�ϸ�Ĳ���Ϊlwd

```r
abline(h = b, lty = b, lwd = b)
```

```
## Error: plot.new has not been called yet
```

```r
plot(x, y, lwd = 1)
plot(a, a, type = "b", lwd = 5)
plot(a, a, type = "b", lwd = 1)
```


# ɫ
ɫ�Ĳ���Ϊcol

```r
# ��ɫ���������ǵ��ʱ�ʾ
plot(x, x, col = "blue", pch = 20)  #��ɫ����
```

![plot of chunk unnamed-chunk-5](figure/unnamed-chunk-51.png) 

```r
plot(x, x, col = "red", pch = 20)  #��ɫ����
```

![plot of chunk unnamed-chunk-5](figure/unnamed-chunk-52.png) 

```r

# ���������ֱ�ʾ
plot(x, x, col = 1, pch = 20)  #��ɫ�±�
```

![plot of chunk unnamed-chunk-5](figure/unnamed-chunk-53.png) 

```r
plot(x, x, col = 2, pch = 20)
```

![plot of chunk unnamed-chunk-5](figure/unnamed-chunk-54.png) 

```r
plot(x, x, col = "#FFFFFF", pch = 20)  #16������ɫֵ
```

![plot of chunk unnamed-chunk-5](figure/unnamed-chunk-55.png) 

```r
plot(x, x, col = "#0000FF", pch = 20)  #��ɫ
```

![plot of chunk unnamed-chunk-5](figure/unnamed-chunk-56.png) 

```r
plot(x, x, col = rgb(0.5, 0.5, 0.5), pch = 20)  #RGB red,green,black
```

![plot of chunk unnamed-chunk-5](figure/unnamed-chunk-57.png) 

```r
plot(x, x, col = hsv(0, 0, 0.5), pch = 20)  #hsv ɫ��-���Ͷ�-����

# �ʺ�����ɫ
plot(x, x, col = rainbow(10), pch = 20)
```

![plot of chunk unnamed-chunk-5](figure/unnamed-chunk-58.png) 

```r
pie(rep(1, 10), col = rainbow(10))
```

![plot of chunk unnamed-chunk-5](figure/unnamed-chunk-59.png) 

```r
# ��׻Ҷ�
pie(rep(1, 10), col = gray(0:10/10))
```

![plot of chunk unnamed-chunk-5](figure/unnamed-chunk-510.png) 

���ǿ϶��Ǽǲ�ס��ô����ɫ�ģ�����������һ��ר������õ���վ�������ǲο�
http://research.stowers-institute.org/efg/R/Color/Chart/
