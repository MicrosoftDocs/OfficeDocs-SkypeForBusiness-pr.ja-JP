---
title: 通話の共有およびグループ通話ピックアップ
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 02/19/2019
ms.reviewer: jenstr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.users.voice.groupcallpickup.tooltip
- ms.teamsadmincenter.users.voice.callorderanddelay.tooltip
- Phone System
- seo-marvel-mar2020
description: Microsoft Teams の通話共有とグループ通話ピックアップを使用すると、ユーザーは、ユーザーが利用できないときに通話をキャプチャできるように、着信通話を同僚と共有できます。
ms.openlocfilehash: 420378ce6d75523bf51b18c17e733d13a76ad877
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2022
ms.locfileid: "68613849"
---
# <a name="call-sharing-and-group-call-pickup"></a>通話の共有およびグループ通話ピックアップ

Microsoft Teams の通話共有機能とグループ通話ピックアップ機能を使用すると、ユーザーは、ユーザーが利用できない間に発生した通話に同僚が応答できるように、着信通話を同僚と共有できます。

グループ通話ピックアップは、他の形式の通話共有よりも受信者に対して中断が少ないため、ユーザーは着信共有通話の通知方法を構成でき、応答するかどうかを決定できます。 通話グループのメンバーに着信呼び出しに関する通知を受け取る順序は、同時または順序で指定できます (メンバー数は 5 以下)。

> [!IMPORTANT]
> ユーザー、通話グループの所有者、および通話グループのメンバーは、Teams のみ展開モードである必要があります。 Teams 展開モードの詳細については、「[Microsoft Teams について理解し、共存と相互運用性をSkype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)する」を参照してください。

## <a name="license-required"></a>必要なライセンス

通話共有とグループ通話ピックアップを設定して使用するには、ユーザーにMicrosoft Teams 電話システム ライセンスを割り当てる必要があります。 ライセンス モデルの詳細については、 [電話システム](/MicrosoftTeams/here-s-what-you-get-with-phone-system)に関するページを参照してください。

## <a name="limitations"></a>制限事項

ユーザーは、1 つの呼び出しグループの所有者に限られます。 構成された各呼び出しグループには、最大 25 人のユーザーまたは 32,768 文字を指定できます。 ユーザーは、最大 25 個の呼び出しグループのメンバーにすることができます。

モバイル デバイスは、バナーと着信音に設定されている場合にのみ通知を受け取ります。

## <a name="enable-the-use-of-group-call-pickup"></a>グループ通話ピックアップの使用を有効にする

通話グループを有効にするには、ユーザーの **TeamsCallingPolicy AllowCallGroups** 設定を構成します。 Teams 管理センターまたは PowerShell を使用できます。 有効にすると、ユーザーは Teams クライアントで通話グループを構成できます。 

重要: ユーザーの通話グループを無効にする場合は、不適切な通話ルーティングを回避するために、Teams 管理センターのユーザーの通話グループ関係をクリーンアップする必要があります。 

## <a name="use-teams-admin-center"></a>Teams 管理センターを使用する

Teams 管理センターを使用してユーザーのグループ通話ピックアップを構成するには、「 [ユーザーの通話設定を構成する](/MicrosoftTeams/user-call-settings)」を参照してください。

## <a name="use-powershell"></a>PowerShell を使用する

ユーザーの呼び出しグループを構成するには、次の Teams PowerShell モジュール コマンドレットを使用します。

- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings)

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings)

### <a name="examples"></a>例

次の例では、メンバー user2@contoso.com と user3@contoso.com を使用して user1@contoso.com の呼び出しグループを作成し、user1@contoso.com の呼び出しグループに即時の通話転送を設定します。

```powershell
$cgm = @("sip:user2@contoso.com","sip:user3@contoso.com")
Set-CsUserCallingSettings -Identity user1@contoso.com -CallGroupOrder InOrder -CallGroupTargets $cgm
Set-CsUserCallingSettings -Identity user1@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType Group
```

次の例では、user1@contoso.com の呼び出しグループを更新して user5@contoso.com を追加し、user6@contoso.com を削除する方法を示します。

```powershell
$ucs = Get-CsUserCallingSettings -Identity user1@contoso.com
$cgt = {$ucs.CallGroupTargets}.Invoke()
$cgt.Add("sip:user5@contoso.com")
$cgt.Remove("sip:user6@contoso.com")
Set-CsUserCallingSettings -Identity user1@contoso.com -CallGroupOrder $ucs.CallGroupOrder -CallGroupTargets $cgt
```

## <a name="more-information"></a>詳細情報

[Teams での通話転送と同時呼び出し](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)

[ポリシーを呼び出す Teams](/MicrosoftTeams/teams-calling-policy)

[New-CsTeamsCallingPolicy](/powershell/module/skype/new-csteamscallingpolicy)

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)
