---
title: Skype for Business Server の場所ポリシーを計画する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
description: このトピックでは、Skype for Business Server エンタープライズ VoIP で拡張緊急サービス (E9-1-1) 展開の場所ポリシーを計画する方法について説明します。
ms.openlocfilehash: 1e89c2f0ea9d5115b29e9bc6d77b3863bb11888c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825537"
---
# <a name="plan-location-policies-for-skype-for-business-server"></a><span data-ttu-id="70723-103">Skype for Business Server の場所ポリシーを計画する</span><span class="sxs-lookup"><span data-stu-id="70723-103">Plan location policies for Skype for Business Server</span></span>
 
<span data-ttu-id="70723-104">このトピックでは、Skype for Business Server エンタープライズ VoIP で拡張緊急サービス (E9-1-1) 展開の場所ポリシーを計画する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="70723-104">Read this topic to learn how to plan location policies for an enhanced emergency services (E9-1-1) deployment in Skype for Business Server Enterprise Voice.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="70723-105">Skype for Business Server では、クライアントの複数の緊急電話番号の構成がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="70723-105">Skype for Business Server now supports the configuration of multiple emergency numbers for a client.</span></span> <span data-ttu-id="70723-106">複数の緊急電話番号を構成する場合は [、「Skype for Business Server](multiple-emergency-numbers.md) で複数の緊急電話番号を計画する」および「Skype for Business で複数の緊急電話番号を構成する」の情報に従う [必要があります](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="70723-106">If you want to configure multiple emergency numbers, you must follow the information in [Plan for multiple emergency numbers in Skype for Business Server](multiple-emergency-numbers.md) and [Configure multiple emergency numbers in Skype for Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).</span></span> 
  
<span data-ttu-id="70723-107">場所ポリシーは、Skype for Business コントロール パネルまたは [New-CsLocationPolicy コマンドレットを使用して作成](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) します。</span><span class="sxs-lookup"><span data-stu-id="70723-107">You create location policies by using the Skype for Business Control Panel or by using the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="70723-108">詳細については [、「Skype for Business Server での場所ポリシーの作成」を参照してください](../../deploy/deploy-enterprise-voice/create-location-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="70723-108">For more information, see [Create location policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md).</span></span>
  
<span data-ttu-id="70723-109">場所ポリシーにはそれぞれ、以下の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="70723-109">Each location policy contains the following information:</span></span>
  
 <span data-ttu-id="70723-110">**Enhanced 9-1-1 を有効にする**</span><span class="sxs-lookup"><span data-stu-id="70723-110">**Enable Enhanced 9-1-1**</span></span>
  
<span data-ttu-id="70723-111">この値を有効にすると、クライアントは拡張緊急サービス (E9-1-1) に対して有効になります。</span><span class="sxs-lookup"><span data-stu-id="70723-111">When this value is enabled, the client is enabled for enhanced emergency services (E9-1-1).</span></span> <span data-ttu-id="70723-112">クライアントが登録すると、場所情報サービスから場所を取得しようとして、緊急電話の一部として場所情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="70723-112">When a client registers, it attempts to acquire a location from the Location Information service and will include the location information as part of an emergency call.</span></span>
  
 <span data-ttu-id="70723-113">**Location**</span><span class="sxs-lookup"><span data-stu-id="70723-113">**Location**</span></span>
  
<span data-ttu-id="70723-114">この設定は、Enable **Enhanced 9-1-1 が** 有効になっている場合にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="70723-114">This setting is used only when **Enable Enhanced 9-1-1** is enabled.</span></span>
  
<span data-ttu-id="70723-115">[場所] 設定を **構成** して、クライアントの動作を次のように定義できます。</span><span class="sxs-lookup"><span data-stu-id="70723-115">You can configure the **Location** setting to define the client behavior as follows:</span></span>
  
- <span data-ttu-id="70723-116">値を [**いいえ**] に設定すると、ユーザーは場所の入力を求められません。</span><span class="sxs-lookup"><span data-stu-id="70723-116">Setting the value to **No** means that the user will not be prompted for a location.</span></span>
    
- <span data-ttu-id="70723-117">値を [**はい**] に設定すると、ユーザーは場所の入力を求められますが、入力せずにプロンプトを閉じることもできます。</span><span class="sxs-lookup"><span data-stu-id="70723-117">Setting the value to **Yes** means that the user will be prompted for a location, but can dismiss the prompt.</span></span>
    
- <span data-ttu-id="70723-118">値を [**免責事項**] に設定すると、ユーザーは場所の入力を求められ、入力せずにプロンプトを閉じようとすると免責事項が表示されます。</span><span class="sxs-lookup"><span data-stu-id="70723-118">Setting the value to **Disclaimer** means that the user will be prompted for a location and also will be shown a disclaimer if they try to dismiss the prompt.</span></span> <span data-ttu-id="70723-119">いずれの場合でも、ユーザーはクライアントを引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="70723-119">In all cases, the user can continue to use the client.</span></span>
    
> [!NOTE]
> <span data-ttu-id="70723-p105">E9-1-1 への対応が有効でない場合に、ユーザーが場所を手動で入力すると、免責事項テキストは表示されません。免責事項が既に表示されたユーザーには、免責事項テキストの更新は表示されません。</span><span class="sxs-lookup"><span data-stu-id="70723-p105">The disclaimer text will not appear if a user manually entered a location before being enabled for E9-1-1. Updates to the disclaimer text will not be viewed by users that have already viewed the disclaimer.</span></span> 
  
 <span data-ttu-id="70723-122">**拡張緊急サービス免責事項**</span><span class="sxs-lookup"><span data-stu-id="70723-122">**Enhanced Emergency Service Disclaimer**</span></span>
  
<span data-ttu-id="70723-123">この設定は、ユーザーが場所を入力せずにプロンプトを閉じた場合に表示される免責事項を指定します。</span><span class="sxs-lookup"><span data-stu-id="70723-123">This setting specifies the disclaimer that users see if they dismiss the prompt for a location.</span></span> <span data-ttu-id="70723-124">Skype for Business Server では、場所ポリシーを使用して、異なるローカルまたは異なるユーザー のセットに異なる免責事項を設定できます。</span><span class="sxs-lookup"><span data-stu-id="70723-124">In Skype for Business Server, you can use location policy to set different disclaimers for different locales or different sets of users.</span></span>
  
 <span data-ttu-id="70723-125">**緊急ダイヤル文字列 (E9-1-1 ダイヤル番号)**</span><span class="sxs-lookup"><span data-stu-id="70723-125">**Emergency Dial String (E9-1-1 dial number)**</span></span>
  
<span data-ttu-id="70723-126">このダイヤル文字列 (先頭の "+" は少なく、ユーザーのダイヤル プランによって行われた正規化を含む) は、通話が緊急電話を表します。</span><span class="sxs-lookup"><span data-stu-id="70723-126">This dial string (less the leading "+", but including any normalization done by the user's Dial Plan) signifies that a call is an emergency call.</span></span> <span data-ttu-id="70723-127">**緊急ダイヤル文字列** を使用すると、クライアントによって場所とコールバック情報が緊急電話に含まれるようになります。</span><span class="sxs-lookup"><span data-stu-id="70723-127">The **Emergency Dial String** causes the client to include location and callback information with the call.</span></span>
  
> [!NOTE]
> <span data-ttu-id="70723-128">組織で外部回線アクセス プレフィックスを使用しない場合は、Skype for Business Server を実行しているサーバー上の発信ルーティングに通話を送信する前に、911 文字列に "+" を追加する対応するダイヤル プラン正規化ルールを作成する必要があります。場所ポリシーの結果、Skype for Business クライアントによって "+" が自動的に先頭に追加されます。</span><span class="sxs-lookup"><span data-stu-id="70723-128">If your organization does not use an external line access prefix, you do not need to create a corresponding Dial Plan normalization rule that adds a "+" to the 911 string prior to sending the call to Outbound Routing on a server running Skype for Business Server; the "+" will be automatically prepended by the Skype for Business client as a result of the location policy.</span></span> <span data-ttu-id="70723-129">ただし、サイトで外部アクセス プレフィックスを使用する場合は、外部アクセス プレフィックスを削除して "+" を追加する、該当するダイヤル プラン ポリシーに正規化ルールを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="70723-129">However, if your site uses an external access prefix, you need to add a normalization rule to the applicable Dial Plan policy that strips the external access prefix and adds the "+".</span></span> <span data-ttu-id="70723-130">たとえば、場所で外部アクセス プレフィックス 9 を使用し、ユーザーが 9 911 をダイヤルして緊急電話を発信する場合、クライアントはダイヤル プラン ポリシーを使用してこれを +911 に正規化してから、発信者の場所プロファイルのルートでダイヤル番号が評価されます。</span><span class="sxs-lookup"><span data-stu-id="70723-130">For example, if your location uses an external access prefix of 9 and a user dials 9 911 to place an emergency call, the client will use its Dial Plan policy to normalize this to +911 before the dialed number is evaluated by the routes in the caller's location profile.</span></span> 
  
 <span data-ttu-id="70723-131">**緊急ダイヤル文字列マスク (E9-1-1 ダイヤル マスク)**</span><span class="sxs-lookup"><span data-stu-id="70723-131">**Emergency Dial String Masks (E9-1-1 dial mask)**</span></span>
  
<span data-ttu-id="70723-132">指定された緊急ダイヤル文字列に変換されるダイヤル文字列のセミコロンで区切られた **リスト**。</span><span class="sxs-lookup"><span data-stu-id="70723-132">A semicolon-separated list of dial strings that is translated into the specified **Emergency Dial String**.</span></span> <span data-ttu-id="70723-133">たとえば、ヨーロッパの大部分の緊急サービス番号である 112 を追加できます。</span><span class="sxs-lookup"><span data-stu-id="70723-133">For example, you may want to add 112, which is the emergency service number for most of Europe.</span></span> <span data-ttu-id="70723-134">ヨーロッパから Skype for Business にアクセスしているユーザーは、911 が米国の緊急電話番号であるのを知らない場合がありますが、112 をダイヤルして同じ結果を得られます。</span><span class="sxs-lookup"><span data-stu-id="70723-134">A visiting Skype for Business user from Europe may not know that 911 is the U.S. emergency number, but they can dial 112 and get the same result.</span></span> <span data-ttu-id="70723-135">緊急ダイヤル文字列の場合と同様に、各番号の前に "+" を含めず、外部回線アクセス コードを使用する場合は、ユーザーのダイヤル プラン ポリシーにアクセス コードの数字を削除する正規化ルールが含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="70723-135">As with the Emergency Dial String, do not include a "+" before each number, and if you use external line access codes, be sure there are normalization rules in the user's Dial Plan policy to strip off the access code digit.</span></span>
  
 <span data-ttu-id="70723-136">**PSTN 使用法**</span><span class="sxs-lookup"><span data-stu-id="70723-136">**PSTN usage**</span></span>
  
<span data-ttu-id="70723-137">緊急通話を行う SIP トランク、PSTN ゲートウェイ、または ELIN ゲートウェイを決定するルーティング パスを含む PSTN 使用法の名前。</span><span class="sxs-lookup"><span data-stu-id="70723-137">The name of the PSTN Usage that contains the routing paths that determine which SIP trunk, PSTN gateway, or ELIN gateway emergency calls will go to.</span></span>
  
> [!NOTE]
> <span data-ttu-id="70723-138">場所ポリシーに割り当て可能な使用法は 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="70723-138">Only one usage can be assigned to a location policy.</span></span> <span data-ttu-id="70723-139">この PSTN 使用法は、ユーザーの音声ポリシーに割り当てられた PSTN 使用法より優先されますが、緊急ダイヤル文字列または緊急ダイヤル文字列マスクの 1 つへの通話にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="70723-139">This PSTN Usage overrides the PSTN Usages assigned to the user's voice policy, but applies only to calls placed to the Emergency Dial String or to one of the Emergency Dial String Masks.</span></span> 
  
 <span data-ttu-id="70723-140">**通知 URI**</span><span class="sxs-lookup"><span data-stu-id="70723-140">**Notification URI**</span></span>
  
<span data-ttu-id="70723-141">緊急電話の際にインスタント メッセージング (IM) 通知を受信するセキュリティ担当者の 1 つ以上の SIP URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="70723-141">Specifies one or more SIP URIs of the security personnel who receive an instant messaging (IM) notification when an emergency call is placed.</span></span> <span data-ttu-id="70723-142">配布グループはサポートされています。</span><span class="sxs-lookup"><span data-stu-id="70723-142">Distribution groups are supported.</span></span>
  
 <span data-ttu-id="70723-143">[**会議 URI**]</span><span class="sxs-lookup"><span data-stu-id="70723-143">**Conference URI**</span></span>
  
<span data-ttu-id="70723-144">緊急電話を発信するときに電話会議を行う必要がある、直接の内向きダイヤル (DID) 番号 (通常はセキュリティ デスク番号) を指定します。</span><span class="sxs-lookup"><span data-stu-id="70723-144">Specifies a direct inward dialing (DID) number (typically, a security desk number) that should be conferenced in when an emergency call is placed.</span></span> 
  
 <span data-ttu-id="70723-145">**会議モード**</span><span class="sxs-lookup"><span data-stu-id="70723-145">**Conference Mode**</span></span>
  
<span data-ttu-id="70723-146">電話会議 URI を一方通行または二者間通信を使用して緊急電話に電話会議を行う場合に指定します。</span><span class="sxs-lookup"><span data-stu-id="70723-146">Specifies if the conference URI will be conferenced into the emergency call by using one-way or two-way communication.</span></span> 
  
 <span data-ttu-id="70723-147">**場所の更新間隔**</span><span class="sxs-lookup"><span data-stu-id="70723-147">**Location Refresh Interval**</span></span>
  
<span data-ttu-id="70723-148">場所情報サービスからの場所の更新に対するクライアント要求間の時間 (時間) を指定します。</span><span class="sxs-lookup"><span data-stu-id="70723-148">Specifies the amount of time (in hours) between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="70723-149">この値は、1 ~ 12 の任意の値に設定できます。</span><span class="sxs-lookup"><span data-stu-id="70723-149">The value can be set to any value between 1 and 12.</span></span> <span data-ttu-id="70723-150">既定値は 4 です。</span><span class="sxs-lookup"><span data-stu-id="70723-150">The default value is 4.</span></span>
  

