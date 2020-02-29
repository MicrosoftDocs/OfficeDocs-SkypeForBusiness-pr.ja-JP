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
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a><span data-ttu-id="643e8-103">Microsoft Teams でユーザーに対して会議のダイヤルアウトの確認を設定する</span><span class="sxs-lookup"><span data-stu-id="643e8-103">Set up meeting dial-out confirmation for your users in Microsoft Teams</span></span>

<span data-ttu-id="643e8-104">会議のダイヤルアウトと通話の呼び出しは、会議に参加するために参加者を招待し、既存の参加者が従来の電話や携帯電話を使って会議に参加するために、非常に便利な方法です。</span><span class="sxs-lookup"><span data-stu-id="643e8-104">Meeting dial outs and Call me calls are very useful ways to invite participants to join a meeting and for existing participants to join a meeting using a traditional or mobile phone.</span></span> <span data-ttu-id="643e8-105">ただし、通話相手が通話に応答できないときに、通話がボイスメールシステムによって応答された場合、ボイスメールシステムは会議に接続され、参加者は会議から削除されるまで聞くことができます。</span><span class="sxs-lookup"><span data-stu-id="643e8-105">However, when the called person is unable to answer the call and the call is answered by a voicemail system, the voicemail system is connected to the meeting and participants will be able to listen to it until it’s removed from the meeting.</span></span>

<span data-ttu-id="643e8-106">会議のダイヤルアウトが電話番号に送信され、通話相手が通話に応答できない場合にボイスメールシステムが会議に接続できないようにするには、チームが会議に参加するために、呼び出されたユーザーからの確認を要求するように設定します。</span><span class="sxs-lookup"><span data-stu-id="643e8-106">To prevent voicemail systems from connecting to meetings when a meeting dial out is sent to a phone number and the called person is unable to answer the call, you can set up Teams to request a confirmation from the called person for them to join the meeting.</span></span> <span data-ttu-id="643e8-107">通話に応答できないという相手がボイスメールシステムによって応答した場合、ボイスメールシステムは会議に接続されません。</span><span class="sxs-lookup"><span data-stu-id="643e8-107">If the called person can’t answer the call and the call is answered by a voicemail system, the voicemail system won‘t be connected to the meeting because it won’t provide a confirmation to join it.</span></span>

<span data-ttu-id="643e8-108">この機能が有効になっていると、ダイヤルアウトまたは着信の呼び出しを受けるユーザーは、従来の電話または携帯電話で1を押すことによって、会議に参加していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="643e8-108">When this capability is enabled, people that receive a dial out or Call me call must confirm that they want to join the meeting by pressing 1 on their traditional or mobile phone.</span></span>

<span data-ttu-id="643e8-109">組織内のすべての会議に対してこの機能を```EnableDialOutJoinConfirmation```有効にするには、 [-](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps)コマンド```true```レットのパラメーターをに設定します。</span><span class="sxs-lookup"><span data-stu-id="643e8-109">To enable this capability for all meetings in your organization, set the ```EnableDialOutJoinConfirmation``` parameter of the [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet to ```true```.</span></span> <span data-ttu-id="643e8-110">これを行うには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="643e8-110">To do this, run the following command:</span></span>

```
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a><span data-ttu-id="643e8-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="643e8-111">Related topics</span></span>

- <span data-ttu-id="643e8-112">[ユーザーの [電話する] 機能をセットアップする](set-up-the-call-me-feature-for-your-users.md)</span><span class="sxs-lookup"><span data-stu-id="643e8-112">[Set up the Call me feature for your users](set-up-the-call-me-feature-for-your-users.md)</span></span>
- [<span data-ttu-id="643e8-113">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="643e8-113">Teams PowerShell overview</span></span>](teams-powershell-overview.md)