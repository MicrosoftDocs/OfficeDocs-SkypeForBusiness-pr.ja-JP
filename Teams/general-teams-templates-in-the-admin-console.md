---
title: 管理センターで一般的なチーム テンプレートを使用する
author: lanachin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: yinchang
ms.collection:
- M365-collaboration
ms.localizationpriority: medium
search.appverid: MET150
description: Teams 管理センターで一般的なチーム テンプレートを管理および使用して、チームをすばやく簡単に作成する方法について説明します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 05e540ea968f04724d5d644f6ad7640b1f46df89
ms.sourcegitcommit: ceba5fd8f098c8d0eafaffe5c5301c845a3ae7ab
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2022
ms.locfileid: "67837347"
---
# <a name="use-general-team-templates-in-the-admin-center"></a>管理センターで一般的なチーム テンプレートを使用する

## <a name="overview"></a>概要

Microsoft Teams のチーム テンプレートでは、設定、チャネル、事前にインストールされたアプリの定義済みチーム構造を使用することで、チームをすばやく簡単に作成できます。

チーム テンプレートを使用して、組織全体に一貫性のあるチームを展開します。 テンプレートは、ユーザーが Teams を効果的に使用する方法を理解するのに役立ちます。 また、テンプレートを拡張して、特定の組織のニーズに合わせて調整されたチームを作成することもできます。

Teams には、特定のビジネス ニーズとプロジェクト用に作成した事前構築済みテンプレートが含まれています。 この記事では、さまざまなシナリオで組織で使用できるテンプレートの一般的なカテゴリについて説明します。

一般的なチーム テンプレートの詳細については、「[Teams 管理センターでチーム テンプレートの使用を開始する](get-started-with-teams-templates-in-the-admin-console.md)」をご参照ください。

