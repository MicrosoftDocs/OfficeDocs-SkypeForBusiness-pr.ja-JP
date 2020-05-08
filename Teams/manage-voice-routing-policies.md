---
title: Microsoft Teams でボイスルーティングポリシーを管理する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords: ''
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams でボイスルーティングポリシーを作成して管理する方法について説明します。
ms.openlocfilehash: 7fa2530e170d398598e56d4b4f846cc316871b16
ms.sourcegitcommit: 6e24ea8aa9cccf8a1a964c8ed414ef5c7de3dc17
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "44160979"
---
# <a name="manage-voice-routing-policies-in-microsoft-teams"></a>Microsoft Teams でボイスルーティングポリシーを管理する

組織で[電話システムのダイレクトルーティング](direct-routing-landing-page.md)を展開した場合は、音声ルーティングポリシーを使用して、チームと Skype For business Online ユーザーがオンプレミスのテレフォニーインフラストラクチャを使って公衆交換電話網 (PSTN) に電話をかけたり、通話を発信したりできるようにします。

ボイスルーティングポリシーは、PSTN 使用状況レコードのコンテナーです。 音声ルーティングのポリシーを作成して管理するには、Microsoft Teams 管理センターまたは Windows PowerShell を使用して**音声** > **音声ルーティングポリシー**に移動します。

グローバル (組織全体の既定) ポリシーを使用するか、カスタムポリシーを作成して割り当てることができます。 カスタムポリシーを作成して割り当てる場合を除き、ユーザーはグローバルポリシーを自動的に取得します。 グローバルポリシーの設定は編集できますが、名前の変更や削除はできないことに注意してください。

ユーザーにボイスルーティングポリシーを割り当てることで、チームで PSTN 通話を発信することはできないことを知っておくことが重要です。 また、ユーザーが電話システムのダイレクトルーティングを有効にし、その他の構成手順を完了する必要があります。 詳細については、「[直接ルーティングを構成](direct-routing-configure.md)する」を参照してください。

## <a name="create-a-custom-voice-routing-policy"></a>カスタムボイスルーティングポリシーを作成する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. Microsoft Teams 管理センターの左のナビゲーションで、[**音声** > **音声ルーティングポリシー**] に移動し、[**追加**] をクリックします。<br>
    ![Microsoft Teams 管理センターの [ボイスルーティングポリシーの追加] ページのスクリーンショット](media/manage-voice-routing-policies.png) 
2. ポリシーの名前と説明を入力します。
3. [ **Pstn 使用状況レコード**] の [ **pstn 使用量の追加**] をクリックし、追加するレコードを選択します。 新しい PSTN 使用状況レコードを作成する必要がある場合は、[**追加**] をクリックします。
4. 複数の PSTN 利用状況レコードを追加した場合は、目的の順序に並べ替えます。
5. 完了したら、[**適用**] をクリックします。
6. **[保存]** をクリックします。

### <a name="using-powershell"></a>PowerShell を使用する場合

「[新規-CsOnlineVoiceRoutingPolicy」を](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy)参照してください。

## <a name="edit-a-voice-routing-policy"></a>音声ルーティングポリシーを編集する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

グローバル ポリシー、または作成したカスタム ポリシーを編集できます。

1. Microsoft Teams 管理センターの左のナビゲーションで、[**音声** > **音声ルーティングポリシー**] に移動します。
2. ポリシー名の左側をクリックしてポリシーを選び、**[編集]** をクリックします。
3. [ **PSTN 使用状況レコードの追加/削除**] をクリックし、必要な変更を加えて、[**保存**] をクリックします。

### <a name="using-powershell"></a>PowerShell を使用する場合

「 [Set-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy)」を参照してください。

## <a name="assign-a-custom-voice-routing-policy-to-users"></a>カスタムボイスルーティングポリシーをユーザーに割り当てる

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動してユーザーをクリックします。
2. **[ポリシー]** をクリックし、**[割り当てられたポリシー]** の横にある **[編集]** をクリックします。
3. [**音声ルーティングポリシー**] で、割り当てるポリシーを選択し、[**保存**] をクリックします。

一度に複数のユーザーにカスタムのチーム ポリシーを割り当てる方法については、「[一括で Teams のユーザー設定を編集する](edit-user-settings-in-bulk.md)」を参照してください。

または、次の操作も実行できます。

1. Microsoft Teams 管理センターの左のナビゲーションで、[**音声** > **音声ルーティングポリシー**] に移動します。
2. ポリシー名の左側をクリックしてポリシーを選びます。
3. [**ユーザーを管理**] を選択します。
4. [**ユーザーを管理**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] を選びます。 追加するユーザーごとに、この手順を繰り返します。
5. ユーザーの追加が完了したら、[**保存**] をクリックします。

### <a name="using-powershell"></a>PowerShell を使用する場合

「 [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy)」を参照してください。

## <a name="related-topics"></a>関連項目

- [Teams での PowerShell の概要](teams-powershell-overview.md)
- [直接ルーティング用のボイスルーティングを構成する](direct-routing-voice-routing.md)
- [ダイレクト ルーティングの場所に基づくルーティングを有効にする](location-based-routing-enable.md)
