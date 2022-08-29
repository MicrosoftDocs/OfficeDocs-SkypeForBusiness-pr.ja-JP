---
title: Teams 管理センターで Praise アプリを管理する
author: LanaChin
ms.author: v-lanachin
manager: samanro
ms.reviewer: rjam
audience: admin
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
description: Microsoft Teams 管理センターで、Praise アプリを管理する方法について説明します。
ms.collection:
- M365-collaboration
- m365-frontline
ms.openlocfilehash: 36f904f40fdb878480addc0d753b4ccb44a3f2d9
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2022
ms.locfileid: "67396688"
---
# <a name="manage-the-praise-app-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターで Praise アプリを管理する

Microsoft Teams の Praise アプリは、ユーザーが組織またはクラスルームのメンバーに感謝を示すのに役立ちます。 「Praise」のバッジは、教育者から現場のワーカーまで、Teams ユーザーが行うさまざまな作業に取り組む取り組みを認識できるように設計されています。 詳細については、「 [人に賛美を送る」を](https://support.microsoft.com/office/send-praise-to-people-50f26b47-565f-40fe-8642-5ca2a5ed261e)参照してください。

この機能にアクセスするには、管理者に Teams ライセンスが必要です。 Teams ライセンスなしでこの機能にアクセスしようとすると、エラー メッセージが表示されます。

> [!NOTE]
> Praise アプリは GCC クラウド環境では使用できますが、GCC High または DoD では使用できません。

## <a name="enable-or-disable-praise-in-your-organization"></a>組織で Praise を有効または無効にする

組織内のすべての Teams ユーザーに対して、既定で評価が有効になっています。 組織レベルでアプリをオフまたはオンにするには、Microsoft Teams 管理センターの [[アプリを管理]](manage-apps.md) ページで行います。

:::image type="content" source="media/manage-praise-app-admin-center.png" alt-text="Teams 管理センターの [認定アプリの詳細] ページのスクリーンショット。[状態] トグルが表示されています。":::

1. Microsoft Teams 管理センターの左側のウィンドウで、**[Teams アプリ]** > **[アプリの管理]** の順に移動します。
2. アプリの一覧で、Praise アプリを検索して選択し、状態トグルを **[ブロック**] または [**許可****]** に切り替えます。

この設定は、Teams のViva インサイト アプリの Praise アプリと Praise 機能の両方に影響を与える点に注意してください。

[状態] を [ブロック] に設定した場合、Teams の場合、数分以内に Praise アプリがブロックされます。 ただし、Viva インサイトでの評価は、ブロックされるまでに 7 ~ 9 日かかる場合があります。

## <a name="enable-or-disable-praise-for-specific-users-in-your-organization"></a>組織内の特定のユーザーに対して Praise を有効または無効にする

組織内の特定のユーザーによる Praise の使用を許可またはブロックするには、[ [アプリの管理](manage-apps.md) ] ページで組織で Praise が有効になっていることを確認します。 次に、カスタム アプリのアクセス許可ポリシーを作成し、それらのユーザーに割り当てます。 詳細については、「[Teams のアプリのアクセス許可ポリシーを管理する](teams-app-permission-policies.md)」を参照してください。

## <a name="badges"></a>バッジ

ここでは、Praise のバッジの既定のセットを示します。 組織内の Teams ユーザーは、これらのバッジを使用して、同僚が自分の仕事を超えて行ったと認識できます。

:::image type="content" source="media/default-set-praise.png" alt-text="既定のバッジ セット内のバッジの画像。":::

> [!NOTE]
> 2022 年 2 月以降、ユーザーは既定のバッジのみを送受信できます。 カスタム バッジは使用できなくなり、カスタム バッジのオプションは Teams 管理センターから削除されました。

## <a name="related-articles"></a>関連記事

[Microsoft Teams 管理センターで、Teams アプリの組織向けアプリを管理します。](manage-apps.md)
