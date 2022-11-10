---
title: さまざまな種類のユーザーによる Teams アプリの可用性と使用
author: ashishguptaiitb
ms.author: guptaashish
ms.reviewer: kojika
manager: prkosh
ms.topic: article
audience: admin
ms.service: msteams
ms.subservice: teams-apps
search.appverid: MET150
description: ゲスト、フェデレーション ユーザー、匿名ユーザー向けの Microsoft Teams のアプリのしくみについて説明します。
ms.localizationpriority: high
ms.date: 09/28/2022
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
ms.openlocfilehash: c618552a574a567a91ddab0e2303fd5f99a2373a
ms.sourcegitcommit: 22f66e314e631b3c9262c5c7dc5664472f42971e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2022
ms.locfileid: "68912606"
---
# <a name="use-of-teams-apps-for-external-attendees-or-guest-from-outside-an-organization"></a>外部出席者または組織外からのゲストに対する Teams アプリの使用

Teams アプリを使用すると、組織外のユーザーとのコラボレーションが可能になります。 管理者は、Teams チャット、会議、チャネルにアクセスして組織のユーザーと共同作業できるユーザーを制御します。 詳細については、 [外部出席者とのコラボレーションを許可する方法](manage-external-access.md) と、 [ゲストが Teams で実行できる操作に関するページを](guest-access.md)参照してください。 この記事では、組織外のユーザーによるアプリの使用に焦点を当てます。

次の種類のユーザーは Teams チャットまたは会議に存在でき、許可した場合は Teams でアプリを使用できます。

* **ゲスト ユーザー** とは、従業員、学生、または組織のメンバーではない人のことです。 ゲストは組織内での学校アカウントまたは職場アカウントを持ちません。

* **外部 (フェデレーション) ユーザー** は別のドメインのユーザーであり、組織の Teams リソースにアクセスできません。

* **匿名ユーザー** は、リンクを介して会議に参加するユーザーです。 ユーザーが自分の Microsoft アカウントまたは組織のアカウントでログインしていません。

ゲスト ユーザーと外部ユーザーの詳細な比較については、「 [他の組織のユーザーとの通信](communicate-with-users-from-other-organizations.md)」を参照してください。

## <a name="guests"></a>ゲスト

### <a name="install-update-and-delete-apps-for-guests"></a>ゲスト用のアプリをインストール、更新、削除する

ゲストは、チャット、チャネル、会議などの共有コンテキストにアプリをインストール、更新、または削除することはできません。 ゲストは、メッセージ拡張機能と直接リンクを使用して、個人用スコープでこれを行うことができます。 ゲストは Teams デスクトップ アプリから Teams アプリ ストアにアクセスできませんが、直接リンクを使用してストアにアクセスできます。

### <a name="usage-behavior-and-policy-for-guests"></a>ゲストの使用動作とポリシー

ゲストは、アプリが組織のユーザーによってインストールされた場合にアプリを使用できます。

#### <a name="bots-installed-to-a-channel"></a>チャネルにインストールされたボット

ゲストはボットに言及し、アダプティブ カードと対話できます。

#### <a name="personal-bots-installed-with-policies"></a>ポリシーを使用してインストールされた個人用ボット

* どのアプリでも、ゲストはホスト組織に対して設定されたグローバルおよび組織全体のアクセス許可ポリシーに従います。 ホスト組織全体に対してアプリがブロックされている場合、ゲストもアプリを使用できません。
* グローバル既定のアプリセットアップ ポリシーに含まれるボットもゲスト用にインストールされます。
* ボットがインストールされると、ボットとゲストは相互に事前に通信できます。
* グローバル既定のアプリセットアップ ポリシーからゲストを削除することはできません。
* ゲストがボットにアクセスできないようにするには、アプリセットアップ ポリシーをさらに作成し、内部ユーザーに割り当て、カスタム ポリシーを使用してボットをインストールします。

## <a name="federated-users"></a>フェデレーション ユーザー

### <a name="install-update-and-delete-apps-for-federated-users"></a>フェデレーション ユーザーのアプリをインストール、更新、削除する

フェデレーション ユーザーは、個人用、チャット、チャネル、会議などのコンテキストにアプリをインストール、更新、または削除することはできません。 ホスティング組織の Teams アプリ ストアにアクセスできません。

### <a name="usage-behavior-and-policy-for-federated-users"></a>フェデレーション ユーザーの使用動作とポリシー

* 他の組織からのPeopleは、ホスティング組織のグローバル (組織全体の既定) ポリシーに準拠しています
* ホスティング組織のユーザーは、他の組織のユーザーと会議チャットにアプリを追加できます。 他の組織からのPeopleは、会議チャットにアプリを追加することはできませんが、チャットに追加されるとボット、タブ、メッセージ拡張機能と対話できます。
* 会議チャットにボットをインストールすると、そのチャット内の他の組織のユーザーとプロアクティブに通信でき、それらのユーザーはボットと通信できます。
* ホスティング組織のデータ ポリシーが適用されます。
* そのユーザーの組織が共有するサード パーティ製アプリのデータ共有プラクティスが適用されます。

## <a name="anonymous-users"></a>匿名ユーザー

### <a name="install-update-and-delete-apps-for-anonymous-users"></a>匿名ユーザーのアプリをインストール、更新、削除する

匿名ユーザーは、会議でアプリをインストール、更新、または削除することはできません。

### <a name="usage-behavior-and-policy-for-anonymous-users"></a>匿名ユーザーの使用行動とポリシー

匿名ユーザーは、会議でアプリを直接使用することはできません。 アプリがチャットでアダプティブ カードを送信した場合、匿名ユーザーはカードと対話できます。 ユーザー レベルのアクセス許可ポリシーでアプリが有効な場合、このようなユーザーは Teams 会議でアプリと対話できます。 匿名ユーザーは、ユーザー レベルのグローバル既定のアクセス許可ポリシーを継承します。

匿名ユーザーは、会議で既に利用できるが、そのようなアプリを取得および管理できないアプリとのみ対話できます。 ネイティブ ユーザーは、匿名ユーザーが会議に出席している場合でも、会議アプリを引き続き使用できます。

### <a name="disallow-anonymous-users-to-use-apps-in-meetings"></a>匿名ユーザーが会議でアプリを使用できないようにする

既定では、匿名ユーザーは会議で既存のアプリと対話できます。 アプリを操作するための匿名ユーザーを禁止できます。

1. Teams 管理センターにサインインし、**会議会議** > の設定にアクセス **[します](https://admin.teams.microsoft.com/meetings/settings)**。

1. [ **参加者]** で、 **匿名ユーザーが会議でアプリと対話できる** トグルを **[オフ]** に変更します。

1. **[保存]** を選択します。

## <a name="related-articles"></a>関連記事

* [匿名ユーザーに会議への参加を許可する](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings)。
* [Microsoft Teams でアプリセットアップ ポリシーを管理](teams-app-setup-policies.md)します。
* [ゲストと外部参加者とのコラボレーションを許可する方法](manage-external-access.md)。
* [ゲストが Teams でできること](guest-access.md)
