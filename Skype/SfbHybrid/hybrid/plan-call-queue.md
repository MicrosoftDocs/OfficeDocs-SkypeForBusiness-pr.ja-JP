---
title: Cloud call queue を計画する
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Skype for Business Server 2019 でのクラウド自動応答の使用の概要。
ms.openlocfilehash: bcb1f14ed9dfc3471b146a318a97700c362f115c
ms.sourcegitcommit: 868db85f0126e8f56d711ea590ad44acce8f96f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2019
ms.locfileid: "36160665"
---
# <a name="plan-cloud-call-queues"></a><span data-ttu-id="610c1-103">クラウド通話キューを計画する</span><span class="sxs-lookup"><span data-stu-id="610c1-103">Plan Cloud call queues</span></span>

<span data-ttu-id="610c1-104">Cloud call queue は、顧客からの通話を受け付け、案内応答メッセージを再生した後、これらの呼び出しを待機キューに格納し、これらの呼び出しに応答するために事前に構成されたエージェントの一覧を検索するサービスです。</span><span class="sxs-lookup"><span data-stu-id="610c1-104">Cloud call queue is a service that accepts customer calls, plays a greeting message, and then places these calls in a wait queue while searching a pre-configured list of agents to answer these calls.</span></span> <span data-ttu-id="610c1-105">メールが有効な配布リストまたはセキュリティグループでは、一連のエージェントを定義できます。</span><span class="sxs-lookup"><span data-stu-id="610c1-105">You can define the set of agents in mail-enabled distribution lists or security groups.</span></span> <span data-ttu-id="610c1-106">組織は、1つまたは複数の通話キューを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="610c1-106">Your organization can have one or many call queues.</span></span> <span data-ttu-id="610c1-107">通常、通話キューは自動応答と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="610c1-107">Call queues are usually used in combination with auto attendants.</span></span>

<span data-ttu-id="610c1-108">さらに、クラウド通話キューは次の機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="610c1-108">In addition, Cloud call queues can provide:</span></span>

- <span data-ttu-id="610c1-109">発信者が保留状態になっているときの音楽</span><span class="sxs-lookup"><span data-stu-id="610c1-109">Music while callers are waiting on hold</span></span>
- <span data-ttu-id="610c1-110">呼び出しキューの最大サイズ、タイムアウト、および通話処理オプションのカスタマイズされた設定</span><span class="sxs-lookup"><span data-stu-id="610c1-110">Customized settings for call queue maximum size, timeout, and call handling options</span></span>

<span data-ttu-id="610c1-111">各呼び出しキューには、Skype for Business Server 2019 システムの**リソースアカウント**(「リソースアカウントの[構成](configure-onprem-ra.md)」を参照) が割り当てられています。これは、Microsoft Teams 管理センターの通話キューに直接リンクされます。</span><span class="sxs-lookup"><span data-stu-id="610c1-111">Each call queue is assigned a **resource account** (see [Configure resource accounts](configure-onprem-ra.md)) on your Skype for Business Server 2019 system that will be linked directly to a call queue in the Microsoft Teams admin center.</span></span> <span data-ttu-id="610c1-112">呼び出しキューの詳細については「 [Create a Cloud call queue](/MicrosoftTeams/create-a-phone-system-call-queue) 」と、通話キューに存在するオプションと機能を参照してください。</span><span class="sxs-lookup"><span data-stu-id="610c1-112">See [Create a Cloud call queue](/MicrosoftTeams/create-a-phone-system-call-queue) for more detail on what call queues are and what options and features exist for call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="610c1-113">複数の電話番号を通話キューに割り当てることができますが、それらは Microsoft サービス番号またはハイブリッド番号である必要があります。</span><span class="sxs-lookup"><span data-stu-id="610c1-113">You can assign multiple phone numbers to a call queue, but they must be Microsoft service numbers or hybrid numbers.</span></span>

## <a name="requirements"></a><span data-ttu-id="610c1-114">要件</span><span class="sxs-lookup"><span data-stu-id="610c1-114">Requirements</span></span>

<span data-ttu-id="610c1-115">次の要件は、サポートされているトポロジで Skype for Business Server 2019 が既に展開されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="610c1-115">The following requirements assume that you already have Skype for Business Server 2019 deployed in a supported topology.</span></span>  <span data-ttu-id="610c1-116">要件は、シナリオによって異なります。</span><span class="sxs-lookup"><span data-stu-id="610c1-116">Your requirements depend on your scenario:</span></span>

- <span data-ttu-id="610c1-117">クラウド通話キューの新しい構成については、「 [Configure resource accounts](configure-onprem-ra.md)」に記載されている手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="610c1-117">For a new configuration of Cloud call queues, follow the steps outlined in [Configure resource accounts](configure-onprem-ra.md).</span></span> <span data-ttu-id="610c1-118">リソースアカウントは、オンラインまたは Skype for Business Server 2019 で作成する必要があります。また、電話番号を通話キューに関連付ける必要がある場合もあります。</span><span class="sxs-lookup"><span data-stu-id="610c1-118">You will need to create resource accounts either online or in Skype for Business Server 2019, and you may also need to associate a phone number with the call queue.</span></span>

<span data-ttu-id="610c1-119">上記の要件に加えて、次の要件を構成して、Microsoft Cloud call queue service に接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="610c1-119">In addition to the requirements above, the below requirements must be configured to connect to the Microsoft Cloud call queue service:</span></span>

