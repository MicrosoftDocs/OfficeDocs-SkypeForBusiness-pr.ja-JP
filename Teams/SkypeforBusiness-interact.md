---
title: "Skype for Business と Microsoft Teams の連携 | Microsoft サポート"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: overview
ms.service: msteams
description: "チャットや通話など、Skype for Business と Microsoft Teams の連携について説明します。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 02d11632a0a6b8f78504ab20ae3415a942e6c91f
ms.sourcegitcommit: 9e217129451afae32eb3cd27fb3ee591874c29c9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
<a name="how-skype-for-business-and-microsoft-teams-interact"></a><span data-ttu-id="b8d73-103">Skype for Business と Microsoft Teams の連携</span><span class="sxs-lookup"><span data-stu-id="b8d73-103">How Skype for Business and Microsoft Teams interact</span></span>
===================================================

<span data-ttu-id="b8d73-104">組織で Skype for Business を使用している場合、Skype for Business と Microsoft Teams がどのように連携するかを理解することは重要です。</span><span class="sxs-lookup"><span data-stu-id="b8d73-104">If your organization uses Skype for Business today, it is important to understand how Skype for Business and Microsoft Teams will interact.</span></span>

<span data-ttu-id="b8d73-105">一般的に配布されている Microsoft Teams では、Microsoft Teams と Skype for Business Online または Hybrid の基本的な相互運用性は、ピアツーピア (P2P) のインスタント メッセージングのみです。</span><span class="sxs-lookup"><span data-stu-id="b8d73-105">At general availability of Microsoft Teams, basic interoperability between Microsoft Teams and Skype for Business Online or Hybrid is available peer to peer (P2P) instant messaging only.</span></span>

<span data-ttu-id="b8d73-p101">既定の動作では、Microsoft Teams クライアントは Microsoft Teams のバックエンド サービスと Skype for Business サービスの両方にサインインします (デュアルスタック アプローチ)。Microsoft Teams クライアントは Skype for Business に対して IM 機能のみを提示するため、Skype for Business から Microsoft Teams ユーザーを検索すると、そのユーザーは「IM のみ」として表示されます。次の例では、Alix Wilber は Microsoft Teams クライアントのみにサインインしています。</span><span class="sxs-lookup"><span data-stu-id="b8d73-p101">The default behavior is that the Microsoft Teams client will sign into both the Microsoft Teams backend services and the Skype for Business services (a dual-stack approach). The Microsoft Teams client will only present IM capabilities to Skype for Business, so looking up a Microsoft Teams user from Skype for Business will only indicate the user as IM Only – shown in the example below, Alix Wilber is only signed into the Microsoft Teams client.</span></span>

![](media/Understand_how_Skype_for_Business_and_Microsoft_Teams_interact_image1.png)

<span data-ttu-id="b8d73-108">Microsoft Teams では、ユーザーは現在 Skype for Business のみが有効になっている組織内のユーザーを検索でき、そのユーザーとインスタント メッセージングによるチャット セッションを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b8d73-108">From Microsoft Teams, users can search for other users within their organization who are currently only enabled for Skype for Business, and conduct instant messaging chat sessions.</span></span>

<span data-ttu-id="b8d73-109">Skype for Business のユーザーは、Microsoft Teams のチャット ウィンドウに受信したインスタント メッセージに返信できます。</span><span class="sxs-lookup"><span data-stu-id="b8d73-109">Users on Skype for Business can reply to the instant messages, which will arrive in Microsoft Teams’ chat window.</span></span>

![](media/Understand_how_Skype_for_Business_and_Microsoft_Teams_interact_image2.png)

<span data-ttu-id="b8d73-110">Microsoft Teams のユーザーは、Skype for Business でも有効になっている場合は、それぞれに対応するクライアントを同時に使用して Microsoft Teams と Skype for Business にサインインできます。</span><span class="sxs-lookup"><span data-stu-id="b8d73-110">Users on Microsoft Teams, if enabled for Skype for Business as well, can sign in to Microsoft Teams and Skype for Business using their own respective clients simultaneously.</span></span>

