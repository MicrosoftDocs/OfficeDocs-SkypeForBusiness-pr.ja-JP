---
title: 会議のユーザーに対して会議のダイヤルアウト確認を設定Microsoft Teams
author: HowlinWolf-92
ms.author: v-mahoffman
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 通話相手が通話に応答できない場合にボイスメール システムが会議に接続できないのを防ぐために、Teams を設定してダイヤルアウト確認を要求する方法について学習します。
ms.localizationpriority: medium
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: ae670cec7adcca3dada49a3dcda0ae11f3d1b7b7
ms.sourcegitcommit: 70bba31b0ca4615a3c6a90f42d3568450ea51b82
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/07/2021
ms.locfileid: "61327255"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a>会議のユーザーに対して会議のダイヤルアウト確認を設定Microsoft Teams

会議のダイヤルアウトと通話は、参加者を招待して会議に参加したり、既存の参加者が従来の電話または携帯電話を使って会議に参加したりするための便利な方法です。 ただし、通話相手が通話に応答できず、ボイスメール システムによって通話に応答すると、ボイスメール システムは会議に接続されます。 参加者は、会議から削除されるまで聞き取りを行います。

会議のダイヤルアウトが電話番号に送信され、通話相手が通話に応答できないときにボイスメール システムが会議に接続されるのを防ぐために、Teams を設定して、通話相手に会議に参加するための確認を要求できます。 通話相手が通話に応答できない場合、ボイスメール システムによって通話に応答した場合、ボイスメール システムは会議に参加するための確認を提供しないので、会議に接続されません。

この機能が有効になっている場合、ダイヤルアウトまたは通話を受け取ったユーザーは、従来の電話または携帯電話で 1 を押するか、"問題ありません" と言って会議に参加する必要があります。

組織内のすべての会議でこの機能を有効にするには ```EnableDialOutJoinConfirmation``` [、Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) コマンドレットの パラメーターを に設定します ```true``` 。 このパラメーターを設定するには、次のコマンドを実行します。

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a>関連トピック

- [ユーザーの [電話する] 機能をセットアップする](set-up-the-call-me-feature-for-your-users.md)
- [Teams での PowerShell の概要](teams-powershell-overview.md)
