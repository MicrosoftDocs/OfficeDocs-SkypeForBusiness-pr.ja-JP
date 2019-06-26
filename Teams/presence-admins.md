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
ms.openlocfilehash: 11902a5d6ef768afa6d7bb1bba2f33b64757fef1
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2019
ms.locfileid: "35222094"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="650d1-103">Teams でのユーザーのプレゼンス</span><span class="sxs-lookup"><span data-stu-id="650d1-103">User presence in Teams</span></span>

<span data-ttu-id="650d1-104">プレゼンスは Microsoft Teams (および Office 365 全体) のユーザーのプロファイルの一部であり、ユーザーの現在の可用性と状態を組織内の他のユーザーに対して示します。</span><span class="sxs-lookup"><span data-stu-id="650d1-104">Presence is part of a user’s profile in Microsoft Teams (and throughout Office 365) – and indicates the user’s current availability and status to other users in the organization.</span></span> <span data-ttu-id="650d1-105">既定では、Teams を使用している組織内のすべてのユーザーは、ほぼリアルタイムで表示できます。これは、他のユーザーがオンラインで利用できるかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="650d1-105">By default, anyone in your organization using Teams can see – in nearly real time – whether or not other users are available online.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="650d1-106">Teams のプレゼンス状態</span><span class="sxs-lookup"><span data-stu-id="650d1-106">Presence states in Teams</span></span>

<span data-ttu-id="650d1-107">Teams で利用できるユーザーのプレゼンス状態は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="650d1-107">The user presence states available in Teams are:</span></span>

