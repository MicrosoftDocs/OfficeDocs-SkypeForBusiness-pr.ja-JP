---
title: Teams で音声と通話のポリシーを管理する
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
ms.openlocfilehash: 7d0ea4db57fbfdc3ab76e8c6c9991e032103b260
ms.sourcegitcommit: e72599d5437773322ae6ef985f804a19101ed84f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2021
ms.locfileid: "50348036"
---
# <a name="manage-voice-and-calling-policies-in-microsoft-teams"></a><span data-ttu-id="349b0-102">Microsoft Teams で音声と通話のポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="349b0-102">Manage voice and calling policies in Microsoft Teams</span></span>

<span data-ttu-id="349b0-103">音声と通話のポリシーは、Microsoft Teams での音声と通話を制御するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="349b0-103">Voice and calling policies are used to control voice and calling in Microsoft Teams.</span></span>

## <a name="emergency-calling-policies"></a><span data-ttu-id="349b0-104">緊急通話ポリシー</span><span class="sxs-lookup"><span data-stu-id="349b0-104">Emergency calling policies</span></span>

<span data-ttu-id="349b0-105">緊急通話 [ポリシーを使用して](manage-emergency-calling-policies.md) 、組織内のユーザーが緊急通話を行った場合の対応を構成します。</span><span class="sxs-lookup"><span data-stu-id="349b0-105">You use [emergency calling policies](manage-emergency-calling-policies.md) to configure what happens when a user in your organization makes an emergency call.</span></span> <span data-ttu-id="349b0-106">これらのポリシーは、Teams 管理センターで管理するか、組織のWindows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="349b0-106">These policies are managed in the Teams admin center or using Windows PowerShell.</span></span>

![緊急通話ポリシーのスクリーンショット。](media/emergency-calling-policy2.png)

## <a name="emergency-call-routing-policies"></a><span data-ttu-id="349b0-108">緊急通話ルーティング ポリシー</span><span class="sxs-lookup"><span data-stu-id="349b0-108">Emergency call routing policies</span></span>

<span data-ttu-id="349b0-109">組織が電話システムダイレクトルーティングを展開している場合は、緊急[](manage-emergency-call-routing-policies.md)通話ルーティング ポリシーを使用して、緊急通話のルーティング先、拡張緊急サービスが有効かどうか、緊急サービスに使用される番号を決定できます。</span><span class="sxs-lookup"><span data-stu-id="349b0-109">If your organization has deployed **Phone System Direct Routing**, you can use [emergency call routing policies](manage-emergency-call-routing-policies.md) to determine where emergency calls are routed, whether enhanced emergency services are enabled, and which numbers are used for emergency services.</span></span> <span data-ttu-id="349b0-110">これらのポリシーは、PowerShell または Microsoft Teams 管理センターを使用して管理されます。</span><span class="sxs-lookup"><span data-stu-id="349b0-110">These policies are managed using PowerShell or in the Microsoft Teams admin center.</span></span>

![緊急通話ルーティング ポリシーのスクリーンショット。](media/emergency-call-routing-policy.png)

## <a name="caller-id-policies"></a><span data-ttu-id="349b0-112">発信者番号ポリシー</span><span class="sxs-lookup"><span data-stu-id="349b0-112">Caller ID policies</span></span>

<span data-ttu-id="349b0-113">[発信者番号ポリシーは、](caller-id-policies.md) 発信者番号を変更またはブロックするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="349b0-113">[Caller ID policies](caller-id-policies.md) are used to change or block caller ID.</span></span>

![発信者番号ポリシーのスクリーンショット。](media/caller-id-policy.png)

## <a name="voice-routing-policies"></a><span data-ttu-id="349b0-115">音声ルーティング ポリシー</span><span class="sxs-lookup"><span data-stu-id="349b0-115">Voice routing policies</span></span>

<span data-ttu-id="349b0-116">音声 [ルーティング ポリシーは、](manage-voice-routing-policies.md) 公衆交換電話網 (PSTN) 利用状況レコードのコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="349b0-116">A [voice routing policy](manage-voice-routing-policies.md) is a container for Public Switched Telephone Network (PSTN) usage records.</span></span> <span data-ttu-id="349b0-117">組織が電話システムダイレクト ルーティングを展開している場合は、これらの **ポリシーを使用できます**。</span><span class="sxs-lookup"><span data-stu-id="349b0-117">You can use these policies if your organization has deployed **Phone System Direct Routing**.</span></span> <span data-ttu-id="349b0-118">音声ルーティング ポリシーは、PowerShell または Teams 管理センターで管理できます。</span><span class="sxs-lookup"><span data-stu-id="349b0-118">Voice routing policies can be managed with PowerShell or in the Teams admin center.</span></span>

