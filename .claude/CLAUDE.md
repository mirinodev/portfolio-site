# ポートフォリオサイト

kaishuのポートフォリオ。Motion/GSAP/R3Fで動きと3Dを活かした体験重視サイト。
スコープ外: CMS機能、ブログ、外部API連携、お問い合わせフォーム（bot スパム対策で 2026-11 に撤去）

## Stack

Next.js 16 (App Router + Turbopack) / React 19 / TypeScript 5.9
Tailwind CSS + CSS Modules / shadcn/ui / Motion + GSAP / R3F + Drei

## Structure

```
src/app/              -- ページ・ルーティング
src/app/components/   -- 共通コンポーネント（3D, Animation, layouts等）
src/app/features/     -- 機能別（about/, skills/, works/）
src/components/ui/    -- shadcn/ui（変更禁止: 自動生成）
src/lib/              -- ユーティリティ
```

## Rules

- `any`禁止、型明示（型安全性）
- 新規コンポーネント: 関数宣言（理由: 既存コードベース統一）
- スタイル: CSS Modules + Tailwind。既存パターン準拠
- アニメーション: Motion優先。GSAP=既存一貫性時のみ（理由: ランタイム二重化回避）
- `src/components/ui/` 変更禁止（shadcn/ui自動生成）
- 新規UI -> `src/app/components/`配置
- 既存コードのパターンに従う

## Commands

dev: `pnpm dev`
build: `pnpm build`
lint: `pnpm lint:fix`
typecheck: `pnpm typecheck`
pkg: pnpm（packageManager設定。npm/yarn不可）

## Docs

- `.docs/conventions.md` -- スタイリング・アニメーション・コンテンツ詳細規約
