---
title: 音声ルーティング ポリシーを管理する Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 音声ルーティング ポリシーを作成して管理する方法については、Microsoft Teams。
ms.openlocfilehash: ac856ef05d425208af43307ebe12ff0c4776ca51
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101073"
---
# <a name="manage-voice-routing-policies-in-microsoft-teams"></a>音声ルーティング ポリシーを管理する Microsoft Teams

組織内に[電話システム](direct-routing-landing-page.md)ダイレクト ルーティングを展開している場合は、音声ルーティング ポリシーを使用して、Teams と Skype for Business Online のユーザーがオンプレミスのテレフォニー インフラストラクチャを使用して公衆交換電話網 (PSTN) を受信および発信できます。

音声ルーティング ポリシーは、PSTN 使用レコードのコンテナーです。 音声ルーティング ポリシーを作成および管理するには、Microsoft Teams管理センターで音声ルーティング ポリシーに移動するか  >  、Windows PowerShell。

グローバル (組織全体の既定) ポリシーを使用ことも、カスタム ポリシーを作成して割り当てることもできます。 カスタム ポリシーを作成して割り当てない限り、ユーザーは自動的にグローバル ポリシーを取得します。 グローバル ポリシーの設定は編集できますが、名前の変更や削除はできないので、ご安心ください。

ユーザーに音声ルーティング ポリシーを割り当てると、ユーザーが PSTN 通話を行えなTeams。 また、ユーザーが直接ルーティングを実行電話システム、その他の構成手順を完了する必要があります。 詳細については、「ダイレクト ルーティングの [構成」を参照してください](direct-routing-configure.md)。

## <a name="create-a-custom-voice-routing-policy"></a>カスタム音声ルーティング ポリシーを作成する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. 管理センターの左側のナビゲーションMicrosoft Teams Voice Voiceルーティング ポリシー] に移動し、[  >  追加] を **クリックします**。<br>
    ![管理センターの [音声ルーティング ポリシーの追加] ページMicrosoft Teamsスクリーンショット](media/manage-voice-routing-policies.png) 
2. ポリシーの名前と説明を入力します。
3. [PSTN **利用状況レコード] で**、[PSTN 使用量の追加] **をクリック** し、追加するレコードを選択します。 新しい PSTN 使用レコードを作成する必要がある場合は、[追加] を **クリックします**。
4. 複数の PSTN 使用レコードを追加した場合は、必要な順序で配置します。
5. 完了したら、[適用] を **クリックします**。
6. **[保存]** をクリックします。

### <a name="using-powershell"></a>PowerShell の使用

[New-CsOnlineVoiceRoutingPolicy を参照してください](/powershell/module/skype/new-csonlinevoiceroutingpolicy)。

## <a name="edit-a-voice-routing-policy"></a>音声ルーティング ポリシーを編集する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

グローバル ポリシー、または作成したカスタム ポリシーを編集できます。

1. 管理センターの左側のナビゲーションMicrosoft Teams音声ルーティング ポリシー に  >  **移動します**。
2. ポリシー名の左側をクリックしてポリシーを選び、**[編集]** をクリックします。
3. [PSTN **使用レコードの追加/** 削除] をクリックし、必要な変更を加え、[保存] を **クリックします**。

### <a name="using-powershell"></a>PowerShell の使用

[「Set-CsOnlineVoiceRoutingPolicy」を参照してください](/powershell/module/skype/set-csonlinevoiceroutingpolicy)。

## <a name="assign-a-custom-voice-routing-policy-to-users"></a>カスタム音声ルーティング ポリシーをユーザーに割り当てる

[!INCLUDE [assign-policy](includes/assign-policy.md)]

[Grant-CsOnlineVoiceRoutingPolicy も参照してください](/powershell/module/skype/grant-csonlinevoiceroutingpolicy)。

## <a name="related-topics"></a>関連項目

[Teams での PowerShell の概要](teams-powershell-overview.md)

[ダイレクト ルーティングの音声ルーティングを構成する](direct-routing-voice-routing.md)

[ダイレクト ルーティングの場所に基づくルーティングを有効にする](location-based-routing-enable.md)

[ Teams でユーザーにポリシーを割り当てる](assign-policies.md)