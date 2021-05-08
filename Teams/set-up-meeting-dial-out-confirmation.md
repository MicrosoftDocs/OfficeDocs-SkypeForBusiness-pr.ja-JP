---
title: 会議のユーザーに対して会議のダイヤルアウト確認を設定Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 通話相手が通話に応答できない場合にボイスメール システムが会議に接続できないのを防ぐために、Teams を設定してダイヤルアウト確認を要求する方法について学習します。
localization_priority: Normal
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4bfa15bdb0e58066d085aa852f671c6d89ff1b90
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117095"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a><span data-ttu-id="e5f6e-103">会議のユーザーに対して会議のダイヤルアウト確認を設定Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e5f6e-103">Set up meeting dial-out confirmation for your users in Microsoft Teams</span></span>

<span data-ttu-id="e5f6e-104">会議のダイヤルアウトと通話は、参加者を招待して会議に参加したり、既存の参加者が従来の電話または携帯電話を使って会議に参加したりするために非常に便利な方法です。</span><span class="sxs-lookup"><span data-stu-id="e5f6e-104">Meeting dial outs and Call me calls are very useful ways to invite participants to join a meeting and for existing participants to join a meeting using a traditional or mobile phone.</span></span> <span data-ttu-id="e5f6e-105">ただし、通話相手が通話に応答できず、ボイスメール システムによって通話に応答すると、ボイスメール システムが会議に接続され、会議から削除されるまで、ボイスメール システムがリッスンできます。</span><span class="sxs-lookup"><span data-stu-id="e5f6e-105">However, when the called person is unable to answer the call and the call is answered by a voicemail system, the voicemail system is connected to the meeting and participants will be able to listen to it until it’s removed from the meeting.</span></span>

<span data-ttu-id="e5f6e-106">会議のダイヤルアウトが電話番号に送信され、通話相手が通話に応答できないときにボイスメール システムが会議に接続されるのを防ぐために、Teams を設定して、通話相手に会議に参加するための確認を要求できます。</span><span class="sxs-lookup"><span data-stu-id="e5f6e-106">To prevent voicemail systems from connecting to meetings when a meeting dial out is sent to a phone number and the called person is unable to answer the call, you can set up Teams to request a confirmation from the called person for them to join the meeting.</span></span> <span data-ttu-id="e5f6e-107">通話相手が通話に応答できない場合、ボイスメール システムによって通話に応答した場合、ボイスメール システムは会議に参加するための確認を提供しないので、会議に接続されません。</span><span class="sxs-lookup"><span data-stu-id="e5f6e-107">If the called person can’t answer the call and the call is answered by a voicemail system, the voicemail system won‘t be connected to the meeting because it won’t provide a confirmation to join it.</span></span>

<span data-ttu-id="e5f6e-108">この機能を有効にすると、ダイヤルアウトまたは通話を受け取るユーザーは、従来の携帯電話または携帯電話で 1 キーを押して、会議に参加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5f6e-108">When this capability is enabled, people that receive a dial out or Call me call must confirm that they want to join the meeting by pressing 1 on their traditional or mobile phone.</span></span>

<span data-ttu-id="e5f6e-109">組織内のすべての会議でこの機能を有効にするには ```EnableDialOutJoinConfirmation``` [、Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) コマンドレットの パラメーターを に設定します ```true``` 。</span><span class="sxs-lookup"><span data-stu-id="e5f6e-109">To enable this capability for all meetings in your organization, set the ```EnableDialOutJoinConfirmation``` parameter of the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet to ```true```.</span></span> <span data-ttu-id="e5f6e-110">これを行うには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e5f6e-110">To do this, run the following command:</span></span>

```
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a><span data-ttu-id="e5f6e-111">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e5f6e-111">Related topics</span></span>

- <span data-ttu-id="e5f6e-112">[ユーザーの [電話する] 機能をセットアップする](set-up-the-call-me-feature-for-your-users.md)</span><span class="sxs-lookup"><span data-stu-id="e5f6e-112">[Set up the Call me feature for your users](set-up-the-call-me-feature-for-your-users.md)</span></span>
- [<span data-ttu-id="e5f6e-113">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="e5f6e-113">Teams PowerShell overview</span></span>](teams-powershell-overview.md)