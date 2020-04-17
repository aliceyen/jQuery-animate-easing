# jQuery animate easing使用方法詳解

_本篇文章轉載自https://codertw.com/%E5%89%8D%E7%AB%AF%E9%96%8B%E7%99%BC/264265/_



從jQuery API 文件中可以知道，jQuery自定義動畫的函式.animate( properties [, duration] [, easing] [, complete] )有四個引數：

• properties：一組包含作為動畫屬性和終值的樣式屬性和及其值的集合

• duration(可選)：動畫執行時間，其值可以是三種預定速度之一的字串(“slow”, “normal”, or “fast”)或表示動畫時長的毫秒數值(如：1000)

• easing(可選)：要使用的過渡效果的名稱，如：”linear” 或”swing”

• complete(可選)：在動畫完成時執行的函式

其中引數easing預設有兩個效果：”linear”和”swing”，如果需要更多效果就要外掛支援了，jQuery Easing Plugin提供了像”easeOutExpo”、”easeOutBounce”等30多種效果，大家可以點選這裡去看每一種easing的演示效果，下面詳細介紹下其使用方法及每種easing的曲線圖。

## jQuery easing 使用方法

首先，專案中如果需要使用特殊的動畫效果，則需要在引入jQuery之後引入jquery.easing.1.3.js：
```html
    <script type="text/javascript" src="http://code.jquery.com/jquery-1.8.3.js"></script>
    <script type="text/javascript" src="http://gsgd.co.uk/sandbox/jquery/easing/jquery.easing.1.3.js"></script> 
```
引入之後，easing引數可選的值就有以下32種：

*  [部分效果可以參考此網址，滑鼠滑入後會出現動態效果](https://easings.net/cn)  
1. linear
2. swing
3. easeInQuad
4. easeOutQuad
5. easeInOutQuad
6. easeInCubic
7. easeOutCubic
8. easeInOutCubic
9. easeInQuart
10. easeOutQuart
11. easeInOutQuart
12. easeInQuint
13. easeOutQuint
14. easeInOutQuint
15. easeInExpo
16. easeOutExpo
17. easeInOutExpo
18. easeInSine
19. easeOutSine
20. easeInOutSine
21. easeInCirc
22. easeOutCirc
23. easeInOutCirc
24. easeInElastic
25. easeOutElastic
26. easeInOutElastic
27. easeInBack
28. easeOutBack
29. easeInOutBack
30. easeInBounce
31. easeOutBounce
32. easeInOutBounce


jQuery 1.4版本中對animate()方法，easing的方法進行了擴充套件，支援為每個屬性指定easing方法，詳細請參考這裡，如：
首先，專案中如果需要使用特殊的動畫效果，則需要在引入jQuery之後引入jquery.easing.1.3.js：
```html
   //第一種寫法
      $(myElement).animate({ 
         left: [500, 'swing'], 
         top: [200, 'easeOutBounce'] 
      }); 
   //第二種寫法
      $(myElement).animate({ 
            left: 500, 
            top: 200 
         }, { 
         specialEasing: { 
            left: 'swing', 
            top: 'easeOutBounce' 
         } 
      });
```
使用jQuery內建動畫函式如slideUp()、slideDown()等來指定easing效果，以下兩種方法都可以：
```html
   $(myElement).slideUp(1000, method, callback}); 
      $(myElement).slideUp({ 
         duration: 1000, 
         easing: method, 
         complete: callback 
   });
```


* * *