> [!NOTE]
> アスタリスク (*) は、テンプレートが *Microsoft 365 接続されたテンプレート* であることを示します。 ユーザーがテンプレートを使用してチームを作成すると、接続された SharePoint テンプレートがサイトとチームに適用されます。 ページ、リスト、Power Platform 統合などの SharePoint コンポーネントは、チームの [全般] チャネルにタブとして自動的に追加され、ピン留めされます。 ユーザーは、Teams 内から直接これらのページとリストを編集できます。
>
> SharePoint テンプレートの詳細については、「 [SharePoint サイト テンプレートの適用とカスタマイズ](https://support.microsoft.com/office/apply-and-customize-sharepoint-site-templates-39382463-0e45-4d1b-be27-0e96aeec8398#ID0EDBJ=Team_site_templates)」を参照してください。

## <a name="manage-a-project"></a>プロジェクトを管理する*

一般的なプロジェクト管理用のこのテンプレートを使用して、タスクの管理、ドキュメントの共有、プロジェクト会議の実施、リスクと決定の文書化を行います。

> [!div class="mx-tdBreakAll"]
> | テンプレートの種類| TemplateId| このテンプレートに含まれるプロパティ |
> | ------------------|--|-----------------------------------------------------------|
> | プロジェクトを管理する |`com.microsoft.teams.template.ManageAProject`| チャネル: <ul><li>全般</li> <li>お知らせ</li> <li>リソース</li> <li>計画</li></ul> アプリ:<ul><li>承認</li><li>情報</li><li>リスト<ul><li>プロジェクト トラッカー</li><li>イシュー トラッカー</li></ul></li><li>マイルス トーン</li><li>OneNote</li><li>Power Automate</li><li>SharePoint ページ<ul><li>サイト</li></ul></li><li>Planner と To Do によるタスク</li><li>Wiki</li></ul> |

## <a name="manage-an-event"></a>イベントを管理する*

魅力的なイベントを配信するために必要なすべてのタスク、ドキュメントを管理し、共同作業を行います。 ゲスト ユーザーを招待して、社内外でセキュリティで保護されたコラボレーションを行います。

アプリのアクセス許可ポリシーに基づいて、特定のアプリにアクセスできない可能性があります。

> [!div class="mx-tdBreakAll"]
> | テンプレートの種類 | TemplateId| このテンプレートに含まれるプロパティ |
> | ------------------ |--|-----------------------------------------------------------|
> | イベントを管理する|`com.microsoft.teams.template.ManageAnEvent` | チャネル: <ul><li>全般</li> <li>お知らせ</li> <li>予算</li> <li>コンテンツ</li><li>物流</li> <li>計画</li> <li> マーケティングと PR</li></ul> アプリ:<ul><li>承認</li><li>情報</li> <li>従業員のアイデア</li> <li>リスト<ul><li>コンテンツ スケジューラ</li></ul><li>マイルス トーン</li></li> <li>OneNote</li> <li>Power Automate</li> <li>SharePoint ページ<ul><li>サイト</li><li>イベントについて</li></ul><li>Planner と To Do によるタスク</li><li>Wiki</li> |

## <a name="onboard-employees"></a>従業員のオンボード*

リソース、質問、および少しの楽しみのために、この中央チームで従業員のオンボーディングを効率化し、文化を向上させましょう。

> [!div class="mx-tdBreakAll"]
> | テンプレートの種類 |TemplateId| このテンプレートに含まれるプロパティ |
> | ------------------|--|-----------------------------------------------------------|
> | 従業員をオンボードする|`com.microsoft.teams.template.OnboardEmployees` | チャネル: <ul><li>全般</li> <li>お知らせ</li> <li>従業員チャット</li> <li>トレーニング</li></ul>アプリ:<ul><li>情報</li><li>従業員のアイデア</li><li>リスト<ul><li>オンボード チェックリスト</li></ul></li><li>マイルス トーン</li><li>Power Automate</li> <li>SharePoint ページ<ul><li>はじめに</li><li>トレーニング</li></ul><li>Planner と To Do によるタスク</li><li>Viva エンゲージ</li><li>Wiki</li></ul>|

## <a name="adopt-office-365"></a>Office 365を採用する

新しいテクノロジを仲間に提供し、支援することで、チャンピオンズ コミュニティのロールアウトを構築、成長、維持するのに役立ちます。

> [!div class="mx-tdBreakAll"]
> | テンプレートの種類 |TemplateId| このテンプレートに含まれるプロパティ |
> | ------------------|--|-----------------------------------------------------------|
> | Office 365を採用する |`com.microsoft.teams.template.AdoptOffice365`|  チャネル: <ul><li>全般</li> <li>お知らせ</li> <li>チャンピオンズ コーナー</li> <li>チーム フォーム</li><li>カレンダー</li></ul> アプリ: <ul><li>Wiki</li>  <li>チャネル カレンダー</li> <li>マイルス トーン</li><li>情報</li></ul>|

## <a name="organize-help-desk"></a>ヘルプ デスクの整理*

ヘルプ デスクをサポートするドキュメント、ポリシー、プロセスで共同作業を行います。 既存のチケット発行システムを統合するか、テンプレートを使用して要求を管理します。

> [!div class="mx-tdBreakAll"]
> | テンプレートの種類 |TemplateId| このテンプレートに含まれるプロパティ |
> | ------------------|--|------------------------------------------------------------|
> | ヘルプ デスクを整理する| `com.microsoft.teams.template.OrganizeHelpDesk`|チャネル:<ul><li>全般</li><li>お知らせ</li><li>よくあるご質問 (FAQ)</li></ul>アプリ:<ul><li>問題の報告</li><li>リスト<ul><li>デバイス</li><li>チケット</li></ul></li><li>OneNote</li><li>Power Automate</li><li>SharePoint ページ<ul><li>サイト</li><li>よく寄せられる質問</li></ul></li><li>Planner と To Do によるタスク</li><li>Wiki</li></ul> |

## <a name="crisis-communications"></a>Crisis Communications*

危機管理またはインシデント対応チームのコミュニケーションと重大な危機リソースを一元化します。 オンライン会議を使用して、情報フローと状況認識を向上させます。

> [!div class="mx-tdBreakAll"]
> | テンプレートの種類 |TemplateId| このテンプレートに含まれるプロパティ |
> | ------------------ |--|----------------------------------------------------------|
> | Crisis Communications |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent`| チャネル: <ul><li>全般<li>お知らせ</li><li>エグゼクティブ更新プログラム</li><li>計画</li><li>物流</li></ul>アプリ: <ul><li>承認</li><li>問題の報告</li><li>リスト<ul><li>コンテンツ スケジューラ</li><li>プロジェクト計画</li></ul></li><li>OneNote</li><li>Power Automate</li><li>SharePoint ページ<ul><li>サイト</li><li>最新の更新プログラム</li></ul><li>Planner と To Do によるタスク</li></ul>|

## <a name="related-articles"></a>関連記事

- [Teams 管理センターで Teams テンプレートの使用を開始する](get-started-with-teams-templates-in-the-admin-console.md)
- [テンプレートからチームを作成する](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)