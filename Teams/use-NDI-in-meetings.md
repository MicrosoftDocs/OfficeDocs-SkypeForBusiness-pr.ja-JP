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
ms.openlocfilehash: 86c0908b04b2eece835a747d9f57625878c15a99
ms.sourcegitcommit: 95989f1a93524a2025feeb50b8635da332961ea3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2020
ms.locfileid: "46588291"
---
# <a name="use-ndi-in-microsoft-teams"></a><span data-ttu-id="89bf5-103">Microsoft Teams で NDI を使用する</span><span class="sxs-lookup"><span data-stu-id="89bf5-103">Use NDI in Microsoft Teams</span></span>

[!INCLUDE [template](includes/preview-feature.md)]

<span data-ttu-id="89bf5-104">ネットワークデバイスインターフェイス (NDI) は、メディアデバイス (studio カメラやミキサーなど) に接続するための最新のソリューションです。</span><span class="sxs-lookup"><span data-stu-id="89bf5-104">Network Device Interface (NDI) is a modern solution for connecting media devices (such as a studio camera and mixer).</span></span> <span data-ttu-id="89bf5-105">NDI は、物理接続を使う代わりに、ローカルコンピューター上など、ローカルイントラネット経由の接続を可能にします。</span><span class="sxs-lookup"><span data-stu-id="89bf5-105">Instead of using physical connections, NDI enables connectivity over a local intranet, including on a local machine.</span></span>

<span data-ttu-id="89bf5-106">NewTek NDI®は、ストリームのライブコンテンツを生成するための標準的な業界ソリューションとなっており、プロフェッショナルなブロードキャスト世界で深刻な認知度と導入を実現しています。</span><span class="sxs-lookup"><span data-stu-id="89bf5-106">NewTek NDI® has become a standard industry solution for producing live content for streams and has gained significant awareness and adoption in the professional broadcast world.</span></span>

<span data-ttu-id="89bf5-107">Skype では、2018の遅刻で Skype に NDI アウト機能が追加されていました。</span><span class="sxs-lookup"><span data-stu-id="89bf5-107">Skype previously added NDI-Out functionality to Skype in late 2018.</span></span> <span data-ttu-id="89bf5-108">Microsoft Teams はこの機能を活用して、会議の操作性を向上させています。</span><span class="sxs-lookup"><span data-stu-id="89bf5-108">Microsoft Teams leverages this functionality to improve the meeting experience.</span></span>

<span data-ttu-id="89bf5-109">NDI はローカルネットワークに限定され、ブロードキャストソリューションではなく、実稼働ワークフローの一部と見なされる必要があります。</span><span class="sxs-lookup"><span data-stu-id="89bf5-109">NDI is limited to a local network and should only be considered a part of the production workflow, not a broadcast solution.</span></span>

## <a name="turn-on-ndi"></a><span data-ttu-id="89bf5-110">NDI を有効にする</span><span class="sxs-lookup"><span data-stu-id="89bf5-110">Turn on NDI</span></span>

<span data-ttu-id="89bf5-111">NDI を有効にするには、ユーザーに対して2つの手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89bf5-111">NDI requires two steps to be turned on for a user.</span></span>

1. <span data-ttu-id="89bf5-112">テナント管理者は、CsTeamsMeetingPolicy で ' AllowNDIStreaming ' プロパティを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="89bf5-112">The tenant admin must enable the 'AllowNDIStreaming' property in CsTeamsMeetingPolicy.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. <span data-ttu-id="89bf5-113">この変更が設定された後、エンドユーザーは、特定のクライアントに対して ndi を**設定**する必要があり  >  **Permissions**ます。</span><span class="sxs-lookup"><span data-stu-id="89bf5-113">After this change has populated, the end user must turn on NDI for their specific client from **Settings** > **Permissions**.</span></span>

<span data-ttu-id="89bf5-114">ユーザーが会議に参加すると、会議がブロードキャストされていることを知らせるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="89bf5-114">When a user joins a meeting, they'll see a message that notifies them that the meeting is being broadcast.</span></span> <span data-ttu-id="89bf5-115">ユーザーがブロードキャストに含まれないようにする必要がある場合は、会議から削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89bf5-115">If users don’t want to be included in the broadcast, they’ll need to drop from the meeting.</span></span>

<span data-ttu-id="89bf5-116">次の画像は、Teams 会議でユーザーに表示されるバナーメッセージを示しています。</span><span class="sxs-lookup"><span data-stu-id="89bf5-116">The following image shows the banner message that a user sees in a Teams meeting.</span></span>

![Teams 会議に表示される NDI バナーの画像。](media/NDI-disclosure.png)

<span data-ttu-id="89bf5-118">バナーには[Microsoft のプライバシーポリシー](https://aka.ms/teamsprivacy)へのリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="89bf5-118">The banner has a link to the [Microsoft privacy policy](https://aka.ms/teamsprivacy).</span></span>

## <a name="supported-locales-and-user-types"></a><span data-ttu-id="89bf5-119">サポートされるロケールとユーザーの種類</span><span class="sxs-lookup"><span data-stu-id="89bf5-119">Supported locales and user types</span></span>

<span data-ttu-id="89bf5-120">NDI は、すべてのロケールでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="89bf5-120">NDI is supported in all locales.</span></span> <span data-ttu-id="89bf5-121">NDI 会議では、次のユーザーがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="89bf5-121">The following users are supported in an NDI meeting:</span></span>

- <span data-ttu-id="89bf5-122">テナント間–発信/テナント/ユーザー Id に基づいて提供される完全なサポート (会議ポリシーによって制御されます)</span><span class="sxs-lookup"><span data-stu-id="89bf5-122">In-tenant – full support, delivered based on ring/tenantId/userId (controlled by Meetings Policy)</span></span>
- <span data-ttu-id="89bf5-123">フェデレーション–いいえ (NDI を使用していても)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="89bf5-123">Federated – no (even when they have NDI on)<sup>1</sup></span></span>
- <span data-ttu-id="89bf5-124">目につき-いいえ (既定値)</span><span class="sxs-lookup"><span data-stu-id="89bf5-124">Freemium - no (default value)</span></span>
- <span data-ttu-id="89bf5-125">匿名–いいえ (既定値)</span><span class="sxs-lookup"><span data-stu-id="89bf5-125">Anonymous – no (default value)</span></span>
- <span data-ttu-id="89bf5-126">Guest – no (既定値)</span><span class="sxs-lookup"><span data-stu-id="89bf5-126">Guest – no  (default value)</span></span>

<span data-ttu-id="89bf5-127"><sup>1 つ</sup>のデバイスには、既定でオンになっている ndi 設定があります。</span><span class="sxs-lookup"><span data-stu-id="89bf5-127"><sup>1</sup> Devices have an NDI setting that is on by default.</span></span> <span data-ttu-id="89bf5-128">会議の出席者が NDI off のデバイスを使用している場合は、NDI を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="89bf5-128">If a meeting participant is using a device with NDI off, they'll need to turn on NDI.</span></span>
