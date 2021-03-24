---
title: ポリシーを使用して Teams を管理する
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Teams のポリシーについて説明します。
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b54c64c637d44132ac0f978561267ef34f720e67
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101103"
---
# <a name="manage-teams-with-policies"></a><span data-ttu-id="8c080-103">ポリシーを使用して Teams を管理する</span><span class="sxs-lookup"><span data-stu-id="8c080-103">Manage Teams with policies</span></span>

<span data-ttu-id="8c080-104">ポリシーは、Teams 管理の重要な部分です。</span><span class="sxs-lookup"><span data-stu-id="8c080-104">Policies are an important part of managing Teams.</span></span> <span data-ttu-id="8c080-105">この記事では、ポリシーを使用して組織に利益をもたらす方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8c080-105">Use this article to navigate how to use policies to benefit your organization.</span></span>

## <a name="what-you-use-policies-for"></a><span data-ttu-id="8c080-106">ポリシーの使用</span><span class="sxs-lookup"><span data-stu-id="8c080-106">What you use policies for</span></span>

<span data-ttu-id="8c080-107">ポリシーは、メッセージング、会議、アプリケーションなど、さまざまな分野にわたって組織内の多くのタスクを実行するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="8c080-107">Policies are used to accomplish many tasks in your organization across different areas such as messaging, meetings, and applications.</span></span> <span data-ttu-id="8c080-108">ユーザーがチーム チャネルで会議をスケジュールできるようにしたり、ユーザーが送信したメッセージを編集したり、ユーザーがアプリを Teams アプリ バーにピン留めできるかどうかを制御したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="8c080-108">Some of the things you can do include allowing users to schedule meetings in a teams channel, enabling users to edit sent messages, and controlling whether users can pin apps to the Teams app bar.</span></span>

## <a name="how-to-assign-policies"></a><span data-ttu-id="8c080-109">ポリシーを割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="8c080-109">How to assign policies</span></span>

<span data-ttu-id="8c080-110">組織が達成しようとしている内容に応じて、いくつかの方法でポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="8c080-110">Policies can be assigned in several different ways depending on what your organization is trying to accomplish.</span></span> <span data-ttu-id="8c080-111">Teams 管理センターで課題を作成および表示できます。</span><span class="sxs-lookup"><span data-stu-id="8c080-111">You can make and view assignments in the Teams admin center.</span></span>

![グループ ポリシーの割り当てのスクリーンショット。](media/group-policy-assignment.png)

