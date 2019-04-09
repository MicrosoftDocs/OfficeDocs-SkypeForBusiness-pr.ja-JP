---
title: Teams でのユーザーのプレゼンス
author: jambirk
ms.author: jambirk
manager: serdars
ms.date: 08/21/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: rakayala
description: 情報の管理者は、チームでの存在について理解する必要があります。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0cffa4e5eef3b5b120e38b103d04adbca08bef0e
ms.sourcegitcommit: 58fec9aebd80029e1f1e71376efe222f9abf707e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "31517088"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="4c76e-103">Teams でのユーザーのプレゼンス</span><span class="sxs-lookup"><span data-stu-id="4c76e-103">User Presence in Teams</span></span>

<span data-ttu-id="4c76e-104">プレゼンスは、マイクロソフトのチームで (および全体で Office 365) – のユーザーのプロファイルの一部であるし、ユーザーの現在の可用性と、組織の他のユーザーのステータスを示します。</span><span class="sxs-lookup"><span data-stu-id="4c76e-104">Presence is part of a user’s profile in Microsoft Teams (and throughout Office 365) – and indicates the user’s current availability and status to other users in the organization.</span></span> <span data-ttu-id="4c76e-105">既定では、かどうか他のユーザーは、利用可能なオンラインのチームを使用して、組織内のだれもが確認できます。</span><span class="sxs-lookup"><span data-stu-id="4c76e-105">By default, anyone in your organization using Teams can see whether or not other users are available online.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="4c76e-106">チームでのプレゼンス状態</span><span class="sxs-lookup"><span data-stu-id="4c76e-106">Presence states in Teams</span></span>

<span data-ttu-id="4c76e-107">チームで使用可能なユーザーのプレゼンス状態は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4c76e-107">The user presence states available in Teams are:</span></span>

|<span data-ttu-id="4c76e-108">ユーザーの構成</span><span class="sxs-lookup"><span data-stu-id="4c76e-108">User configured</span></span>|<span data-ttu-id="4c76e-109">アプリケーションの構成</span><span class="sxs-lookup"><span data-stu-id="4c76e-109">App configured</span></span>|
|:--- |:---|
| ![プレゼンスの使用](media/Presence_Available.png) <span data-ttu-id="4c76e-111">利用可能</span><span class="sxs-lookup"><span data-stu-id="4c76e-111">Available</span></span>|![プレゼンスの使用](media/Presence_Available.png) <span data-ttu-id="4c76e-113">利用可能</span><span class="sxs-lookup"><span data-stu-id="4c76e-113">Available</span></span>|
|| ![不在時の利用可能です](media/Presence_Available_OOF.png) <span data-ttu-id="4c76e-115">Office から、使用可能です</span><span class="sxs-lookup"><span data-stu-id="4c76e-115">Available, Out of Office</span></span> |
|  ![ビジー状態です。](media/Presence_Busy.png) <span data-ttu-id="4c76e-117">ビジー状態です。</span><span class="sxs-lookup"><span data-stu-id="4c76e-117">Busy</span></span> |  ![ビジー状態です。](media/Presence_Busy.png) <span data-ttu-id="4c76e-119">ビジー状態です。</span><span class="sxs-lookup"><span data-stu-id="4c76e-119">Busy</span></span>  |
|| ![ビジー状態です。](media/Presence_Busy.png) <span data-ttu-id="4c76e-121">呼び出しで</span><span class="sxs-lookup"><span data-stu-id="4c76e-121">In a call</span></span>|
|| ![ビジー状態です。](media/Presence_Busy.png) <span data-ttu-id="4c76e-123">会議に参加</span><span class="sxs-lookup"><span data-stu-id="4c76e-123">In a meeting</span></span> |
|| ![使用中の不在時](media/Presence_Busy_OOF.png) <span data-ttu-id="4c76e-125">不在時の呼び出しで</span><span class="sxs-lookup"><span data-stu-id="4c76e-125">In a call, out of office</span></span>|
|  ![不可します。](media/Presence_DND.png) <span data-ttu-id="4c76e-127">不可します。</span><span class="sxs-lookup"><span data-stu-id="4c76e-127">Do not disturb</span></span> ||
|| ![不可します。](media/Presence_DND.png) <span data-ttu-id="4c76e-129">表示します。</span><span class="sxs-lookup"><span data-stu-id="4c76e-129">Presenting</span></span>|
| ![退席中](media/Presence_Away.png) <span data-ttu-id="4c76e-131">退席中</span><span class="sxs-lookup"><span data-stu-id="4c76e-131">Away</span></span>| ![退席中](media/Presence_Away.png) <span data-ttu-id="4c76e-133">退席中</span><span class="sxs-lookup"><span data-stu-id="4c76e-133">Away</span></span>|
|| <span data-ttu-id="4c76e-134">![離れた](media/Presence_Away.png)から最後の表示*時間*</span><span class="sxs-lookup"><span data-stu-id="4c76e-134">![away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![退席中](media/Presence_Away.png) <span data-ttu-id="4c76e-136">一時退席中</span><span class="sxs-lookup"><span data-stu-id="4c76e-136">Be right back</span></span>| |
|| ![退席中](media/Presence_Away.png)  <span data-ttu-id="4c76e-138">作業オフ</span><span class="sxs-lookup"><span data-stu-id="4c76e-138">Off Work</span></span>|
|| ![オフライン](media/Presence_Offline.png) <span data-ttu-id="4c76e-140">オフライン</span><span class="sxs-lookup"><span data-stu-id="4c76e-140">Offline</span></span> |
|| ![不明です](media/Presence_Unknown.png) <span data-ttu-id="4c76e-142">状態不明</span><span class="sxs-lookup"><span data-stu-id="4c76e-142">Status unknown</span></span>|
||![ブロック](media/Presence_Blocked.png) <span data-ttu-id="4c76e-144">ブロックされました</span><span class="sxs-lookup"><span data-stu-id="4c76e-144">Blocked</span></span> |
|| ![不在時](media/Presence_OOF.png) <span data-ttu-id="4c76e-146">Office から</span><span class="sxs-lookup"><span data-stu-id="4c76e-146">Out of Office</span></span>|
|||
 
<span data-ttu-id="4c76e-147">いくつかのオプションをユーザーが、現在のプレゼンス状態を手動で設定しての状態を取得する他のすべてのユーザーに反映されます。</span><span class="sxs-lookup"><span data-stu-id="4c76e-147">Users can manually set their current presence state to some options, and their state gets reflected to all other users.</span></span> <span data-ttu-id="4c76e-148">その他のユーザーのプレゼンスの詳細情報も自動的に更新され、ユーザーの利用状況 (「使用可能」、「退席中」など)、Outlook の予定表の状態 (会議など)、またはチーム アプリケーションの状態 (呼び出し発表者)、リスト内のインデントされた状態にします。</span><span class="sxs-lookup"><span data-stu-id="4c76e-148">Additional user presence details are also automatically updated based on user activity (such as Available or Away), Outlook calendar states (such as In a meeting), or Teams app states (In a call, Presenting), to states that are indented in the list.</span></span>

<span data-ttu-id="4c76e-149">退席中] にリセットされるが、ユーザーの現在の状態まで、15 分間アイドル状態のタイムアウトがあります。</span><span class="sxs-lookup"><span data-stu-id="4c76e-149">There is a 15 minute inactivity timeout, after which your users' current presence state will be reset to Away.</span></span>

