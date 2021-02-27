---
title: ポリシーを使用してチームを管理する
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: ''
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ad39b24ee177e8e8282c6ad948b69fbdf866aa56
ms.sourcegitcommit: e72599d5437773322ae6ef985f804a19101ed84f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2021
ms.locfileid: "50347687"
---
# <a name="manage-teams-with-policies"></a><span data-ttu-id="3dffa-102">ポリシーを使用してチームを管理する</span><span class="sxs-lookup"><span data-stu-id="3dffa-102">Manage teams with policies</span></span>

<span data-ttu-id="3dffa-103">ポリシーは、Teams 管理の重要な部分です。</span><span class="sxs-lookup"><span data-stu-id="3dffa-103">Policies are an important part of managing Teams.</span></span> <span data-ttu-id="3dffa-104">この記事では、ポリシーを使用して組織に利益をもたらす方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3dffa-104">Use this article to navigate how to use policies to benefit your organization.</span></span>

## <a name="what-you-use-policies-for"></a><span data-ttu-id="3dffa-105">ポリシーの使用</span><span class="sxs-lookup"><span data-stu-id="3dffa-105">What you use policies for</span></span>

<span data-ttu-id="3dffa-106">ポリシーは、メッセージング、会議、アプリケーションなど、さまざまな分野にわたって組織内の多くのタスクを実行するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="3dffa-106">Policies are used to accomplish many tasks in your organization across different areas such as messaging, meetings, and applications.</span></span> <span data-ttu-id="3dffa-107">ユーザーがチーム チャネルで会議をスケジュールできるようにしたり、ユーザーが送信したメッセージを編集したり、ユーザーがアプリを Teams アプリ バーにピン留めできるかどうかを制御したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="3dffa-107">Some of the things you can do include allowing users to schedule meetings in a teams channel, enabling users to edit sent messages, and controlling whether users can pin apps to the Teams app bar.</span></span>

## <a name="how-to-assign-policies"></a><span data-ttu-id="3dffa-108">ポリシーを割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="3dffa-108">How to assign policies</span></span>

<span data-ttu-id="3dffa-109">組織が達成しようとしている内容に応じて、いくつかの方法でポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="3dffa-109">Policies can be assigned in several different ways depending on what your organization is trying to accomplish.</span></span> <span data-ttu-id="3dffa-110">Teams 管理センターで課題を作成および表示できます。</span><span class="sxs-lookup"><span data-stu-id="3dffa-110">You can make and view assignments in the Teams admin center.</span></span>

![グループ ポリシーの割り当てのスクリーンショット。](media/group-policy-assignment.png)

