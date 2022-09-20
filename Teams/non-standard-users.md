---
title: ユーザーの種類に基づく Teams アプリの動作
author: ashishguptaiitb
ms.author: guptaashish
ms.reviewer: joglocke
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.subservice: teams-apps
search.appverid: MET150
description: ゲスト、フェデレーション ユーザー、匿名ユーザーに対して Microsoft Teams のアプリの動作が異なる方法について説明します。
ms.localizationpriority: high
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4e39aac93c7311785c0f740eded8a0021e321c43
ms.sourcegitcommit: ceba5fd8f098c8d0eafaffe5c5301c845a3ae7ab
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2022
ms.locfileid: "67837497"
---
# <a name="behavior-of-microsoft-teams-apps-based-on-types-of-in-meeting-users"></a>会議中のユーザーの種類に基づく Microsoft Teams アプリの動作

Teams アプリは、ゲスト、外部 (フェデレーション)、匿名ユーザーが Teams コンテキストに存在する場合に動作します。

* **ゲスト ユーザー** とは、従業員、学生、または組織のメンバーではない人のことです。 ゲストは組織内での学校アカウントまたは職場アカウントを持ちません。

* **外部 (フェデレーション) ユーザー** は別のドメインのユーザーであり、組織の Teams リソースにアクセスできません。

  > [!Note]
  > ゲスト ユーザーと外部ユーザーの比較の詳細については、「 [他の組織のユーザーとの通信](./communicate-with-users-from-other-organizations.md)」を参照してください。

* **匿名ユーザー** とは、リンクを介して会議に参加するユーザーです。 ユーザーは自分の Microsoft アカウントまたは組織のアカウントでログインしていません。

## <a name="guests"></a>ゲスト

### <a name="install-update-and-delete-for-guests"></a>ゲストのインストール、更新、削除

ゲストは、チャット、チャネル、会議などの共有コンテキストにアプリをインストール、更新、または削除することはできません。 ゲストは、メッセージ拡張機能と直接リンクを使用して、個人用スコープでこれを行うことができます。 ゲストは Teams デスクトップ アプリから Teams アプリ ストアにアクセスできませんが、直接リンクを使用してストアにアクセスできます。

### <a name="usage-behavior-and-policy-for-guests"></a>ゲストの使用動作とポリシー

アプリがネイティブ ユーザーによってインストールされた場合、ゲストはアプリを使用できます。

#### <a name="bots-installed-to-a-channel"></a>チャネルにインストールされたボット

ゲストはボットに言及し、アダプティブ カードを操作できます。

#### <a name="personal-bots-installed-with-policies"></a>ポリシーと共にインストールされた個人用ボット

* どのアプリでも、ゲストはホスト組織に設定されたグローバルおよび組織全体のアクセス許可ポリシーに準拠します。 ホスト組織全体でアプリがブロックされている場合、ゲストもアプリを使用できません。
* グローバル既定のアプリセットアップ ポリシーに含まれるボットもゲストにインストールされます。
* ボットがインストールされると、ボットはゲストと事前に通信でき、ゲストはボットとやり取りできます。
* グローバル既定のアプリセットアップ ポリシーからゲストを削除することはできません。
* ゲストがボットにアクセスするのを防ぐために、より多くのアプリセットアップ ポリシーを作成し、それらを内部ユーザーに割り当て、カスタム ポリシーを使用してボットをインストールできます。

## <a name="federated-users"></a>フェデレーション ユーザー

### <a name="install-update-and-delete-for-federated-users"></a>フェデレーション ユーザーのインストール、更新、削除

フェデレーション ユーザーは、個人用、チャット、チャネル、会議などの任意のコンテキストにアプリをインストール、更新、または削除することはできません。 ホスト組織の Teams アプリ ストアにはアクセスできません。

### <a name="usage-behavior-and-policy-for-federated-users"></a>フェデレーション ユーザーの使用動作とポリシー

* 他の組織からのPeopleは、ホスティング組織のグローバル (組織全体の既定) ポリシーに準拠しています
* ホスティング組織内のユーザーは、他の組織のユーザーとの会議チャットでアプリを追加できます。 他の組織のPeopleは、会議チャットにアプリを追加することはできませんが、チャットに追加されるとボット、タブ、メッセージ拡張機能と対話できます。
* ボットが会議チャットにインストールされると、そのチャット内の他の組織のユーザーと積極的に通信でき、それらのユーザーはボットと通信できます。
* ホスティング組織のデータ ポリシーが適用されます。
* そのユーザーの組織によって共有されているサード パーティ製アプリのデータ共有プラクティスが適用されます。

## <a name="anonymous-users"></a>匿名ユーザー

### <a name="install-update-and-delete-for-anonymous-users"></a>匿名ユーザーのインストール、更新、削除

匿名ユーザーは、会議でアプリをインストール、更新、または削除することはできません。

### <a name="usage-behavior-and-policy-for-anonymous-users"></a>匿名ユーザーの使用行動とポリシー

匿名ユーザーは、会議でアプリを直接使用することはできません。 アプリがチャットでアダプティブ カードを送信した場合、匿名ユーザーはカードと対話できます。 ユーザー レベルのアクセス許可ポリシーでアプリが有効な場合、このようなユーザーは Teams 会議でアプリを操作できます。 匿名ユーザーは、ユーザー レベルのグローバル既定のアクセス許可ポリシーを継承します。

匿名ユーザーは、会議で既に利用可能ですが、そのようなアプリを取得および管理できないアプリとのみ対話できます。 ネイティブ ユーザーは、匿名ユーザーが会議に出席している場合でも、会議アプリを引き続き使用できます。

## <a name="see-also"></a>関連項目

* [匿名ユーザーが会議に参加できるようにします](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings)。
* [Microsoft Teams でアプリセットアップ ポリシーを管理します](teams-app-setup-policies.md)。
