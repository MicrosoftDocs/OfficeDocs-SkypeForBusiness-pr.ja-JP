---
title: ダイレクト ルーティングの呼び出しルーティング ポリシーを管理する
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: filippse
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
ms.localizationpriority: medium
search.appverid: MET150
description: ダイレクト ルーティングの呼び出しルーティング ポリシーを作成および管理するMicrosoft Teams説明します。
ms.openlocfilehash: 348eef9e33dba4f33868c94d72e21289b1a87690
ms.sourcegitcommit: 79dfda39db208cf943d0f7b4906883bb9d034281
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2022
ms.locfileid: "62457397"
---
# <a name="manage-call-routing-policies-for-direct-routing"></a>ダイレクト ルーティングの呼び出しルーティング ポリシーを管理する

組織に直接ルーティングを展開[](direct-routing-landing-page.md)している場合は、Teams ユーザーがオンプレミスのテレフォニー インフラストラクチャを使用して公衆交換電話網 (PSTN) を受信および発信するために、通話ルーティング ポリシーを使用します。

通話ルーティング ポリシー (音声ルーティング ポリシーとも呼ばれる) は、PSTN 使用レコードのコンテナーです。 音声ルーティング ポリシーを作成および管理するには、Microsoft Teams 管理センターで **VoiceVoice**  >  ルーティング ポリシーに移動するか、Windows PowerShell を使用します。

グローバル (組織全体の既定) ポリシーを使用ことも、カスタム ポリシーを作成して割り当てることもできます。 カスタム ポリシーを作成して割り当てない限り、ユーザーは自動的にグローバル ポリシーを取得します。 グローバル ポリシーの設定は編集できますが、名前の変更や削除はできないので、ご安心ください。

ユーザーに音声ルーティング ポリシーを割り当てると、ユーザーが PSTN 通話を行えなTeams。 また、ユーザーがダイレクト ルーティングを有効にし、その他の構成手順を完了する必要があります。 詳細については、「ダイレクト ルーティングの [構成」を参照してください](direct-routing-configure.md)。

## <a name="create-a-custom-call-routing-policy"></a>カスタム通話ルーティング ポリシーを作成する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. 管理センターの左側のナビゲーションMicrosoft Teams **VoiceVoice** ルーティング ポリシー **に** > 移動し、[追加] をクリック **します**。<br>

2. ポリシーの名前と説明を入力します。

3. [ **PSTN 利用状況レコード] で**、[PSTN 使用量の **追加] をクリック** し、追加するレコードを選択します。 新しい PSTN 使用レコードを作成する必要がある場合は、[追加] をクリック **します**。

4. 複数の PSTN 使用レコードを追加した場合は、必要な順序で配置します。
5. 完了したら、[適用] を **クリックします**。

6. **[保存]** をクリックします。

### <a name="using-powershell"></a>PowerShell の使用

[「New-CsOnlineVoiceRoutingPolicy」を参照してください](/powershell/module/skype/new-csonlinevoiceroutingpolicy)。

## <a name="edit-a-call-routing-policy"></a>通話ルーティング ポリシーを編集する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

グローバル ポリシー、または作成したカスタム ポリシーを編集できます。

1. 管理センターの左側のナビゲーションMicrosoft Teams **VoiceVoice** >  ルーティング ポリシーに移動します。

2. ポリシー名の左側をクリックしてポリシーを選び、**[編集]** をクリックします。

3. [ **PSTN 使用レコードの追加/** 削除] をクリックし、必要な変更を加え、[保存] をクリック **します**。

### <a name="using-powershell"></a>PowerShell の使用

[「Set-CsOnlineVoiceRoutingPolicy」を参照してください](/powershell/module/skype/set-csonlinevoiceroutingpolicy)。

## <a name="assign-a-custom-call-routing-policy-to-users"></a>カスタム通話ルーティング ポリシーをユーザーに割り当てる

[!INCLUDE [assign-policy](includes/assign-policy.md)]

「 [Grant-CsOnlineVoiceRoutingPolicy」も参照してください](/powershell/module/skype/grant-csonlinevoiceroutingpolicy)。

## <a name="related-topics"></a>関連項目

[Teams での PowerShell の概要](teams-powershell-overview.md)

[ダイレクト ルーティングの呼び出しルーティングを構成する](direct-routing-voice-routing.md)

[ダイレクト ルーティングの場所に基づくルーティングを有効にする](location-based-routing-enable.md)

[ Teams でユーザーにポリシーを割り当てる](policy-assignment-overview.md)