# ��R�Ļ�����ͼϵͳ��ggplot2������ͼ
## �γ�Ŀ��
* ��ϰ������ͼ����
* ѧϰ������ggplot��ͼ����

�������ǻ���R�����еĻ�����ͼϵͳ��ggplot2�е�qplot�Լ�ggplot��������ͼ��

�����Ǽ��ֳ�����ͼ��
* ɢ��ͼ
* ��ͼ
* ����ͼ
* ֱ��ͼ,���ܶ�ͼ
* ����ͼ
* ��ͼ
* ����ͼ
������ͼ�εĴ��붼���������վ�
http://docs.ggplot2.org/current/

## ������
* plot: ��R������ͼ������
* qplot:quick plot,��ggplot2�еļ�����ͼϵͳ��
* ggplot:��ggplot2����ͼ����

## ggplot2�İ�װ,������

```r
# install.packages('ggplot2')
library(ggplot2)
```


## ɢ��ͼ 
### plot

```r
# ʹ�õ����ݼ�
head(mtcars)
```

```
##                    mpg cyl disp  hp drat    wt  qsec vs am gear carb
## Mazda RX4         21.0   6  160 110 3.90 2.620 16.46  0  1    4    4
## Mazda RX4 Wag     21.0   6  160 110 3.90 2.875 17.02  0  1    4    4
## Datsun 710        22.8   4  108  93 3.85 2.320 18.61  1  1    4    1
## Hornet 4 Drive    21.4   6  258 110 3.08 3.215 19.44  1  0    3    1
## Hornet Sportabout 18.7   8  360 175 3.15 3.440 17.02  0  0    3    2
## Valiant           18.1   6  225 105 2.76 3.460 20.22  1  0    3    1
```

```r
plot(mtcars$wt, mtcars$mpg, col = "red")
```

![plot of chunk unnamed-chunk-2](figure/unnamed-chunk-2.png) 

 plot�������Ҫ�к���������ݺ�����������ݣ�
 col���Ƶ�����ɫ
 �������Ҫָ��ͼ�ε��������ԣ���ôҪ��������Ĳ���

```r
plot(mtcars$wt, mtcars$mpg, col = "red", cex = 2, pch = 25)
```

![plot of chunk unnamed-chunk-3](figure/unnamed-chunk-3.png) 

pch���Ƶ�ķ��ţ�cex���Ʒ��ŵĴ�С�������뿴�����ĵ���

### qplot
qplot��plot�ǳ�����
������colour������ɫ,��˼������

```r
qplot(mtcars$wt, mtcars$mpg, colour = "red", size = 2)
```

![plot of chunk unnamed-chunk-4](figure/unnamed-chunk-4.png) 

geom��geometric object���ζ���
 Ҳ�������ǿ��Կ���geom�����Ʋ�ͬ��ͼ��
 �����������ڵ�ɢ��ͼ�����ǰ�geom�Ĳ�������Ϊpoint,Ҳ����ɢ��ͼ����˼

```r
qplot(mtcars$wt, mtcars$mpg, geom = "point", colour = "red", size = 2)
```

![plot of chunk unnamed-chunk-5](figure/unnamed-chunk-5.png) 

����һ�ַ�ʽ��ͨ��data���������ݼ�����������һ����Ч����

```r
qplot(wt, mpg, data = mtcars, geom = "point", colour = "red", size = 2)
```

![plot of chunk unnamed-chunk-6](figure/unnamed-chunk-6.png) 

### ggplot
����������ggplot��ɢ��ͼ��������ʽ����΢��ͬ��
��ggplot��������ͼ�����Էֳ������֣�

��һ:���ݼ���ggplot(mtcars,aes(x=wt,y=mpg)),ͨ����һ�����û�ͼ��Ҫ�õ����ݡ�

�ڶ���ͼ�����ͣ�������geom_point,geom_line�ȡ�

```r
ggplot(mtcars, aes(x = wt, y = mpg)) + geom_point(colour = "red", size = 3)
```

![plot of chunk unnamed-chunk-7](figure/unnamed-chunk-7.png) 

## ��ͼ
### plot
�����������ʵ��plot����type="l",Ҳ����line����˼

