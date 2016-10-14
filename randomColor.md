#获取随机颜色
1.
function getRandomColor(){ 

return "#"+("00000"+((Math.random()*16777215+0.5)>>0).toString(16)).slice(-6); 

} 
2.
var getRandomColor = function() {
return '#' + (function(color) { 
//这个写法比较有意思,Math.floor(Math.random()*16);返回的是一个小于或等于16的数.然后作为0123456789abcdef的下标,这样每次就会得到一个这个字符串当中的一个字符
return (color += '0123456789abcdef' [Math.floor(Math.random() * 16)]) 
//然后判断这个新字符串的长度是否到6,因为16进制的颜色是由6个字符组成的,如果到6了,就返回这6个字符拼成的字符串,如果没有就执行arguments.callee(color)也就是函数本身.
&& (color.length == 6) ? color: arguments.callee(color); //将''字符串传给color
})('');
}
