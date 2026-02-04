# Void Mediator — Phase-Law Architecture

<p align="center">
  <img src="https://img.shields.io/badge/version-0.1-cyan?style=flat-square" alt="Version">
  <img src="https://img.shields.io/badge/pTCP-Phase--Law_Architecture-1a6a5a?style=flat-square" alt="pTCP">
</p>

> **情報と物理の断絶を橋渡しする**  
> *Bridging the discontinuity between information and physics*

## 🌐 Live Demo

- **Main App**: [https://yourusername.github.io/void-mediator/](https://yourusername.github.io/void-mediator/)
- **Field Analysis**: [https://yourusername.github.io/void-mediator/field-analysis.html](https://yourusername.github.io/void-mediator/field-analysis.html)

## 📱 Quick Start

### スマートフォンでアクセス

1. 上記URLをSafari（iOS）またはChrome（Android）で開く
2. 「ACTIVATE FIELD」をタップ
3. センサーアクセス許可を付与
4. ホーム画面に追加でフルスクリーンアプリとして利用可能

### センサー対応状況

| センサー | iOS | Android | Desktop |
|---------|-----|---------|---------|
| 加速度計 | ✓ | ✓ | ✗ |
| ジャイロスコープ | ✓ | ✓ | ✗ |
| マイク | ✓ (許可必要) | ✓ (許可必要) | ✓ |
| 位置情報 | ✓ (許可必要) | ✓ (許可必要) | ✓ |

## 🔬 Concept

Void Mediator は **Phase-Law Architecture (pTCP)** の実装プロトタイプです。

### μ（ミュー）動態

```
dμ/dt = α(μ_env − μ) + β·∇ρ(x)
```

- **α = 0.08**: 環境適応係数
- **β = 0.04**: 場密度勾配係数
- **μ_env**: 環境から推定される調停強度
- **∇ρ(x)**: 場密度の空間勾配

### フェーズ状態

| μ値 | 状態 | 説明 |
|-----|------|------|
| < 0.15 | VOID | 純粋物理状態 — 情報との接続なし |
| < 0.35 | LATENT | 潜在調停 — 場の発生 |
| < 0.55 | MEDIATING | 調停中 — 双方向拘束伝播 |
| < 0.75 | COHERENT | 場秩序確立 — 命令なき誘導 |
| ≥ 0.75 | DISSOLVED | 完全調停 — 情報/物理の区別消失 |

## 📁 Structure

```
void-mediator/
├── index.html          # メインアプリ（PWA対応）
├── field-analysis.html # CSVログ分析ツール
└── README.md
```

## 🛠️ Development

### ローカルサーバー起動

```bash
# Python
python -m http.server 8000

# Node.js
npx serve

# HTTPS（センサーテスト用）
npx serve --ssl
```

※ センサーアクセスにはHTTPSが必要です

### デプロイ

```bash
# GitHub Pagesの場合
# Settings → Pages → Source: main branch を設定するだけ

# Vercelの場合
vercel --prod

# Netlifyの場合
# Drag & Drop でindex.htmlをアップロード
```

## 📊 Field Analysis Tool

街歩きで記録したCSVログを分析するためのツールです。

1. `field-analysis.html` を開く
2. CSVファイルをドラッグ＆ドロップ
3. μ時系列、センサー相関、フェーズ分布を可視化

### CSV形式

```csv
time, elapsed_ms, mu, field_density, motion_energy, env_complexity,
constraint_tension, phase_gear_ratio, field_phase,
accel_x, accel_y, accel_z, gyro_alpha, gyro_beta, gyro_gamma,
audio_level, light_lux, wifi_ap_count, wifi_density, wifi_stale, wifi_stale_ms
```

## 🔗 Related

- **Android App**: 完全版はKotlinネイティブ実装（別リポジトリ）
- **Phase-Law Architecture Spec**: pTCPプロトコル仕様書

---

<p align="center">
  <sub>Phase-Law Architecture / pTCP</sub><br>
  <sub>Void Mediator v0.1</sub>
</p>
