# チートシート

チュートリアルの内容を簡単にまとめたもの．

### 変数

値にラベル付けを行う．変数に使用できる文字には制限がある．

- アルファベット
- 数字
- アンダースコア

変数名は数字で初めてはいけない．以下のような変数名は使用できない．

- 0a
- 1111

```javascript
let a = 10
let b = 'Text'
```

> 変更の可能性がない変数は `let` ではなく `const` を使用して定数にする．

### 条件分岐

指定した条件によって処理を分岐させる．

- `else if` 節で複数の条件での分岐ができる
- `else` 節は省略可能である

```javascript
if(condition1){
  // condition1 が真のとき statement1 を実行する
  statement1
} else if(condition2) {
  // condition1 が偽で condition2 が真のとき statement2 を実行する
  statement2
} else {
  // condition1 と condition2 が偽のとき statement3 を実行する
  statement3
}
```

| 条件 | | 例 |  |
|:-|:-|:-|:-|
| == | 等しい | A == B | A と B は等しい |
| != | 等しくない | A != B | A と B は等しくない |
| >= | 以上（以下） | A >= B | A は B 以上 |
| <= | 以下（以上） | A <= B | A は B 以下 |
| > | 大きい（小さい） | A > B | A は B より大きい |
| < | 小さい（大きい） | A < B | A は B より小さい |

> `==` ではなく `===`，`!=` ではなく `!==` を使用する．

| 条件 | | 例 |  |
|:-|:-|:-|:-|
| &#124;&#124; | または | A &#124;&#124; B | A または B が真である |
| && | かつ | A && B | A と B はどちらも真である |


### ループ

単調な処理をまとめる．

```javascript
for(let i=0; i<5; i++){
  console.log(i)
}
// 0
// 1
// 2
// 3
// 4
```

### 関数

共通の処理をひとつにまとめる．

```javascript
function add(x, y) {
  const result = x + y
  return result
}

// 以下は上記の関数と動作は同じ

const add = function(x, y) {
  const result = x + y
  return result
}

const add = (x, y) => {
  const result = x + y
  return result
}

const add = (x, y) => {
  return x + y
}

const add = (x, y) => x + y
```

> 無名関数やアロー関数の記述に注意する．

### オブジェクト

複数の値をひとつにまとめる．

##### 配列

複数の値を持つことができる．

```javascript
const array = [1, 2, 3, 4, 5]

console.log(array[0]) // 1
console.log(array[1]) // 2
```

> 添字を使用して値を参照する．添字は 0 から始まることに注意する．

##### 連想配列

配列の添字に数値以外の値が使用できる．

```javascript
const object = {
  message: 'Hello World',
  profile: {
    name: 'Diarmait Mac Craith',
    age: 20
  }
}

console.log(object['message']) // Hello World
console.log(object['profile']['age']) // 20

console.log(object.message) // Hello World
console.log(object.profile.age) // 20
```
