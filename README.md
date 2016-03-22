#Animate.css

`animate.css`是一个很酷,很有趣的跨浏览器动画库。

##基本使用

1. 在`<head>`处添加样式表

  ```html
  <head>
    <link rel="stylesheet" href="animate.min.css">
  </head>
  ```
2. 在需要应用动画的元素上添加`animated`类。
 注：`infinite`类表示无限循环。

3. 最后还需要添加以下具体的动画类：

  * `bounce`
  * `flash`
  * `pulse`
  * `rubberBand`
  * `shake`
  * `headShake`
  * `swing`
  * `tada`
  * `wobble`
  * `jello`
  * `bounceIn`
  * `bounceInDown`
  * `bounceInLeft`
  * `bounceInRight`
  * `bounceInUp`
  * `bounceOut`
  * `bounceOutDown`
  * `bounceOutLeft`
  * `bounceOutRight`
  * `bounceOutUp`
  * `fadeIn`
  * `fadeInDown`
  * `fadeInDownBig`
  * `fadeInLeft`
  * `fadeInLeftBig`
  * `fadeInRight`
  * `fadeInRightBig`
  * `fadeInUp`
  * `fadeInUpBig`
  * `fadeOut`
  * `fadeOutDown`
  * `fadeOutDownBig`
  * `fadeOutLeft`
  * `fadeOutLeftBig`
  * `fadeOutRight`
  * `fadeOutRightBig`
  * `fadeOutUp`
  * `fadeOutUpBig`
  * `flipInX`
  * `flipInY`
  * `flipOutX`
  * `flipOutY`
  * `lightSpeedIn`
  * `lightSpeedOut`
  * `rotateIn`
  * `rotateInDownLeft`
  * `rotateInDownRight`
  * `rotateInUpLeft`
  * `rotateInUpRight`
  * `rotateOut`
  * `rotateOutDownLeft`
  * `rotateOutDownRight`
  * `rotateOutUpLeft`
  * `rotateOutUpRight`
  * `hinge`
  * `rollIn`
  * `rollOut`
  * `zoomIn`
  * `zoomInDown`
  * `zoomInLeft`
  * `zoomInRight`
  * `zoomInUp`
  * `zoomOut`
  * `zoomOutDown`
  * `zoomOutLeft`
  * `zoomOutRight`
  * `zoomOutUp`
  * `slideInDown`
  * `slideInLeft`
  * `slideInRight`
  * `slideInUp`
  * `slideOutDown`
  * `slideOutLeft`
  * `slideOutRight`
  * `slideOutUp`

举例：
```html
<h1 class="animated infinite bounce">Example</h1>
```

[点击此处查看所有动画](https://daneden.github.io/animate.css/)

##使用
在你的网站使用animate.css，首先在`<head>`包含样式表链接，接着为元素添加`animated`类名，再添加你具体用到的动画类名，就这么简单！

```html
<head>
  <link rel="stylesheet" href="animate.min.css">
</head>
```

可以结合jQuery或自定义的CSS规则来使用animate.css
使用jQuery动态添加动画：

```javascript
$('#yourElement').addClass('animated bounceOutLeft');
```

监听动画结束事件：

```javascript
$('#yourElement').one('webkitAnimationEnd mozAnimationEnd MSAnimationEnd oanimationend animationend', doSomething);
```

[点击此处查看视频教程](https://www.youtube.com/watch?v=CBQGl6zokMs) 结合JQuery使用Animate.css。 

**注意:** `jQuery.one()` 用于只执行一次事件回调。更多信息 [点击这里](http://api.jquery.com/one/).

可以扩展一个jQuery插件来简化使用：

```javascript
$.fn.extend({
    animateCss: function (animationName) {
        var animationEnd = 'webkitAnimationEnd mozAnimationEnd MSAnimationEnd oanimationend animationend';
        $(this).addClass('animated ' + animationName).one(animationEnd, function() {
            $(this).removeClass('animated ' + animationName);
        });
    }
});
```

这样使用：

```javascript
$('#yourElement').animateCss('bounce');
```

可以在CSS中改变动画的持续时间，延迟时间，播放次数：

```css
#yourElement {
  -vendor-animation-duration: 3s;
  -vendor-animation-delay: 2s;
  -vendor-animation-iteration-count: infinite;
}
```

*注意：使用浏览器前缀(webkit, moz, etc)替换CSS中的"vendor"*

## 自定义构建
Animate.css使用[gulp.js](http://gulpjs.com/)构建，你可以很容易地创建自定义构建。首先你需要Gulp和其它依赖：

```sh
$ cd path/to/animate.css/
$ sudo npm install
```

接着，运行 `gulp` 来编译自定义构建。例如，你只需要部分“attention seekers”, 简单地编辑 `animate-config.json` 文件来选择你需要使用的动画名。

```javascript
"attention_seekers": {
  "bounce": true,
  "flash": false,
  "pulse": false,
  "shake": true,
  "headShake": true,
  "swing": true,
  "tada": true,
  "wobble": true,
  "jello":true
}
```

## License
Animate.css is licensed under the MIT license. (http://opensource.org/licenses/MIT)

## Contributing
Pull requests are the way to go here. I apologise in advance for the slow action on pull requests and issues. I only have two rules for submitting a pull request: match the naming convention (camelCase, categorised [fades, bounces, etc]) and let us see a demo of submitted animations in a [pen](http://codepen.io). That last one is important.
