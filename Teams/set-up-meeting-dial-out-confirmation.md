---
title: Microsoft Teams でユーザーの会議のダイヤルアウト確認を設定する
author: cichur
ms.author: v-cichur
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 通話相手が通話に応答できない場合にボイスメール システムが会議に接続できないのを防ぐために、ダイヤルアウトの確認を要求する Teams を設定する方法について学習します。
localization_priority: Normal
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 37d68eb90e42b57ff76d352ea2c856e6904a9308
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806147"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a>Microsoft Teams でユーザーの会議のダイヤルアウト確認を設定する

会議のダイヤルアウトと通話は、参加者を会議に参加したり、既存の参加者が従来の携帯電話を使って会議に参加したりするために非常に便利な方法です。 ただし、呼び出されたユーザーが通話に応答できず、通話がボイスメール システムによって応答されると、ボイスメール システムが会議に接続され、会議から削除されるまで、参加者はそれを聞く事ができます。

会議のダイヤルアウトが電話番号に送信され、通話相手が通話に応答できない場合にボイスメール システムが会議に接続されるのを防ぐには、Teams を設定して、通話相手に会議への参加の確認を要求することができます。 通話相手が通話に応答できない場合、通話がボイスメール システムによって応答された場合、ボイスメール システムは参加の確認を提供しないので、会議に接続されません。

この機能を有効にすると、ダイヤルアウトまたは電話で通話を受けるユーザーは、従来の携帯電話または携帯電話で 1 を押して会議に参加する必要があります。

組織内のすべての会議でこの機能を有効にするには ```EnableDialOutJoinConfirmation``` [、Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) コマンドレットのパラメーターを次に設定します ```true``` 。 これを行うには、次のコマンドを実行します。

```
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a>関連項目

- [ユーザーの [電話する] 機能をセットアップする](set-up-the-call-me-feature-for-your-users.md)
- [Teams での PowerShell の概要](teams-powershell-overview.md)