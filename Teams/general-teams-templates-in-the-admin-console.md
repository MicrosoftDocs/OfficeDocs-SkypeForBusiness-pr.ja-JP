---
title: 管理センターで一般的なチーム テンプレートを使用する
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
ms.localizationpriority: medium
search.appverid: MET150
description: 管理センターを使用して定義済みの設定、チャネル、およびプレインストールされたアプリを提供することで、一般的なチーム テンプレートを使用してチーム構造を作成する方法について説明します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3427a14da3d994b10bf8d83f5d03f76769401670
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58634051"
---
# <a name="use-general-team-templates-in-the-admin-center"></a>管理センターで一般的なチーム テンプレートを使用する

チーム テンプレートを使用すると、設定、チャネル、およびプレインストールされたアプリの定義済みのテンプレートを提供することで、チームをすばやく簡単に作成できます。

チーム テンプレートには、財務ニーズを中心に設計されたチーム構造の事前構築された定義があります。 また、チーム テンプレートを拡張して、特定の組織のニーズに合わせて調整されたチームを作成することもできます。

この記事では、各チーム テンプレートを紹介し、その使い方をお勧めします。

この記事は、組織全体で複数のチームを計画、デプロイ、管理する責任がある場合に役立ちます。 組織内に Teams サービスがすでに展開されています。 ロールアウトしていない場合は、Teamsの展開方法に関する記事を読[Microsoft Teams。](./deploy-overview.md)

チーム テンプレート全般の詳細については、「チーム テンプレートの概要 [」を参照してください](get-started-with-teams-templates-in-the-admin-console.md)。

## <a name="global-crisis-or-event"></a>グローバルな危機またはイベント

ビジネス ユニット間で危機的チームの共同作業を一元化し、ビジネス継続性計画の作成、リモート作業のヒントの共有、顧客とのコミュニケーションの追跡、お知らせやニュースによる全員のループ状態の維持を支援します。

> [!div class="mx-tdBreakAll"]
> | 基本テンプレートの種類 |baseTemplateId| この基本テンプレートに含まれるプロパティ |
> | ------------------ |--|----------------------------------------------------------|
> | グローバルな危機やイベントで共同作業を行う |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent` | チャネル <ul><li>全般<li>お知らせ</li><li>世界のニュース</li><li>ビジネス継続性</li><li>外部通信</li><li>承認要求</li><li>リモート作業</li><li>内部 comms</li><li>外部通信</li><li>顧客からの苦情</li><li>Kudos</li><li>エグゼクティブの更新</li></ul>アプリ: <ul><li>称賛</li><li>Wiki</li><li>Web サイト</li><li>プランナー</li></ul>|
> ||||

## <a name="adopt-office-365"></a>導入Office 365

新しいテクノロジを同僚に提供し、支援することで、チャンピオン コミュニティのロールアウトを構築、拡大、維持できます。

> [!div class="mx-tdBreakAll"]
> | 基本テンプレートの種類 |baseTemplateId| この基本テンプレートに含まれるプロパティ |
> | ------------------|--|-----------------------------------------------------------|
> | 導入Office 365 | `com.microsoft.teams.template.AdoptOffice365` | チャネル <ul><li>全般</li> <li>お知らせ</li> <li>チャンピオン コーナー</li> <li>チーム フォーム</li></ul> アプリ: <ul><li>Wiki</li>  <li>カレンダー</li><li>スキル開発</li><li>ローン処理</li><li>顧客からの苦情</li><li>Kudos</li><li>楽しい情報</li><li>コンプライアンス</li></ul>|
> ||||

## <a name="manage-a-project"></a>プロジェクトを管理する

このテンプレートを使用して、タスクの管理、ドキュメントの共有、プロジェクト会議の実施、リスクと決定の文書化を行い、一般的なプロジェクト管理を行います。

> [!div class="mx-tdBreakAll"]
> | 基本テンプレートの種類| baseTemplateId| この基本テンプレートに含まれるプロパティ |
> | ------------------|--|-----------------------------------------------------------|
> | プロジェクトを管理する| `com.microsoft.teams.template.ManageAProject`  | チャネル <ul><li>全般</li> <li>お知らせ</li> <li>リソース</li> <li>計画</li></ul> アプリ:<ul><li>Wiki</li><li>OneNote</li><li>プランナー</li><li>リスト</li> </ul> |
> ||||

## <a name="manage-an-event"></a>イベントを管理する

魅力的なイベントを実現するために必要なタスク、ドキュメント、共同作業を管理します。 ゲスト ユーザーを招待して、会社の内部と外部で安全な共同作業を行います。

アプリのアクセス許可ポリシーに基づいて、特定のアプリにアクセスできない可能性があります。

> [!div class="mx-tdBreakAll"]
> | 基本テンプレートの種類 | baseTemplateId| この基本テンプレートに含まれるプロパティ |
> | ------------------ |--|-----------------------------------------------------------|
> | イベントを管理する| `com.microsoft.teams.template.ManageAnEvent` | チャネル <ul><li>全般</li> <li>お知らせ</li> <li>予算</li> <li>コンテンツ</li><li>物流</li> <li>計画</li> <li> マーケティングと PR</li></ul> アプリ:<ul><li>Wiki</li><li>Web サイト</li> <li>YouTube</li> <li>プランナー</li> <li>OneNote</li></ul> |
> ||||

## <a name="onboard-employees"></a>従業員のオンボード

この中央チームを使用して、リソース、質問、および少しの楽しみのために、文化を向上し、従業員のオンボーディングを効率化します。

> [!div class="mx-tdBreakAll"]
> | 基本テンプレートの種類 |baseTemplateId| この基本テンプレートに含まれるプロパティ |
> | ------------------|--|-----------------------------------------------------------|
> | 従業員のオンボード|`com.microsoft.teams.template.OnboardEmployees`  | チャネル <ul><li>全般</li> <li>お知らせ</li> <li>従業員チャット</li> <li>トレーニング</li></ul>アプリ:<ul><li>Wiki</li><li>コミュニティ</li><li>プランナー</li></ul>|
> ||||

## <a name="organize-a-help-desk"></a>ヘルプ デスクを整理する

ヘルプデスクをサポートするドキュメント、ポリシー、プロセスで共同作業を行います。 既存のチケットシステムを統合するか、テンプレートを使用して要求を管理します。

> [!div class="mx-tdBreakAll"]
> | 基本テンプレートの種類 |baseTemplateId| この基本テンプレートに含まれるプロパティ |
> | ------------------|--|------------------------------------------------------------|
> | ヘルプ デスクを整理する|`com.microsoft.teams.template.OrganizeHelpDesk`| チャネル <ul><li>全般</li><li>お知らせ</li><li>よくあるご質問 (FAQ)</li></ul>アプリ:<ul><li>Wiki</li><li>OneNote</li><li>プランナー </li><li>称賛 </li></ul> |
> ||||
