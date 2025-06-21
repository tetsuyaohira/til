## Fetch関数
- Web標準APIのFetch関数はNext.jsにおいて、フレームワークレベルで拡張されている
- 結果をキャッシュしてくれる
- キャッシュをしない場合は、引数にcache: "no-store"`を指定

## Hydration
### 概要
- **Hydration = 静的なHTMLに命を吹き込むこと**
- React.jsの技術だが、Next.jsが自動化・最適化してくれる
- Server ComponentとClient Componentの境界で発生

### 流れ
1. **サーバーサイド**: 静的HTML生成（骨格のみ）
2. **ブラウザ受信**: HTML表示（まだ機能なし）  
3. **Hydration開始**: JavaScriptコンポーネントと照合
4. **Hydration完了**: イベントリスナー追加、動的機能有効化

### 対象範囲
- ✅ **`'use client'`コンポーネント**: Hydrationあり
- ❌ **Server Component**: Hydrationなし（JavaScriptすら送信されない）

### ブラウザ専用ライブラリとの問題
```tsx
// 問題: Hydration時にwindowオブジェクトアクセス
import { MapContainer } from 'react-leaflet'  // ← エラー！

// 解決: dynamic import + ssr: false
const MapContainer = dynamic(() => import('...'), { ssr: false })
```

### 重要なポイント
- **`'use client'`**: コンポーネントの実行場所を制御
- **`dynamic` + `ssr: false`**: importの評価タイミングを制御
- Hydrationは「完全なブラウザ環境」ではない微妙なタイミング