- <span data-ttu-id="610c1-120">ハイブリッド接続。</span><span class="sxs-lookup"><span data-stu-id="610c1-120">Hybrid connectivity.</span></span> <span data-ttu-id="610c1-121">Skype for Business Server を既に展開しており、オンプレミスのユーザーのためにクラウドコールキューを有効にする場合は、オンプレミスの環境とオンライン環境の間でハイブリッド接続が設定されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="610c1-121">If you already have Skype for Business Server deployed, and you want to enable Cloud call queues for your on-premises users, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="610c1-122">これは、分割ドメイン構成と呼ばれることがあります。</span><span class="sxs-lookup"><span data-stu-id="610c1-122">This is sometimes called a split domain configuration.</span></span>

   <span data-ttu-id="610c1-123">詳細については、「skype for business [server と office 365 の間のハイブリッド接続を計画](plan-hybrid-connectivity.md)する」および「 [Skype for Business server と office 365 の間のハイブリッド接続を構成する](configure-hybrid-connectivity.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="610c1-123">For more information, see [Plan hybrid connectivity between Skype for Business Server and Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="610c1-124">リソースアカウントに電話番号を割り当てる場合は、費用がかからない電話システムの仮想ユーザーライセンスを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="610c1-124">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="610c1-125">これにより、組織レベルで電話番号に電話システム機能が提供され、自動応答と通話キュー機能を作成できるようになります。</span><span class="sxs-lookup"><span data-stu-id="610c1-125">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>

- <span data-ttu-id="610c1-126">各呼び出しキューに対してオンプレミスの[リソースアカウント](configure-onprem-ra.md)を作成し、必要に応じてライセンスと電話番号を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="610c1-126">Create an on-premises [resource account](configure-onprem-ra.md) for each call queue, and assign a license and phone number if required.</span></span>  

## <a name="additional-planning-resources"></a><span data-ttu-id="610c1-127">その他の計画に関するリソース</span><span class="sxs-lookup"><span data-stu-id="610c1-127">Additional planning resources</span></span>

<span data-ttu-id="610c1-128">「[小規模企業の例-自動応答の設定](/microsoftteams/tutorial-org-aa)」というタイトルのチュートリアルでは、ユーザーのニーズに関する情報の収集、自動応答とユーザーの構成 (および場合によっては呼び出しキュー) の計画、およびメニュープロンプトの作成のプロセスについて説明します。オンライン管理センターでプランを実装します。</span><span class="sxs-lookup"><span data-stu-id="610c1-128">The tutorial titled [Small business example - Set up an auto attendant](/microsoftteams/tutorial-org-aa) goes through the process of gathering information about user needs, planning a structure of auto attendants and users (and possibly call queues), writing the menu prompts, and implementing the plan in the Online Admin center.</span></span> <span data-ttu-id="610c1-129">チュートリアルを確認し、演習を使用してプランを作成します。</span><span class="sxs-lookup"><span data-stu-id="610c1-129">review the tutorial and use the exercises there t create your plan.</span></span>

<span data-ttu-id="610c1-130">お客様のニーズを満たす堅固な構造を持っていて、顧客に効率的に対応するスクリプトを実行している場合は、「[リソースアカウントを構成](configure-onprem-ra.md)する」に進みます。</span><span class="sxs-lookup"><span data-stu-id="610c1-130">When you have a solid structure that meets your needs and a script that guides customers efficiently, proceed to  [Configure resource accounts](configure-onprem-ra.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="610c1-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="610c1-131">See Also</span></span>

[<span data-ttu-id="610c1-132">リソースアカウントを構成する</span><span class="sxs-lookup"><span data-stu-id="610c1-132">Configure resource accounts</span></span>](configure-onprem-ra.md)

[<span data-ttu-id="610c1-133">電話ユーザー インターフェイスでカスタム プロンプト録音を有効にする</span><span class="sxs-lookup"><span data-stu-id="610c1-133">Enable custom prompt recording using the telephone user interface</span></span>](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[<span data-ttu-id="610c1-134">クラウド自動応答とは</span><span class="sxs-lookup"><span data-stu-id="610c1-134">What are Cloud auto attendants?</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[<span data-ttu-id="610c1-135">クラウドの自動応答を設定する</span><span class="sxs-lookup"><span data-stu-id="610c1-135">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[<span data-ttu-id="610c1-136">Skype for Business Server と Office 365 の間のハイブリッド接続を計画する</span><span class="sxs-lookup"><span data-stu-id="610c1-136">Plan hybrid connectivity between Skype for Business Server and Office 365</span></span>](plan-hybrid-connectivity.md)

[<span data-ttu-id="610c1-137">Skype for Business Server と Office 365 の間のハイブリッド接続を構成する</span><span class="sxs-lookup"><span data-stu-id="610c1-137">Configure hybrid connectivity between Skype for Business Server and Office 365</span></span>](configure-hybrid-connectivity.md)

[<span data-ttu-id="610c1-138">Microsoft Teams でリソースアカウントを管理する</span><span class="sxs-lookup"><span data-stu-id="610c1-138">Manage resource accounts in Microsoft Teams</span></span>](/MicrosoftTeams/manage-resource-accounts)
