---
title: Teams で音声と通話のポリシーを管理する
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Teams の音声および通話ポリシーについて説明します。
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9056c9b81fcda9c0e7408c63b4af00c1aabbffd0
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460587"
---
# <a name="manage-voice-and-calling-policies-in-microsoft-teams"></a><span data-ttu-id="d8c8c-103">Microsoft Teams で音声と通話のポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="d8c8c-103">Manage voice and calling policies in Microsoft Teams</span></span>

<span data-ttu-id="d8c8c-104">音声と通話のポリシーは、Microsoft Teams での音声と通話を制御するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d8c8c-104">Voice and calling policies are used to control voice and calling in Microsoft Teams.</span></span>

## <a name="emergency-calling-policies"></a><span data-ttu-id="d8c8c-105">緊急通話ポリシー</span><span class="sxs-lookup"><span data-stu-id="d8c8c-105">Emergency calling policies</span></span>

<span data-ttu-id="d8c8c-106">緊急通話 [ポリシーを使用して](manage-emergency-calling-policies.md) 、組織内のユーザーが緊急通話を行った場合の対応を構成します。</span><span class="sxs-lookup"><span data-stu-id="d8c8c-106">You use [emergency calling policies](manage-emergency-calling-policies.md) to configure what happens when a user in your organization makes an emergency call.</span></span> <span data-ttu-id="d8c8c-107">これらのポリシーは、Teams 管理センターで管理するか、組織のWindows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="d8c8c-107">These policies are managed in the Teams admin center or using Windows PowerShell.</span></span>

![緊急通話ポリシーのスクリーンショット。](media/emergency-calling-policy2.png)

## <a name="emergency-call-routing-policies"></a><span data-ttu-id="d8c8c-109">緊急通話ルーティング ポリシー</span><span class="sxs-lookup"><span data-stu-id="d8c8c-109">Emergency call routing policies</span></span>

<span data-ttu-id="d8c8c-110">組織が電話システムダイレクトルーティングを展開している場合は、緊急[](manage-emergency-call-routing-policies.md)通話ルーティング ポリシーを使用して、緊急通話のルーティング先、拡張緊急サービスが有効かどうか、緊急サービスに使用する番号を決定できます。</span><span class="sxs-lookup"><span data-stu-id="d8c8c-110">If your organization has deployed **Phone System Direct Routing**, you can use [emergency call routing policies](manage-emergency-call-routing-policies.md) to determine where emergency calls are routed, whether enhanced emergency services are enabled, and which numbers are used for emergency services.</span></span> <span data-ttu-id="d8c8c-111">これらのポリシーは、PowerShell または Microsoft Teams 管理センターを使用して管理されます。</span><span class="sxs-lookup"><span data-stu-id="d8c8c-111">These policies are managed using PowerShell or in the Microsoft Teams admin center.</span></span>

![緊急通話ルーティング ポリシーのスクリーンショット。](media/emergency-call-routing-policy.png)

## <a name="caller-id-policies"></a><span data-ttu-id="d8c8c-113">発信者番号ポリシー</span><span class="sxs-lookup"><span data-stu-id="d8c8c-113">Caller ID policies</span></span>

<span data-ttu-id="d8c8c-114">[発信者番号ポリシーは、](caller-id-policies.md) 発信者番号を変更またはブロックするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d8c8c-114">[Caller ID policies](caller-id-policies.md) are used to change or block caller ID.</span></span>

![発信者番号ポリシーのスクリーンショット。](media/caller-id-policy.png)

## <a name="voice-routing-policies"></a><span data-ttu-id="d8c8c-116">音声ルーティング ポリシー</span><span class="sxs-lookup"><span data-stu-id="d8c8c-116">Voice routing policies</span></span>

<span data-ttu-id="d8c8c-117">音声 [ルーティング ポリシーは、](manage-voice-routing-policies.md) 公衆交換電話網 (PSTN) 利用状況レコードのコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="d8c8c-117">A [voice routing policy](manage-voice-routing-policies.md) is a container for Public Switched Telephone Network (PSTN) usage records.</span></span> <span data-ttu-id="d8c8c-118">組織が電話システムダイレクト ルーティングを展開している場合は、 **これらのポリシーを使用できます**。</span><span class="sxs-lookup"><span data-stu-id="d8c8c-118">You can use these policies if your organization has deployed **Phone System Direct Routing**.</span></span> <span data-ttu-id="d8c8c-119">音声ルーティング ポリシーは、PowerShell または Teams 管理センターで管理できます。</span><span class="sxs-lookup"><span data-stu-id="d8c8c-119">Voice routing policies can be managed with PowerShell or in the Teams admin center.</span></span>

