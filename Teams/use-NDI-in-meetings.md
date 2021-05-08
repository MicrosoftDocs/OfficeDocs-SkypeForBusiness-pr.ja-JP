---
title: NDI を使用Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aaglick
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Microsoft Teams で NDI を使用する方法についてMicrosoft Teams。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e26c6a7ad92353e083c67d0dad777e980a83fdfe
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598466"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a><span data-ttu-id="a862a-103">NDI の®を使用Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a862a-103">Use NDI® technology in Microsoft Teams</span></span>

 <span data-ttu-id="a862a-104">NewTek NDI® (ネットワーク デバイス インターフェイス) テクノロジは、メディア デバイス (スタジオ カメラやミキサーなど) を接続するための最新のソリューションです。</span><span class="sxs-lookup"><span data-stu-id="a862a-104">NewTek NDI® (Network Device Interface) technology is a modern solution for connecting media devices (such as a studio camera and mixer).</span></span> <span data-ttu-id="a862a-105">NDI® テクノロジでは、物理的な接続を使用する代わりに、ローカル コンピューターを含むローカル イントラネットを使用して接続できます。</span><span class="sxs-lookup"><span data-stu-id="a862a-105">Instead of using physical connections, NDI® technology enables connectivity over a local intranet, including on a local machine.</span></span>

<span data-ttu-id="a862a-106">NDI®は、ストリームのライブ コンテンツを生成するための標準的な業界標準ソリューションになり、プロのブロードキャストの世界で大きな認識と導入を獲得しています。</span><span class="sxs-lookup"><span data-stu-id="a862a-106">NDI® technology has become a standard industry solution for producing live content for streams and has gained significant awareness and adoption in the professional broadcast world.</span></span>

<span data-ttu-id="a862a-107">Skype 2018 年後半に NDI ®アウト機能が追加Skypeに追加されました。</span><span class="sxs-lookup"><span data-stu-id="a862a-107">Skype previously added NDI®-out functionality to Skype in late 2018.</span></span> <span data-ttu-id="a862a-108">Microsoft Teamsこの機能を使用して、会議のエクスペリエンスを向上します。</span><span class="sxs-lookup"><span data-stu-id="a862a-108">Microsoft Teams uses this functionality to improve the meeting experience.</span></span>

<span data-ttu-id="a862a-109">NDI®はローカル ネットワークに限定され、ブロードキャスト ソリューションではなく、実稼働ワークフローの一部と見なす必要があります。</span><span class="sxs-lookup"><span data-stu-id="a862a-109">NDI® technology is limited to a local network and should only be considered a part of the production workflow, not a broadcast solution.</span></span>

## <a name="turn-on-ndi-technology"></a><span data-ttu-id="a862a-110">NDI テクノロジを有効®する</span><span class="sxs-lookup"><span data-stu-id="a862a-110">Turn on NDI® technology</span></span>

<span data-ttu-id="a862a-111">NDI®、ユーザーに対して 2 つの手順を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a862a-111">NDI® technology requires two steps to be turned on for a user.</span></span>

1. <span data-ttu-id="a862a-112">テナント管理者は、CsTeamsMeetingPolicy で "AllowNDIStreaming" プロパティを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a862a-112">The tenant admin must enable the 'AllowNDIStreaming' property in CsTeamsMeetingPolicy.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. <span data-ttu-id="a862a-113">この変更が設定された後、エンド ユーザーは、特定のクライアントの NDI ® テクノロジを[アクセス許可] から有効設定  >  **があります**。</span><span class="sxs-lookup"><span data-stu-id="a862a-113">After this change has populated, the end user must turn on NDI® technology for their specific client from **Settings** > **Permissions**.</span></span>

