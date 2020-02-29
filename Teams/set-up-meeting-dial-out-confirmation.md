---
title: 会議のダイヤルアウトを設定する (Microsoft Teams でユーザーの確認を行う)
author: LanaChin
ms.author: v-lanac
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 着信者が電話に応答できないときにボイスメールシステムが会議に接続できないようにするために、ダイヤルアウトの確認を要求するようにチームを設定する方法について説明します。
localization_priority: Normal
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0a7d36d499ff7466fc1e0441bfd37bd7e6f863ae
ms.sourcegitcommit: 35de08b532eb7cf58c3221210c2b3b52f8aa047e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "42339475"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a>Microsoft Teams でユーザーに対して会議のダイヤルアウトの確認を設定する

会議のダイヤルアウトと通話の呼び出しは、会議に参加するために参加者を招待し、既存の参加者が従来の電話や携帯電話を使って会議に参加するために、非常に便利な方法です。 ただし、通話相手が通話に応答できないときに、通話がボイスメールシステムによって応答された場合、ボイスメールシステムは会議に接続され、参加者は会議から削除されるまで聞くことができます。

会議のダイヤルアウトが電話番号に送信され、通話相手が通話に応答できない場合にボイスメールシステムが会議に接続できないようにするには、チームが会議に参加するために、呼び出されたユーザーからの確認を要求するように設定します。 通話に応答できないという相手がボイスメールシステムによって応答した場合、ボイスメールシステムは会議に接続されません。

この機能が有効になっていると、ダイヤルアウトまたは着信の呼び出しを受けるユーザーは、従来の電話または携帯電話で1を押すことによって、会議に参加していることを確認する必要があります。

組織内のすべての会議に対してこの機能を```EnableDialOutJoinConfirmation```有効にするには、 [-](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps)コマンド```true```レットのパラメーターをに設定します。 これを行うには、次のコマンドを実行します。

```
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a>関連項目

- [ユーザーの [電話する] 機能をセットアップする](set-up-the-call-me-feature-for-your-users.md)
- [Teams での PowerShell の概要](teams-powershell-overview.md)