<span data-ttu-id="3dffa-112">ポリシーの割り当てに関する詳細については、こちらを参照 [してください](assign-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="3dffa-112">Read more about assigning policies [here](assign-policies.md).</span></span>

## <a name="how-to-manage-policies"></a><span data-ttu-id="3dffa-113">ポリシーを管理する方法</span><span class="sxs-lookup"><span data-stu-id="3dffa-113">How to manage policies</span></span>

<span data-ttu-id="3dffa-114">ポリシーは、Microsoft Teams 管理センターまたは [PowerShell を使用して管理されます](https://docs.microsoft.com/microsoftteams/teams-powershell-managing-teams#manage-policies-via-powershell)。</span><span class="sxs-lookup"><span data-stu-id="3dffa-114">Policies are managed with the Microsoft Teams admin center or [using PowerShell](https://docs.microsoft.com/microsoftteams/teams-powershell-managing-teams#manage-policies-via-powershell).</span></span>

<span data-ttu-id="3dffa-115">たとえば、アプリセットアップ ポリシーを使用すると、ユーザーがカスタム アプリをアップロードし、ユーザーの代わりにアプリをインストールし、アプリを Teams アプリ バーにピン留めすることができます。</span><span class="sxs-lookup"><span data-stu-id="3dffa-115">For example, an app setup policy can allow you to enable users to upload custom apps, install apps on behalf of your users, and pin apps to the Teams app bar.</span></span> <span data-ttu-id="3dffa-116">これらのポリシーは、Teams 管理センターで構成されます。</span><span class="sxs-lookup"><span data-stu-id="3dffa-116">These policies are configured in the Teams admin center.</span></span>

![アプリセットアップ ポリシーのスクリーンショット。](media/app-setup-policy.png)

<span data-ttu-id="3dffa-118">さらに、会議ポリシーを使用して、議事書き、クラウドレコーディング、IP オーディオ/ビデオなどの Teams 会議の音声とビデオの設定を制御できます。</span><span class="sxs-lookup"><span data-stu-id="3dffa-118">Additionally, a meeting policy can be used to control audio and video settings in Teams meetings such as transcriptions, cloud recordings, and IP audio/video.</span></span>

![会議ポリシーのスクリーンショット。](media/engineering-meeting-policy.png)

### <a name="teams-for-education"></a><span data-ttu-id="3dffa-120">教育機関用 Teams</span><span class="sxs-lookup"><span data-stu-id="3dffa-120">Teams for Education</span></span>

<span data-ttu-id="3dffa-121">[Teams for Education](easy-policy-setup-edu.md)ポリシー ウィザードを使用して、学習環境のポリシーを簡単に設定および管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="3dffa-121">You can also use the [Teams for Education policy wizard](easy-policy-setup-edu.md) to easily set up and manage policies for your learning environment.</span></span>

![Teams for Education ポリシー ウィザードのスクリーンショット。](media/easy-policy-setup-quick-setup.png)

## <a name="types-of-policies"></a><span data-ttu-id="3dffa-123">ポリシーの種類</span><span class="sxs-lookup"><span data-stu-id="3dffa-123">Types of policies</span></span>

<span data-ttu-id="3dffa-124">次のポリシーは、Microsoft Teams で管理できます。</span><span class="sxs-lookup"><span data-stu-id="3dffa-124">The following policies can be managed with Microsoft Teams.</span></span>

<span data-ttu-id="3dffa-125">ポリシーの種類</span><span class="sxs-lookup"><span data-stu-id="3dffa-125">Policy type</span></span> | <span data-ttu-id="3dffa-126">説明</span><span class="sxs-lookup"><span data-stu-id="3dffa-126">Description</span></span>
------------|------------
[<span data-ttu-id="3dffa-127">ポリシー パッケージ</span><span class="sxs-lookup"><span data-stu-id="3dffa-127">Policy packages</span></span>](manage-policy-packages.md) | <span data-ttu-id="3dffa-128">Microsoft Teams のポリシー パッケージは、組織内で同様の役割を持つユーザーに割り当て可能な定義済みのポリシーと設定のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="3dffa-128">A policy package in Microsoft Teams is a collection of predefined policies and settings you can assign to users who have similar roles in your organization.</span></span>
[<span data-ttu-id="3dffa-129">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="3dffa-129">Meeting policies</span></span>](meeting-policies-in-teams.md) | <span data-ttu-id="3dffa-130">会議ポリシーは、組織内のユーザーがスケジュールした会議の会議参加者が使用できる機能を制御するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="3dffa-130">A meeting policy is used to control the features that are available to meeting participants for meetings scheduled by users in your organization.</span></span> <span data-ttu-id="3dffa-131">会議ポリシーには、次のトピックが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3dffa-131">Meeting policies include the following topics.</span></span><br> <span data-ttu-id="3dffa-132">- オーディオ ポリシーとビデオ ポリシー</span><span class="sxs-lookup"><span data-stu-id="3dffa-132">- Audio and video policies</span></span><br> <span data-ttu-id="3dffa-133">- コンテンツと画面の共有ポリシー</span><span class="sxs-lookup"><span data-stu-id="3dffa-133">- Content and screen sharing policies</span></span><br> <span data-ttu-id="3dffa-134">- 参加者、ゲスト、アクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="3dffa-134">- Participants, guests, and access policies</span></span><br> <span data-ttu-id="3dffa-135">- 一般的なポリシー</span><span class="sxs-lookup"><span data-stu-id="3dffa-135">- General policies</span></span>
[<span data-ttu-id="3dffa-136">音声と通話のポリシー</span><span class="sxs-lookup"><span data-stu-id="3dffa-136">Voice and calling policies</span></span>](voice-and-calling-policies.md)| <span data-ttu-id="3dffa-137">音声および通話ポリシーは、緊急通話、通話ルーティング、発信者番号などのチームを通じてこれらの設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="3dffa-137">Voice and calling policies manage these settings through teams such as emergency calling, call routing, and caller ID.</span></span>
[<span data-ttu-id="3dffa-138">アプリ ポリシー</span><span class="sxs-lookup"><span data-stu-id="3dffa-138">App policies</span></span>](app-policies.md)| <span data-ttu-id="3dffa-139">アプリ ポリシーは、Microsoft Teams でアプリケーションを制御するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="3dffa-139">App policies are used to control applications in Microsoft Teams.</span></span> <span data-ttu-id="3dffa-140">管理者は、ユーザーがインストールできるアプリを許可またはブロックしたり、ユーザーの Teams アプリ バーにアプリケーションをピン留めしたり、ユーザーの代わりにアプリケーションをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="3dffa-140">Admins can allow or block which apps users can install, pin applications to a user's Teams app bar, and install application on behalf of your users.</span></span>
[<span data-ttu-id="3dffa-141">メッセージング ポリシー</span><span class="sxs-lookup"><span data-stu-id="3dffa-141">Messaging policies</span></span>](messaging-policies-in-teams.md)| <span data-ttu-id="3dffa-142">メッセージング ポリシーは、チャットとチャネル機能の可用性を制御します。</span><span class="sxs-lookup"><span data-stu-id="3dffa-142">Messaging policies control chat and channel feature availability.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3dffa-143">関連トピック</span><span class="sxs-lookup"><span data-stu-id="3dffa-143">Related topics</span></span>

* [<span data-ttu-id="3dffa-144">Microsoft Teams でフィードバック ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="3dffa-144">Manage feedback policies in Microsoft Teams</span></span>](manage-feedback-policies-in-teams.md)
* [<span data-ttu-id="3dffa-145">Microsoft Teams でチーム ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="3dffa-145">Manage teams policies in Microsoft Teams</span></span>](teams-policies.md)
* [<span data-ttu-id="3dffa-146">Microsoft Teams でのライブ イベントのセットアップ</span><span class="sxs-lookup"><span data-stu-id="3dffa-146">Set up for live events in Microsoft Teams</span></span>](teams-live-events/set-up-for-teams-live-events.md)
* [<span data-ttu-id="3dffa-147">Teams for Education ポリシーとポリシー パッケージ</span><span class="sxs-lookup"><span data-stu-id="3dffa-147">Teams for Education policies and policy packages</span></span>](policy-packages-edu.md)
