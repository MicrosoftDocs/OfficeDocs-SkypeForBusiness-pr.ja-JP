---
title: Microsoft Teams で NDI を使用する
author: cichur
ms.author: v-cichur
ms.reviewer: aaglick
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Microsoft Teams で NDI を使用する方法について説明します。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: d971a7c9e44e2fbf7c3d2500f237e3755c5f89d0
ms.sourcegitcommit: 824c79bd050b0abb576004f6209bb081d5090a8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522917"
---
# <a name="use-ndi-in-microsoft-teams"></a><span data-ttu-id="259f1-103">Microsoft Teams で NDI を使用する</span><span class="sxs-lookup"><span data-stu-id="259f1-103">Use NDI in Microsoft Teams</span></span>

[!INCLUDE [template](includes/preview-feature.md)]

<span data-ttu-id="259f1-104">ネットワークデバイスインターフェイス (NDI) は、メディアデバイス (studio カメラやミキサーなど) に接続するための最新のソリューションです。</span><span class="sxs-lookup"><span data-stu-id="259f1-104">Network Device Interface (NDI) is a modern solution for connecting media devices (such as a studio camera and mixer).</span></span> <span data-ttu-id="259f1-105">NDI は、物理接続を使う代わりに、ローカルコンピューター上など、ローカルイントラネット経由の接続を可能にします。</span><span class="sxs-lookup"><span data-stu-id="259f1-105">Instead of using physical connections, NDI enables connectivity over a local intranet, including on a local machine.</span></span>

<span data-ttu-id="259f1-106">NewTek NDI®は、ストリームのライブコンテンツを生成するための標準的な業界ソリューションとなっており、プロフェッショナルなブロードキャスト世界で深刻な認知度と導入を実現しています。</span><span class="sxs-lookup"><span data-stu-id="259f1-106">NewTek NDI® has become a standard industry solution for producing live content for streams and has gained significant awareness and adoption in the professional broadcast world.</span></span>

<span data-ttu-id="259f1-107">Skype では、2018の遅刻で Skype に NDI アウト機能が追加されていました。</span><span class="sxs-lookup"><span data-stu-id="259f1-107">Skype previously added NDI-Out functionality to Skype in late 2018.</span></span> <span data-ttu-id="259f1-108">Microsoft Teams はこの機能を活用して、会議の操作性を向上させています。</span><span class="sxs-lookup"><span data-stu-id="259f1-108">Microsoft Teams leverages this functionality to improve the meeting experience.</span></span>

<span data-ttu-id="259f1-109">NDI はローカルネットワークに限定され、ブロードキャストソリューションではなく、実稼働ワークフローの一部と見なされる必要があります。</span><span class="sxs-lookup"><span data-stu-id="259f1-109">NDI is limited to a local network and should only be considered a part of the production workflow, not a broadcast solution.</span></span>

## <a name="turn-on-ndi"></a><span data-ttu-id="259f1-110">NDI を有効にする</span><span class="sxs-lookup"><span data-stu-id="259f1-110">Turn on NDI</span></span>

<span data-ttu-id="259f1-111">NDI を有効にするには、ユーザーに対して2つの手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="259f1-111">NDI requires two steps to be turned on for a user.</span></span>

1. <span data-ttu-id="259f1-112">テナント管理者は、機能フラグ enableStreamingCallsOverNdi を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="259f1-112">The tenant admin must enable the feature flag enableStreamingCallsOverNdi.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. <span data-ttu-id="259f1-113">この変更が設定された後、エンドユーザーは、特定のクライアントに対して ndi を**設定**する必要があり  >  **Permissions**ます。</span><span class="sxs-lookup"><span data-stu-id="259f1-113">After this change has populated, the end user must turn on NDI for their specific client from **Settings** > **Permissions**.</span></span>

<span data-ttu-id="259f1-114">ユーザーが会議に参加すると、会議がブロードキャストされていることを知らせるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="259f1-114">When a user joins a meeting, they'll see a message that notifies them that the meeting is being broadcast.</span></span> <span data-ttu-id="259f1-115">ユーザーがブロードキャストに含まれないようにする必要がある場合は、会議から削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="259f1-115">If users don’t want to be included in the broadcast, they’ll need to drop from the meeting.</span></span>

<span data-ttu-id="259f1-116">次の画像は、Teams 会議でユーザーに表示されるバナーメッセージを示しています。</span><span class="sxs-lookup"><span data-stu-id="259f1-116">The following image shows the banner message that a user sees in a Teams meeting.</span></span>

![Teams 会議に表示される NDI バナーの画像。](media/NDI-disclosure.png)

<span data-ttu-id="259f1-118">バナーには[Microsoft のプライバシーポリシー](https://support.skype.com/faq/FA34853/what-is-skype-for-content-creators?q=ndi)へのリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="259f1-118">The banner has a link to the [Microsoft privacy policy](https://support.skype.com/faq/FA34853/what-is-skype-for-content-creators?q=ndi).</span></span>

## <a name="supported-locales-and-user-types"></a><span data-ttu-id="259f1-119">サポートされるロケールとユーザーの種類</span><span class="sxs-lookup"><span data-stu-id="259f1-119">Supported locales and user types</span></span>

<span data-ttu-id="259f1-120">NDI は、すべてのロケールでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="259f1-120">NDI is supported in all locales.</span></span> <span data-ttu-id="259f1-121">NDI 会議では、次のユーザーがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="259f1-121">The following users are supported in an NDI meeting:</span></span>

- <span data-ttu-id="259f1-122">テナント間–発信/テナント/ユーザー Id に基づいて提供される完全なサポート (会議ポリシー + 機能フラグによって制御されます)</span><span class="sxs-lookup"><span data-stu-id="259f1-122">In-tenant – full support, delivered based on ring/tenantId/userId (controlled by Meetings Policy + Feature Flag)</span></span>
- <span data-ttu-id="259f1-123">フェデレーション–いいえ (NDI を使用していても)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="259f1-123">Federated – no (even when they have NDI on)<sup>1</sup></span></span>
- <span data-ttu-id="259f1-124">目につき-いいえ (既定値)</span><span class="sxs-lookup"><span data-stu-id="259f1-124">Freemium - no (default value)</span></span>
- <span data-ttu-id="259f1-125">匿名–いいえ (既定値)</span><span class="sxs-lookup"><span data-stu-id="259f1-125">Anonymous – no (default value)</span></span>
- <span data-ttu-id="259f1-126">Guest – no (既定値)</span><span class="sxs-lookup"><span data-stu-id="259f1-126">Guest – no  (default value)</span></span>

<span data-ttu-id="259f1-127"><sup>1 つ</sup>のデバイスには、既定でオンになっている ndi 設定があります。</span><span class="sxs-lookup"><span data-stu-id="259f1-127"><sup>1</sup> Devices have an NDI setting that is on by default.</span></span> <span data-ttu-id="259f1-128">会議の出席者が NDI off のデバイスを使用している場合は、NDI を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="259f1-128">If a meeting participant is using a device with NDI off, they'll need to turn on NDI.</span></span>
