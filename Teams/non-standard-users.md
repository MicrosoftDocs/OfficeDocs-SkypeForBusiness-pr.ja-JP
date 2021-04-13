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
ms.openlocfilehash: fb4b5dfebabfcd0bc86006d93272c3901e7dcfc7
ms.sourcegitcommit: b52b6aba289396c4fc10dd856817137eb1bc1f67
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/07/2021
ms.locfileid: "51617850"
---
# <a name="microsoft-teams-apps-behavior-for-non-standard-users"></a>非標準ユーザーに対する Microsoft Teams アプリの動作

この記事では、ゲスト、外部 (フェデレーション)、および匿名ユーザーが Teams コンテキストに存在する場合に、Teams 内のアプリがどのように動作するかについて説明します。

- **ゲスト ユーザー** とは、従業員、学生、または組織のメンバーではない人のことです。 ゲストは組織内での学校アカウントまたは職場アカウントを持ちません。

- **外部 (フェデレーション) ユーザー** は別のドメインに属しており、組織のチームやチーム リソースにアクセスできません。

  > [!Note]
  > ゲスト ユーザーと外部ユーザーの詳細な比較については、[「他の組織のユーザーとの通信」を参照してください](./communicate-with-users-from-other-organizations.md)。

- **匿名ユーザー** は、ユーザーがリンクを介して会議に参加している Teams 会議の概念です。 ユーザーが Microsoft または組織のアカウントでログインしていません。

## <a name="guest-user-access"></a>ゲスト ユーザー アクセス

### <a name="install-update-and-delete-for-guest-users"></a>ゲスト ユーザーのインストール、更新、削除

ゲストは、チャット、チャネル、会議などの共有コンテキストにアプリをインストール、更新、または削除することはできません。 メッセージ拡張機能と直接リンクを使用して、個人の範囲に合わせてアプリをインストール、更新、または削除できます。 ゲストは Teams アプリ ストアにアクセスできません。

### <a name="usage-behavior-and-policy-for-guest-users"></a>ゲスト ユーザーの使用行動とポリシー

アプリがネイティブ ユーザーによってインストールされた場合、ゲストはアプリを使用できます。

ボットはゲスト ユーザーに積極的にメッセージを送信できますが、ゲストはボットと対話できません。 ゲストはボットに 1 対 1 のメッセージを送信したり、ボットに @ mention したり、ボットと通信するアダプティブ カードを操作したりすることはできません。

ゲストは、すべてのアプリのホスト テナントに設定されたグローバルおよび組織全体のアクセス許可ポリシーを順守します。 つまり、ホスト組織全体でアプリがブロックされている場合、ゲストもそのアプリを使用できません。

設定ポリシーはゲスト ユーザーには適用されません。 これは、既定のポリシーから管理者が固定したアプリがゲストユーザーに影響を与えないことを意味します。

## <a name="external-federated-user-access"></a>外部 (フェデレーション) ユーザー アクセス

### <a name="install-update-and-delete-for-external-users"></a>外部ユーザーのインストール、更新、および削除

外部ユーザーは、個人、チャット、チャネル、会議などのコンテキストにアプリをインストール、更新、または削除することはできません。 外部ユーザーは Teams アプリ ストアにアクセスできません。

### <a name="usage-behavior-and-policy-for-external-users"></a>外部ユーザーの使用行動とポリシー

外部ユーザーは Teams アプリを使用できません。また、外部ユーザーがネイティブ ユーザーとのコンテキストに追加されると、ネイティブ ユーザーと外部ユーザーのすべてのユーザーがアプリを使用できなくなります。

外部ユーザーは Teams アプリを使用できないため、アプリ ポリシーの影響を受けません。

## <a name="anonymous-user-in-meetings-access"></a>会議アクセスの匿名ユーザー

### <a name="install-update-and-delete-for-anonymous-users"></a>匿名ユーザーのインストール、更新、削除

匿名ユーザーは、会議でアプリをインストール、更新、または削除することはできません。

### <a name="usage-behavior-and-policy-for-anonymous-users"></a>匿名ユーザーの使用行動とポリシー

匿名ユーザーは、会議でアプリを直接使用することはできません。 匿名ユーザーがいる場合、ネイティブ ユーザーは引き続き会議アプリを使用できます。  アプリがチャットでアダプティブ カードを送信する場合、匿名ユーザーはカードを操作できます。詳細については、「[匿名ユーザーに会議への参加を許可する](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams#allow-anonymous-users-to-join-meetings)」を参照してください。

匿名ユーザーは、ユーザー レベルのグローバル既定権限ポリシーを継承します。 ユーザー レベルのアクセス許可ポリシーでアプリが有効になっている場合は、Teams 会議でアプリを操作できます。 匿名ユーザーは、会議ですでに利用可能なアプリのみを操作でき、これらのアプリを取得または管理できないことに注意してください。