<span data-ttu-id="b8d73-p102">最後にアクティブであったエンドポイントが優先されるため、ユーザーが Microsoft Teams を積極的に使用している場合、Skype for Business ユーザーが送信したインスタント メッセージは Microsoft Teams チャット ウィンドウで受信します。ユーザーが Skype for Business を使用して通話の着信や発信を行っている場合や Skype for Business での通話を終えたばかりの場合に Microsoft Teams クライアントに戻っていなければ、Skype for Business が最近のアクティブなエンドポイントとなるため、Skype for Business ユーザーが送信したインスタント メッセージは Skype for Business クライアントで受信します。</span><span class="sxs-lookup"><span data-stu-id="b8d73-p102">The last active endpoint will be honored, so if the user is actively using Microsoft Teams, any instant messages sent from a Skype for Business user will arrive in the Microsoft Teams chat window. If the user is currently using Skype for Business to receive/make phone calls or just finished taking a call using Skype for Business, and have not returned to Microsoft Teams client, incoming instant messages sent from a Skype for Business user will arrive in Skype for Business client as this will be the most active endpoint.</span></span>

<span data-ttu-id="b8d73-p103">現時点では、Microsoft Teams は Skype for Business に対してピアツーピア (P2P) インスタント メッセージングの相互運用性しかサポートしません。そのため、Skype for Business ユーザーからの一切の音声/ビデオの通話、Skype for Business 会議への招待はその形式に関わらず Skype for Business クライアントのみで受信します。Microsoft Teams クライアントからの一切の音声/ビデオの通話、グループ通話への招待はその形式に関わらず Microsoft Teams クライアントのみで受信します。</span><span class="sxs-lookup"><span data-stu-id="b8d73-p103">As Microsoft Teams only currently supports peer-to-peer (P2P) instant messaging interop between Skype for Business, any audio/video calls or invitation to join a Skype for Business meetings, for any modalities, from other Skype for Business users will arrive on the Skype for Business client only. In the reverse, any audio/video calls or invitation to join group calling, for any modalities from Microsoft Teams client, will only arrive on the Microsoft Teams client.</span></span>

<span data-ttu-id="b8d73-p104">上記の動作により、Microsoft Teams と Skype for Business を同時に使用しても操作の快適性が確保され、エンドユーザーは適切なツールを使って特定の通信を処理できます。ただし、相互運用性の仕組みとそれがエンドユーザーのエクスペリエンスに与える影響を理解するには、エンドユーザーの正しい知識が必要になります。</span><span class="sxs-lookup"><span data-stu-id="b8d73-p104">With the above behavior, end users can comfortably use both Microsoft Teams and Skype for Business at the same time, and handle specific communications needs using the right tool. However, proper end user awareness may be required to understand how interoperability works and how it may impact end user experience.</span></span>


|  |  |
|---------|---------|
|![](media/Understand_how_Skype_for_Business_and_Microsoft_Teams_interact_image3.png)<br><span data-ttu-id="b8d73-117">注意</span><span class="sxs-lookup"><span data-stu-id="b8d73-117">Note</span></span></br>      |<span data-ttu-id="b8d73-118">Skype for Business との相互運用において、Teams で受信するインスタント メッセージは Skype for Business 会話履歴に記録されません。</span><span class="sxs-lookup"><span data-stu-id="b8d73-118">With Skype for Business interoperability, instant messages that arrive in Teams will not be recorded in Skype for Business conversation history.</span></span>         |

<span data-ttu-id="b8d73-p105">Microsoft Teams では、[通知] 設定で Skype for Business との相互運用を無効にする機能が提供されています。この設定はユーザー制御が可能であるため、各ユーザーは動作を任意に決定することができます。</span><span class="sxs-lookup"><span data-stu-id="b8d73-p105">Microsoft Teams provides the ability for users to disable Skype for Business interoperability from within the Notification settings. This setting is user controlled, allowing each user to decide on the behavior they prefer.</span></span>