<span data-ttu-id="8c080-113">ポリシーの割り当てに関する詳細については、こちらを参照 [してください](assign-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="8c080-113">Read more about assigning policies [here](assign-policies.md).</span></span>

## <a name="how-to-manage-policies"></a><span data-ttu-id="8c080-114">ポリシーを管理する方法</span><span class="sxs-lookup"><span data-stu-id="8c080-114">How to manage policies</span></span>

<span data-ttu-id="8c080-115">ポリシーは、Microsoft Teams 管理センターまたは [PowerShell を使用して管理されます](./teams-powershell-managing-teams.md#manage-policies-via-powershell)。</span><span class="sxs-lookup"><span data-stu-id="8c080-115">Policies are managed with the Microsoft Teams admin center or [using PowerShell](./teams-powershell-managing-teams.md#manage-policies-via-powershell).</span></span>

<span data-ttu-id="8c080-116">たとえば、アプリセットアップ ポリシーを使用すると、ユーザーがカスタム アプリをアップロードし、ユーザーの代わりにアプリをインストールし、アプリを Teams アプリ バーにピン留めすることができます。</span><span class="sxs-lookup"><span data-stu-id="8c080-116">For example, an app setup policy can allow you to enable users to upload custom apps, install apps on behalf of your users, and pin apps to the Teams app bar.</span></span> <span data-ttu-id="8c080-117">これらのポリシーは、Teams 管理センターで構成されます。</span><span class="sxs-lookup"><span data-stu-id="8c080-117">These policies are configured in the Teams admin center.</span></span>

![アプリセットアップ ポリシーのスクリーンショット。](media/app-setup-policy.png)

<span data-ttu-id="8c080-119">さらに、会議ポリシーを使用して、議事書き、クラウドレコーディング、IP オーディオ/ビデオなどの Teams 会議の音声とビデオの設定を制御できます。</span><span class="sxs-lookup"><span data-stu-id="8c080-119">Additionally, a meeting policy can be used to control audio and video settings in Teams meetings such as transcriptions, cloud recordings, and IP audio/video.</span></span>

![会議ポリシーのスクリーンショット。](media/engineering-meeting-policy.png)

### <a name="teams-for-education"></a><span data-ttu-id="8c080-121">教育機関用 Teams</span><span class="sxs-lookup"><span data-stu-id="8c080-121">Teams for Education</span></span>

<span data-ttu-id="8c080-122">[Teams for Education](easy-policy-setup-edu.md)ポリシー ウィザードを使用して、学習環境のポリシーを簡単に設定および管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="8c080-122">You can also use the [Teams for Education policy wizard](easy-policy-setup-edu.md) to easily set up and manage policies for your learning environment.</span></span>

![Teams for Education ポリシー ウィザードのスクリーンショット。](media/easy-policy-setup-quick-setup.png)

## <a name="types-of-policies"></a><span data-ttu-id="8c080-124">ポリシーの種類</span><span class="sxs-lookup"><span data-stu-id="8c080-124">Types of policies</span></span>

<span data-ttu-id="8c080-125">次のポリシーは、Microsoft Teams で管理できます。</span><span class="sxs-lookup"><span data-stu-id="8c080-125">The following policies can be managed with Microsoft Teams.</span></span>

<span data-ttu-id="8c080-126">ポリシーの種類</span><span class="sxs-lookup"><span data-stu-id="8c080-126">Policy type</span></span> | <span data-ttu-id="8c080-127">説明</span><span class="sxs-lookup"><span data-stu-id="8c080-127">Description</span></span>
------------|------------
[<span data-ttu-id="8c080-128">ポリシー パッケージ</span><span class="sxs-lookup"><span data-stu-id="8c080-128">Policy packages</span></span>](manage-policy-packages.md) | <span data-ttu-id="8c080-129">Microsoft Teams のポリシー パッケージは、組織内で同様の役割を持つユーザーに割り当て可能な定義済みのポリシーと設定のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="8c080-129">A policy package in Microsoft Teams is a collection of predefined policies and settings you can assign to users who have similar roles in your organization.</span></span>
[<span data-ttu-id="8c080-130">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="8c080-130">Meeting policies</span></span>](meeting-policies-in-teams.md) | <span data-ttu-id="8c080-131">会議ポリシーは、組織内のユーザーがスケジュールした会議の会議参加者が使用できる機能を制御するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="8c080-131">A meeting policy is used to control the features that are available to meeting participants for meetings scheduled by users in your organization.</span></span> <span data-ttu-id="8c080-132">会議ポリシーには、次のトピックが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8c080-132">Meeting policies include the following topics.</span></span><br> <span data-ttu-id="8c080-133">- オーディオ ポリシーとビデオ ポリシー</span><span class="sxs-lookup"><span data-stu-id="8c080-133">- Audio and video policies</span></span><br> <span data-ttu-id="8c080-134">- コンテンツと画面の共有ポリシー</span><span class="sxs-lookup"><span data-stu-id="8c080-134">- Content and screen sharing policies</span></span><br> <span data-ttu-id="8c080-135">- 参加者、ゲスト、アクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="8c080-135">- Participants, guests, and access policies</span></span><br> <span data-ttu-id="8c080-136">- 一般的なポリシー</span><span class="sxs-lookup"><span data-stu-id="8c080-136">- General policies</span></span>
[<span data-ttu-id="8c080-137">音声と通話のポリシー</span><span class="sxs-lookup"><span data-stu-id="8c080-137">Voice and calling policies</span></span>](voice-and-calling-policies.md)| <span data-ttu-id="8c080-138">音声および通話ポリシーは、緊急通話、通話ルーティング、発信者番号などのチームを通じてこれらの設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="8c080-138">Voice and calling policies manage these settings through teams such as emergency calling, call routing, and caller ID.</span></span>
[<span data-ttu-id="8c080-139">アプリ ポリシー</span><span class="sxs-lookup"><span data-stu-id="8c080-139">App policies</span></span>](app-policies.md)| <span data-ttu-id="8c080-140">アプリ ポリシーは、Microsoft Teams でアプリケーションを制御するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="8c080-140">App policies are used to control applications in Microsoft Teams.</span></span> <span data-ttu-id="8c080-141">管理者は、ユーザーがインストールできるアプリを許可またはブロックしたり、ユーザーの Teams アプリ バーにアプリケーションをピン留めしたり、ユーザーの代わりにアプリケーションをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="8c080-141">Admins can allow or block which apps users can install, pin applications to a user's Teams app bar, and install application on behalf of your users.</span></span>
[<span data-ttu-id="8c080-142">メッセージング ポリシー</span><span class="sxs-lookup"><span data-stu-id="8c080-142">Messaging policies</span></span>](messaging-policies-in-teams.md)| <span data-ttu-id="8c080-143">メッセージング ポリシーは、チャットとチャネル機能の可用性を制御します。</span><span class="sxs-lookup"><span data-stu-id="8c080-143">Messaging policies control chat and channel feature availability.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8c080-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="8c080-144">Related topics</span></span>

* [<span data-ttu-id="8c080-145">Microsoft Teams でフィードバック ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="8c080-145">Manage feedback policies in Microsoft Teams</span></span>](manage-feedback-policies-in-teams.md)
* [<span data-ttu-id="8c080-146">Microsoft Teams でチーム ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="8c080-146">Manage teams policies in Microsoft Teams</span></span>](teams-policies.md)
* [<span data-ttu-id="8c080-147">アクティビティ ログでポリシー割り当てを表示する</span><span class="sxs-lookup"><span data-stu-id="8c080-147">View policy assignments in the Activity Log</span></span>](activity-log.md)
* [<span data-ttu-id="8c080-148">Microsoft Teams でのライブ イベントのセットアップ</span><span class="sxs-lookup"><span data-stu-id="8c080-148">Set up for live events in Microsoft Teams</span></span>](teams-live-events/set-up-for-teams-live-events.md)
* [<span data-ttu-id="8c080-149">Teams for Education ポリシーとポリシー パッケージ</span><span class="sxs-lookup"><span data-stu-id="8c080-149">Teams for Education policies and policy packages</span></span>](policy-packages-edu.md)