```r
x = c(1, 3, 4, 9, 11, 17, 3, 4)
y = c(2, 5, 9, 12, 15, 19, 6, 8)
data1 = data.frame(x, y)
plot(x, y, type = "l")
# ��������ӵ�
points(x, y)
y1 = y * 0.9
# ���һ����
lines(x, y1, col = "red")
points(x, y1)
# ���ƽ������ ��spline�����
lines(spline(x, y, n = 20), col = 454, lwd = 2)
# nԽ������Խƽ��
lines(spline(x, y, n = 201), col = 454, lwd = 2)
lines(spline(x, y1, n = 201), col = 454, lwd = 2)
```

![plot of chunk unnamed-chunk-8](figure/unnamed-chunk-8.png) 

### qplot
geom����ͨ����ͬ����������Ӳ�ͬ�����ߡ�
���ҿ��Ը�geom�����ֵ�����£�

```r
# ����ͼ
qplot(data1$x, data1$y, geom = "line")
```

![plot of chunk unnamed-chunk-9](figure/unnamed-chunk-91.png) 

```r
# ����+��ͼ
qplot(x, y, data = data1, geom = c("line", "point"), colour = "red")
```

![plot of chunk unnamed-chunk-9](figure/unnamed-chunk-92.png) 

```r
# ����+��+ƽ����ģ������ ��Ӱ��ʾ����95%����������
qplot(x, y, data = data1, geom = c("line", "point", "smooth"))
```

```
## geom_smooth: method="auto" and size of largest group is <1000, so using loess. Use 'method = x' to change the smoothing method.
```

![plot of chunk unnamed-chunk-9](figure/unnamed-chunk-93.png) 

### ggplot

```r
ggplot(data1, aes(x = x, y = y)) + geom_line()
```

![plot of chunk unnamed-chunk-10](figure/unnamed-chunk-101.png) 

```r
ggplot(data1, aes(x = x, y = y)) + geom_line() + geom_point() + geom_smooth()
```

```
## geom_smooth: method="auto" and size of largest group is <1000, so using loess. Use 'method = x' to change the smoothing method.
```

![plot of chunk unnamed-chunk-10](figure/unnamed-chunk-102.png) 

## ����ͼ
### barplot

```r
# ��mtcar������
data2 = table(mtcars$cyl)
data2
```

```
## 
##  4  6  8 
## 11  7 14
```

```r

barplot(table(mtcars$cyl))
```

![plot of chunk unnamed-chunk-11](figure/unnamed-chunk-111.png) 

```r
# names.arg �����ú����������
BOD
```

```
##   Time demand
## 1    1    8.3
## 2    2   10.3
## 3    3   19.0
## 4    4   16.0
## 5    5   15.6
## 6    7   19.8
```

```r
barplot(BOD$demand, names.arg = BOD$Time)
```

![plot of chunk unnamed-chunk-11](figure/unnamed-chunk-112.png) 


### qplot

```r
# stat ��ͳ�Ʒ�ʽ��Ĭ��Ϊbin��
# bin��ͳ�Ʒ�ʽ�Ƕ����е��ṩ�ı��������ݽ���ͳ�ƣ�Ȼ��ͳ�Ƶ���Ŀ��Ϊy��
qplot(mtcars$cyl)
```

```
## stat_bin: binwidth defaulted to range/30. Use 'binwidth = x' to adjust this.
```

![plot of chunk unnamed-chunk-12](figure/unnamed-chunk-121.png) 

```r
# ���ǿ�ͼ�ᷢ����Ȼû��5��7����㣬������Ȼ�ճ���λ�á�
# ������ǲ���Ҫ���λ�ã���������Ҫ��x���Ԫ�ر�����ӣ�factor��
qplot(factor(mtcars$cyl))
```

![plot of chunk unnamed-chunk-12](figure/unnamed-chunk-122.png) 

```r
# ����������Ѿ�ͳ�ƺõģ���ô������Ҫ�ı�ͳ�Ƶķ�ʽ
# ���������޸�Ϊidentity,�����ṩ��������
qplot(BOD$Time, BOD$demand, geom = "bar", stat = "identity")
```

![plot of chunk unnamed-chunk-12](figure/unnamed-chunk-123.png) 

```r
qplot(factor(BOD$Time), BOD$demand, geom = "bar", stat = "identity")
```

![plot of chunk unnamed-chunk-12](figure/unnamed-chunk-124.png) 


### ggplot

