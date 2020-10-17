---
title: 'Lync Server 2013: 場所ポリシーの定義'
description: 'Lync Server 2013: 場所のポリシーの定義。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the location policy
ms:assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398962(v=OCS.15)
ms:contentKeyID: 48185553
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fddd5b2ce34e44240162e886672a236789857e7b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567543"
---
# <a name="defining-the-location-policy-for-lync-server-2013"></a><span data-ttu-id="54be9-103">Lync Server 2013 の場所ポリシーの定義</span><span class="sxs-lookup"><span data-stu-id="54be9-103">Defining the location policy for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54be9-104">_**トピックの最終更新日:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="54be9-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="54be9-105">場所ポリシーにはそれぞれ、以下の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="54be9-105">Each location policy contains the following information:</span></span>

  - <span data-ttu-id="54be9-106">**緊急サービスへの対応有効**</span><span class="sxs-lookup"><span data-stu-id="54be9-106">**Emergency Services Enabled**</span></span>  
    <span data-ttu-id="54be9-107">この値を [**はい**] に設定すると、クライアントが E9-1-1 に対して有効になります。</span><span class="sxs-lookup"><span data-stu-id="54be9-107">When this value is **Yes**, the client is enabled for E9-1-1.</span></span> <span data-ttu-id="54be9-108">クライアントは、登録時に場所情報サービスから場所を取得しようと試み、緊急電話の一部として場所情報を含めます。</span><span class="sxs-lookup"><span data-stu-id="54be9-108">When a client registers, it attempts to acquire a location from the Location Information service and will include the location information as part of an emergency call.</span></span>

