<link rel="stylesheet" href="style.css">

# 🎮 C++ × Singleton パターン 練習問題

## 🧪 前提
ゲームには「音量設定」「BGM制御」「ログ出力」など、**1つだけ存在すべき要素**があります。
これらを**シングルトンパターン**を使って実装してください。

---

## ✏️ 問題1：GameSettings クラス

### 📋 内容：
- 音量（int）を保持する
- `setVolume(int)` / `getVolume()` を提供
- Singletonで1インスタンスのみ
- mainで `setVolume(75)` → `getVolume()` を表示

---

## ✏️ 問題2：SoundManager クラス

### 📋 内容：
- `playBGM()` → 「BGMを再生中…」
- `stopBGM()` → 「BGMを停止しました」
- Singletonパターンで設計
- mainで2回再生・1回停止

---

## ✏️ 問題3：Logger クラス（応用）

### 📋 内容：
- `log(string message)` を持つ
- 出力形式：[LOG]: メッセージ
- 複数のログを出力する

---

## ✏️ ボーナス問題

### 🎯 複数の Singleton クラスを連携させよう：

- `GameSettings` で音量を設定
- `SoundManager` は `GameSettings` の音量に従って再生（例：「音量80で再生中」）
- `Logger` は再生・停止をログ出力

<div style="page-break-after: always;"></div>

## ✅ 提出main関数例

```cpp
int main() {
    GameSettings::getInstance()->setVolume(80);
    SoundManager::getInstance()->playBGM();
    Logger::getInstance()->log("BGM再生を開始しました。");

    SoundManager::getInstance()->stopBGM();
    Logger::getInstance()->log("BGMを停止しました。");

    return 0;
}
```

---
