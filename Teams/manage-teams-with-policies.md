---
title: ポリシー Teamsを管理する
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: ポリシーをTeamsしてください。
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 77afc1cbb71fff9cb54decbbf6e5cfd10d6c4e59
ms.sourcegitcommit: 2bb8556650120b4f7cf509d8ff93d7e4d058829b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574186"
---
# <a name="manage-teams-with-policies"></a><span data-ttu-id="98585-103">ポリシー Teamsを管理する</span><span class="sxs-lookup"><span data-stu-id="98585-103">Manage Teams with policies</span></span>

<span data-ttu-id="98585-104">ポリシーは、管理の重要な部分Teams。</span><span class="sxs-lookup"><span data-stu-id="98585-104">Policies are an important part of managing Teams.</span></span> <span data-ttu-id="98585-105">この記事では、ポリシーを使用して組織の利益を得る方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="98585-105">Use this article to navigate how to use policies to benefit your organization.</span></span>

## <a name="what-you-use-policies-for"></a><span data-ttu-id="98585-106">ポリシーの使用</span><span class="sxs-lookup"><span data-stu-id="98585-106">What you use policies for</span></span>

<span data-ttu-id="98585-107">ポリシーは、メッセージング、会議、アプリケーションなどのさまざまな領域にわたって、組織内の多くのタスクを実行するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="98585-107">Policies are used to accomplish many tasks in your organization across different areas such as messaging, meetings, and applications.</span></span> <span data-ttu-id="98585-108">ユーザーがチーム チャネルで会議をスケジュールできるようにしたり、ユーザーが送信されたメッセージを編集したり、ユーザーが Teams アプリ バーにアプリをピン留めできるかどうかを制御したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="98585-108">Some of the things you can do include allowing users to schedule meetings in a teams channel, enabling users to edit sent messages, and controlling whether users can pin apps to the Teams app bar.</span></span>

## <a name="how-to-assign-policies"></a><span data-ttu-id="98585-109">ポリシーを割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="98585-109">How to assign policies</span></span>

<span data-ttu-id="98585-110">ポリシーは、組織が何を達成しようとしているかによって、さまざまな方法で割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="98585-110">Policies can be assigned in several different ways depending on what your organization is trying to accomplish.</span></span> <span data-ttu-id="98585-111">管理者センターで割り当てを行Teams表示できます。</span><span class="sxs-lookup"><span data-stu-id="98585-111">You can make and view assignments in the Teams admin center.</span></span>

![グループ ポリシーの割り当てのスクリーンショット。](media/group-policy-assignment.png)

