---
title: Microsoft Teams でユーザーの会議ダイヤルアウト確認を設定する
author: MicrosoftHeidi
ms.author: heidip
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 通話者が通話に応答できない場合にボイスメール システムが会議に接続できないようにするために、ダイヤルアウトの確認を要求するように Teams を設定する方法について説明します。
ms.localizationpriority: medium
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: a74a02b8d6c0a11202676144ce2dba91618118c9
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271562"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a>Microsoft Teams でユーザーの会議ダイヤルアウト確認を設定する

会議のダイヤルアウトと通話は、参加者を会議に参加するように招待し、既存の参加者が従来または携帯電話を使用して会議に参加するための便利な方法です。 ただし、着信者が通話に応答できず、通話にボイスメール システムによって応答されると、ボイスメール システムは会議に接続されます。 参加者は、会議から削除されるまで聞くことができます。

会議のダイヤルアウトが電話番号に送信され、通話者が通話に応答できない場合にボイスメール システムが会議に接続できないようにするには、Teams を設定して、通話者が会議に参加するための確認を要求できます。 着信者が通話に応答できず、通話にボイスメール システムによって応答された場合、ボイスメール システムは会議に接続されません。参加の確認は提供されないためです。

この機能が有効になっている場合、ダイヤルアウトまたは通話を受け取るユーザーは、従来または携帯電話で 1 キーを押すか、"Ok" と言って会議に参加することを確認する必要があります。 この確認により、ユーザーのボイスメール メッセージが会議に参加できなくなります。

組織内のすべての会議でこの機能を有効にするには、```EnableDialOutJoinConfirmation```[Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) コマンドレットのパラメーターを```true```設定します。 このパラメーターを設定するには、次のコマンドを実行します。

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a>関連項目

- [ユーザーの [電話する] 機能をセットアップする](set-up-the-call-me-feature-for-your-users.md)
- [Teams での PowerShell の概要](teams-powershell-overview.md)
