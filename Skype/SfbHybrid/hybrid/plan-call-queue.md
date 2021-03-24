---
title: クラウド通話キューを計画する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Skype for Business Server 2019 でのクラウド自動応答の使用の概要。
ms.openlocfilehash: 62731691f4e56c923d2dd8fa6057f244776ec65b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110493"
---
# <a name="plan-cloud-call-queues"></a><span data-ttu-id="52559-103">クラウド通話キューの計画</span><span class="sxs-lookup"><span data-stu-id="52559-103">Plan Cloud call queues</span></span>

<span data-ttu-id="52559-104">クラウド通話キューは、顧客の呼び出しを受け入れ、案内応答メッセージを再生し、これらの呼び出しに応答するために事前に構成されたエージェントのリストを検索しながら、これらの呼び出しを待機キューに入れるサービスです。</span><span class="sxs-lookup"><span data-stu-id="52559-104">Cloud call queue is a service that accepts customer calls, plays a greeting message, and then places these calls in a wait queue while searching a pre-configured list of agents to answer these calls.</span></span> <span data-ttu-id="52559-105">メールが有効な配布リストまたはセキュリティ グループでエージェントのセットを定義できます。</span><span class="sxs-lookup"><span data-stu-id="52559-105">You can define the set of agents in mail-enabled distribution lists or security groups.</span></span> <span data-ttu-id="52559-106">組織には、1 つ以上の呼び出しキューを設定できます。</span><span class="sxs-lookup"><span data-stu-id="52559-106">Your organization can have one or many call queues.</span></span> <span data-ttu-id="52559-107">通話キューは、通常、自動応答と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="52559-107">Call queues are usually used in combination with auto attendants.</span></span>

<span data-ttu-id="52559-108">さらに、クラウド通話キューは次の機能を提供できます。</span><span class="sxs-lookup"><span data-stu-id="52559-108">In addition, Cloud call queues can provide:</span></span>

- <span data-ttu-id="52559-109">発信者が保留を待っている間の音楽</span><span class="sxs-lookup"><span data-stu-id="52559-109">Music while callers are waiting on hold</span></span>
- <span data-ttu-id="52559-110">通話キューの最大サイズ、タイムアウト、通話処理オプションのカスタマイズされた設定</span><span class="sxs-lookup"><span data-stu-id="52559-110">Customized settings for call queue maximum size, timeout, and call handling options</span></span>

<span data-ttu-id="52559-111">各通話キューには、Microsoft Teams 管理センターの通話キューに直接リンクされる Skype for Business Server 2019 システムのリソース アカウント **(「** リソース アカウントの構成」を [参照)](configure-onprem-ra.md)が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="52559-111">Each call queue is assigned a **resource account** (see [Configure resource accounts](configure-onprem-ra.md)) on your Skype for Business Server 2019 system that will be linked directly to a call queue in the Microsoft Teams admin center.</span></span> <span data-ttu-id="52559-112">通話 [キューの種類と](/MicrosoftTeams/create-a-phone-system-call-queue) 、通話キューに存在するオプションと機能の詳細については、「Create a Cloud call queue」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52559-112">See [Create a Cloud call queue](/MicrosoftTeams/create-a-phone-system-call-queue) for more detail on what call queues are and what options and features exist for call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="52559-113">複数の電話番号を通話キューに割り当てできますが、Microsoft サービス番号、ダイレクト ルーティング番号、またはハイブリッド番号である必要があります。</span><span class="sxs-lookup"><span data-stu-id="52559-113">You can assign multiple phone numbers to a call queue, but they must be Microsoft service numbers, Direct Routing numbers, or hybrid numbers.</span></span>

## <a name="requirements"></a><span data-ttu-id="52559-114">要件</span><span class="sxs-lookup"><span data-stu-id="52559-114">Requirements</span></span>

<span data-ttu-id="52559-115">次の要件では、サポートされているトポロジに Skype for Business Server 2019 が既に展開済みである必要があります。</span><span class="sxs-lookup"><span data-stu-id="52559-115">The following requirements assume that you already have Skype for Business Server 2019 deployed in a supported topology.</span></span>  <span data-ttu-id="52559-116">要件はシナリオによって異なります。</span><span class="sxs-lookup"><span data-stu-id="52559-116">Your requirements depend on your scenario:</span></span>

