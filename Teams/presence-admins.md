---
title: Teams でのユーザーのプレゼンス
author: jambirk
ms.author: jambirk
manager: serdars
ms.date: 08/21/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: rakayala
description: 情報管理者は、Teams でのプレゼンスについて理解する必要があります。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0cffa4e5eef3b5b120e38b103d04adbca08bef0e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32246255"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="f6086-103">Teams でのユーザーのプレゼンス</span><span class="sxs-lookup"><span data-stu-id="f6086-103">User Presence in Teams</span></span>

<span data-ttu-id="f6086-104">プレゼンスは Microsoft Teams (および Office 365 全体) のユーザーのプロファイルの一部であり、ユーザーの現在の可用性と状態を組織内の他のユーザーに対して示します。</span><span class="sxs-lookup"><span data-stu-id="f6086-104">Presence is part of a user’s profile in Microsoft Teams (and throughout Office 365) – and indicates the user’s current availability and status to other users in the organization.</span></span> <span data-ttu-id="f6086-105">既定では、チームを使用する組織内のすべてのユーザーは、他のユーザーがオンラインで利用できるかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="f6086-105">By default, anyone in your organization using Teams can see whether or not other users are available online.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="f6086-106">Teams のプレゼンス状態</span><span class="sxs-lookup"><span data-stu-id="f6086-106">Presence states in Teams</span></span>

<span data-ttu-id="f6086-107">Teams で利用できるユーザーのプレゼンス状態は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f6086-107">The user presence states available in Teams are:</span></span>

