---
title: ユーザーの種類に基づいてアプリの動作をTeamsする
author: guptaashish
ms.author: guptaashish
ms.reviewer: joglocke
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Microsoft Teams内のアプリがさまざまな種類のユーザーに対して動作する方法について説明します。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: a407564986d5e4c758d39e2684e5c068539bb9dc
ms.sourcegitcommit: 1d990582e2deb5f55ba9adada3e17377f792a141
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2022
ms.locfileid: "64922468"
---
# <a name="microsoft-teams-apps-behavior-based-on-types-of-users"></a>ユーザーの種類に基づいてアプリの動作をMicrosoft Teamsする

Teams アプリは、ゲスト、外部 (フェデレーション)、匿名ユーザーがTeams コンテキストに存在する場合に動作します。

* **ゲスト ユーザー** とは、従業員、学生、または組織のメンバーではない人のことです。 ゲストは組織内での学校アカウントまたは職場アカウントを持ちません。

* **外部 (フェデレーション) ユーザー** は別のドメインに属しており、組織のチームやチーム リソースにアクセスできません。

  > [!Note]
  > ゲスト ユーザーと外部ユーザーの詳細な比較については、[「他の組織のユーザーとの通信」を参照してください](./communicate-with-users-from-other-organizations.md)。

* **匿名ユーザー** は、ユーザーがリンクを介して会議に参加している Teams 会議の概念です。 ユーザーが Microsoft または組織のアカウントでログインしていません。

## <a name="guest-users"></a>ゲスト ユーザー

### <a name="install-update-and-delete-for-guest-users"></a>ゲスト ユーザーのインストール、更新、削除

ゲストは、チャット、チャネル、会議などの共有コンテキストにアプリをインストール、更新、または削除することはできませんが、メッセージ拡張機能と直接リンクを使用して、個人用スコープにアクセスできます。 ゲストは、Teams デスクトップ アプリケーションからTeams アプリ ストアにアクセスすることはできませんが、直接リンクを使用してアクセスできます。

### <a name="usage-behavior-and-policy-for-guest-users"></a>ゲスト ユーザーの使用行動とポリシー

アプリがネイティブ ユーザーによってインストールされた場合、ゲストはアプリを使用できます。

#### <a name="bots-installed-to-a-channel"></a>チャネルにインストールされたボット

ゲスト ユーザーはボットに言及し、アダプティブ カードを操作できます。

#### <a name="personal-bots-installed-with-policies"></a>ポリシーと共にインストールされた個人用ボット

* ゲストは、任意のアプリのホスト テナントに設定されたグローバルおよび組織全体のアクセス許可ポリシーに準拠します。 ホスト組織全体でアプリがブロックされている場合、ゲストもアプリを使用できません。
* グローバル既定のアプリセットアップ ポリシーに含まれるボットもゲストにインストールされます。
* ボットがインストールされると、ボットはゲストと事前に通信でき、ゲストはボットとやり取りできます。
* グローバル既定のアプリセットアップ ポリシーからゲストを削除することはできません。
* ゲストがボットにアクセスするのを防ぐために、より多くのアプリセットアップ ポリシーを作成し、それらを内部ユーザーに割り当て、カスタム ポリシーを使用してボットをインストールできます。

## <a name="external-federated-users"></a>外部 (フェデレーション) ユーザー

### <a name="install-update-and-delete-for-external-users"></a>外部ユーザーのインストール、更新、および削除

外部ユーザーは、個人、チャット、チャネル、会議などのコンテキストにアプリをインストール、更新、または削除することはできません。 ホスティング組織のTeamsアプリ ストアにはアクセスできません。

### <a name="usage-behavior-and-policy-for-external-users"></a>外部ユーザーの使用行動とポリシー

* 他の組織のユーザーは、ホスティング組織のグローバル (組織全体の既定) ポリシーに準拠しています
* ホスティング組織内のユーザーは、他の組織のユーザーとの会議チャットでアプリを追加できます。 他の組織のユーザーは、会議チャットにアプリを追加することはできませんが、チャットに追加されると、ボット、タブ、メッセージ拡張機能を操作できます。
* ボットが会議チャットにインストールされると、そのチャット内の他の組織のユーザーと積極的に通信でき、それらのユーザーはボットと通信できます。
* ホスティング組織のデータ ポリシーと、そのユーザーの組織によって共有されているサードパーティアプリのデータ共有プラクティスが適用されます。

## <a name="anonymous-users"></a>匿名ユーザー

### <a name="install-update-and-delete-for-anonymous-users"></a>匿名ユーザーのインストール、更新、削除

匿名ユーザーは、会議でアプリをインストール、更新、または削除することはできません。

### <a name="usage-behavior-and-policy-for-anonymous-users"></a>匿名ユーザーの使用行動とポリシー

匿名ユーザーは、会議でアプリを直接使用することはできません。 匿名ユーザーは、ユーザー レベルのグローバル既定のアクセス許可ポリシーを継承します。 アプリがチャットでアダプティブ カードを送信した場合、匿名ユーザーはカードと対話できます。 このようなユーザーは、ユーザー レベルのアクセス許可ポリシーでアプリが有効な場合、Teams会議でアプリを操作できます。

匿名ユーザーは、会議で既に利用可能なアプリとのみ対話でき、そのようなアプリを取得および管理することはできません。 ネイティブ ユーザーは、匿名ユーザーが会議に出席している場合でも、会議アプリを引き続き使用できます。

## <a name="see-also"></a>関連項目

* [匿名ユーザーが会議に参加できるようにします](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings)。
* [Microsoft Teamsでアプリセットアップ ポリシーを管理します](teams-app-setup-policies.md)。
