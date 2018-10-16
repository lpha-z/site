# ceil
* chrono[meta header]
* std::chrono[meta namespace]
* function[meta id-type]
* cpp17[meta cpp]

```cpp
namespace std::chrono {
  template <class ToDuration, class Rep, class Period>
  constexpr ToDuration ceil(const duration<Rep, Period>& d);
}
```

## 概要
分解能が低い`duration`に変換する際に、天井関数 (正の無限大方向への丸め、切り上げ) による丸めを行う。


## 戻り値
`d`以上の値を返す。


## 例
```cpp example
#include <iostream>
#include <chrono>

using namespace std::chrono;

int main()
{
  milliseconds ms{1500};
  seconds s = ceil<seconds>(ms);

  std::cout << s.count() << std::endl;
}
```
* ceil[color ff0000]
* milliseconds[link /reference/chrono/milliseconds.md]
* seconds[link /reference/chrono/seconds.md]
* s.count()[link count.md]

### 出力
```
2
```

## バージョン
### 言語
- C++17

### 処理系
- [GCC, C++17 mode](/implementation.md#gcc): 7.3
- [Clang, C++17 mode](/implementation.md#clang): 3.8
- [Visual C++](/implementation.md#visual_cpp): ??


## 関連項目

| 名前 | 説明 |
|------|------|
| [`duration_cast`](/reference/chrono/duration_cast.md) | ゼロ方向への丸め |
| [`floor`](floor.md)                                   | 負の無限大方向への丸め |
| [`round`](round.md)                                   | 偶数方向への丸め |