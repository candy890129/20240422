手風琴選單
開啟時
+ -> -
內容展開
使用:checked來處理狀態切換
checkbox -> 多項目展開
radio -> 單項目展開
accrodion.html

單選
結構與多選一樣，可直接複製多選結構。
將 checkbox 改為 radio 並且給予同樣的 name 值。
步驟拆解
<div class="accrodion-item">
    <input type="checkbox" class="accrodion-switch" id="accrodion-multi-1">
    <label for="accrodion-multi-1" class="accrodion-header">
        <div>One</div>
        <div class="accrodion-to-open">+</div>
        <div class="accrodion-to-close">-</div>
    </label>
    <div class="accrodion-body zh-tw">我是第一個問題回答</div>
</div>
預設accrodion-to-close隱藏，accrodion-to-open顯示
.accrodion-wrap .accrodion-to-close {
    display: none;
}
預設accrodion-body隱藏
.accrodion-wrap .accrodion-body {
    padding: 10px;
    border: 1px solid #1a63b6;
    display: none;
}
accrodion-switch:checked時
3-1. accrodion-to-close顯示，accrodion-to-open隱藏

.accrodion-wrap .accrodion-switch:checked~.accrodion-header .accrodion-to-open {
    display: none;
}

.accrodion-wrap .accrodion-switch:checked~.accrodion-header .accrodion-to-close {
    display: block;
}
3-2. accrodion-body顯示

.accrodion-wrap .accrodion-switch:checked~.accrodion-body {
    display: block;
}
位置
使用position屬性

relative 浮貼，有z-index屬性可用，會佔據原本位置
absolute 遮住，有z-index屬性可用，不會佔據原本位置
fixed 遮住，有z-index屬性可用，不會佔據原本位置
z-index
圖層的概念，數字越高代表圖層越高
當數字相同時，後者蓋住前者
position.html

<div class="wrap">
    <div class="item relative">R1</div>
    <div class="item absolute">A</div>
    <div class="item relative">R2</div>
</div>
.wrap {
    padding: 20px;
    border: 1px solid #505050;
}

.wrap .item {
    width: 100px;
    height: 100px;
    background: #dedede;
    color: #fff;
    display: flex;
    align-items: center;
    justify-content: center;
}

.wrap .relative {
    background: red;
    position: relative;
    /* opacity: 0.2; */
    z-index: 1;
}

.wrap .absolute {
    background: yellow;
    color: red;
    position: absolute;
    z-index: 1; /* 調整數字觀察 */
    opacity: 0.5;
}
移動
left跟right一組，不可同時使用
top跟bottom一組，不可同時使用
數值為數字加單位，例如 10px
relative不參考原點直接移動，基本上只做為參考點，不移動
absolute移動時會往上一層找原點，原點指的是非static，如果都找不到就已body為原點
fixed直接參考body為原點，通常都是放在第一層
畫臉練習
face.html

區塊置中顯示公式
.some {
    width: 100px;
    height: 50px;
    position: absolute;
    left: calc(50% - 50px); /* width 一半 */
    top: calc(50% - 25px); /* height 一半 */
}
NEXT 位置實戰#POPUP