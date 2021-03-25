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
description: 管理センターを使用して定義済みの設定、チャネル、およびプレインストールされたアプリを提供することで、一般的な Teams テンプレートを使用してチーム構造を作成する方法について説明します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: bc21c4137547f34e82e22cc13f9be9e8e1bb257a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120728"
---
# <a name="use-general-teams-templates-in-the-admin-center"></a>管理センターで一般的な Teams テンプレートを使用する

Teams テンプレートでは、設定、チャネル、事前にインストールされたアプリの定義済みテンプレートを使用することで、チームをすばやく簡単に作成できます。

Teams テンプレートには、財務上のニーズを中心に設計されたチーム構造の定義があらかじめ組み込まれています。 Teams テンプレートを拡張して、組織固有のニーズに合わせてチームを作成することもできます。

この記事では、Teams の各テンプレートについて説明し、その使い方をお勧めします。

この記事は、財務組織全体で複数のチームを計画、展開、管理する責任がある場合に役立ちます。 組織内に Teams サービスがすでに展開されています。 Teams を展開していない場合は、まず、Microsoft Teams を展開する方法 [を参照してください](./deploy-overview.md)。

一般的なチーム テンプレートの詳細については、「[Teams テンプレートの使用を開始する](get-started-with-teams-templates-in-the-admin-console.md)」をご参照ください。

## <a name="global-crisis-or-event"></a>グローバルクライシスまたはイベント

ビジネス ユニット間でクライシス チームの共同作業を一元管理し、ビジネス継続性計画の作成、リモート作業のヒントの共有、顧客とのコミュニケーションの追跡、お知らせやニュースで全員が常に連絡を取り合うのに役立ちます。

| 基本テンプレートの種類 |baseTemplateId| この基本テンプレートに含まれるプロパティ |
| ------------------ |--|----------------------------------------------------------|
| グローバルクライシスまたはイベントで共同作業する |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent` |チャネル: <ul><li>全般<li>お知らせ</li><li>世界のニュース</li><li>ビジネス継続性</li><li>外部通信</li><li>承認要求</li><li>リモートでの作業</li><li>内部通信</li><li>外部通信</li><li>顧客からの苦情</li><li>クード</li><li>エグゼクティブ更新</li></ul>アプリ: <ul><li>称賛</li><li>Wiki</li><li>Web サイト</li><li>プランナー</li></ul>|
||||

## <a name="adopt-office-365"></a>365 をOfficeする

新しいテクノロジを使用して同僚に対して提供および支援を行い、チャンピオン コミュニティの展開を構築、成長、維持します。

| 基本テンプレートの種類 |baseTemplateId| この基本テンプレートに含まれるプロパティ |
| ------------------|--|-----------------------------------------------------------|
| 365 をOfficeする | `com.microsoft.teams.template.AdoptOffice365` |  チャネル: <ul><li>全般</li> <li>お知らせ</li> <li>チャンピオン コーナー</li> <li>チーム フォーム</li></ul> アプリ: <ul><li>Wiki</li>  <li>カレンダー</li><li>スキル開発</li><li>ローン処理</li><li>顧客からの苦情</li><li>クード</li><li>楽しい情報</li><li>コンプライアンス</li></ul>|
||||

## <a name="manage-a-project"></a>プロジェクトを管理する

一般的なプロジェクト管理用のテンプレートを使用して、タスクの管理、ドキュメントの共有、プロジェクト会議の実施、リスクと決定の文書化を行います。

| 基本テンプレートの種類| baseTemplateId| この基本テンプレートに含まれるプロパティ |
| ------------------|--|-----------------------------------------------------------|
| プロジェクトを管理する| `com.microsoft.teams.template.ManageAProject`  | チャネル: <ul><li>全般</li> <li>お知らせ</li> <li>リソース</li> <li>計画</li></ul> アプリ:<ul><li>Wiki</li><li>OneNote</li><li>プランナー</li><li>リスト</li> </ul> |
||||

## <a name="manage-an-event"></a>イベントを管理する

タスク、ドキュメントを管理し、説得力のあるイベントを実現するために必要なすべてについて共同作業します。 ゲスト ユーザーを招待して、会社の内部と外部で安全な共同作業を行います。

アプリのアクセス許可ポリシーに基づいて、特定のアプリにアクセスできない場合があります。

| 基本テンプレートの種類 | baseTemplateId| この基本テンプレートに含まれるプロパティ |
| ------------------ |--|-----------------------------------------------------------|
| イベントを管理する| `com.microsoft.teams.template.ManageAnEvent` | チャネル: <ul><li>全般</li> <li>お知らせ</li> <li>予算</li> <li>コンテンツ</li><li>物流</li> <li>計画</li> <li> マーケティングと PR</li></ul> アプリ:<ul><li>Wiki</li><li>Web サイト</li> <li>YouTube</li> <li>プランナー</li> <li>OneNote</li></ul> |
||||

## <a name="onboard-employees"></a>従業員のオンボード

この中央チームを使用して、リソース、質問、および少しの楽しみのために、文化を改善し、従業員のオンボーディングを合理化します。

| 基本テンプレートの種類 |baseTemplateId| この基本テンプレートに含まれるプロパティ |
| ------------------|--|-----------------------------------------------------------|
|従業員のオンボード|`com.microsoft.teams.template.OnboardEmployees`  | チャネル: <ul><li>全般</li> <li>お知らせ</li> <li>従業員のチャット</li> <li>トレーニング</li></ul>アプリ:<ul><li>Wiki</li><li>コミュニティ</li><li>プランナー</li></ul>|
||||

## <a name="organize-a-help-desk"></a>ヘルプ デスクを整理する

ヘルプデスクをサポートするドキュメント、ポリシー、プロセスで共同作業を行います。 既存のチケット システムを統合するか、テンプレートを使用して要求を管理します。

| 基本テンプレートの種類 |baseTemplateId| この基本テンプレートに含まれるプロパティ |
| ------------------|--|------------------------------------------------------------|
|ヘルプ デスクを整理する|`com.microsoft.teams.template.OrganizeHelpDesk`| チャネル:<ul><li>全般</li><li>お知らせ</li><li>よくあるご質問 (FAQ)</li></ul>アプリ:<ul><li>Wiki</li><li>OneNote</li><li>プランナー </li><li>称賛 </li></ul> |
||||