<!-- end list -->

  - <span data-ttu-id="54be9-109">**場所必須**</span><span class="sxs-lookup"><span data-stu-id="54be9-109">**Location Required**</span></span>  
    <span data-ttu-id="54be9-110">この設定は、[**利用可能なサービスを有効**にする   **] が [はい]** に設定されている場合のみ使用します。</span><span class="sxs-lookup"><span data-stu-id="54be9-110">This setting is used only when **Emergence Services Enabled** is set to **Yes**.</span></span>
    
    <span data-ttu-id="54be9-p102">[**場所 (必須)**] 設定を構成して、クライアントの動作を定義できます。値を [**いいえ**] に設定すると、ユーザーは場所の入力を求められません。値を [**はい**] に設定すると、ユーザーは場所の入力を求められますが、入力せずにプロンプトを閉じることもできます。値を [**免責事項**] に設定すると、ユーザーは場所の入力を求められ、入力せずにプロンプトを閉じようとすると免責事項が表示されます。いずれの場合でも、ユーザーはクライアントを引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="54be9-p102">You can configure the **Location Required** setting to define the client behavior. Setting the value to **No** means that the user will not be prompted for a location. Setting the value to **Yes** means that the user will be prompted for a location, but can dismiss the prompt. Setting the value to **Disclaimer** means that the user will be prompted for a location and also will be shown a disclaimer if they try to dismiss the prompt. In all cases, the user can continue to use the client.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="54be9-p103">E9-1-1 への対応が有効でない場合に、ユーザーが場所を手動で入力すると、免責事項テキストは表示されません。免責事項が既に表示されたユーザーには、免責事項テキストの更新は表示されません。</span><span class="sxs-lookup"><span data-stu-id="54be9-p103">The disclaimer text will not appear if a user manually entered a location before being enabled for E9-1-1. Updates to the disclaimer text will not be viewed by users that have already viewed the disclaimer.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="54be9-118">**拡張緊急サービス免責事項**</span><span class="sxs-lookup"><span data-stu-id="54be9-118">**Enhanced Emergency Service Disclaimer**</span></span>  
    <span data-ttu-id="54be9-119">この設定は、ユーザーが場所を入力せずにプロンプトを閉じた場合に表示される免責事項を指定します。</span><span class="sxs-lookup"><span data-stu-id="54be9-119">This setting specifies the disclaimer that users see if they dismiss the prompt for a location.</span></span> <span data-ttu-id="54be9-120">Lync Server 2013 では、場所ポリシーを使用して、ロケールやユーザーの異なるセットに異なる免責事項を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="54be9-120">In Lync Server 2013, you can use location policy to set different disclaimers for different locales or different sets of users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="54be9-121">この場所のポリシー設定は、Lync Server 2010 とは異なります。ここでは、 <STRONG>CsEnhancedEmergencyServiceDisclaimer</STRONG> コマンドレットを使用して組織全体のグローバルな免責事項を設定しています。</span><span class="sxs-lookup"><span data-stu-id="54be9-121">This location policy setting differs from Lync Server 2010, where you used the <STRONG>Set-CsEnhancedEmergencyServiceDisclaimer</STRONG> cmdlet to set a global disclaimer for the entire organization.</span></span> <span data-ttu-id="54be9-122">グローバル免責事項が既に存在する場合は、場所ポリシーでその免責事項を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54be9-122">If a global disclaimer already exists, you need to specify that disclaimer in location policy.</span></span> <span data-ttu-id="54be9-123">つまり、Lync Server 2013 は、場所のポリシーで指定された免責事項のみを使用します。</span><span class="sxs-lookup"><span data-stu-id="54be9-123">That is, Lync Server 2013 uses only disclaimers specified in location policy.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="54be9-124">**緊急ダイヤル文字列**</span><span class="sxs-lookup"><span data-stu-id="54be9-124">**Emergency Dial String**</span></span>  
    <span data-ttu-id="54be9-p106">このダイヤル文字列 (先頭の「+」を省き、Lync ユーザーのダイヤル プランによって行われる正規化をすべて含めます) は、通話が緊急電話であることを表します。**緊急ダイヤル文字列**を使用すると、クライアントによって場所とコールバック情報が緊急電話に含まれるようになります。</span><span class="sxs-lookup"><span data-stu-id="54be9-p106">This dial string (less the leading “+”, but including any normalization done by the Lync user’s Dial Plan) signifies that a call is an emergency call. The **Emergency Dial String** causes the client to include location and callback information with the call.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="54be9-127">組織で外部回線アクセスプレフィックスを使用していない場合は、Lync プールサーバーで送信ルーティングに通話を送信する前に、911文字列に "+" を追加する、対応するダイヤルプラン正規化ルールを作成する必要はありません。"+" は、場所のポリシーの結果として、Lync クライアントによって自動的に先頭に付けられます。</span><span class="sxs-lookup"><span data-stu-id="54be9-127">If your organization does not use an external line access prefix, you do not need to create a corresponding Dial Plan normalization rule that adds a “+” to the 911 string prior to sending the call to Outbound Routing on a Lync pool server; the “+” will be automatically prepended by the Lync client as a result of the location policy.</span></span> <span data-ttu-id="54be9-128">ただし、サイトで外部アクセスプレフィックスが使用されている場合は、その外部アクセスプレフィックスを取り除いて、"+" を追加する、適用可能なダイヤルプランポリシーに正規化ルールを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54be9-128">However, if your site uses an external access prefix, you need to add a normalization rule to the applicable Dial Plan policy that strips the external access prefix and adds the “+”.</span></span> <span data-ttu-id="54be9-129">たとえば、ユーザーが外部アクセスプレフィックス9を使用していて、緊急電話を発信するためにユーザーが 9 911 にダイヤルした場合、 &nbsp; クライアントはダイヤルプランポリシーを使用してこれを + 911 に正規化してから、発信者の場所プロファイル内のルートでダイヤル番号が評価されます。</span><span class="sxs-lookup"><span data-stu-id="54be9-129">For example, if your location uses an external access prefix of 9 and a user dials 9&nbsp;911 to place an emergency call, the client will use its Dial Plan policy to normalize this to +911 before the dialed number is evaluated by the routes in the caller’s location profile.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="54be9-130">**緊急ダイヤル文字列マスク**</span><span class="sxs-lookup"><span data-stu-id="54be9-130">**Emergency Dial String Masks**</span></span>  
    <span data-ttu-id="54be9-131">指定した **緊急ダイヤル文字列**に変換されるダイヤル文字列のセミコロンで区切られたリスト。</span><span class="sxs-lookup"><span data-stu-id="54be9-131">A semicolon-separated list of dial strings that is translated into the specified **Emergency Dial String**.</span></span> <span data-ttu-id="54be9-132">たとえば、112を追加したい場合があります。これは、ヨーロッパの大部分の緊急サービス番号です。</span><span class="sxs-lookup"><span data-stu-id="54be9-132">For example, you may want to add 112, which is the emergency service number for most of Europe.</span></span> <span data-ttu-id="54be9-133">ヨーロッパの Lync ユーザーは、911が米国の緊急電話番号であることを認識していない可能性がありますが、112にダイヤルして同じ結果を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="54be9-133">A visiting Lync user from Europe may not know that 911 is the U.S. emergency number, but they can dial 112 and get the same result.</span></span> <span data-ttu-id="54be9-134">緊急ダイヤル文字列の場合と同様に、各番号の前に "+" を含めないでください。また、外部回線アクセスコードを使用する場合は、ユーザーのダイヤルプランポリシーに、アクセスコードの数字を除去するための正規化ルールがあることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="54be9-134">As with the Emergency Dial String, do not include a “+” before each number, and if you use external line access codes, be sure there are normalization rules in the user’s Dial Plan policy to strip off the access code digit.</span></span>