<span data-ttu-id="4c76e-150">人を突破できるユーザーを指定できます (不可の設定をオーバーライドすることをお問い合わせください)。</span><span class="sxs-lookup"><span data-stu-id="4c76e-150">Users can specify who can break through (contact them overriding a Do Not Disturb setting).</span></span> <span data-ttu-id="4c76e-151">これらの設定は、アプリケーションで利用可能です。</span><span class="sxs-lookup"><span data-stu-id="4c76e-151">These settings are available in-app.</span></span>

## <a name="teams-is-not-skype-for-business"></a><span data-ttu-id="4c76e-152">チームは、ビジネスの Skype ではありません。</span><span class="sxs-lookup"><span data-stu-id="4c76e-152">Teams is not Skype for Business</span></span>

<span data-ttu-id="4c76e-153">ビジネス用の Skype では、次の管理設定は、チームでは異なります。</span><span class="sxs-lookup"><span data-stu-id="4c76e-153">The following Admin settings in Skype for Business are different in Teams:</span></span>
- <span data-ttu-id="4c76e-154">プレゼンスの共有が常に有効チーム、組織内のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="4c76e-154">Presence sharing is always enabled in Teams for users in the organization.</span></span> <span data-ttu-id="4c76e-155">(プレゼンスを表示できるユーザーを決定する) のプライバシーの設定は、チームで使用可能ではありません。</span><span class="sxs-lookup"><span data-stu-id="4c76e-155">Privacy (deciding who can see Presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="4c76e-156">(フェデレーション サービスを含む) すべてのユーザーと共有の存在は常にチーム内のユーザーの有効にします。</span><span class="sxs-lookup"><span data-stu-id="4c76e-156">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="4c76e-157">(であるかのデバイスのいずれか)、連絡先の一覧は、 **_gt 連絡先のチャット**] の下、または**呼び出し _gt 連絡先**] の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="4c76e-157">Their contact list (if they had one in SfB) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="4c76e-158">クライアントが応答しないと画期的な機能は常に、チーム内のユーザーに対して有効にします。</span><span class="sxs-lookup"><span data-stu-id="4c76e-158">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="4c76e-159">(を含む不在時の & その他の予定表の情報) の予定表の統合は、常に有効にチーム内のユーザーの Outlook と統合されている場合。</span><span class="sxs-lookup"><span data-stu-id="4c76e-159">Calendar (includes OOF & other calendar info) integration  is always enabled for users in Teams if integrated with Outlook.</span></span>
- <span data-ttu-id="4c76e-160">*Last seen*または*から退席中*(ビジネス用の Skype でデュアル環境の場合) のインジケーターは常にチーム内のユーザーに対して有効です。</span><span class="sxs-lookup"><span data-stu-id="4c76e-160">The *Last seen* or *Away since* (if in a dual environment with Skype for Business) indicator is always enabled for users in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="4c76e-161">これらの設定をカスタマイズするのには、チームの管理者の機能は現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="4c76e-161">The ability of a Teams Admin to customize these settings is not currently supported.</span></span>


## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="4c76e-162">Skype for Business と共存する</span><span class="sxs-lookup"><span data-stu-id="4c76e-162">Coexistence with Skype for Business</span></span>

<span data-ttu-id="4c76e-163">Skype のビジネスとの共存と、チームの存在がどのように機能の詳細については、 [Skype のビジネスとの共存](coexistence-chat-calls-presence.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c76e-163">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when coexisting with Skype for Business.</span></span> 
