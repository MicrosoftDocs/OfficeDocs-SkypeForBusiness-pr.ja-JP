---
title: Teams テンプレートを使用して新しいチームを作成する
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: aaglick
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Teams テンプレートを使用して、事前にインストールされているテンプレートを使用してさまざまなトピックでコラボレーション スペースを作成する方法について説明します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 5a43a34ac130f4b5b168d46fa2a69476c42abd7b
ms.sourcegitcommit: cd16ff6007e0a798493e2fa469c6681993380420
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2020
ms.locfileid: "46860798"
---
# <a name="get-started-with-teams-templates-in-the-teams-admin-console"></a>Teams 管理コンソールで Teams テンプレートの使用を開始する

[!INCLUDE [template](includes/preview-feature.md)]

**EDU お客様向けのカスタム テンプレートはまだサポートされていません。**

> [!NOTE]
> 現在、Teams テンプレートではプライベート チャネルの作成はサポートされていません。 プライベート チャネルの作成は、テンプレート定義に含まれません。

チーム テンプレートは、ビジネス ニーズまたはプロジェクトに合わせて設計されたチームの構造の定義です。 あらかじめ作成されたテンプレートを使用するか、独自のテンプレートを作成します。 Teams テンプレートを使用すると、さまざまなトピックのチャネルを使用して、リッチ コラボレーション スペースをすばやく作成して、ミッションのクリティカル コンテンツとサービスをプルに取り入れることができます。 Teams テンプレートは、組織内で一からの一つのチームを簡単に作成できる、定義済みのチーム構造を提供します。 現在、Teams のテンプレートからチームを作成したり [、Microsoft](get-started-with-teams-templates.md)Graph を使用したりすることができます。

この記事では、テンプレートで定義できるプロパティ、基本テンプレートの種類、およびいくつかのサンプル要求を使用してテンプレートからチームを作成する方法について説明します。

この記事は、次のユーザーを目的としています。

- 組織内で複数のチームを計画、展開、管理する必要がある<br>
- プログラムを使用して、定義済みのチャネルとアプリでチームを作成する開発者

## <a name="teams-template-capabilities"></a>Teams のテンプレート機能

チームのほとんどのプロパティはテンプレートでサポートされています。 ただし、現時的にはサポートされていないプロパティと機能はいくつかあります。 次の表は、Teams テンプレートに含まれる機能と含まれない機能の概要を示しています。

| **Teams テンプレートでサポートされるチームのプロパティ** | **Teams テンプレートでまだサポートされていないチームプロパティ** |
| ------------------------------------------------ | -------------------------------------------------------- |
| 基本テンプレートの種類 | チーム メンバーシップ |
| チーム名 | チームの画像 |
| チームの説明 | チャンネル設定 |
| チームの公開 (パブリックまたはプライベート) | コネクタ |
| チームの設定 (メンバー、ゲスト、@メンションなど) | ファイルとコンテンツ |
| チャネルをお気に入りに自動お気に入りに追加する | |
| インストールされているアプリ | |
| ピンプされたタブ | |

> [!NOTE]
> Microsoft Teams の今後のリリースでテンプレート機能を追加する予定ですので、サポートされているプロパティの最新情報を確認してください。

## <a name="what-are-base-template-types"></a>基本テンプレートの種類

基本テンプレートは、特定の組織に対して Microsoft で作成した特別なテンプレートです。 これらの基本テンプレートには、アプリ ストアで使用できる適切なアプリが含まれている場合が通常です。

基本テンプレートの種類が定義されたら、これらの特別なテンプレートを拡張または上書きして、指定する追加のプロパティを指定できます。 ただし、基本テンプレートの種類には、上書きできないプロパティが含まれているものもありました。

> [!NOTE]
> Microsoft Teams で事前に定義されたベース テンプレートは、重複できますが編集はできません。

