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
description: ゲスト、フェデレーション ユーザー、匿名ユーザーに対する Microsoft Teams のアプリのしくみについて説明します。
ms.localizationpriority: high
ms.date: 09/28/2022
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6fa9b56a17cdba5bfe4b075199a3373470d1630a
ms.sourcegitcommit: d6e180791134426445a35fd485dcca18bde2006b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2022
ms.locfileid: "68494630"
---
# <a name="use-teams-apps-as-an-external-attendees-or-guest"></a>Teams アプリを外部出席者またはゲストとして使用する

Teams アプリを使用すると、組織外のユーザーとのコラボレーションが可能になります。 管理者は、Teams チャット、会議、チャネルにアクセスして組織のユーザーと共同作業できるユーザーを制御します。 詳細については、 [外部出席者とのコラボレーションを許可する方法](manage-external-access.md) と、 [Teams でゲストができること](guest-access.md)について説明します。 この記事では、組織外のユーザーによるアプリの使用について説明します。

次の種類のユーザーは Teams チャットまたは会議に参加でき、許可すると Teams でアプリを使用できます。

* **ゲスト ユーザー** とは、従業員、学生、または組織のメンバーではない人のことです。 ゲストは組織内での学校アカウントまたは職場アカウントを持ちません。

* **外部 (フェデレーション) ユーザー** は別のドメインのユーザーであり、組織の Teams リソースにアクセスできません。

* **匿名ユーザー** とは、リンクを介して会議に参加するユーザーです。 ユーザーは自分の Microsoft アカウントまたは組織のアカウントでログインしていません。

ゲスト ユーザーと外部ユーザーの比較の詳細については、「 [他の組織のユーザーとの通信](communicate-with-users-from-other-organizations.md)」を参照してください。

## <a name="guests"></a>ゲスト

### <a name="install-update-and-delete-apps-for-guests"></a>ゲスト向けのアプリのインストール、更新、削除

ゲストは、チャット、チャネル、会議などの共有コンテキストにアプリをインストール、更新、または削除することはできません。 ゲストは、メッセージ拡張機能と直接リンクを使用して、個人用スコープでこれを行うことができます。 ゲストは Teams デスクトップ アプリから Teams アプリ ストアにアクセスできませんが、直接リンクを使用してストアにアクセスできます。

### <a name="usage-behavior-and-policy-for-guests"></a>ゲストの使用動作とポリシー

組織のユーザーがアプリをインストールした場合、ゲストはアプリを使用できます。

#### <a name="bots-installed-to-a-channel"></a>チャネルにインストールされたボット

ゲストはボットに言及し、アダプティブ カードを操作できます。

#### <a name="personal-bots-installed-with-policies"></a>ポリシーと共にインストールされた個人用ボット

* どのアプリでも、ゲストはホスト組織に設定されたグローバルおよび組織全体のアクセス許可ポリシーに準拠します。 ホスト組織全体でアプリがブロックされている場合、ゲストもアプリを使用できません。
* グローバル既定のアプリセットアップ ポリシーに含まれるボットもゲストにインストールされます。
* ボットがインストールされると、ボットとゲストは相互にプロアクティブに通信できるようになります。
* グローバル既定のアプリセットアップ ポリシーからゲストを削除することはできません。
* ゲストがボットにアクセスするのを防ぐために、より多くのアプリセットアップ ポリシーを作成し、それらを内部ユーザーに割り当て、カスタム ポリシーを使用してボットをインストールできます。

## <a name="federated-users"></a>フェデレーション ユーザー

### <a name="install-update-and-delete-apps-for-federated-users"></a>フェデレーション ユーザー向けのアプリのインストール、更新、削除

フェデレーション ユーザーは、個人用、チャット、チャネル、会議などの任意のコンテキストにアプリをインストール、更新、または削除することはできません。 ホスト組織の Teams アプリ ストアにはアクセスできません。

### <a name="usage-behavior-and-policy-for-federated-users"></a>フェデレーション ユーザーの使用動作とポリシー

* 他の組織からのPeopleは、ホスティング組織のグローバル (組織全体の既定) ポリシーに準拠しています
* ホスティング組織内のユーザーは、他の組織のユーザーとの会議チャットでアプリを追加できます。 他の組織のPeopleは、会議チャットにアプリを追加することはできませんが、チャットに追加されるとボット、タブ、メッセージ拡張機能と対話できます。
* ボットが会議チャットにインストールされると、そのチャット内の他の組織のユーザーと積極的に通信でき、それらのユーザーはボットと通信できます。
* ホスティング組織のデータ ポリシーが適用されます。
* そのユーザーの組織によって共有されているサード パーティ製アプリのデータ共有プラクティスが適用されます。

## <a name="anonymous-users"></a>匿名ユーザー

### <a name="install-update-and-delete-apps-for-anonymous-users"></a>匿名ユーザー向けのアプリのインストール、更新、削除

匿名ユーザーは、会議でアプリをインストール、更新、または削除することはできません。

### <a name="usage-behavior-and-policy-for-anonymous-users"></a>匿名ユーザーの使用行動とポリシー

匿名ユーザーは、会議でアプリを直接使用することはできません。 アプリがチャットでアダプティブ カードを送信した場合、匿名ユーザーはカードと対話できます。 ユーザー レベルのアクセス許可ポリシーでアプリが有効な場合、このようなユーザーは Teams 会議でアプリを操作できます。 匿名ユーザーは、ユーザー レベルのグローバル既定のアクセス許可ポリシーを継承します。

匿名ユーザーは、会議で既に利用可能ですが、そのようなアプリを取得および管理できないアプリとのみ対話できます。 ネイティブ ユーザーは、匿名ユーザーが会議に出席している場合でも、会議アプリを引き続き使用できます。

### <a name="disallow-anonymous-users-to-use-apps-in-meetings"></a>匿名ユーザーが会議でアプリを使用できないようにする

既定では、匿名ユーザーは会議内の既存のアプリと対話できます。 匿名ユーザーがアプリと対話できないようにすることができます。

1. Teams 管理センターにサインインし、会議 **[の設定](https://admin.teams.microsoft.com/meetings/settings)****に** > アクセスします。

1. [ **参加者]** で、[ **匿名ユーザーが会議でアプリを操作できる** ] のトグルを **[オフ]** に変更します。

1. **[保存]** を選択します。

## <a name="related-articles"></a>関連記事

* [匿名ユーザーが会議に参加できるようにします](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings)。
* [Microsoft Teams でアプリセットアップ ポリシーを管理します](teams-app-setup-policies.md)。
* [ゲストおよび外部参加者とのコラボレーションを許可する方法](manage-external-access.md)。
* [Teams でゲストができること](guest-access.md)
