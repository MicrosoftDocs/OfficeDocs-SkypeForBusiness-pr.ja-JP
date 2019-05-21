---
title: Skype for Business Server の位置情報ポリシーを計画する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
description: このトピックでは、Skype for Business Server Enterprise Voice で強化された緊急サービス (E9) 展開の位置情報ポリシーを計画する方法について説明します。
ms.openlocfilehash: 8f21a5a0f54fbeaca4c46ed51bf4dafe4c2a3dcb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276755"
---
# <a name="plan-location-policies-for-skype-for-business-server"></a><span data-ttu-id="fe602-103">Skype for Business Server の位置情報ポリシーを計画する</span><span class="sxs-lookup"><span data-stu-id="fe602-103">Plan location policies for Skype for Business Server</span></span>
 
<span data-ttu-id="fe602-104">このトピックでは、Skype for Business Server Enterprise Voice で強化された緊急サービス (E9) 展開の位置情報ポリシーを計画する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fe602-104">Read this topic to learn how to plan location policies for an enhanced emergency services (E9-1-1) deployment in Skype for Business Server Enterprise Voice.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="fe602-105">Skype for Business Server で、クライアントの複数の緊急電話番号の構成がサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="fe602-105">Skype for Business Server now supports the configuration of multiple emergency numbers for a client.</span></span> <span data-ttu-id="fe602-106">複数の緊急電話番号を構成する場合は、Skype for business [Server の複数の緊急電話番号に](multiple-emergency-numbers.md)ついて、計画の情報に従って、 [skype for business で複数の緊急電話番号を設定](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe602-106">If you want to configure multiple emergency numbers, you must follow the information in [Plan for multiple emergency numbers in Skype for Business Server](multiple-emergency-numbers.md) and [Configure multiple emergency numbers in Skype for Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).</span></span> 
  
