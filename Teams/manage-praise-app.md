---
title: Teams管理センターで称賛 アプリを管理する
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.reviewer: rjam
audience: admin
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
description: Microsoft Teams管理センターで称賛 アプリを管理する方法について説明します。
ms.openlocfilehash: ff9985025146136ae78d8e822dd5b61903443605
ms.sourcegitcommit: 73df40ce6fbd1d305fd381140f293a2feb0d27bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2022
ms.locfileid: "65359777"
---
# <a name="manage-the-praise-app-in-the-microsoft-teams-admin-center"></a>Microsoft Teams管理センターで称賛 アプリを管理する

Microsoft Teamsの称賛 アプリは、ユーザーが組織またはクラスルームのメンバーに感謝を示すのに役立ちます。 称賛のバッジは、教育者から現場のワーカーまで、Teamsユーザーが行うさまざまな作業に取り組む作業を認識するのに役立ちます。 詳細については、「[称賛をユーザーに送信する」を](https://support.microsoft.com/office/send-praise-to-people-50f26b47-565f-40fe-8642-5ca2a5ed261e)参照してください。

この機能にアクセスするには、管理者にTeamsライセンスが必要です。 Teams ライセンスなしでこの機能にアクセスしようとすると、エラー メッセージが表示されます。

> [!NOTE]
> 称賛 アプリは、GCC クラウド環境では使用できますが、GCC High または DoD では使用できません。

## <a name="enable-or-disable-praise-in-your-organization"></a>組織内の称賛を有効または無効にする

称賛は、組織内のすべてのTeams ユーザーに対して既定で有効になっています。 組織レベルでアプリをオフまたはオンにするには、Microsoft Teams 管理センターの [[アプリを管理]](manage-apps.md) ページで行います。

:::image type="content" source="media/manage-praise-app-admin-center.png" alt-text="Teams管理センターの [称賛 アプリの詳細] ページのスクリーンショット。[状態] トグルが表示されています。":::

1. Microsoft Teams管理センターの左側のウィンドウで、**Teams** **appsManage アプリ** > に移動します。
2. アプリの一覧で、称賛 アプリを検索して選択し、状態トグルを **[ブロック**] または [**許可****]** に切り替えます。

この設定は、称賛 アプリとTeamsのViva インサイト アプリの称賛機能の両方に影響します。

[状態] を [ブロック] に設定すると、称賛 アプリは数分以内にTeamsブロックされます。 ただし、Viva インサイトでの評価は、ブロックされるまでに 7 ~ 9 日かかる場合があります。

## <a name="enable-or-disable-praise-for-specific-users-in-your-organization"></a>組織内の特定のユーザーの称賛を有効または無効にする

組織内の特定のユーザーによる称賛の使用を許可またはブロックするには、[[アプリの管理](manage-apps.md)] ページで組織の称賛が有効になっていることを確認します。 次に、カスタム アプリのアクセス許可ポリシーを作成し、それらのユーザーに割り当てます。 詳細については、「[Teams のアプリのアクセス許可ポリシーを管理する](teams-app-permission-policies.md)」を参照してください。

## <a name="badges"></a>バッジ

称賛のバッジの既定のセットを次に示します。 組織内のユーザー Teams、これらのバッジを使用して、同僚が自分の仕事を上回っていることを認識できます。

:::image type="content" source="media/default-set-praise.png" alt-text="既定のバッジ セット内のバッジの画像。":::

> [!NOTE]
> 2022 年 2 月以降、ユーザーは既定のバッジのみを送受信できます。 カスタム バッジは使用できなくなり、カスタム バッジのオプションはTeams管理センターから削除されました。

## <a name="related-articles"></a>関連記事

[Microsoft Teams 管理センターで、Teams アプリの組織向けアプリを管理します。](manage-apps.md)
