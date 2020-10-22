---
title: 管理センターで一般的な Teams テンプレートを使用する
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: 管理センターを使って、定義済みの設定、チャネル、事前にインストールされているアプリを提供して、チームの構造を作成するための一般的な Teams テンプレートの使用方法について説明します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: a158850a70a0410c9be7cb434d6f0868d68218f5
ms.sourcegitcommit: 0a9c5c01b37a93eecc369ca0ed49ae18f6a5065b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2020
ms.locfileid: "48655504"
---
# <a name="use-general-teams-templates-in-the-admin-center"></a>管理センターで一般的な Teams テンプレートを使用する

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Teams テンプレートを使用すると、設定、チャネル、プリインストールされているアプリに定義済みのテンプレートを提供して、チームをすばやく簡単に作成できます。

Teams テンプレートには、財務ニーズに合わせて設計されたチーム構造の事前定義が含まれています。 また、チームテンプレートを拡張して、特定の組織のニーズに合わせてカスタマイズされたチームを作成することもできます。

この記事では、各チームテンプレートを紹介し、その使い方をお勧めします。

この記事は、お客様が財務組織全体の複数のチームの計画、展開、管理を担当している場合に適しています。 組織に Teams サービスを既に展開している。 チームをロールアウトしていない場合は、「 [Microsoft teams をロールアウトする方法](How-to-roll-out-teams.md)」を参照してください。

チームテンプレート全般の詳細については、「 [チームテンプレートの概要](get-started-with-teams-templates-in-the-admin-console.md)」を参照してください。

## <a name="global-crisis-or-event"></a>グローバルな危機またはイベント

ビジネスユニット全体での危機管理チームの共同作業を一元化して、ビジネス継続性プランの作成、リモートの作業ヒントの共有、顧客の通信の追跡、全員がお知らせとニュースの記録を行うことができます。

| ベーステンプレートの種類 |baseTemplateId| この基本テンプレートに含まれるプロパティ |
| ------------------ |--|----------------------------------------------------------|
| グローバルな危機またはイベントでの共同作業 |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent` |チャネル <ul><li>一般<li>お知らせ</li><li>世界中のニュース</li><li>ビジネス継続性</li><li>リモート作業</li><li>内部通信</li><li>外部通信</li><li>顧客の苦情</li><li>称賛</li><li>エグゼクティブ更新プログラム</li></ul>アプリ <ul><li>称賛</li><li>ウィキ</li><li>当</li></ul>|
||||

## <a name="adopt-office-365"></a>Office 365 を導入する

良さによって、お客様のエキスパートコミュニティの構築、成長、維持を支援し、新しいテクノロジでお互いの協力を支援します。

| ベーステンプレートの種類 |baseTemplateId| この基本テンプレートに含まれるプロパティ |
| ------------------|--|-----------------------------------------------------------|
| Office 365 を導入する | `com.microsoft.teams.template.AdoptOffice365` |  チャネル <ul><li>一般</li> <li>お知らせ</li> <li>チャンピオンのコーナー</li> <li>チームフォーム</li></ul> アプリ <ul><li>ウィキ</li>  <li>カレンダー</li><li>スキルの開発</li><li>ローン処理</li><li>顧客の苦情</li><li>称賛</li><li>楽しい機能</li><li>コンプライアンス</li></ul>|
||||

## <a name="manage-a-project"></a>プロジェクトを管理する

一般的なプロジェクト管理については、このテンプレートを使用して、タスクの管理、ドキュメントの共有、プロジェクト会議の実施、リスクの文書化、意思決定を行うことができます。

| ベーステンプレートの種類| baseTemplateId| この基本テンプレートに含まれるプロパティ |
| ------------------|--|-----------------------------------------------------------|
| プロジェクトを管理する| office の管理について  | チャネル <ul><li>一般</li> <li>お知らせ</li> <li>参照</li> <li>計画</li></ul> アプリ<ul><li>ウィキ</li><li>OneNote</li></ul> |
||||

## <a name="manage-an-event"></a>イベントを管理する

魅力的なイベントを実現するために必要なすべての情報について、タスクやドキュメントを管理し、共同作業を行うことができます。 ゲストユーザーを招待して、社外と社外の間で安全な共同作業を行います。

アプリのアクセス許可ポリシーに基づいて、特定のアプリにアクセスできない場合があります。

| ベーステンプレートの種類 | baseTemplateId| この基本テンプレートに含まれるプロパティ |
| ------------------ |--|-----------------------------------------------------------|
| イベントを管理する| `com.microsoft.teams.template.ManageAnEvent` | チャネル <ul><li>一般</li> <li>お知らせ</li> <li>予算</li> <li>コンテンツ</li><li>物流</li> <li>計画</li> <li> マーケティングと PR</li></ul> アプリ<ul><li>ウィキ</li><li>当</li> <li>YouTube</li> <li>プランナー</li> <li>OneNote</li></ul> |
||||

## <a name="onboard-employees"></a>オンボード従業員

この中央のチームを使って、自分の文化を改善し、従業員のオンボードを効率化することができます。

| ベーステンプレートの種類 |baseTemplateId| この基本テンプレートに含まれるプロパティ |
| ------------------|--|-----------------------------------------------------------|
|オンボード従業員|`com.microsoft.teams.template.OnboardEmployees`  | チャネル <ul><li>一般</li> <li>お知らせ</li> <li>従業員チャット</li> <li>トレーニング</li></ul>アプリ<ul><li>ウィキ</li><li>お気に入り</li></ul>|
||||

## <a name="organize-a-help-desk"></a>ヘルプデスクを整理する

ヘルプデスクをサポートするドキュメント、ポリシー、プロセスについて共同作業を行います。 既存のチケットシステムを統合するか、テンプレートを使用して要求を管理します。

| ベーステンプレートの種類 |baseTemplateId| この基本テンプレートに含まれるプロパティ |
| ------------------|--|------------------------------------------------------------|
|ヘルプデスクを整理する|`com.microsoft.teams.template.OrganizeHelpDesk`| チャネル<ul><li>一般</li><li>お知らせ</li><li>FAQ</li></ul>アプリ<ul><li>ウィキ</li><li>OneNote</li></ul> |
||||