<span data-ttu-id="fe602-107">場所のポリシーを作成するには、[Skype for Business] コントロールパネルを使用するか、または[新しい-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="fe602-107">You create location policies by using the Skype for Business Control Panel or by using the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="fe602-108">詳細については、「 [Skype For Business Server で場所のポリシーを作成する](../../deploy/deploy-enterprise-voice/create-location-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe602-108">For more information, see [Create location policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md).</span></span>
  
<span data-ttu-id="fe602-109">場所ポリシーにはそれぞれ、以下の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="fe602-109">Each location policy contains the following information:</span></span>
  
 <span data-ttu-id="fe602-110">**Enhanced 9-1-1 の有効化**</span><span class="sxs-lookup"><span data-stu-id="fe602-110">**Enable Enhanced 9-1-1**</span></span>
  
<span data-ttu-id="fe602-111">この値が有効になっていると、クライアントが緊急サービス (E9-1-1) に対して有効になります。</span><span class="sxs-lookup"><span data-stu-id="fe602-111">When this value is enabled, the client is enabled for enhanced emergency services (E9-1-1).</span></span> <span data-ttu-id="fe602-112">クライアントが登録されると、位置情報サービスから場所を取得しようとし、緊急通話の一部として位置情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="fe602-112">When a client registers, it attempts to acquire a location from the Location Information service and will include the location information as part of an emergency call.</span></span>
  
 <span data-ttu-id="fe602-113">**場所**</span><span class="sxs-lookup"><span data-stu-id="fe602-113">**Location**</span></span>
  
<span data-ttu-id="fe602-114">この設定は **Enable Enhanced 9-1-1** が有効の場合にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="fe602-114">This setting is used only when **Enable Enhanced 9-1-1** is enabled.</span></span>
  
<span data-ttu-id="fe602-115">**[場所]** 設定を構成して、次のようにクライアントの動作を定義できます。</span><span class="sxs-lookup"><span data-stu-id="fe602-115">You can configure the **Location** setting to define the client behavior as follows:</span></span>
  
- <span data-ttu-id="fe602-116">値を [\*\*いいえ \*\*] に設定すると、ユーザーは場所の入力を求められません。</span><span class="sxs-lookup"><span data-stu-id="fe602-116">Setting the value to **No** means that the user will not be prompted for a location.</span></span>
    
- <span data-ttu-id="fe602-117">値を [\*\*はい \*\*] に設定すると、ユーザーは場所の入力を求められますが、入力せずにプロンプトを閉じることもできます。</span><span class="sxs-lookup"><span data-stu-id="fe602-117">Setting the value to **Yes** means that the user will be prompted for a location, but can dismiss the prompt.</span></span>
    
- <span data-ttu-id="fe602-p104">値を [\*\*免責事項 \*\*] に設定すると、ユーザーは場所の入力を求められ、入力せずにプロンプトを閉じようとすると免責事項が表示されます。すべての場合において、ユーザーはクライアントを使用し続けることができます。</span><span class="sxs-lookup"><span data-stu-id="fe602-p104">Setting the value to **Disclaimer** means that the user will be prompted for a location and also will be shown a disclaimer if they try to dismiss the prompt. In all cases, the user can continue to use the client.</span></span>
    
> [!NOTE]
> <span data-ttu-id="fe602-p105">E9-1-1 への対応が有効でない場合に、ユーザーが場所を手動で入力すると、免責事項テキストは表示されません。免責事項が既に表示されたユーザーには、免責事項テキストの更新は表示されません。</span><span class="sxs-lookup"><span data-stu-id="fe602-p105">The disclaimer text will not appear if a user manually entered a location before being enabled for E9-1-1. Updates to the disclaimer text will not be viewed by users that have already viewed the disclaimer.</span></span> 
  
 <span data-ttu-id="fe602-122">**拡張緊急サービス免責事項**</span><span class="sxs-lookup"><span data-stu-id="fe602-122">**Enhanced Emergency Service Disclaimer**</span></span>
  
<span data-ttu-id="fe602-123">この設定は、ユーザーが場所を入力せずにプロンプトを閉じた場合に表示される免責事項を指定します。</span><span class="sxs-lookup"><span data-stu-id="fe602-123">This setting specifies the disclaimer that users see if they dismiss the prompt for a location.</span></span> <span data-ttu-id="fe602-124">Skype for Business Server では、場所のポリシーを使って、ロケールやユーザーのセットごとに異なる免責事項を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="fe602-124">In Skype for Business Server, you can use location policy to set different disclaimers for different locales or different sets of users.</span></span>
  
 <span data-ttu-id="fe602-125">**緊急ダイヤル文字列 (E9-1-1 ダイヤル番号)**</span><span class="sxs-lookup"><span data-stu-id="fe602-125">**Emergency Dial String (E9-1-1 dial number)**</span></span>
  
<span data-ttu-id="fe602-126">このダイヤル文字列 (先頭が "+" より小さいが、ユーザーのダイヤルプランによる正規化を含む) は、通話が緊急通話であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="fe602-126">This dial string (less the leading "+", but including any normalization done by the user's Dial Plan) signifies that a call is an emergency call.</span></span> <span data-ttu-id="fe602-127">**緊急ダイヤル文字列**を使用すると、クライアントによって場所とコールバック情報が緊急電話に含まれるようになります。</span><span class="sxs-lookup"><span data-stu-id="fe602-127">The **Emergency Dial String** causes the client to include location and callback information with the call.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fe602-128">組織で外部回線アクセスプレフィックスを使用していない場合は、Skype for Business Server を実行しているサーバーで送信ルーティングに通話を送信する前に、対応するダイヤルプランの正規化ルールを作成して、911文字列に "+" を追加する必要はありません。"+" は、場所のポリシーの結果として、Skype for Business クライアントの先頭に自動的に付加されます。</span><span class="sxs-lookup"><span data-stu-id="fe602-128">If your organization does not use an external line access prefix, you do not need to create a corresponding Dial Plan normalization rule that adds a "+" to the 911 string prior to sending the call to Outbound Routing on a server running Skype for Business Server; the "+" will be automatically prepended by the Skype for Business client as a result of the location policy.</span></span> <span data-ttu-id="fe602-129">ただし、サイトで外部アクセスプレフィックスが使用されている場合は、その外部アクセスプレフィックスを取り除き、"+" を追加する、該当するダイヤルプランポリシーに正規化ルールを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe602-129">However, if your site uses an external access prefix, you need to add a normalization rule to the applicable Dial Plan policy that strips the external access prefix and adds the "+".</span></span> <span data-ttu-id="fe602-130">たとえば、場所で外部アクセスプレフィックス9を使用していて、ユーザーが 9 911 をダイヤルして緊急通話を発信している場合、クライアントは、ダイヤルプラン911ポリシーを使って、ダイヤル先の場所プロファイルのルートによってダイヤルされた番号を評価します。</span><span class="sxs-lookup"><span data-stu-id="fe602-130">For example, if your location uses an external access prefix of 9 and a user dials 9 911 to place an emergency call, the client will use its Dial Plan policy to normalize this to +911 before the dialed number is evaluated by the routes in the caller's location profile.</span></span> 
  
 <span data-ttu-id="fe602-131">**緊急ダイヤル文字列マスク (E9-1-1 ダイヤルマスク)**</span><span class="sxs-lookup"><span data-stu-id="fe602-131">**Emergency Dial String Masks (E9-1-1 dial mask)**</span></span>
  
<span data-ttu-id="fe602-132">指定された**緊急ダイヤル文字列**に変換されたダイヤル文字列のセミコロン区切りのリスト。</span><span class="sxs-lookup"><span data-stu-id="fe602-132">A semicolon-separated list of dial strings that is translated into the specified **Emergency Dial String**.</span></span> <span data-ttu-id="fe602-133">たとえば、ヨーロッパのほとんどの緊急サービス番号である112を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="fe602-133">For example, you may want to add 112, which is the emergency service number for most of Europe.</span></span> <span data-ttu-id="fe602-134">ヨーロッパの Skype for Business ユーザーは、911が米国の緊急電話番号であることを認識していませんが、112をダイヤルして、同じ結果を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="fe602-134">A visiting Skype for Business user from Europe may not know that 911 is the U.S. emergency number, but they can dial 112 and get the same result.</span></span> <span data-ttu-id="fe602-135">緊急ダイヤルの文字列の場合と同様に、各番号の前に "+" を含めないでください。また、外部回線のアクセスコードを使用している場合は、ユーザーのダイヤルプランポリシーに正規化ルールが適用されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="fe602-135">As with the Emergency Dial String, do not include a "+" before each number, and if you use external line access codes, be sure there are normalization rules in the user's Dial Plan policy to strip off the access code digit.</span></span>
  
 <span data-ttu-id="fe602-136">**PSTN 使用法**</span><span class="sxs-lookup"><span data-stu-id="fe602-136">**PSTN usage**</span></span>
  
<span data-ttu-id="fe602-137">PSTN 使用法の名前です。PSTN 使用法には、緊急電話がどの SIP トランク、PSTN ゲートウェイ、または ELIN ゲートウェイを通るかを決定するルーティング パスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="fe602-137">The name of the PSTN Usage that contains the routing paths that determine which SIP trunk, PSTN gateway, or ELIN gateway emergency calls will go to.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fe602-138">場所ポリシーに割り当てられる使用法は 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="fe602-138">Only one usage can be assigned to a location policy.</span></span> <span data-ttu-id="fe602-139">この PSTN 使用状況では、ユーザーのボイスポリシーに割り当てられている PSTN の使用状況は上書きされますが、緊急ダイヤルの文字列または緊急ダイヤルの文字列マスクへの通話にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="fe602-139">This PSTN Usage overrides the PSTN Usages assigned to the user's voice policy, but applies only to calls placed to the Emergency Dial String or to one of the Emergency Dial String Masks.</span></span> 
  
 <span data-ttu-id="fe602-140">**通知 URI**</span><span class="sxs-lookup"><span data-stu-id="fe602-140">**Notification URI**</span></span>
  
<span data-ttu-id="fe602-p111">緊急電話が発信されたときに、インスタント メッセージング (IM) 通知を受信するセキュリティ担当者の 1 つ以上の SIP URI を指定します。配布グループがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="fe602-p111">Specifies one or more SIP URIs of the security personnel who receive an instant messaging (IM) notification when an emergency call is placed. Distribution groups are supported.</span></span>
  
 <span data-ttu-id="fe602-143">**会議 URI**</span><span class="sxs-lookup"><span data-stu-id="fe602-143">**Conference URI**</span></span>
  
<span data-ttu-id="fe602-144">緊急電話が発信されたときに、参加することが必要な DID (Direct Inward Dialing) の番号 (通常はセキュリティ デスクの電話番号) を指定します。</span><span class="sxs-lookup"><span data-stu-id="fe602-144">Specifies a direct inward dialing (DID) number (typically, a security desk number) that should be conferenced in when an emergency call is placed.</span></span> 
  
 <span data-ttu-id="fe602-145">**会議モード**</span><span class="sxs-lookup"><span data-stu-id="fe602-145">**Conference Mode**</span></span>
  
<span data-ttu-id="fe602-146">会議 URI が単方向または双方向の通信を使用して緊急電話に参加するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="fe602-146">Specifies if the conference URI will be conferenced into the emergency call by using one-way or two-way communication.</span></span> 
  
 <span data-ttu-id="fe602-147">**場所の更新間隔**</span><span class="sxs-lookup"><span data-stu-id="fe602-147">**Location Refresh Interval**</span></span>
  
<span data-ttu-id="fe602-148">位置情報サービスからの位置情報更新に対するクライアント要求の時間 (時間) を指定します。</span><span class="sxs-lookup"><span data-stu-id="fe602-148">Specifies the amount of time (in hours) between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="fe602-149">値は、1 ～ 12 の範囲で任意の値に設定できます。</span><span class="sxs-lookup"><span data-stu-id="fe602-149">The value can be set to any value between 1 and 12.</span></span> <span data-ttu-id="fe602-150">既定値は 4 です。</span><span class="sxs-lookup"><span data-stu-id="fe602-150">The default value is 4.</span></span>
  