|<span data-ttu-id="650d1-108">ユーザー構成済み</span><span class="sxs-lookup"><span data-stu-id="650d1-108">User configured</span></span>|<span data-ttu-id="650d1-109">構成済みのアプリ</span><span class="sxs-lookup"><span data-stu-id="650d1-109">App configured</span></span>|
|:--- |:---|
| ![使用可能かどうかを示す緑色の塗りマーク](media/Presence_Available.png) <span data-ttu-id="650d1-111">利用可能</span><span class="sxs-lookup"><span data-stu-id="650d1-111">Available</span></span>|![使用可能かどうかを示す緑色の塗りマーク](media/Presence_Available.png) <span data-ttu-id="650d1-113">利用可能</span><span class="sxs-lookup"><span data-stu-id="650d1-113">Available</span></span>|
|| ![使用可能な oof を示す緑のボックスを開く](media/Presence_Available_OOF.png) <span data-ttu-id="650d1-115">利用可能、外出中</span><span class="sxs-lookup"><span data-stu-id="650d1-115">Available, Out of Office</span></span> |
|  ![[取り込み中] を示す赤の丸](media/Presence_Busy.png) <span data-ttu-id="650d1-117">少ない</span><span class="sxs-lookup"><span data-stu-id="650d1-117">Busy</span></span> |  ![[取り込み中] を示す赤の丸](media/Presence_Busy.png) <span data-ttu-id="650d1-119">少ない</span><span class="sxs-lookup"><span data-stu-id="650d1-119">Busy</span></span>  |
|| ![通話中にビジー状態であることを示す赤い丸](media/Presence_Busy.png) <span data-ttu-id="650d1-121">通話中</span><span class="sxs-lookup"><span data-stu-id="650d1-121">In a call</span></span>|
|| ![会議中にビジー状態であることを示す赤い丸](media/Presence_Busy.png) <span data-ttu-id="650d1-123">会議中</span><span class="sxs-lookup"><span data-stu-id="650d1-123">In a meeting</span></span> |
|| ![[取り込み中] oof を示す赤い円を開く](media/Presence_Busy_OOF.png) <span data-ttu-id="650d1-125">通話中、外出中</span><span class="sxs-lookup"><span data-stu-id="650d1-125">In a call, out of office</span></span>|
|  ![[応答不可] を示す赤の丸 (白線)](media/Presence_DND.png) <span data-ttu-id="650d1-127">応答不可</span><span class="sxs-lookup"><span data-stu-id="650d1-127">Do not disturb</span></span> ||
|| ![プレゼンテーション中の白い線で囲まれた赤い円](media/Presence_DND.png) <span data-ttu-id="650d1-129">発表</span><span class="sxs-lookup"><span data-stu-id="650d1-129">Presenting</span></span>|
| ![退席中のことを示す黄色の時計アイコン](media/Presence_Away.png) <span data-ttu-id="650d1-131">位置</span><span class="sxs-lookup"><span data-stu-id="650d1-131">Away</span></span>| ![退席中のことを示す黄色の時計アイコン](media/Presence_Away.png) <span data-ttu-id="650d1-133">位置</span><span class="sxs-lookup"><span data-stu-id="650d1-133">Away</span></span>|
|| <span data-ttu-id="650d1-134">![黄色の時計アイコン。 [](media/Presence_Away.png)最終版] が表示されていない*状態*を示します。</span><span class="sxs-lookup"><span data-stu-id="650d1-134">![Yellow clock icon, indicating away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![退席中であることを示す黄色の時計アイコン](media/Presence_Away.png) <span data-ttu-id="650d1-136">一時退席中</span><span class="sxs-lookup"><span data-stu-id="650d1-136">Be right back</span></span>| |
|| ![退席中、作業オフを示す黄色の時計アイコン](media/Presence_Away.png)  <span data-ttu-id="650d1-138">業務時間外</span><span class="sxs-lookup"><span data-stu-id="650d1-138">Off Work</span></span>|
|| ![[オフライン] を示す、x の付いた灰色の円](media/Presence_Offline.png) <span data-ttu-id="650d1-140">で</span><span class="sxs-lookup"><span data-stu-id="650d1-140">Offline</span></span> |
|| ![状態が不明であることを示す灰色の円を開く](media/Presence_Unknown.png) <span data-ttu-id="650d1-142">状態不明</span><span class="sxs-lookup"><span data-stu-id="650d1-142">Status unknown</span></span>|
||![ブロックされていることを示す斜め線の付いた赤い丸を開く](media/Presence_Blocked.png) <span data-ttu-id="650d1-144">ブロックされました</span><span class="sxs-lookup"><span data-stu-id="650d1-144">Blocked</span></span> |
|| ![矢印付き紫色の丸、外出中であることを示す](media/Presence_OOF.png) <span data-ttu-id="650d1-146">外出中</span><span class="sxs-lookup"><span data-stu-id="650d1-146">Out of Office</span></span>|
|||
 
<span data-ttu-id="650d1-147">ユーザーは、現在のプレゼンス状態をいくつかのオプションに手動で設定することができ、その状態は他のすべてのユーザーに反映されます。</span><span class="sxs-lookup"><span data-stu-id="650d1-147">Users can manually set their current presence state to some options, and their state gets reflected to all other users.</span></span> <span data-ttu-id="650d1-148">また、ユーザーのプレゼンス情報は、ユーザーのアクティビティ (使用可能または退席中など)、Outlook の予定表の状態 (会議中など)、またはチームアプリの状態 (通話中、プレゼンテーション中) に基づいて、一覧でインデントされた状態に応じて自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="650d1-148">Additional user presence details are also automatically updated based on user activity (such as Available or Away), Outlook calendar states (such as In a meeting), or Teams app states (In a call, Presenting), to states that are indented in the list.</span></span>

<span data-ttu-id="650d1-149">15分間の非アクティブなタイムアウトがあります。その後、ユーザーの現在のプレゼンス状態が [退席中] にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="650d1-149">There is a 15 minute inactivity timeout, after which your users' current presence state will be reset to Away.</span></span>

<span data-ttu-id="650d1-150">ユーザーは、中断できるユーザーを指定できます (応答不可の設定を上書きすることに連絡してください)。</span><span class="sxs-lookup"><span data-stu-id="650d1-150">Users can specify who can break through (contact them overriding a Do Not Disturb setting).</span></span> <span data-ttu-id="650d1-151">これらの設定は、アプリ内で利用できます。</span><span class="sxs-lookup"><span data-stu-id="650d1-151">These settings are available in-app.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="650d1-152">Skype for Business と比較した場合のチームの管理設定</span><span class="sxs-lookup"><span data-stu-id="650d1-152">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="650d1-153">Skype for Business の次の管理設定は、Teams では異なります。</span><span class="sxs-lookup"><span data-stu-id="650d1-153">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="650d1-154">Teams では、組織内のユーザーに対してプレゼンス共有が常に有効になります。</span><span class="sxs-lookup"><span data-stu-id="650d1-154">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="650d1-155">[プライバシー] (プレゼンスを表示できるユーザーを決定する) 構成は、Teams では利用できません。</span><span class="sxs-lookup"><span data-stu-id="650d1-155">Privacy (deciding who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="650d1-156">すべてのユーザー (フェデレーションサービスを含む) とのプレゼンスの共有は、Teams のユーザーに対して常に有効になっています。</span><span class="sxs-lookup"><span data-stu-id="650d1-156">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="650d1-157">連絡先リスト (Skype for Business に含まれている場合) は、**チャット >** の [連絡先] または [ **> の連絡先**への通話] の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="650d1-157">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="650d1-158">クライアントが応答不可であり、チーム内のユーザーに対して画期的な機能が常に有効になります。</span><span class="sxs-lookup"><span data-stu-id="650d1-158">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="650d1-159">予定表 (不在およびその他の予定表情報が含まれます) 統合は、Outlook と統合されている場合に、Teams のユーザーに対して常に有効になります。</span><span class="sxs-lookup"><span data-stu-id="650d1-159">Calendar (includes out of office and other calendar information) integration  is always enabled for users in Teams if integrated with Outlook.</span></span>
- <span data-ttu-id="650d1-160">*最終表示*または*退席*中 (Skype for business によるデュアル環境の場合) は、Teams のユーザーに対して常に有効になっています。</span><span class="sxs-lookup"><span data-stu-id="650d1-160">The *Last seen* or *Away since* (if in a dual environment with Skype for Business) indicator is always enabled for users in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="650d1-161">チーム管理者がこれらの設定をカスタマイズできるかどうかは、現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="650d1-161">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="650d1-162">Skype for Business と共存する</span><span class="sxs-lookup"><span data-stu-id="650d1-162">Coexistence with Skype for Business</span></span>

<span data-ttu-id="650d1-163">Skype for business と共存する場合の Teams のプレゼンス機能の詳細については、「 [skype For business との共存](coexistence-chat-calls-presence.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="650d1-163">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when coexisting with Skype for Business.</span></span> 
