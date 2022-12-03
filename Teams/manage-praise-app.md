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
ms.openlocfilehash: 9b1155560c0f901b88d3983e2ff3738e5ffa6e47
ms.sourcegitcommit: 54c691bd34980a47a5ebf58555529a618a8cada7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2022
ms.locfileid: "69251770"
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

状態を **[ブロック]** に設定した場合、Teams の評価アプリは数分以内にブロックされます。 ただし、Viva インサイトでの賞賛は、ブロックされるまでに 7 日から 9 日かかることがあります。

## <a name="enable-or-disable-praise-for-specific-users-in-your-organization"></a>組織内の特定のユーザーに対して評価を有効または無効にする

組織内の特定のユーザーが賞賛を使用することを許可またはブロックするには、[ [アプリの管理](manage-apps.md) ] ページで組織に対して [称賛] がオンになっていることを確認します。 次に、アプリのアクセス許可のカスタム ポリシーを作成し、それらのユーザーに割り当てます。 詳細については、「[Teams のアプリのアクセス許可ポリシーを管理する](teams-app-permission-policies.md)」を参照してください。

## <a name="composer"></a>作曲 家

組織内の Teams ユーザーは、称賛コンポーザーを使用して、同僚が自分の仕事を超えて行くことを認識できます。 メッセージを作成しながら、**勇気**、**楽観主義**、**親切心**、**クリエイティブ**&mdash;などの14タイトル&mdash;から選んで、同僚の貢献を認めることができます。

:::image type="content" source="media/praise.png" alt-text="賞賛の作曲家のスクリーンショット。":::

## <a name="related-articles"></a>関連記事

[Microsoft Teams 管理センターで、Teams アプリの組織向けアプリを管理します。](manage-apps.md)