|<span data-ttu-id="f6086-108">ユーザー構成済み</span><span class="sxs-lookup"><span data-stu-id="f6086-108">User configured</span></span>|<span data-ttu-id="f6086-109">構成済みのアプリ</span><span class="sxs-lookup"><span data-stu-id="f6086-109">App configured</span></span>|
|:--- |:---|
| ![プレゼンスが利用可能](media/Presence_Available.png) <span data-ttu-id="f6086-111">利用可能</span><span class="sxs-lookup"><span data-stu-id="f6086-111">Available</span></span>|![プレゼンスが利用可能](media/Presence_Available.png) <span data-ttu-id="f6086-113">利用可能</span><span class="sxs-lookup"><span data-stu-id="f6086-113">Available</span></span>|
|| ![利用可能な oof](media/Presence_Available_OOF.png) <span data-ttu-id="f6086-115">利用可能、外出中</span><span class="sxs-lookup"><span data-stu-id="f6086-115">Available, Out of Office</span></span> |
|  ![少ない](media/Presence_Busy.png) <span data-ttu-id="f6086-117">少ない</span><span class="sxs-lookup"><span data-stu-id="f6086-117">Busy</span></span> |  ![少ない](media/Presence_Busy.png) <span data-ttu-id="f6086-119">少ない</span><span class="sxs-lookup"><span data-stu-id="f6086-119">Busy</span></span>  |
|| ![少ない](media/Presence_Busy.png) <span data-ttu-id="f6086-121">通話中</span><span class="sxs-lookup"><span data-stu-id="f6086-121">In a call</span></span>|
|| ![少ない](media/Presence_Busy.png) <span data-ttu-id="f6086-123">会議中</span><span class="sxs-lookup"><span data-stu-id="f6086-123">In a meeting</span></span> |
|| ![取り込み中 (oof)](media/Presence_Busy_OOF.png) <span data-ttu-id="f6086-125">通話中、外出中</span><span class="sxs-lookup"><span data-stu-id="f6086-125">In a call, out of office</span></span>|
|  ![応答不可](media/Presence_DND.png) <span data-ttu-id="f6086-127">応答不可</span><span class="sxs-lookup"><span data-stu-id="f6086-127">Do not disturb</span></span> ||
|| ![応答不可](media/Presence_DND.png) <span data-ttu-id="f6086-129">発表</span><span class="sxs-lookup"><span data-stu-id="f6086-129">Presenting</span></span>|
| ![位置](media/Presence_Away.png) <span data-ttu-id="f6086-131">位置</span><span class="sxs-lookup"><span data-stu-id="f6086-131">Away</span></span>| ![位置](media/Presence_Away.png) <span data-ttu-id="f6086-133">位置</span><span class="sxs-lookup"><span data-stu-id="f6086-133">Away</span></span>|
|| <span data-ttu-id="f6086-134">![](media/Presence_Away.png)退席中の最終*日時*</span><span class="sxs-lookup"><span data-stu-id="f6086-134">![away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![位置](media/Presence_Away.png) <span data-ttu-id="f6086-136">一時退席中</span><span class="sxs-lookup"><span data-stu-id="f6086-136">Be right back</span></span>| |
|| ![位置](media/Presence_Away.png)  <span data-ttu-id="f6086-138">業務時間外</span><span class="sxs-lookup"><span data-stu-id="f6086-138">Off Work</span></span>|
|| ![で](media/Presence_Offline.png) <span data-ttu-id="f6086-140">で</span><span class="sxs-lookup"><span data-stu-id="f6086-140">Offline</span></span> |
|| ![未](media/Presence_Unknown.png) <span data-ttu-id="f6086-142">状態不明</span><span class="sxs-lookup"><span data-stu-id="f6086-142">Status unknown</span></span>|
||![さ](media/Presence_Blocked.png) <span data-ttu-id="f6086-144">ブロックされました</span><span class="sxs-lookup"><span data-stu-id="f6086-144">Blocked</span></span> |
|| ![外出中](media/Presence_OOF.png) <span data-ttu-id="f6086-146">外出中</span><span class="sxs-lookup"><span data-stu-id="f6086-146">Out of Office</span></span>|
|||
 
<span data-ttu-id="f6086-147">ユーザーは、現在のプレゼンス状態をいくつかのオプションに手動で設定することができ、その状態は他のすべてのユーザーに反映されます。</span><span class="sxs-lookup"><span data-stu-id="f6086-147">Users can manually set their current presence state to some options, and their state gets reflected to all other users.</span></span> <span data-ttu-id="f6086-148">また、ユーザーのプレゼンス情報は、ユーザーのアクティビティ (使用可能または退席中など)、Outlook の予定表の状態 (会議中など)、またはチームアプリの状態 (通話中、プレゼンテーション中) に基づいて、一覧でインデントされた状態に応じて自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="f6086-148">Additional user presence details are also automatically updated based on user activity (such as Available or Away), Outlook calendar states (such as In a meeting), or Teams app states (In a call, Presenting), to states that are indented in the list.</span></span>

<span data-ttu-id="f6086-149">15分間の非アクティブなタイムアウトがあります。その後、ユーザーの現在のプレゼンス状態が [退席中] にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="f6086-149">There is a 15 minute inactivity timeout, after which your users' current presence state will be reset to Away.</span></span>

<span data-ttu-id="f6086-150">ユーザーは、中断できるユーザーを指定できます (応答不可の設定を上書きすることに連絡してください)。</span><span class="sxs-lookup"><span data-stu-id="f6086-150">Users can specify who can break through (contact them overriding a Do Not Disturb setting).</span></span> <span data-ttu-id="f6086-151">これらの設定は、アプリ内で利用できます。</span><span class="sxs-lookup"><span data-stu-id="f6086-151">These settings are available in-app.</span></span>

## <a name="teams-is-not-skype-for-business"></a><span data-ttu-id="f6086-152">Teams は Skype for Business ではありません</span><span class="sxs-lookup"><span data-stu-id="f6086-152">Teams is not Skype for Business</span></span>

<span data-ttu-id="f6086-153">Skype for Business の次の管理設定は、Teams では異なります。</span><span class="sxs-lookup"><span data-stu-id="f6086-153">The following Admin settings in Skype for Business are different in Teams:</span></span>
- <span data-ttu-id="f6086-154">プレゼンスの共有は、組織内のユーザーに対して Teams で常に有効になっています。</span><span class="sxs-lookup"><span data-stu-id="f6086-154">Presence sharing is always enabled in Teams for users in the organization.</span></span> <span data-ttu-id="f6086-155">[プライバシー] (プレゼンスを表示できるユーザーを決定する) 構成は、Teams では利用できません。</span><span class="sxs-lookup"><span data-stu-id="f6086-155">Privacy (deciding who can see Presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="f6086-156">すべてのユーザー (フェデレーションサービスを含む) とのプレゼンスの共有は、Teams のユーザーに対して常に有効になっています。</span><span class="sxs-lookup"><span data-stu-id="f6086-156">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="f6086-157">コンタクトリスト (SfB に含まれている場合) は、**チャット >** のコンタクトまたは「> のコンタクトに**発信**」の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6086-157">Their contact list (if they had one in SfB) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="f6086-158">クライアントが応答不可であり、チーム内のユーザーに対して画期的な機能が常に有効になります。</span><span class="sxs-lookup"><span data-stu-id="f6086-158">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="f6086-159">予定表 (OOF & 他の予定表の情報を含む) 統合は、Outlook と統合されている場合、Teams のユーザーに対して常に有効になります。</span><span class="sxs-lookup"><span data-stu-id="f6086-159">Calendar (includes OOF & other calendar info) integration  is always enabled for users in Teams if integrated with Outlook.</span></span>
- <span data-ttu-id="f6086-160">*最終表示*または*退席*中 (Skype for business によるデュアル環境の場合) は、Teams のユーザーに対して常に有効になっています。</span><span class="sxs-lookup"><span data-stu-id="f6086-160">The *Last seen* or *Away since* (if in a dual environment with Skype for Business) indicator is always enabled for users in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="f6086-161">チーム管理者がこれらの設定をカスタマイズできるかどうかは、現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f6086-161">The ability of a Teams Admin to customize these settings is not currently supported.</span></span>


## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="f6086-162">Skype for Business と共存する</span><span class="sxs-lookup"><span data-stu-id="f6086-162">Coexistence with Skype for Business</span></span>

<span data-ttu-id="f6086-163">Skype for business と共存する場合の Teams のプレゼンス機能の詳細については、「 [skype For business との共存](coexistence-chat-calls-presence.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6086-163">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when coexisting with Skype for Business.</span></span> 
