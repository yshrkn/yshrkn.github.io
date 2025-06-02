# EvenオブジェクトのtargetとcurrentTargetの違いについて

いつも忘れてしまうのでまとめておく。

## サンプルコード

テキストをクリックしたときの挙動の違いは以下の通り。

```js
function Button({ children }) {
  const handleClick = (e) => {
    console.log(e.target); // <strong>​テキスト​</strong>​
    console.log(e.currentTarget); // <button>​<strong>​テキスト​</strong>​</button>​
  };

  return (
    <button onClick={handleClick}>
      <strong>{children}</strong>
    </button>
  );
}
```

## まとめ

- Eventのtarget: イベントが実際に発生した要素への参照を格納している
- EventのcurrentTarget: イベントハンドラが登録されている要素への参照を格納している

## 参考

[Event: target プロパティ](https://developer.mozilla.org/ja/docs/Web/API/Event/target)
[Event: currentTarget プロパティ](https://developer.mozilla.org/ja/docs/Web/API/Event/currentTarget