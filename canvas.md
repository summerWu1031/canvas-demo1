
## 在使用canvas画图前， 需要使用getContext() 这个方法来获得渲染上下文和它的绘画功能。getContext('2d')是对于2D图像而言。
```html
ctx = canvas.getContext('2d');
```
<br>

## canvas提供了三种方法绘制矩形：

```html
fillRect(x, y, width, height)
绘制一个填充的矩形
strokeRect(x, y, width, height)
绘制一个矩形的边框
clearRect(x, y, width, height)
清除指定矩形区域，让清除部分完全透明。
```

## 画矩形实例：
```html
ctx.fillStyle = 'blue';
ctx.fillRect(e.clientX-5 ,e.clientY-5, 10, 10);
ctx.fillRect(左边距(-5是为了让鼠标在图形中间)，上边距，width,height)
```

## 画圆形：
```html
ctx.beginPath();
ctx.arc(e.clientX, e.clientY, 10, 0, 2 * Math.PI);
//arc(圆弧中心（圆心）的 x 轴坐标，圆弧中心（圆心）的 y 轴坐标，圆弧的半径，圆弧的起始点， x轴方向开始计算，单位以弧度表示，圆弧的终点， 单位以弧度表示)
ctx.fill(); //填充
ctx.stroke(); //画边线
```

## 画直线：
```html
  ctx.beginPath();
  ctx.moveTo(0, 0);
  ctx.lineTo(0, 100);
  ctx.stroke();

  // 封装一个画线的函数
        function drawLine(x1,y1,x2,y2){
            ctx.beginPath();
            ctx.moveTo(x1,y1);
            ctx.lineTo(x2,y2);
            ctx.stroke();
        }

        drawLine(0,0,100,100);
```

## 描边三角形：
```html
  ctx.beginPath();
  ctx.moveTo(0, 0);起始端点
  ctx.lineTo(0, 200);链接到x为0，y为200；现在是打竖的一条直线
  ctx.lineTo(200, 200);再由起始点连接到x200 y200;现在是一个直角三角形
  ctx.closePath();把这三个点连起来
  ctx.stroke();
```

## 怎么把canvas的宽高设置自适应屏幕
```html
<canvas id="canvas" width="100" height="100"></canvas>
    <script>
        let canvas = document.getElementById('canvas');
        canvas.width= document.documentElement.clientWidth
        canvas.height= document.documentElement.clientHeight
    </script>
```