- <span data-ttu-id="52559-117">クラウド通話キューの新しい構成については、「リソース アカウントの構成」で説明されている [手順に従います](configure-onprem-ra.md)。</span><span class="sxs-lookup"><span data-stu-id="52559-117">For a new configuration of Cloud call queues, follow the steps outlined in [Configure resource accounts](configure-onprem-ra.md).</span></span> <span data-ttu-id="52559-118">オンラインまたは Skype for Business Server 2019 でリソース アカウントを作成する必要があります。また、電話番号を通話キューに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="52559-118">You will need to create resource accounts either online or in Skype for Business Server 2019, and you may also need to associate a phone number with the call queue.</span></span>

<span data-ttu-id="52559-119">上記の要件に加えて、Microsoft Cloud 通話キュー サービスに接続するように以下の要件を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52559-119">In addition to the requirements above, the below requirements must be configured to connect to the Microsoft Cloud call queue service:</span></span>

- <span data-ttu-id="52559-120">ハイブリッド接続。</span><span class="sxs-lookup"><span data-stu-id="52559-120">Hybrid connectivity.</span></span> <span data-ttu-id="52559-121">Skype for Business Server が既に展開済みで、オンプレミス ユーザーのクラウド通話キューを有効にする場合は、オンプレミス環境とオンライン環境の間にハイブリッド接続がセットアップされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="52559-121">If you already have Skype for Business Server deployed, and you want to enable Cloud call queues for your on-premises users, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="52559-122">これは、分割ドメイン構成と呼ばれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="52559-122">This is sometimes called a split domain configuration.</span></span>

   <span data-ttu-id="52559-123">詳細については、「Plan hybrid connectivity between Skype for Business Server and [Microsoft 365 or Office 365」](plan-hybrid-connectivity.md) および「Configure hybrid connectivity between Skype for Business Server and [Microsoft 365 or Office 365」](configure-hybrid-connectivity.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52559-123">For more information, see [Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="52559-124">電話番号をリソース アカウントに割り当てる場合は、コストフリーの電話システム仮想ユーザー ライセンスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="52559-124">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="52559-125">これにより、組織レベルの電話番号に電話システム機能が提供され、自動応答機能と通話キュー機能を作成できます。</span><span class="sxs-lookup"><span data-stu-id="52559-125">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>

- <span data-ttu-id="52559-126">各通話キューのオンプレミス [リソース アカウント](configure-onprem-ra.md) を作成し、必要に応じてライセンスと電話番号を割り当てる。</span><span class="sxs-lookup"><span data-stu-id="52559-126">Create an on-premises [resource account](configure-onprem-ra.md) for each call queue, and assign a license and phone number if required.</span></span>  

<span data-ttu-id="52559-127">ニーズを満たす堅実な構造と、顧客を効率的に導くスクリプトがある場合は、「リソース アカウントの構成」に  [進んでください](configure-onprem-ra.md)。</span><span class="sxs-lookup"><span data-stu-id="52559-127">When you have a solid structure that meets your needs and a script that guides customers efficiently, proceed to  [Configure resource accounts](configure-onprem-ra.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="52559-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="52559-128">See Also</span></span>

[<span data-ttu-id="52559-129">リソース アカウントの構成</span><span class="sxs-lookup"><span data-stu-id="52559-129">Configure resource accounts</span></span>](configure-onprem-ra.md)

[<span data-ttu-id="52559-130">電話ユーザー インターフェイスでカスタム プロンプト録音を有効にする</span><span class="sxs-lookup"><span data-stu-id="52559-130">Enable custom prompt recording using the telephone user interface</span></span>](/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[<span data-ttu-id="52559-131">クラウドの自動応答とは</span><span class="sxs-lookup"><span data-stu-id="52559-131">What are Cloud auto attendants?</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[<span data-ttu-id="52559-132">クラウドの自動応答をセットアップする</span><span class="sxs-lookup"><span data-stu-id="52559-132">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[<span data-ttu-id="52559-133">Skype for Business Server と Microsoft 365 または Office 365 の間のハイブリッド接続を計画する</span><span class="sxs-lookup"><span data-stu-id="52559-133">Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](plan-hybrid-connectivity.md)

[<span data-ttu-id="52559-134">Skype for Business Server と Microsoft 365 または Microsoft 365 または Office 365 間のハイブリッド接続を構成する</span><span class="sxs-lookup"><span data-stu-id="52559-134">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](configure-hybrid-connectivity.md)

[<span data-ttu-id="52559-135">Microsoft Teams のリソースのアカウントの管理</span><span class="sxs-lookup"><span data-stu-id="52559-135">Manage resource accounts in Microsoft Teams</span></span>](/MicrosoftTeams/manage-resource-accounts)