---
title: Teams 管理センターで Praise アプリを管理する
author: LanaChin
ms.author: v-lanachin
manager: samanro
ms.reviewer: rjam
audience: admin
ms.topic: how-to
ms.service: msteams
ms.localizationpriority: medium
description: Microsoft Teams 管理センターで Praise アプリを管理する方法について説明します。
ms.collection:
- M365-collaboration
- m365-frontline
- tier2
- highpri
ms.openlocfilehash: 31a185239607c2458636dd6cadc83b7462135112
ms.sourcegitcommit: ff161779577ce9cc892f1b6b8861ad49ff4c3ca3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2022
ms.locfileid: "69131176"
---
# <a name="manage-the-praise-app-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターで Praise アプリを管理する

Microsoft Teams の Praise アプリは、ユーザーが組織または教室のメンバーに感謝の気持ちを示すのに役立ちます。 賞賛のバッジは、教育者から現場担当者まで、Teams ユーザーが行う幅広い作業に対する取り組みを認識できるように設計されています。 詳細については、「 [ユーザーに賞賛を送信する」を](https://support.microsoft.com/office/send-praise-to-people-50f26b47-565f-40fe-8642-5ca2a5ed261e)参照してください。

管理者は、この機能にアクセスするために Teams ライセンスを持っている必要があります。 Teams ライセンスなしでこの機能にアクセスしようとすると、エラー メッセージが表示されます。

> [!NOTE]
> Praise アプリは GCC クラウド環境で使用できますが、GCC High または DoD には使用できません。

## <a name="enable-or-disable-praise-in-your-organization"></a>組織内で賞賛を有効または無効にする

賞賛は、組織内のすべての Teams ユーザーに対して既定で有効になっています。 組織レベルでアプリをオフまたはオンにするには、Microsoft Teams 管理センターの [[アプリを管理]](manage-apps.md) ページで行います。

:::image type="content" source="media/manage-praise-app-admin-center.png" alt-text="Teams 管理センターの [アプリの詳細を褒める] ページのスクリーンショット。[状態] トグルが表示されています。":::

1. Microsoft Teams 管理センターの左側のウィンドウで、**[Teams アプリ]** > **[アプリの管理]** の順に移動します。
2. アプリの一覧で、賞賛アプリを検索して選択し、[ **状態]** トグルを **[ブロック** ] または [ **許可]** に切り替えます。

この設定は、Teams のViva インサイト アプリの賞賛アプリと称賛機能の両方に影響します。

[状態] を [ブロック] に設定した場合、Teams の評価アプリは数分以内にブロックされます。 ただし、Viva インサイトでの賞賛には、ブロックされるまでに 7 日から 9 日かかる場合があります。

## <a name="enable-or-disable-praise-for-specific-users-in-your-organization"></a>組織内の特定のユーザーに対して評価を有効または無効にする

組織内の特定のユーザーが賞賛を使用することを許可またはブロックするには、[ [アプリの管理](manage-apps.md) ] ページで組織に対して [称賛] がオンになっていることを確認します。 次に、アプリのアクセス許可のカスタム ポリシーを作成し、それらのユーザーに割り当てます。 詳細については、「[Teams のアプリのアクセス許可ポリシーを管理する](teams-app-permission-policies.md)」を参照してください。

## <a name="badges"></a>バッジ

[賞賛] のバッジの既定のセットを次に示します。 組織内の Teams ユーザーは、これらのバッジを使用して、同僚が自分の仕事を超えて行くことを認識できます。

:::image type="content" source="media/default-set-praise.png" alt-text="既定のバッジ セット内のバッジの画像。":::

> [!NOTE]
> 2022 年 2 月以降、ユーザーは既定のバッジのみを送受信できます。 カスタム バッジは使用できなくなり、カスタム バッジのオプションは Teams 管理センターから削除されました。

## <a name="related-articles"></a>関連記事

[Microsoft Teams 管理センターで、Teams アプリの組織向けアプリを管理します。](manage-apps.md)