<!-- end list -->

  - <span data-ttu-id="54be9-135">**PSTN 使用法**</span><span class="sxs-lookup"><span data-stu-id="54be9-135">**PSTN Usage**</span></span>  
    <span data-ttu-id="54be9-136">PSTN 使用法の名前。 SIP トランク、PSTN ゲートウェイ、または ELIN ゲートウェイの緊急通話を決定するルーティングパスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="54be9-136">The name of the PSTN Usage that contains the routing paths that determine which SIP trunk, PSTN gateway, or ELIN gateway emergency calls will go to.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="54be9-137">場所のポリシーに割り当てることができるのは1つの使用法のみです。</span><span class="sxs-lookup"><span data-stu-id="54be9-137">Only one usage can be assigned to a location policy.</span></span> <span data-ttu-id="54be9-138">この PSTN 使用法は、ユーザーの音声ポリシーに割り当てられている PSTN 使用法より優先されますが、緊急ダイヤル文字列または緊急ダイヤル文字列マスクにかけられる通話にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="54be9-138">This PSTN Usage overrides the PSTN Usages assigned to the user’s voice policy, but applies only to calls placed to the Emergency Dial String or to one of the Emergency Dial String Masks.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="54be9-139">**通知 URI**</span><span class="sxs-lookup"><span data-stu-id="54be9-139">**Notification URI**</span></span>  
    <span data-ttu-id="54be9-140">緊急電話をかけたときにインスタントメッセージング (IM) 通知を受け取るセキュリティ担当者の1つ以上の SIP Uri を指定します。</span><span class="sxs-lookup"><span data-stu-id="54be9-140">Specifies one or more SIP URIs of the security personnel who receive an instant messaging (IM) notification when an emergency call is placed.</span></span> <span data-ttu-id="54be9-141">配布グループがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="54be9-141">Distribution groups are supported.</span></span>

<!-- end list -->

  - <span data-ttu-id="54be9-142">[**会議 URI**]</span><span class="sxs-lookup"><span data-stu-id="54be9-142">**Conference URI**</span></span>  
    <span data-ttu-id="54be9-143">緊急電話が発信されたときに一方向する必要がある、直接の中向きダイヤル (DID) 番号 (通常はセキュリティデスク番号) を指定します。</span><span class="sxs-lookup"><span data-stu-id="54be9-143">Specifies a direct inward dialing (DID) number (typically, a security desk number) that should be conferenced in when an emergency call is placed.</span></span>

<!-- end list -->

  - <span data-ttu-id="54be9-144">**電話会議モード**</span><span class="sxs-lookup"><span data-stu-id="54be9-144">**Conference Mode**</span></span>  
    <span data-ttu-id="54be9-145">会議 URI を、一ウェイまたは双方向通信を使用して緊急電話に一方向するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="54be9-145">Specifies if the conference URI will be conferenced into the emergency call by using one-way or two-way communication.</span></span>

<!-- end list -->

  - <span data-ttu-id="54be9-146">**場所の更新間隔**</span><span class="sxs-lookup"><span data-stu-id="54be9-146">**Location Refresh Interval**</span></span>  
    <span data-ttu-id="54be9-147">場所情報サービスからの場所の更新に関するクライアント要求間の時間 (時間単位) を指定します。</span><span class="sxs-lookup"><span data-stu-id="54be9-147">Specifies the amount of time (in hours) between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="54be9-148">この値は、1から12までの任意の値に設定できます。</span><span class="sxs-lookup"><span data-stu-id="54be9-148">The value can be set to any value between 1 and 12.</span></span> <span data-ttu-id="54be9-149">既定値は 4 です。</span><span class="sxs-lookup"><span data-stu-id="54be9-149">The default value is 4.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