| 基本テンプレートの種類 | この基本テンプレートに付くプロパティ |
| ------------------ |----------------------------------------------------- |
| 365 Officeドプット |  チャネル: <ul><li>一般</li> <li>お知らせ</li> <li>チャンパン</li> <li>チーム フォーム</li></ul> アプリ: <ul><li>Wiki</li>  <li>カレンダー</li> |
| プロジェクトを管理する | チャネル: <ul><li>一般</li> <li>お知らせ</li> <li>リソース</li> <li>計画</li></ul> アプリ:<ul><li>Wiki</li><li>OneNote</li></ul> |
| イベントを管理する | チャネル: <ul><li>一般</li> <li>お知らせ</li> <li>予算</li> <li>コンテンツ</li><li>物流</li> <li>計画</li> <li> マーケティングと PR</li></ul> アプリ:<ul><li>Wiki</li><li>Web サイト</li> <li>YouTube</li> <li>プランナー</li> <li>OneNote</li></ul> |
|従業員のオンボード | チャネル: <ul><li>一般</li> <li>お知らせ</li> <li>従業員のチャット</li> <li>トレーニング</li></ul>アプリ:<ul><li>Wiki</li><li>コミュニティ</li>|</ul>
|ヘルプ デスクを整理する| チャネル:<ul><li>一般</li><li>お知らせ</li><li>FAQ</li></ul>アプリ:<ul><li>Wiki</li><li>OneNote</li></ul> |
| ペンキャラクターで共同作業する | チャネル:<ul><li>一般</li><li>お知らせ</li><li>ハードディル</li><li>丸</li><li>スタッフ</li><li>トレーニング</li></ul> アプリ: <ul><li>Wiki</li>|
| グローバル制限またはイベントで共同作業する |チャネル: <ul><li>一般<li>お知らせ</li><li><c0><c1>ニュース</c1></c</li><li>ビジネスの常性</li><li>リモート作業中</li><li>内部コミュニティ</li><li>外部のコミュニティ</li><li>顧客の複雑な説明</li><li>クウド</li><li>エグゼクティブの更新プログラム</li></ul>アプリ: <ul><li>[声書]</li><li>Wiki</li><li>Web サイト</li></ul>|
|ブランク ブランチ内で共同作業する |チャネル: <ul><li>一般<li>お知らせ</li><li>ハードディル</li><li>顧客の会議</li><li>コーチ</li><li>スキル開発</li><li>ローン処理</li><li>顧客の複雑な説明</li><li>クウド</li><li>おかげでとう</li><li>コンプライアンス</li></ul>|
|インシデント応答を整合する |チャネル: <ul><li>一般<li>お知らせ</li><li>物流</li><li>計画</li><li>回復</li><li>アーゲット</li></ul> アプリ: <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>プランナー</li></ul>|
|病院 |チャネル: <ul><li>一般<li>お知らせ</li><li>コンプライアンス</li><li>Custodial/li><li>人事</li><li>Pharmacy</li></ul> アプリ: <ul><li>Wiki</li></ul>|
|ストアを整理する |チャネル: <ul><li>一般<li>Shift handoff</li><li>学習</li></ul> アプリ: <ul><li>Wiki</li></ul>|
|品質と安全性 |チャネル: <ul><li>一般<li>お知らせ</li><li>行 1</li><li>行 2</li><li>行 3</li><li>安全性</li><li>トレーニング</li><li>メンテナンス</li><li>おかげでとう</li></ul> アプリ: <ul><li>Wiki</li></ul>|
|リテール - マネージャーの共同作業 |チャネル: <ul><li>一般<li>操作</li><li>学習</li></ul> アプリ: <ul><li>Wiki</li></ul>|
|||

## <a name="template-size-limits"></a>テンプレートのサイズ制限

テンプレートは、特定のチャンネル、タブ、アプリの数に制限されます。

 > [!Note]
 > テンプレートから作成された後に、その他のチャネル、タブ、アプリをチームに追加できます。

|機能 | 制限|
|-|-|
|テンプレートごとのチャネル | 15 |
|テンプレートのチャンネルごとのタブ | 20 |
|テンプレートあたりのアプリ | 50|
|||

詳細 [については、Teams の制限と指定](limits-specifications-teams.md) を参照してください。

## <a name="related-topics"></a>関連トピック

- [カスタム チーム テンプレートを作成する](create-a-team-template.md)
- [既存のチーム テンプレートからチーム テンプレートを作成する](create-template-from-existing-template.md)
- [既存のチームからテンプレートを作成する](create-template-from-existing-team.md)