<span data-ttu-id="98585-113">ポリシーの割り当ての詳細については、こちらを参照 [してください](policy-assignment-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="98585-113">Learn more about assigning policies [here](policy-assignment-overview.md).</span></span>

## <a name="how-to-manage-policies"></a><span data-ttu-id="98585-114">ポリシーを管理する方法</span><span class="sxs-lookup"><span data-stu-id="98585-114">How to manage policies</span></span>

<span data-ttu-id="98585-115">ポリシーは、管理センター Microsoft Teams PowerShell を使用[して管理されます](./teams-powershell-managing-teams.md#manage-policies-via-powershell)。</span><span class="sxs-lookup"><span data-stu-id="98585-115">Policies are managed with the Microsoft Teams admin center or [using PowerShell](./teams-powershell-managing-teams.md#manage-policies-via-powershell).</span></span>

<span data-ttu-id="98585-116">たとえば、アプリセットアップ ポリシーを使用すると、ユーザーがカスタム アプリをアップロードし、ユーザーに代わってアプリをインストールし、アプリを Teams アプリ バーにピン留めできます。</span><span class="sxs-lookup"><span data-stu-id="98585-116">For example, an app setup policy can allow you to enable users to upload custom apps, install apps on behalf of your users, and pin apps to the Teams app bar.</span></span> <span data-ttu-id="98585-117">これらのポリシーは、管理センター Teams構成されます。</span><span class="sxs-lookup"><span data-stu-id="98585-117">These policies are configured in the Teams admin center.</span></span>

![アプリセットアップ ポリシーのスクリーンショット。](media/app-setup-policy.png)

<span data-ttu-id="98585-119">さらに、会議ポリシーを使用して、トランスクリプション、クラウド録画、IP オーディオ/ビデオなどの Teams 会議の音声とビデオの設定を制御できます。</span><span class="sxs-lookup"><span data-stu-id="98585-119">Additionally, a meeting policy can be used to control audio and video settings in Teams meetings such as transcriptions, cloud recordings, and IP audio/video.</span></span>

![会議ポリシーのスクリーンショット。](media/engineering-meeting-policy.png)

### <a name="teams-for-education"></a><span data-ttu-id="98585-121">教育機関用 Teams</span><span class="sxs-lookup"><span data-stu-id="98585-121">Teams for Education</span></span>

<span data-ttu-id="98585-122">Teams [for Education](easy-policy-setup-edu.md)ポリシー ウィザードを使用して、学習環境のポリシーを簡単に設定および管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="98585-122">You can also use the [Teams for Education policy wizard](easy-policy-setup-edu.md) to easily set up and manage policies for your learning environment.</span></span>

![Teams ポリシー ウィザードのスクリーンショット。](media/easy-policy-setup-quick-setup.png)

## <a name="types-of-policies"></a><span data-ttu-id="98585-124">ポリシーの種類</span><span class="sxs-lookup"><span data-stu-id="98585-124">Types of policies</span></span>

<span data-ttu-id="98585-125">次のポリシーは、次のポリシーを使用Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="98585-125">The following policies can be managed with Microsoft Teams.</span></span>

<span data-ttu-id="98585-126">ポリシーの種類</span><span class="sxs-lookup"><span data-stu-id="98585-126">Policy type</span></span> | <span data-ttu-id="98585-127">説明</span><span class="sxs-lookup"><span data-stu-id="98585-127">Description</span></span>
------------|------------
[<span data-ttu-id="98585-128">ポリシー パッケージ</span><span class="sxs-lookup"><span data-stu-id="98585-128">Policy packages</span></span>](manage-policy-packages.md) | <span data-ttu-id="98585-129">Microsoft Teams のポリシー パッケージは、組織内で同様のロールを持つユーザーに割り当て可能な定義済みのポリシーと設定のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="98585-129">A policy package in Microsoft Teams is a collection of predefined policies and settings you can assign to users who have similar roles in your organization.</span></span>
[<span data-ttu-id="98585-130">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="98585-130">Meeting policies</span></span>](meeting-policies-in-teams.md) | <span data-ttu-id="98585-131">会議ポリシーは、組織内のユーザーがスケジュールした会議に対して会議参加者が使用できる機能を制御するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="98585-131">A meeting policy is used to control the features that are available to meeting participants for meetings scheduled by users in your organization.</span></span> <span data-ttu-id="98585-132">会議ポリシーには、次のトピックが含まれます。</span><span class="sxs-lookup"><span data-stu-id="98585-132">Meeting policies include the following topics.</span></span><br> <span data-ttu-id="98585-133">- オーディオポリシーとビデオ ポリシー</span><span class="sxs-lookup"><span data-stu-id="98585-133">- Audio and video policies</span></span><br> <span data-ttu-id="98585-134">- コンテンツと画面共有ポリシー</span><span class="sxs-lookup"><span data-stu-id="98585-134">- Content and screen sharing policies</span></span><br> <span data-ttu-id="98585-135">- 参加者、ゲスト、アクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="98585-135">- Participants, guests, and access policies</span></span><br> <span data-ttu-id="98585-136">- 一般的なポリシー</span><span class="sxs-lookup"><span data-stu-id="98585-136">- General policies</span></span>
[<span data-ttu-id="98585-137">音声と通話のポリシー</span><span class="sxs-lookup"><span data-stu-id="98585-137">Voice and calling policies</span></span>](voice-and-calling-policies.md)| <span data-ttu-id="98585-138">音声および通話ポリシーは、緊急通話、通話ルーティング、発信者番号などのチームを通じてこれらの設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="98585-138">Voice and calling policies manage these settings through teams such as emergency calling, call routing, and caller ID.</span></span>
[<span data-ttu-id="98585-139">アプリ ポリシー</span><span class="sxs-lookup"><span data-stu-id="98585-139">App policies</span></span>](app-policies.md)| <span data-ttu-id="98585-140">アプリ ポリシーは、アプリケーションの管理に使用Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="98585-140">App policies are used to control applications in Microsoft Teams.</span></span> <span data-ttu-id="98585-141">管理者は、ユーザーがインストールできるアプリを許可またはブロックしたり、ユーザーの Teams アプリ バーにアプリケーションをピン留めしたり、ユーザーに代わってアプリケーションをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="98585-141">Admins can allow or block which apps users can install, pin applications to a user's Teams app bar, and install application on behalf of your users.</span></span>
[<span data-ttu-id="98585-142">メッセージング ポリシー</span><span class="sxs-lookup"><span data-stu-id="98585-142">Messaging policies</span></span>](messaging-policies-in-teams.md)| <span data-ttu-id="98585-143">メッセージング ポリシーは、チャットとチャネル機能の可用性を制御します。</span><span class="sxs-lookup"><span data-stu-id="98585-143">Messaging policies control chat and channel feature availability.</span></span>

## <a name="related-topics"></a><span data-ttu-id="98585-144">関連トピック</span><span class="sxs-lookup"><span data-stu-id="98585-144">Related topics</span></span>

* [<span data-ttu-id="98585-145">グループでポリシーを割りTeams - 使用を開始する</span><span class="sxs-lookup"><span data-stu-id="98585-145">Assign policies in Teams - getting started</span></span>](policy-assignment-overview.md)
* [<span data-ttu-id="98585-146">Microsoft Teams でフィードバック ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="98585-146">Manage feedback policies in Microsoft Teams</span></span>](manage-feedback-policies-in-teams.md)
* [<span data-ttu-id="98585-147">Microsoft Teams でチーム ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="98585-147">Manage teams policies in Microsoft Teams</span></span>](teams-policies.md)
* [<span data-ttu-id="98585-148">Microsoft Teams でのライブ イベントのセットアップ</span><span class="sxs-lookup"><span data-stu-id="98585-148">Set up for live events in Microsoft Teams</span></span>](teams-live-events/set-up-for-teams-live-events.md)
* [<span data-ttu-id="98585-149">Teamsのポリシーとポリシー パッケージの詳細</span><span class="sxs-lookup"><span data-stu-id="98585-149">Teams for Education policies and policy packages</span></span>](policy-packages-edu.md)