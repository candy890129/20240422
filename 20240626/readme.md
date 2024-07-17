DOM 單選
只會取得第一個找到的DOM

let selector = '#some';
let dom = document.querySelector(selector);
DOM 多選
不管找到幾個，都使用NodeList陣列包裝

let selector = '#some';
let items = document.querySelectorAll(selector);
取得內容
內容指的是<div>內容</div>

let some = document.querySelector('#some');
let text = some.innerHTML;
取得數值
數值指的是<input value="">

let input = document.querySelector('#account');
let value = input.value;
事件監聽
let getAccountBtn = document.querySelector('#get-account');
getAccountBtn.addEventListener('click', () => {
    cosole.log('click');
})
Say hi 練習
say_hi.html

判斷式
let condition = true;
if (condition) {
    console.log('ok');
} else {
    console.log('no');
}


let a = 10;
let b = 20;

console.log(`a: ${a}, b: ${b}, a - b`);
if (a - b) {
    console.log('ok') // here.
} else {
    console.log('no')
}
鎖定輸入框
usernameInput.focus();
附加 class
dom.classList.add('classname');
移除 class
dom.classList.remove('classname');
加法
math.html

const addCalc = () => {
    let num = getNum();
    if (!num) {
        return false;
    }

    let result = num[0] + num[1];
    response.innerHTML = `${num[0]} + ${num[1]} = ${result}`;
    response.classList.add('d-block');
    response.classList.remove('d-none');
}


calc1Btn.addEventListener('click', addCalc);
減法
const substructCalc = () => {
    let num = getNum();
    if (!num) {
        return false;
    }

    let result = num[0] - num[1];
    response.innerHTML = `${num[0]} - ${num[1]} = ${result}`;
    done();
}
乘法
const multiplyCalc = () => {
    let num = getNum();
    if (!num) {
        return false;
    }

    let result = num[0] * num[1];
    response.innerHTML = `${num[0]} * ${num[1]} = ${result}`;
    done();
}
除法
const dividedCalc = () => {
    let num = getNum();
    if (!num) {
        return false;
    }

    if (num[1] == 0) {
        alert('分母不可為0');
        return false;
    }

    let result = num[0] / num[1];
    response.innerHTML = `${num[0]} / ${num[1]} = ${result}`;
    done();
}
餘數
const remainderCalc = () => {
    let num = getNum();
    if (!num) {
        return false;
    }

    if (num[1] == 0) {
        alert('分母不可為0');
        return false;
    }

    let result = num[0] % num[1];
    response.innerHTML = `${num[0]} % ${num[1]} = ${result}`;
    done();
}
NEXT 改用下拉選單實作計算