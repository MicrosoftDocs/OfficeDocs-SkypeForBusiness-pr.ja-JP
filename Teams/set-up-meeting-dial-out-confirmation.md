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
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a><span data-ttu-id="b63b6-103">Microsoft Teams でユーザーの会議のダイヤルアウト確認を設定する</span><span class="sxs-lookup"><span data-stu-id="b63b6-103">Set up meeting dial-out confirmation for your users in Microsoft Teams</span></span>

<span data-ttu-id="b63b6-104">会議のダイヤルアウトと通話は、参加者を会議に参加したり、既存の参加者が従来の携帯電話を使って会議に参加したりするために非常に便利な方法です。</span><span class="sxs-lookup"><span data-stu-id="b63b6-104">Meeting dial outs and Call me calls are very useful ways to invite participants to join a meeting and for existing participants to join a meeting using a traditional or mobile phone.</span></span> <span data-ttu-id="b63b6-105">ただし、呼び出されたユーザーが通話に応答できず、通話がボイスメール システムによって応答されると、ボイスメール システムが会議に接続され、会議から削除されるまで、参加者はそれを聞く事ができます。</span><span class="sxs-lookup"><span data-stu-id="b63b6-105">However, when the called person is unable to answer the call and the call is answered by a voicemail system, the voicemail system is connected to the meeting and participants will be able to listen to it until it’s removed from the meeting.</span></span>

<span data-ttu-id="b63b6-106">会議のダイヤルアウトが電話番号に送信され、通話相手が通話に応答できない場合にボイスメール システムが会議に接続されるのを防ぐには、Teams を設定して、通話相手に会議への参加の確認を要求することができます。</span><span class="sxs-lookup"><span data-stu-id="b63b6-106">To prevent voicemail systems from connecting to meetings when a meeting dial out is sent to a phone number and the called person is unable to answer the call, you can set up Teams to request a confirmation from the called person for them to join the meeting.</span></span> <span data-ttu-id="b63b6-107">通話相手が通話に応答できない場合、通話がボイスメール システムによって応答された場合、ボイスメール システムは参加の確認を提供しないので、会議に接続されません。</span><span class="sxs-lookup"><span data-stu-id="b63b6-107">If the called person can’t answer the call and the call is answered by a voicemail system, the voicemail system won‘t be connected to the meeting because it won’t provide a confirmation to join it.</span></span>

<span data-ttu-id="b63b6-108">この機能を有効にすると、ダイヤルアウトまたは電話で通話を受けるユーザーは、従来の携帯電話または携帯電話で 1 を押して会議に参加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b63b6-108">When this capability is enabled, people that receive a dial out or Call me call must confirm that they want to join the meeting by pressing 1 on their traditional or mobile phone.</span></span>

<span data-ttu-id="b63b6-109">組織内のすべての会議でこの機能を有効にするには ```EnableDialOutJoinConfirmation``` [、Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) コマンドレットのパラメーターを次に設定します ```true``` 。</span><span class="sxs-lookup"><span data-stu-id="b63b6-109">To enable this capability for all meetings in your organization, set the ```EnableDialOutJoinConfirmation``` parameter of the [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet to ```true```.</span></span> <span data-ttu-id="b63b6-110">これを行うには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b63b6-110">To do this, run the following command:</span></span>

```
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a><span data-ttu-id="b63b6-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="b63b6-111">Related topics</span></span>

- <span data-ttu-id="b63b6-112">[ユーザーの [電話する] 機能をセットアップする](set-up-the-call-me-feature-for-your-users.md)</span><span class="sxs-lookup"><span data-stu-id="b63b6-112">[Set up the Call me feature for your users](set-up-the-call-me-feature-for-your-users.md)</span></span>
- [<span data-ttu-id="b63b6-113">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="b63b6-113">Teams PowerShell overview</span></span>](teams-powershell-overview.md)