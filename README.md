# HackRapeSenpai

新概念Rape黑科技。喜欢的话点一下右上角的⭐吧！

科学代码

```JavaScript
const numBlock = 4, cap = 20;
let index = 1, gameLayers = ["GameLayer1", "GameLayer2"], blocks = [];


for(let gl of gameLayers){
    for(let num=0;num<40;num++){
        let glName = gl+"-"+num;
        blocks.push(glName);
    }
}

let keyid2keycode = {
    0: 'd',
    1: 'f',
    2: 'j',
    3: 'k'
}

function getTarget() {
    let candidates = blocks.slice(index*4, index*4+4);
    index = (index+1)%cap;
    for(let i in candidates){
        let classes = document.getElementById(candidates[i]).classList;
        if(classes[classes.length-1].charAt(0)=='t') return i;
    }
    console.log(index);
}

function resume() {
    index = 1;
}

function hack() {
    let code = keyid2keycode[getTarget()];    
    var evt = new KeyboardEvent('keydown', {'key':code}); 
    document.dispatchEvent (evt); 
}

function go(cnt){
    for(let i=0;i<cnt;i++){
        hack();
    }
}

function keepRaping(cnt){
    setInterval(hack, 20000/(cnt-1));
}
```

默认你用的是Chrome，其他浏览器应该也可以有类似的调用console的方法，但我的所有开发和测试都在chrome上完成的

## 声明

[雷普先辈游戏地址](https://xiaohuang257.github.io/RapeSenpai/index.html)

[雷普先辈游戏GitHub Repo](https://github.com/Xiaohuang257/RapeSenpai)

如果要使用本外挂请使用默认按键`dfjk`。由于代码量很少直接放在README里了。

本Repo纯娱乐Rape，该游戏既非竞技游戏也非打榜类游戏。

## 函数注入

Chrome打开上述游戏网址，点击开始游戏。（游戏会在第一个按键开始后才计时）

按`F12`调出面板后切换到`console`，在终端复制上述代码，回车。

## 科技使用

以下方法都用在在上面提到的终端，建议是在点`开始游戏`后和按第一个按键之前的时候使用。

### resume()

**在开科技之前务必在console运行一下这个方法**

### hack()

输入hack()的话可以完成一次雷普

### go([输入你要雷普的次数])

对先辈进行狂暴雷普，缺点是由于雷普过于密集会影响计时，优点是可以保质保量完成雷普。

### keepRaping([输入你要雷普的次数])

对先辈进行间歇性雷普，会在20秒内完成。好处是不影响计时，坏处是如果雷普次数过多没办法保证正好完成雷普。
