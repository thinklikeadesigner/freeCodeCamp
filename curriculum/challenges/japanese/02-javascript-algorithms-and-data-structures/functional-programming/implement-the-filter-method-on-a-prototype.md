---
id: 587d7b8f367417b2b2512b64
title: プロトタイプに filter メソッドを実装する
challengeType: 1
forumTopicId: 301231
dashedName: implement-the-filter-method-on-a-prototype
---

# --description--

`filter` メソッドについては、独自のバージョンを実装することで多くのことを学べるかもしれません。 `for` ループまたは `Array.prototype.forEach()` を使用することをお勧めします。

# --instructions--

`Array.prototype.filter()` とまったく同じように動作する、独自の `Array.prototype.myFilter()`を記述してください。 組み込みの `filter` メソッドを使用しないでください。 `myFilter` メソッドで `Array` インスタンスにアクセスするには `this` を使用します。

# --hints--

`[23, 65, 98, 5, 13].myFilter(item => item % 2)` should equal `[23, 65, 5, 13]`.

```js
const _test_s = [23, 65, 98, 5, 13];
const _callback = item => item % 2;
assert(JSON.stringify(_test_s.filter(_callback)) === JSON.stringify(_test_s.myFilter(_callback)));
```

`filter` メソッドを使用しないでください。

```js
assert(!code.match(/\.?[\s\S]*?filter/g));
```

# --seed--

## --seed-contents--

```js
Array.prototype.myFilter = function(callback) {
  const newArray = [];
  // Only change code below this line

  // Only change code above this line
  return newArray;
};
```

# --solutions--

```js
Array.prototype.myFilter = function(callback) {
  const newArray = [];
  for (let i = 0; i < this.length; i++) {
    if (callback(this[i])) newArray.push(this[i]);
  }
  return newArray;
};

// Test case
const s = [23, 65, 98, 5];
const odd_s = s.myFilter(item => item % 2 === 1);
```
