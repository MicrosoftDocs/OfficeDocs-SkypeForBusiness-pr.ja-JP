---
title: Skype のビジネスのサーバーの場所のポリシーを計画します。
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
description: ビジネス サーバーのエンタープライズ VoIP の Skype で、拡張緊急サービス (~ 9-1-1) の配置の場所のポリシーを計画する方法の詳細については、このトピックを参照してください。
ms.openlocfilehash: cbc4bdbf552c3839cef0701dcf3e47e4603a270e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20971168"
---
# <a name="plan-location-policies-for-skype-for-business-server"></a><span data-ttu-id="5825e-103">Skype のビジネスのサーバーの場所のポリシーを計画します。</span><span class="sxs-lookup"><span data-stu-id="5825e-103">Plan location policies for Skype for Business Server</span></span>
 
<span data-ttu-id="5825e-104">ビジネス サーバーのエンタープライズ VoIP の Skype で、拡張緊急サービス (~ 9-1-1) の配置の場所のポリシーを計画する方法の詳細については、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5825e-104">Read this topic to learn how to plan location policies for an enhanced emergency services (E9-1-1) deployment in Skype for Business Server Enterprise Voice.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="5825e-105">Skype ビジネス サーバーがクライアントの複数の緊急番号の構成をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="5825e-105">Skype for Business Server now supports the configuration of multiple emergency numbers for a client.</span></span> <span data-ttu-id="5825e-106">複数の緊急番号を構成する場合は、 [Skype ビジネス サーバーの複数の緊急番号に計画](multiple-emergency-numbers.md)し、[ビジネスの Skype で複数の緊急番号の構成](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md)内の情報に従ってください。</span><span class="sxs-lookup"><span data-stu-id="5825e-106">If you want to configure multiple emergency numbers, you must follow the information in [Plan for multiple emergency numbers in Skype for Business Server](multiple-emergency-numbers.md) and [Configure multiple emergency numbers in Skype for Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).</span></span> 
  