```r
ggplot(BOD, aes(x = Time, y = demand)) + geom_bar(stat = "identity")
```

![plot of chunk unnamed-chunk-13](figure/unnamed-chunk-131.png) 

```r
ggplot(BOD, aes(x = factor(Time), y = demand)) + geom_bar(stat = "identity")
```

![plot of chunk unnamed-chunk-13](figure/unnamed-chunk-132.png) 

## ֱ��ͼ-���ܶ�ͼ
### hist
ֱ��ͼ�漰��һ����������������磬������е����ݷֳ����飬
��ֻ��2�����ֳ�10��������10��,�ֵ�Խ�࣬Խ��ϸ��

```r
hist(mtcars$mpg, breaks = 3)
```

![plot of chunk unnamed-chunk-14](figure/unnamed-chunk-141.png) 

```r
hist(mtcars$mpg, breaks = 10)
# ��Ӻ��ܶ�����
lines(density(mtcars$mpg), col = "blue")
```

![plot of chunk unnamed-chunk-14](figure/unnamed-chunk-142.png) 

```r
# ����������densityͳ�����ܶȣ���������Ҫ֪������һ�������У��κ�һ������ı�����С��1��
# �������Ҫ��ȷ�ı�����Ҫ��һ������
hist(mtcars$mpg, breaks = 10, freq = FALSE)
lines(density(mtcars$mpg), col = "blue")
```

![plot of chunk unnamed-chunk-14](figure/unnamed-chunk-143.png) 

### qplot
�����hist������ͬ��hist��ȷ���ָ�ķ���������qplotȷ�����Ƿָ�Ŀ�ȣ�Ҳ����һ�ݵĿ���Ƕ��١�
ͬ���������Խխ��Ҳ��Խ��ϸ�ġ�

```r
qplot(mpg, data = mtcars, geom = "histogram", binwidth = 2)
```

![plot of chunk unnamed-chunk-15](figure/unnamed-chunk-151.png) 

```r
qplot(mpg, data = mtcars, geom = "histogram", binwidth = 1)
```

![plot of chunk unnamed-chunk-15](figure/unnamed-chunk-152.png) 

```r
qplot(mpg, data = mtcars, geom = "density")
```

![plot of chunk unnamed-chunk-15](figure/unnamed-chunk-153.png) 

### ggplot
ggplot��һ���ص���ͼ��

```r
# ����
first = ggplot(mtcars, aes(x = mpg))
# ֱ��ͼ
first + geom_histogram(binwidth = 2, fill = "red", colour = "black")
```

![plot of chunk unnamed-chunk-16](figure/unnamed-chunk-161.png) 

```r
# �ܶ�ͼ
first + geom_density(fill = "red", colour = "black")
```

![plot of chunk unnamed-chunk-16](figure/unnamed-chunk-162.png) 

```r
# ֱ��ͼ���ܶ�ͼ
first = ggplot(mtcars, aes(x = mpg, y = ..density..))
# ������������ʾ����Ƶ��������..density..��Ƶ��ת����Ƶ��
first + geom_histogram(binwidth = 2) + geom_density()
```

![plot of chunk unnamed-chunk-16](figure/unnamed-chunk-163.png) 


## ����ͼ
### boxplot

```r
# ��������ͼ
boxplot(mtcars$mpg)
```

![plot of chunk unnamed-chunk-17](figure/unnamed-chunk-171.png) 

```r
# ��������ͼ
boxplot(mpg ~ cyl, data = mtcars)
```

![plot of chunk unnamed-chunk-17](figure/unnamed-chunk-172.png) 


### qplot

```r
qplot(x = cyl, y = mpg, data = mtcars, geom = "boxplot")
```

![plot of chunk unnamed-chunk-18](figure/unnamed-chunk-181.png) 

```r
qplot(x = factor(cyl), y = mpg, data = mtcars, geom = "boxplot")
```

![plot of chunk unnamed-chunk-18](figure/unnamed-chunk-182.png) 


### ggplot

```r
ggplot(mtcars, aes(x = cyl, y = mpg)) + geom_boxplot()
```

![plot of chunk unnamed-chunk-19](figure/unnamed-chunk-191.png) 

```r
ggplot(mtcars, aes(x = factor(cyl), y = mpg)) + geom_boxplot()
```

![plot of chunk unnamed-chunk-19](figure/unnamed-chunk-192.png) 

