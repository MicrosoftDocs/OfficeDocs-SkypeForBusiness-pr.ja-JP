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
ms.openlocfilehash: 24e4312af520bf783c0382b7543190644bfc1ff0
ms.sourcegitcommit: 7c701fc38c8a81ac0938f666c336252c3983ca4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/01/2020
ms.locfileid: "47323991"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a><span data-ttu-id="0d1ff-103">Microsoft Teams で NDI®テクノロジを使用する</span><span class="sxs-lookup"><span data-stu-id="0d1ff-103">Use NDI® technology in Microsoft Teams</span></span>

[!INCLUDE [template](includes/preview-feature.md)]

 <span data-ttu-id="0d1ff-104">NDI® (Network Device Interface) テクノロジは、メディアデバイス (スタジオカメラやミキサーなど) に接続するための最新のソリューションです。</span><span class="sxs-lookup"><span data-stu-id="0d1ff-104">NDI® (Network Device Interface) technology is a modern solution for connecting media devices (such as a studio camera and mixer).</span></span> <span data-ttu-id="0d1ff-105">NDI®テクノロジを使用する代わりに、ローカルコンピューター上など、ローカルイントラネット経由での接続を可能にします。</span><span class="sxs-lookup"><span data-stu-id="0d1ff-105">Instead of using physical connections, NDI® technology enables connectivity over a local intranet, including on a local machine.</span></span>

<span data-ttu-id="0d1ff-106">NewTek NDI®テクノロジは、ストリームのライブコンテンツを生成するための標準的な業界ソリューションとなっており、プロフェッショナルなブロードキャスト世界で深刻な認知度と導入を実現しています。</span><span class="sxs-lookup"><span data-stu-id="0d1ff-106">NewTek NDI® technology has become a standard industry solution for producing live content for streams and has gained significant awareness and adoption in the professional broadcast world.</span></span>

<span data-ttu-id="0d1ff-107">Skype では、2018遅刻の Skype に NDI®機能が追加されました。</span><span class="sxs-lookup"><span data-stu-id="0d1ff-107">Skype previously added NDI®-out functionality to Skype in late 2018.</span></span> <span data-ttu-id="0d1ff-108">Microsoft Teams はこの機能を活用して、会議の操作性を向上させています。</span><span class="sxs-lookup"><span data-stu-id="0d1ff-108">Microsoft Teams leverages this functionality to improve the meeting experience.</span></span>

<span data-ttu-id="0d1ff-109">NDI®テクノロジはローカルネットワークに限定され、ブロードキャストソリューションではなく、運用ワークフローの一部と見なされる必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d1ff-109">NDI® technology is limited to a local network and should only be considered a part of the production workflow, not a broadcast solution.</span></span>

## <a name="turn-on-ndi-technology"></a><span data-ttu-id="0d1ff-110">NDI®テクノロジを有効にする</span><span class="sxs-lookup"><span data-stu-id="0d1ff-110">Turn on NDI® technology</span></span>

<span data-ttu-id="0d1ff-111">NDI®テクノロジを有効にするには、2つの手順をユーザーに対して行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d1ff-111">NDI® technology requires two steps to be turned on for a user.</span></span>

1. <span data-ttu-id="0d1ff-112">テナント管理者は、CsTeamsMeetingPolicy で ' AllowNDIStreaming ' プロパティを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d1ff-112">The tenant admin must enable the 'AllowNDIStreaming' property in CsTeamsMeetingPolicy.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. <span data-ttu-id="0d1ff-113">この変更が設定された後、エンドユーザーは、特定のクライアントの [**設定**] 権限から ndi®テクノロジを有効にする必要があり  >  **Permissions**ます。</span><span class="sxs-lookup"><span data-stu-id="0d1ff-113">After this change has populated, the end user must turn on NDI® technology for their specific client from **Settings** > **Permissions**.</span></span>

<span data-ttu-id="0d1ff-114">ユーザーが会議に参加すると、会議がブロードキャストされていることを知らせるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0d1ff-114">When a user joins a meeting, they'll see a message that notifies them that the meeting is being broadcast.</span></span> <span data-ttu-id="0d1ff-115">ユーザーがブロードキャストに含まれないようにする必要がある場合は、会議から削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d1ff-115">If users don’t want to be included in the broadcast, they’ll need to drop from the meeting.</span></span>

<span data-ttu-id="0d1ff-116">次の画像は、Teams 会議でユーザーに表示されるバナーメッセージを示しています。</span><span class="sxs-lookup"><span data-stu-id="0d1ff-116">The following image shows the banner message that a user sees in a Teams meeting.</span></span>

![Teams 会議に表示される NDI®技術バナーの画像。](media/NDI-disclosure.png)

<span data-ttu-id="0d1ff-118">バナーには [Microsoft のプライバシーポリシー](https://aka.ms/teamsprivacy)へのリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0d1ff-118">The banner has a link to the [Microsoft privacy policy](https://aka.ms/teamsprivacy).</span></span>

## <a name="supported-locales-and-user-types"></a><span data-ttu-id="0d1ff-119">サポートされるロケールとユーザーの種類</span><span class="sxs-lookup"><span data-stu-id="0d1ff-119">Supported locales and user types</span></span>

<span data-ttu-id="0d1ff-120">NDI®テクノロジは、すべてのロケールでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0d1ff-120">NDI® technology is supported in all locales.</span></span> <span data-ttu-id="0d1ff-121">次のユーザーは、NDI®テクノロジストリームに含まれていますが、すべてのユーザーが NDI®テクノロジストリームにアクセスできるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="0d1ff-121">The following users are included in an NDI® technology stream, but not all users can access the NDI® technology stream:</span></span>

- <span data-ttu-id="0d1ff-122">テナント間–発信/テナント/ユーザー Id に基づいて提供される完全なサポート (会議ポリシーによって制御されます)</span><span class="sxs-lookup"><span data-stu-id="0d1ff-122">In-tenant – full support, delivered based on ring/tenantId/userId (controlled by Meetings Policy)</span></span>
- <span data-ttu-id="0d1ff-123">フェデレーション–ストリームアクセスなし (NDI®テクノロジを使用していても)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0d1ff-123">Federated – no stream access (even when they have NDI® technology on)<sup>1</sup></span></span>
- <span data-ttu-id="0d1ff-124">目につき-ストリームアクセスなし</span><span class="sxs-lookup"><span data-stu-id="0d1ff-124">Freemium - no stream access</span></span>
- <span data-ttu-id="0d1ff-125">匿名–ストリームにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="0d1ff-125">Anonymous – no stream access</span></span>
- <span data-ttu-id="0d1ff-126">ゲスト–ストリームへのアクセスはありません。</span><span class="sxs-lookup"><span data-stu-id="0d1ff-126">Guest – no stream access</span></span>  

<span data-ttu-id="0d1ff-127"><sup>1 つ</sup> のデバイスには、既定でオンになっている ndi®テクノロジ設定があります。</span><span class="sxs-lookup"><span data-stu-id="0d1ff-127"><sup>1</sup> Devices have an NDI® technology setting that is on by default.</span></span> <span data-ttu-id="0d1ff-128">会議の出席者が NDI®テクノロジを使用していないデバイスを使っている場合は、NDI®テクノロジを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d1ff-128">If a meeting participant is using a device with NDI® technology off, they'll need to turn on NDI® technology.</span></span>
