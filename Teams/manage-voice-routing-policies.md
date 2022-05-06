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
description: Microsoft Teams ダイレクト ルーティングの通話ルーティング ポリシーを作成および管理する方法について説明します。
ms.openlocfilehash: 348eef9e33dba4f33868c94d72e21289b1a87690
ms.sourcegitcommit: 79dfda39db208cf943d0f7b4906883bb9d034281
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2022
ms.locfileid: "62457397"
---
# <a name="manage-call-routing-policies-for-direct-routing"></a>ダイレクト ルーティングの呼び出しルーティング ポリシーを管理する

組織内に[ダイレクト ルーティング](direct-routing-landing-page.md)を展開した場合は、通話ルーティング ポリシーを使用して、Teams ユーザーがオンプレミステレフォニー インフラストラクチャを使用して公衆交換電話網 (PSTN) に電話を受信して発信できるようにします。

通話ルーティング ポリシー (音声ルーティング ポリシーとも呼ばれます) は、PSTN 使用法レコードのコンテナーです。 音声ルーティング ポリシーを作成および管理するには、Microsoft Teams管理センターの **VoiceVoice** >  **ルーティング ポリシー** に移動するか、Windows PowerShellを使用します。

グローバル (組織全体の既定) ポリシーを使用ことも、カスタム ポリシーを作成して割り当てることもできます。 カスタム ポリシーを作成して割り当てる場合を除き、ユーザーはグローバル ポリシーを自動的に取得します。 グローバル ポリシーの設定は編集できますが、名前の変更や削除はできません。

音声ルーティング ポリシーをユーザーに割り当てると、Teamsで PSTN 通話を行うことはできません。 また、ユーザーがダイレクト ルーティングを有効にし、他の構成手順を完了する必要もあります。 詳細については、「 [ダイレクト ルーティングの構成」を](direct-routing-configure.md)参照してください。

## <a name="create-a-custom-call-routing-policy"></a>カスタム通話ルーティング ポリシーを作成する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. Microsoft Teams管理センターの左側のナビゲーションで、**VoiceVoice** >  **ルーティング ポリシー** に移動し、[**追加**] をクリックします。<br>

2. ポリシーの名前と説明を入力します。

3. [ **PSTN 使用法レコード**] で、[ **PSTN 使用法の追加**] をクリックし、追加するレコードを選択します。 新しい PSTN 使用法レコードを作成する必要がある場合は、[ **追加**] をクリックします。

4. 複数の PSTN 使用法レコードを追加した場合は、必要な順序で並べ替えます。
5. 完了したら、[ **適用**] をクリックします。

6. **[保存]** をクリックします。

### <a name="using-powershell"></a>PowerShell の使用

[New-CsOnlineVoiceRoutingPolicy を](/powershell/module/skype/new-csonlinevoiceroutingpolicy)参照してください。

## <a name="edit-a-call-routing-policy"></a>通話ルーティング ポリシーを編集する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

グローバル ポリシー、または作成したカスタム ポリシーを編集できます。

1. Microsoft Teams管理センターの左側のナビゲーションで、**VoiceVoice** >  **ルーティング ポリシーに移動します**。

2. ポリシー名の左側をクリックしてポリシーを選び、**[編集]** をクリックします。

3. [ **PSTN 使用法レコードの追加と削除]** をクリックし、必要な変更を加えて、[保存] をクリック **します**。

### <a name="using-powershell"></a>PowerShell の使用

[Set-CsOnlineVoiceRoutingPolicy に関するページを参照](/powershell/module/skype/set-csonlinevoiceroutingpolicy)してください。

## <a name="assign-a-custom-call-routing-policy-to-users"></a>ユーザーにカスタム通話ルーティング ポリシーを割り当てる

[!INCLUDE [assign-policy](includes/assign-policy.md)]

[Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy) も参照してください。

## <a name="related-topics"></a>関連項目

[Teams での PowerShell の概要](teams-powershell-overview.md)

[ダイレクト ルーティングの呼び出しルーティングを構成する](direct-routing-voice-routing.md)

[ダイレクト ルーティングの場所に基づくルーティングを有効にする](location-based-routing-enable.md)

[ Teams でユーザーにポリシーを割り当てる](policy-assignment-overview.md)