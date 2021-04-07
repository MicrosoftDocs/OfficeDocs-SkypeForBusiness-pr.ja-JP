---
title: 標準以外のユーザーの Teams アプリの動作
author: cichur
ms.author: v-cichur
ms.reviewer: joglocke
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Microsoft Teams のアプリが標準以外のユーザーに対してどのように動作するのかについて説明します。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6fc4f4f53262127355afa573b0fc2abec6b05e64
ms.sourcegitcommit: 3861d661d32f507bd8479509ed09b1cfcf0b214f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/07/2021
ms.locfileid: "51607519"
---
# <a name="microsoft-teams-apps-behavior-for-non-standard-users"></a>標準以外のユーザーに対する Microsoft Teams アプリの動作

この記事では、ゲスト、外部 (フェデレーション)、匿名ユーザーが Teams のコンテキストで存在する場合の Teams のアプリの動作について説明します。

- ゲスト **ユーザーとは** 、組織の従業員、学生、またはメンバーではないユーザーです。 ゲストは組織内での学校アカウントまたは職場アカウントを持ちません。

- 外部 **(フェデレーション) ユーザー** は別のドメインに属し、組織のチームまたはチーム リソースにアクセス権はありません。

>[!Note]
> ゲストと外部ユーザーの詳細な比較については、「他の組織のユーザーとの通信」を [参照してください](./communicate-with-users-from-other-organizations.md)。

- 匿名 **ユーザーは、** ユーザーがリンクを介して会議に参加した Teams 会議の概念です。 ユーザーが Microsoft または組織のアカウントでログインしていない。

## <a name="guest-user-access"></a>ゲスト ユーザー アクセス

### <a name="install-update-and-delete-for-guest-users"></a>ゲスト ユーザーのインストール、更新、削除

ゲストは、チャット、チャネル、会議などの共有コンテキストにアプリをインストール、更新、または削除できません。 メッセージ拡張機能と直接リンクを使用して、アプリを個人用範囲にインストール、更新、または削除できます。 ゲストは Teams アプリ ストアにアクセスできます。

### <a name="usage-behavior-and-policy-for-guest-users"></a>ゲスト ユーザーの使用状況の動作とポリシー

ネイティブ ユーザーがアプリをインストールした場合、ゲストはアプリを使用できます。

ボットはゲスト ユーザーに積極的にメッセージを送信できますが、ゲストはボットとやり取りを行う必要があります。 ゲストはボットに 1 対 1 でメッセージを送信したり、ボットに @メンションしたり、ボットと通信するアダプティブ カードを操作したりできない。

ゲストは、任意のアプリのホスト テナントに設定されたグローバルおよび組織全体のアクセス許可ポリシーに従います。 つまり、ホスト組織全体でアプリがブロックされている場合、ゲストはアプリを使用できません。

セットアップ ポリシーはゲスト ユーザーには適用されません。 つまり、既定のポリシーからピン留めされた管理者アプリは、ゲスト ユーザーに影響を与えはありません。

## <a name="external-federated-user-access"></a>外部 (フェデレーション) ユーザー アクセス

### <a name="install-update-and-delete-for-external-users"></a>外部ユーザーのインストール、更新、削除

外部ユーザーは、個人、チャット、チャネル、会議などのコンテキストでアプリをインストール、更新、または削除できません。 Teams アプリ ストアにアクセスできない。

### <a name="usage-behavior-and-policy-for-external-users"></a>外部ユーザーの使用状況の動作とポリシー

外部ユーザーは Teams アプリを使用できません。また、外部ユーザーがネイティブ ユーザーとのコンテキストに追加された場合、すべてのユーザー (ネイティブユーザーと外部ユーザー) はアプリを使用できなくなりました。

外部ユーザーは Teams アプリを使用できないので、アプリ ポリシーの影響を受け取らない。

## <a name="anonymous-user-in-meetings-access"></a>会議アクセスの匿名ユーザー

### <a name="install-update-and-delete-for-anonymous-users"></a>匿名ユーザーのインストール、更新、削除

匿名ユーザーは、会議でアプリをインストール、更新、または削除できない。

### <a name="usage-behavior-and-policy-for-anonymous-users"></a>匿名ユーザーの使用状況の動作とポリシー

匿名ユーザーは、会議でアプリを直接使用することはできません。 匿名ユーザーが存在する場合、ネイティブ ユーザーは会議アプリを引き続き使用できます。 アプリがチャットでアダプティブ カードを送信する場合、匿名ユーザーはカードを操作できます。詳細については、「匿名ユーザーに会議への参加を許可する」を [参照してください](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams#allow-anonymous-users-to-join-meetings)。

匿名ユーザーは、ユーザー レベルのグローバル既定のアクセス許可ポリシーを継承します。 ユーザー レベルのアクセス許可ポリシーでアプリが有効になっている場合は、Teams 会議でアプリを操作できます。 匿名ユーザーは、会議で既に利用可能であり、これらのアプリを取得および管理できないアプリのみを操作できます。