<span data-ttu-id="a862a-114">ユーザーが会議に参加すると、会議がブロードキャスト中であることの通知メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a862a-114">When a user joins a meeting, they'll see a message that notifies them that the meeting is being broadcast.</span></span> <span data-ttu-id="a862a-115">ユーザーをブロードキャストに含めたくない場合は、会議から削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a862a-115">If users don’t want to be included in the broadcast, they’ll need to drop from the meeting.</span></span>

<span data-ttu-id="a862a-116">次の図は、ユーザーが会議中に表示するバナー メッセージTeamsしています。</span><span class="sxs-lookup"><span data-stu-id="a862a-116">The following image shows the banner message that a user sees in a Teams meeting.</span></span>

![彼は、®に表示される NDI の技術バナー Teamsします。](media/NDI-disclosure.png)

<span data-ttu-id="a862a-118">バナーには、Microsoft のプライバシー ポリシー [へのリンクがあります](https://aka.ms/teamsprivacy)。</span><span class="sxs-lookup"><span data-stu-id="a862a-118">The banner has a link to the [Microsoft privacy policy](https://aka.ms/teamsprivacy).</span></span>

> [!NOTE]
> <span data-ttu-id="a862a-119">NDI®セッションごとにのみアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="a862a-119">NDI® is activated per session only.</span></span> <span data-ttu-id="a862a-120">次のログインでは、ユーザーは NDI を使用する前にアクティブ化する®。</span><span class="sxs-lookup"><span data-stu-id="a862a-120">On the next login, the user must activate it before using NDI®.</span></span>

## <a name="supported-locales-and-user-types"></a><span data-ttu-id="a862a-121">サポートされている地域とユーザーの種類</span><span class="sxs-lookup"><span data-stu-id="a862a-121">Supported locales and user types</span></span>

<span data-ttu-id="a862a-122">NDI®は、すべての地域でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a862a-122">NDI® technology is supported in all locales.</span></span> <span data-ttu-id="a862a-123">NDI テクノロジ ストリームには次のユーザー®含まれますが、すべてのユーザーが NDI テクノロジ ストリームにアクセス®はありません。</span><span class="sxs-lookup"><span data-stu-id="a862a-123">The following users are included in an NDI® technology stream, but not all users can access the NDI® technology stream:</span></span>

- <span data-ttu-id="a862a-124">テナント内 – リング/tenantId/userId に基づいて配信される完全なサポート (会議ポリシーによって制御)</span><span class="sxs-lookup"><span data-stu-id="a862a-124">In-tenant – full support, delivered based on ring/tenantId/userId (controlled by Meetings Policy)</span></span>
- <span data-ttu-id="a862a-125">フェデレーション – ストリーム アクセスなし (NDI テクノロジ®場合でも)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a862a-125">Federated – no stream access (even when they have NDI® technology on)<sup>1</sup></span></span>
- <span data-ttu-id="a862a-126">プレミアム - ストリーム アクセスなし</span><span class="sxs-lookup"><span data-stu-id="a862a-126">Premium - no stream access</span></span>
- <span data-ttu-id="a862a-127">匿名 – ストリーム アクセスなし</span><span class="sxs-lookup"><span data-stu-id="a862a-127">Anonymous – no stream access</span></span>
- <span data-ttu-id="a862a-128">ゲスト – ストリーム アクセスなし</span><span class="sxs-lookup"><span data-stu-id="a862a-128">Guest – no stream access</span></span>  

<span data-ttu-id="a862a-129"><sup>1</sup> デバイスには、既定でオン® NDI のテクノロジ設定があります。</span><span class="sxs-lookup"><span data-stu-id="a862a-129"><sup>1</sup> Devices have an NDI® technology setting that is on by default.</span></span> <span data-ttu-id="a862a-130">会議の参加者が NDI テクノロジをオフにしたデバイス®場合は、NDI テクノロジを有効にする®があります。</span><span class="sxs-lookup"><span data-stu-id="a862a-130">If a meeting participant is using a device with NDI® technology off, they'll need to turn on NDI® technology.</span></span>