![音声ルーティング ポリシーのスクリーンショット。](media/voice-routing-policy.png)

## <a name="calling-policies"></a><span data-ttu-id="d8c8c-121">通話ポリシー</span><span class="sxs-lookup"><span data-stu-id="d8c8c-121">Calling policies</span></span>

<span data-ttu-id="d8c8c-122">[通話ポリシーは](teams-calling-policy.md) 、ユーザーがプライベート通話を行うかどうか、通話グループに通話を送信できるかどうか、通話をボイスメールにルーティングできるかどうかなど、ユーザーが使用できる通話と着信の転送機能を制御します。</span><span class="sxs-lookup"><span data-stu-id="d8c8c-122">[Calling policies](teams-calling-policy.md) control which calling and call forwarding features are available to users including whether a user can make private calls, send calls to call groups, and route calls to voicemail.</span></span>

![通話ポリシーのスクリーンショット。](media/calling-policy.png)

## <a name="call-park-and-retrieve-policies"></a><span data-ttu-id="d8c8c-124">コール パークと取得ポリシー</span><span class="sxs-lookup"><span data-stu-id="d8c8c-124">Call park and retrieve policies</span></span>

<span data-ttu-id="d8c8c-125">[コール パークと取得により](call-park-and-retrieve.md) 、ユーザーは他のユーザーを保留にし、同じユーザーまたは他のユーザーが通話を継続できます。</span><span class="sxs-lookup"><span data-stu-id="d8c8c-125">[Call park and retrieve](call-park-and-retrieve.md) lets users put other users on hold and enables the same user or someone else to continue the call.</span></span>

![コール パークと取得ポリシーのスクリーンショット。](media/call-park-policy.png)

## <a name="create-and-manage-dial-plans"></a><span data-ttu-id="d8c8c-127">ダイヤル プランを作成および管理する</span><span class="sxs-lookup"><span data-stu-id="d8c8c-127">Create and manage dial plans</span></span>

<span data-ttu-id="d8c8c-128">[ダイヤル プランは、](create-and-manage-dial-plans.md) 通話の承認とルーティングのためにダイヤルされた電話番号を翻訳します。</span><span class="sxs-lookup"><span data-stu-id="d8c8c-128">[Dial plans](create-and-manage-dial-plans.md) translate dialed phone numbers for call authorization and routing.</span></span> <span data-ttu-id="d8c8c-129">ダイヤル プランは、PowerShell または Microsoft Teams 管理センターで作成および管理できます。</span><span class="sxs-lookup"><span data-stu-id="d8c8c-129">You can create and manage dial plans through PowerShell or in the Microsoft Teams admin center.</span></span>

![ダイヤル プランのスクリーンショット。](media/dial-plans.png)

## <a name="related-topics"></a><span data-ttu-id="d8c8c-131">関連トピック</span><span class="sxs-lookup"><span data-stu-id="d8c8c-131">Related topics</span></span>

* [<span data-ttu-id="d8c8c-132">Microsoft Teams で緊急通話ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="d8c8c-132">Manage emergency calling policies in Microsoft Teams</span></span>](manage-emergency-calling-policies.md)
* [<span data-ttu-id="d8c8c-133">緊急通話のルーティング ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="d8c8c-133">Manage emergency call routing policies</span></span>](manage-emergency-call-routing-policies.md)
* [<span data-ttu-id="d8c8c-134">Microsoft Teams で発信者番号ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="d8c8c-134">Manage caller ID policies in Microsoft Teams</span></span>](caller-id-policies.md)
* [<span data-ttu-id="d8c8c-135">音声ルーティング ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="d8c8c-135">Manage voice routing policies</span></span>](manage-voice-routing-policies.md)
* [<span data-ttu-id="d8c8c-136">Microsoft Teams の発信通話制限ポリシー</span><span class="sxs-lookup"><span data-stu-id="d8c8c-136">Calling policies in Microsoft Teams</span></span>](teams-calling-policy.md)
* [<span data-ttu-id="d8c8c-137">Microsoft Teams でのコール パークおよび保留解除</span><span class="sxs-lookup"><span data-stu-id="d8c8c-137">Call park and retrieve in Microsoft Teams</span></span>](call-park-and-retrieve.md)
* [<span data-ttu-id="d8c8c-138">ダイヤル プランを作成および管理する</span><span class="sxs-lookup"><span data-stu-id="d8c8c-138">Create and manage dial plans</span></span>](create-and-manage-dial-plans.md)
* [<span data-ttu-id="d8c8c-139">ポリシーを使用して Teams を管理する</span><span class="sxs-lookup"><span data-stu-id="d8c8c-139">Manage Teams with policies</span></span>](manage-teams-with-policies.md)
