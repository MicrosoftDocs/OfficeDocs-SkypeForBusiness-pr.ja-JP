---
title: 会議のユーザーに対して会議のダイヤルアウト確認を設定Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
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
ms.openlocfilehash: 32cdc63f2b129e7d925fed46a8b89ac90944926e
ms.sourcegitcommit: bb302109886a4b853a8e493fb0ffafad4bc4f86b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/20/2022
ms.locfileid: "62085236"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a>会議のユーザーに対して会議のダイヤルアウト確認を設定Microsoft Teams

会議のダイヤルアウトと通話は、参加者を招待して会議に参加したり、既存の参加者が従来の電話または携帯電話を使って会議に参加したりするための便利な方法です。 ただし、通話相手が通話に応答できず、ボイスメール システムによって通話に応答すると、ボイスメール システムは会議に接続されます。 参加者は、会議から削除されるまで聞き取りを行います。

会議のダイヤルアウトが電話番号に送信され、通話相手が通話に応答できないときにボイスメール システムが会議に接続されるのを防ぐために、Teams を設定して、通話相手に会議に参加するための確認を要求できます。 通話相手が通話に応答できない場合、ボイスメール システムによって通話に応答した場合、ボイスメール システムは会議に参加するための確認を提供しないので、会議に接続されません。

この機能が有効になっている場合、ダイヤルアウトまたは通話を受け取ったユーザーは、従来の電話または携帯電話で 1 を押するか、"問題ありません" と言って会議に参加する必要があります。 この確認により、ユーザーのボイスメール メッセージが会議に参加しなきます。

組織内のすべての会議でこの機能を有効にするには ```EnableDialOutJoinConfirmation``` [、Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) コマンドレットの パラメーターを に設定します ```true``` 。 このパラメーターを設定するには、次のコマンドを実行します。

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a>関連項目

- [ユーザーの [電話する] 機能をセットアップする](set-up-the-call-me-feature-for-your-users.md)
- [Teams での PowerShell の概要](teams-powershell-overview.md)