![音声ルーティング ポリシーのスクリーンショット。](media/voice-routing-policy.png)

## <a name="calling-policies"></a><span data-ttu-id="349b0-120">通話ポリシー</span><span class="sxs-lookup"><span data-stu-id="349b0-120">Calling policies</span></span>

<span data-ttu-id="349b0-121">[通話ポリシーは](teams-calling-policy.md) 、ユーザーがプライベート通話を行うかどうか、通話グループに通話を送信できるかどうか、通話をボイスメールにルーティングできるかどうかなど、ユーザーが使用できる通話と着信の転送機能を制御します。</span><span class="sxs-lookup"><span data-stu-id="349b0-121">[Calling policies](teams-calling-policy.md) control which calling and call forwarding features are available to users including whether a user can make private calls, send calls to call groups, and route calls to voicemail.</span></span>

![通話ポリシーのスクリーンショット。](media/calling-policy.png)

## <a name="call-park-and-retrieve-policies"></a><span data-ttu-id="349b0-123">コール パークと取得ポリシー</span><span class="sxs-lookup"><span data-stu-id="349b0-123">Call park and retrieve policies</span></span>

<span data-ttu-id="349b0-124">[コール パークと取得により](call-park-and-retrieve.md) 、ユーザーは他のユーザーを保留にし、同じユーザーまたは他のユーザーが通話を継続できます。</span><span class="sxs-lookup"><span data-stu-id="349b0-124">[Call park and retrieve](call-park-and-retrieve.md) lets users put other users on hold and enables the same user or someone else to continue the call.</span></span>

![コール パークと取得ポリシーのスクリーンショット。](media/call-park-policy.png)

## <a name="create-and-manage-dial-plans"></a><span data-ttu-id="349b0-126">ダイヤル プランを作成および管理する</span><span class="sxs-lookup"><span data-stu-id="349b0-126">Create and manage dial plans</span></span>

<span data-ttu-id="349b0-127">[ダイヤル プランは、](create-and-manage-dial-plans.md) 通話の承認とルーティングのためにダイヤルされた電話番号を翻訳します。</span><span class="sxs-lookup"><span data-stu-id="349b0-127">[Dial plans](create-and-manage-dial-plans.md) translate dialed phone numbers for call authorization and routing.</span></span> <span data-ttu-id="349b0-128">ダイヤル プランは、PowerShell または Microsoft Teams 管理センターで作成および管理できます。</span><span class="sxs-lookup"><span data-stu-id="349b0-128">You can create and manage dial plans through PowerShell or in the Microsoft Teams admin center.</span></span>

![ダイヤル プランのスクリーンショット。](media/dial-plans.png)

## <a name="related-topics"></a><span data-ttu-id="349b0-130">関連トピック</span><span class="sxs-lookup"><span data-stu-id="349b0-130">Related topics</span></span>

* [<span data-ttu-id="349b0-131">Microsoft Teams で緊急通話ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="349b0-131">Manage emergency calling policies in Microsoft Teams</span></span>](manage-emergency-calling-policies.md)
* [<span data-ttu-id="349b0-132">緊急通話のルーティング ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="349b0-132">Manage emergency call routing policies</span></span>](manage-emergency-call-routing-policies.md)
* [<span data-ttu-id="349b0-133">Microsoft Teams で発信者番号ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="349b0-133">Manage caller ID policies in Microsoft Teams</span></span>](caller-id-policies.md)
* [<span data-ttu-id="349b0-134">音声ルーティング ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="349b0-134">Manage voice routing policies</span></span>](manage-voice-routing-policies.md)
* [<span data-ttu-id="349b0-135">Microsoft Teams の発信通話制限ポリシー</span><span class="sxs-lookup"><span data-stu-id="349b0-135">Calling policies in Microsoft Teams</span></span>](teams-calling-policy.md)
* [<span data-ttu-id="349b0-136">Microsoft Teams でのコール パークおよび保留解除</span><span class="sxs-lookup"><span data-stu-id="349b0-136">Call park and retrieve in Microsoft Teams</span></span>](call-park-and-retrieve.md)
* [<span data-ttu-id="349b0-137">ダイヤル プランを作成および管理する</span><span class="sxs-lookup"><span data-stu-id="349b0-137">Create and manage dial plans</span></span>](create-and-manage-dial-plans.md)
* [<span data-ttu-id="349b0-138">ポリシーを使用して Teams を管理する</span><span class="sxs-lookup"><span data-stu-id="349b0-138">Manage Teams with policies</span></span>](manage-teams-with-policies.md)