<span data-ttu-id="5825e-107">ビジネス コントロール パネルの Skype を使用して、または[新規 CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps)コマンドレットを使用して、場所のポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="5825e-107">You create location policies by using the Skype for Business Control Panel or by using the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="5825e-108">詳細については、 [Skype ビジネス サーバー用に作成する場所のポリシー](../../deploy/deploy-enterprise-voice/create-location-policies.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5825e-108">For more information, see [Create location policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md).</span></span>
  
<span data-ttu-id="5825e-109">場所ポリシーにはそれぞれ、以下の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5825e-109">Each location policy contains the following information:</span></span>
  
 <span data-ttu-id="5825e-110">**Enhanced 9-1-1 の有効化**</span><span class="sxs-lookup"><span data-stu-id="5825e-110">**Enable Enhanced 9-1-1**</span></span>
  
<span data-ttu-id="5825e-111">この値が有効になっていると、クライアントが緊急サービス (E9-1-1) に対して有効になります。</span><span class="sxs-lookup"><span data-stu-id="5825e-111">When this value is enabled, the client is enabled for enhanced emergency services (E9-1-1).</span></span> <span data-ttu-id="5825e-112">クライアントを登録すると位置情報サービスから場所を取得しようとして、緊急の呼び出しの一部として場所情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5825e-112">When a client registers, it attempts to acquire a location from the Location Information service and will include the location information as part of an emergency call.</span></span>
  
 <span data-ttu-id="5825e-113">**場所**</span><span class="sxs-lookup"><span data-stu-id="5825e-113">**Location**</span></span>
  
<span data-ttu-id="5825e-114">この設定は **Enable Enhanced 9-1-1** が有効の場合にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="5825e-114">This setting is used only when **Enable Enhanced 9-1-1** is enabled.</span></span>
  
<span data-ttu-id="5825e-115">**[場所]** 設定を構成して、次のようにクライアントの動作を定義できます。</span><span class="sxs-lookup"><span data-stu-id="5825e-115">You can configure the **Location** setting to define the client behavior as follows:</span></span>
  
- <span data-ttu-id="5825e-116">値を [**いいえ **] に設定すると、ユーザーは場所の入力を求められません。</span><span class="sxs-lookup"><span data-stu-id="5825e-116">Setting the value to **No** means that the user will not be prompted for a location.</span></span>
    
- <span data-ttu-id="5825e-117">値を [**はい **] に設定すると、ユーザーは場所の入力を求められますが、入力せずにプロンプトを閉じることもできます。</span><span class="sxs-lookup"><span data-stu-id="5825e-117">Setting the value to **Yes** means that the user will be prompted for a location, but can dismiss the prompt.</span></span>
    
- <span data-ttu-id="5825e-p104">値を [**免責事項 **] に設定すると、ユーザーは場所の入力を求められ、入力せずにプロンプトを閉じようとすると免責事項が表示されます。すべての場合において、ユーザーはクライアントを使用し続けることができます。</span><span class="sxs-lookup"><span data-stu-id="5825e-p104">Setting the value to **Disclaimer** means that the user will be prompted for a location and also will be shown a disclaimer if they try to dismiss the prompt. In all cases, the user can continue to use the client.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5825e-p105">E9-1-1 への対応が有効でない場合に、ユーザーが場所を手動で入力すると、免責事項テキストは表示されません。免責事項が既に表示されたユーザーには、免責事項テキストの更新は表示されません。</span><span class="sxs-lookup"><span data-stu-id="5825e-p105">The disclaimer text will not appear if a user manually entered a location before being enabled for E9-1-1. Updates to the disclaimer text will not be viewed by users that have already viewed the disclaimer.</span></span> 
  
 <span data-ttu-id="5825e-122">**拡張緊急サービス免責事項**</span><span class="sxs-lookup"><span data-stu-id="5825e-122">**Enhanced Emergency Service Disclaimer**</span></span>
  
<span data-ttu-id="5825e-123">この設定は、ユーザーが場所を入力せずにプロンプトを閉じた場合に表示される免責事項を指定します。</span><span class="sxs-lookup"><span data-stu-id="5825e-123">This setting specifies the disclaimer that users see if they dismiss the prompt for a location.</span></span> <span data-ttu-id="5825e-124">ビジネス サーバーの Skype で別のロケールまたはユーザーのセットを別の免責事項を設定するのに場所のポリシーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5825e-124">In Skype for Business Server, you can use location policy to set different disclaimers for different locales or different sets of users.</span></span>
  
 <span data-ttu-id="5825e-125">**緊急ダイヤル文字列 (E9-1-1 ダイヤル番号)**</span><span class="sxs-lookup"><span data-stu-id="5825e-125">**Emergency Dial String (E9-1-1 dial number)**</span></span>
  
<span data-ttu-id="5825e-126">この電話番号 (以下、先頭の「+」、ユーザーのダイヤル プランでどのような正規化を含むが、) の呼び出しが、緊急の呼び出しであることを示します。</span><span class="sxs-lookup"><span data-stu-id="5825e-126">This dial string (less the leading "+", but including any normalization done by the user's Dial Plan) signifies that a call is an emergency call.</span></span> <span data-ttu-id="5825e-127">**緊急ダイヤル文字列**を使用すると、クライアントによって場所とコールバック情報が緊急電話に含まれるようになります。</span><span class="sxs-lookup"><span data-stu-id="5825e-127">The **Emergency Dial String** causes the client to include location and callback information with the call.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5825e-128">組織では、行の外部アクセス プレフィックスを使用しない場合は、対応するダイヤル プランの正規化ルールを作成ビジネス サーバの Skype を実行するサーバーの発信ルーティングの呼び出しを送信する前に 911 の文字列に「+」を追加する必要はありません。「+」がビジネスのクライアントの場所のポリシーの結果としての Skype によって自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="5825e-128">If your organization does not use an external line access prefix, you do not need to create a corresponding Dial Plan normalization rule that adds a "+" to the 911 string prior to sending the call to Outbound Routing on a server running Skype for Business Server; the "+" will be automatically prepended by the Skype for Business client as a result of the location policy.</span></span> <span data-ttu-id="5825e-129">ただし、自分のサイトは、外部アクセス プレフィックスを使用する場合する必要があります、適用可能なダイヤル プラン ポリシーの外部アクセス プレフィックスを削除し、追加する正規化ルールを追加するのには、「+」です。</span><span class="sxs-lookup"><span data-stu-id="5825e-129">However, if your site uses an external access prefix, you need to add a normalization rule to the applicable Dial Plan policy that strips the external access prefix and adds the "+".</span></span> <span data-ttu-id="5825e-130">など 9 の外部アクセス プレフィックスを使用して、自分の場所と、ユーザーのダイヤル、緊急通話をするための 9 911、クライアントはポリシーを使用してそのダイヤル プランの作成これを正規化する前に +911 に、ダイヤル番号は、呼び出し元の場所のプロファイルのルートを評価します。</span><span class="sxs-lookup"><span data-stu-id="5825e-130">For example, if your location uses an external access prefix of 9 and a user dials 9 911 to place an emergency call, the client will use its Dial Plan policy to normalize this to +911 before the the dialed number is evaluated by the routes in the caller's location profile.</span></span> 
  
 <span data-ttu-id="5825e-131">**緊急ダイヤル文字列マスク (E9-1-1 ダイヤルマスク)**</span><span class="sxs-lookup"><span data-stu-id="5825e-131">**Emergency Dial String Masks (E9-1-1 dial mask)**</span></span>
  
<span data-ttu-id="5825e-132">セミコロンで区切られたリスト ダイヤル文字列の指定した**緊急ダイヤル文字列**に変換します。</span><span class="sxs-lookup"><span data-stu-id="5825e-132">A semicolon-separated list of dial strings that is translated into the specified **Emergency Dial String**.</span></span> <span data-ttu-id="5825e-133">などの可能性があります追加する 112、ヨーロッパのほとんどの緊急サービス番号であります。</span><span class="sxs-lookup"><span data-stu-id="5825e-133">For example, you may want to add 112, which is the emergency service number for most of Europe.</span></span> <span data-ttu-id="5825e-134">ヨーロッパからのビジネス ユーザーの訪問の Skype が不明なこと 911 は、米国の緊急電話番号では、112 をダイヤルし、同じ結果を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="5825e-134">A visiting Skype for Business user from Europe may not know that 911 is the U.S. emergency number, but they can dial 112 and get the same result.</span></span> <span data-ttu-id="5825e-135">緊急ダイヤル文字列を含めないでください、それぞれの番号の前に「+」と外部ライン アクセス コードを使用する場合、ユーザーのアクセス コードの桁数を取り除くのポリシーの [ダイヤル プランの正規化の規則があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5825e-135">As with the Emergency Dial String, do not include a "+" before each number, and if you use external line access codes, be sure there are normalization rules in the user's Dial Plan policy to strip off the access code digit.</span></span>
  
 <span data-ttu-id="5825e-136">**PSTN 使用法**</span><span class="sxs-lookup"><span data-stu-id="5825e-136">**PSTN usage**</span></span>
  
<span data-ttu-id="5825e-137">PSTN 使用法の名前です。PSTN 使用法には、緊急電話がどの SIP トランク、PSTN ゲートウェイ、または ELIN ゲートウェイを通るかを決定するルーティング パスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5825e-137">The name of the PSTN Usage that contains the routing paths that determine which SIP trunk, PSTN gateway, or ELIN gateway emergency calls will go to.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5825e-138">場所ポリシーに割り当てられる使用法は 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="5825e-138">Only one usage can be assigned to a location policy.</span></span> <span data-ttu-id="5825e-139">この PSTN 使用法では、ユーザーの音声ポリシーに割り当てられた PSTN 使用法をオーバーライドしますが、緊急電話番号や緊急ダイヤル文字列マスクのいずれかの呼び出しにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="5825e-139">This PSTN Usage overrides the PSTN Usages assigned to the user's voice policy, but applies only to calls placed to the Emergency Dial String or to one of the Emergency Dial String Masks.</span></span> 
  
 <span data-ttu-id="5825e-140">**通知 URI**</span><span class="sxs-lookup"><span data-stu-id="5825e-140">**Notification URI**</span></span>
  
<span data-ttu-id="5825e-p111">緊急電話が発信されたときに、インスタント メッセージング (IM) 通知を受信するセキュリティ担当者の 1 つ以上の SIP URI を指定します。配布グループがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="5825e-p111">Specifies one or more SIP URIs of the security personnel who receive an instant messaging (IM) notification when an emergency call is placed. Distribution groups are supported.</span></span>
  
 <span data-ttu-id="5825e-143">**会議 URI**</span><span class="sxs-lookup"><span data-stu-id="5825e-143">**Conference URI**</span></span>
  
<span data-ttu-id="5825e-144">緊急電話が発信されたときに、参加することが必要な DID (Direct Inward Dialing) の番号 (通常はセキュリティ デスクの電話番号) を指定します。</span><span class="sxs-lookup"><span data-stu-id="5825e-144">Specifies a direct inward dialing (DID) number (typically, a security desk number) that should be conferenced in when an emergency call is placed.</span></span> 
  
 <span data-ttu-id="5825e-145">**会議モード**</span><span class="sxs-lookup"><span data-stu-id="5825e-145">**Conference Mode**</span></span>
  
<span data-ttu-id="5825e-146">会議 URI が単方向または双方向の通信を使用して緊急電話に参加するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="5825e-146">Specifies if the conference URI will be conferenced into the emergency call by using one-way or two-way communication.</span></span> 
  
 <span data-ttu-id="5825e-147">**場所の更新間隔**</span><span class="sxs-lookup"><span data-stu-id="5825e-147">**Location Refresh Interval**</span></span>
  
<span data-ttu-id="5825e-148">場所情報サービスから場所の更新プログラムのクライアント要求の間の時間 (時間単位) を指定します。</span><span class="sxs-lookup"><span data-stu-id="5825e-148">Specifies the amount of time (in hours) between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="5825e-149">値は、1 ～ 12 の範囲で任意の値に設定できます。</span><span class="sxs-lookup"><span data-stu-id="5825e-149">The value can be set to any value between 1 and 12.</span></span> <span data-ttu-id="5825e-150">既定値は 4 です。</span><span class="sxs-lookup"><span data-stu-id="5825e-150">The default value is 4.</span></span>
  

