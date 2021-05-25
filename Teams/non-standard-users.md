---
title: 非標準ユーザーに対する Teams アプリの動作
author: cichur
ms.author: v-cichur
ms.reviewer: joglocke
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Microsoft Teams のアプリが非標準ユーザーに対してどのように動作するかを学びます。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: c27a73928e0740eb325c269fd5ac625fa4c43086
ms.sourcegitcommit: 330e60ff3549cd5cff5b52ad95dc4259e4e8de13
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2021
ms.locfileid: "52628926"
---
# <a name="microsoft-teams-apps-behavior-for-non-standard-users"></a>非標準ユーザーに対する Microsoft Teams アプリの動作

この記事では、ゲスト、外部 (フェデレーション)、および匿名ユーザーが Teams コンテキストに存在する場合に、Teams 内のアプリがどのように動作するかについて説明します。

- **ゲスト ユーザー** とは、従業員、学生、または組織のメンバーではない人のことです。 ゲストは組織内での学校アカウントまたは職場アカウントを持ちません。

- **外部 (フェデレーション) ユーザー** は別のドメインに属しており、組織のチームやチーム リソースにアクセスできません。

  > [!Note]
  > ゲスト ユーザーと外部ユーザーの詳細な比較については、[「他の組織のユーザーとの通信」を参照してください](./communicate-with-users-from-other-organizations.md)。

- **匿名ユーザー** は、ユーザーがリンクを介して会議に参加している Teams 会議の概念です。 ユーザーが Microsoft または組織のアカウントでログインしていません。

## <a name="guest-users"></a>ゲスト ユーザー

### <a name="install-update-and-delete-for-guest-users"></a>ゲスト ユーザーのインストール、更新、削除

ゲストは、チャット、チャネル、会議などの共有コンテキストにアプリをインストール、更新、または削除できませんが、メッセージ拡張機能と直接リンクを使用して個人スコープにアクセスできます。 ゲストは Teams デスクトップ アプリケーションから Teams アプリ ストアにアクセスできますが、直接リンクを使用してアクセスできます。

### <a name="usage-behavior-and-policy-for-guest-users"></a>ゲスト ユーザーの使用行動とポリシー 

アプリがネイティブ ユーザーによってインストールされた場合、ゲストはアプリを使用できます。

#### <a name="bots-installed-to-a-channel"></a>チャネルにインストールされたボット

ボットはゲスト ユーザーに積極的にメッセージを送信できますが、ゲストはボットと対話できません。 ゲストは、ボットに対して 1 対 1 でメッセージを送信したり、ボットにメンションしたり、ボットと通信するアダプティブ カードを操作したりできない。

#### <a name="personal-bots-installed-with-policies"></a>ポリシーと一緒にインストールされた個人用ボット

- ゲストは、すべてのアプリのホスト テナントに設定されたグローバルおよび組織全体のアクセス許可ポリシーを順守します。 ホスト組織全体でアプリがブロックされている場合、ゲストもアプリを使用できません。
- グローバルな既定のアプリ セットアップ ポリシーに含まれるボットも、ゲスト用にインストールされます。
- ボットがインストールされた後、ボットはゲストと事前に通信し、ゲストはボットと通信できます。
- グローバルな既定のアプリセットアップ ポリシーからゲストを削除できない。
- ゲストがボットにアクセスしないようにするには、さらに多くのアプリ セットアップ ポリシーを作成し、それらを内部ユーザーに割り当て、カスタム ポリシーを使用してボットをインストールします。

## <a name="external-federated-users"></a>外部 (フェデレーション) ユーザー

### <a name="install-update-and-delete-for-external-users"></a>外部ユーザーのインストール、更新、および削除

外部ユーザーは、個人、チャット、チャネル、会議などのコンテキストにアプリをインストール、更新、または削除することはできません。 外部ユーザーは Teams アプリ ストアにアクセスできません。

### <a name="usage-behavior-and-policy-for-external-users"></a>外部ユーザーの使用行動とポリシー

- 外部ユーザーは Teams アプリを使用できません。また、外部ユーザーがネイティブ ユーザーとのコンテキストに追加されると、ネイティブ ユーザーと外部ユーザーのすべてのユーザーがアプリを使用できなくなります。
- 外部ユーザーは Teams アプリを使用できないため、アプリ ポリシーの影響を受けません。

## <a name="anonymous-users"></a>匿名ユーザー

### <a name="install-update-and-delete-for-anonymous-users"></a>匿名ユーザーのインストール、更新、削除

匿名ユーザーは、会議でアプリをインストール、更新、または削除することはできません。

### <a name="usage-behavior-and-policy-for-anonymous-users"></a>匿名ユーザーの使用行動とポリシー

匿名ユーザーは、会議でアプリを直接使用することはできません。 匿名ユーザーがいる場合、ネイティブ ユーザーは引き続き会議アプリを使用できます。  アプリがチャットでアダプティブ カードを送信した場合、匿名ユーザーはカードを操作できます。 詳細については、「匿名ユーザーに [会議への参加を許可する」を参照してください](/meeting-settings-in-teams#allow-anonymous-users-to-join-meetings)。

匿名ユーザーは、ユーザー レベルのグローバル既定権限ポリシーを継承します。 ユーザー レベルのアクセス許可ポリシーでアプリが有効になっている場合は、Teams 会議でアプリを操作できます。 匿名ユーザーは、会議ですでに利用可能なアプリのみを操作でき、これらのアプリを取得または管理できないことに注意してください。
