---
layout: post
title:  "SICP - 1.18 exercise"
---
# SICP - 1.18 exercise
## 13 x 6 -> a x b
<pre>
13 连续除以 2  
6 ··· 1  
3 ··· 0  
1 ··· 1  
0 ··· 1

13 = 2^0 + 0*2^1 + 2^2 + 2^3    
13 * 6 = 6*2^0 + 6*0*2^1 + 6*2^2 + 6*2^3 
       = b * 2^n
</pre>

{% highlight scheme %}     
(define (mult a b)
  (fast-mult a b 0 0))

(define (fast-mult a b product counter)
  (cond ((= a 0) product)
        ((= (remainder a 2) 1) (fast-mult (div a 2) b (+ product (* (expt 2 counter) b)) (+ counter 1)))
        (else (fast-mult (div a 2) b product (+ counter 1)))))      
{% endhighlight %}
## **source**:
[russian peasants method](https://mindyourdecisions.com/blog/2014/08/27/the-egyptian-method-russian-peasant-multiplication-video-and-a-proof/#:~:text=Proof%20of%20Egyptian%20Method%20%2F%20Russian%20Peasant%20Multiplication&text=In%20other%20words%2C%20XY%20is,%2C%20then%20c0%20%3D%200.)
