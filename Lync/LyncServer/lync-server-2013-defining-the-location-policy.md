---
title: 'Lync Server 2013: 場所のポリシーを定義する'
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
ms.openlocfilehash: feb7550412fa6cdcda3a8fc4dd9b7913912c34e1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728357"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-location-policy-for-lync-server-2013"></a><span data-ttu-id="43aa5-102">Lync Server 2013 の位置情報ポリシーの定義</span><span class="sxs-lookup"><span data-stu-id="43aa5-102">Defining the location policy for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43aa5-103">_**最終更新日:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="43aa5-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="43aa5-104">場所ポリシーにはそれぞれ、以下の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="43aa5-104">Each location policy contains the following information:</span></span>

  - <span data-ttu-id="43aa5-105">**緊急電話サービスが有効**</span><span class="sxs-lookup"><span data-stu-id="43aa5-105">**Emergency Services Enabled**</span></span>  
    <span data-ttu-id="43aa5-106">この値が**Yes**の場合、クライアントは E9-1 で有効になります。</span><span class="sxs-lookup"><span data-stu-id="43aa5-106">When this value is **Yes**, the client is enabled for E9-1-1.</span></span> <span data-ttu-id="43aa5-107">クライアントが登録されると、位置情報サービスから場所を取得しようとし、緊急通話の一部として位置情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="43aa5-107">When a client registers, it attempts to acquire a location from the Location Information service and will include the location information as part of an emergency call.</span></span>

<!-- end list -->

  - <span data-ttu-id="43aa5-108">**必要な場所**</span><span class="sxs-lookup"><span data-stu-id="43aa5-108">**Location Required**</span></span>  
    <span data-ttu-id="43aa5-109">この設定は、[**利用可能なサービス**  **] が [はい]** に設定されている場合にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="43aa5-109">This setting is used only when **Emergence Services Enabled** is set to **Yes**.</span></span>
    
    <span data-ttu-id="43aa5-110">[場所] に**必要な**設定を構成して、クライアントの動作を定義することができます。</span><span class="sxs-lookup"><span data-stu-id="43aa5-110">You can configure the **Location Required** setting to define the client behavior.</span></span> <span data-ttu-id="43aa5-111">値を [\*\*いいえ \*\*] に設定すると、ユーザーは場所の入力を求められません。</span><span class="sxs-lookup"><span data-stu-id="43aa5-111">Setting the value to **No** means that the user will not be prompted for a location.</span></span> <span data-ttu-id="43aa5-112">値を [\*\*はい \*\*] に設定すると、ユーザーは場所の入力を求められますが、入力せずにプロンプトを閉じることもできます。</span><span class="sxs-lookup"><span data-stu-id="43aa5-112">Setting the value to **Yes** means that the user will be prompted for a location, but can dismiss the prompt.</span></span> <span data-ttu-id="43aa5-113">値を [\*\*免責事項 \*\*] に設定すると、ユーザーは場所の入力を求められ、入力せずにプロンプトを閉じようとすると免責事項が表示されます。</span><span class="sxs-lookup"><span data-stu-id="43aa5-113">Setting the value to **Disclaimer** means that the user will be prompted for a location and also will be shown a disclaimer if they try to dismiss the prompt.</span></span> <span data-ttu-id="43aa5-114">すべての場合において、ユーザーはクライアントを使用し続けることができます。</span><span class="sxs-lookup"><span data-stu-id="43aa5-114">In all cases, the user can continue to use the client.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="43aa5-p103">E9-1-1 への対応が有効でない場合に、ユーザーが場所を手動で入力すると、免責事項テキストは表示されません。免責事項が既に表示されたユーザーには、免責事項テキストの更新は表示されません。</span><span class="sxs-lookup"><span data-stu-id="43aa5-p103">The disclaimer text will not appear if a user manually entered a location before being enabled for E9-1-1. Updates to the disclaimer text will not be viewed by users that have already viewed the disclaimer.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="43aa5-117">**拡張緊急サービス免責事項**</span><span class="sxs-lookup"><span data-stu-id="43aa5-117">**Enhanced Emergency Service Disclaimer**</span></span>  
    <span data-ttu-id="43aa5-118">この設定は、ユーザーが場所を入力せずにプロンプトを閉じた場合に表示される免責事項を指定します。</span><span class="sxs-lookup"><span data-stu-id="43aa5-118">This setting specifies the disclaimer that users see if they dismiss the prompt for a location.</span></span> <span data-ttu-id="43aa5-119">Lync Server 2013 では、場所ポリシーを使って、ロケールやユーザーの種類ごとに異なる免責事項を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="43aa5-119">In Lync Server 2013, you can use location policy to set different disclaimers for different locales or different sets of users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="43aa5-120">この場所のポリシー設定は、Lync Server 2010 とは異なります。ここでは、 <STRONG>CsEnhancedEmergencyServiceDisclaimer</STRONG>コマンドレットを使用して、組織全体のグローバル免責事項を設定しています。</span><span class="sxs-lookup"><span data-stu-id="43aa5-120">This location policy setting differs from Lync Server 2010, where you used the <STRONG>Set-CsEnhancedEmergencyServiceDisclaimer</STRONG> cmdlet to set a global disclaimer for the entire organization.</span></span> <span data-ttu-id="43aa5-121">グローバル免責事項が既に存在する場合は、位置情報ポリシーでその免責事項を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="43aa5-121">If a global disclaimer already exists, you need to specify that disclaimer in location policy.</span></span> <span data-ttu-id="43aa5-122">つまり、Lync Server 2013 は、位置情報ポリシーで指定された免責事項のみを使用します。</span><span class="sxs-lookup"><span data-stu-id="43aa5-122">That is, Lync Server 2013 uses only disclaimers specified in location policy.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="43aa5-123">**緊急ダイヤル文字列**</span><span class="sxs-lookup"><span data-stu-id="43aa5-123">**Emergency Dial String**</span></span>  
    <span data-ttu-id="43aa5-124">このダイヤル文字列は、"+" のように入力します (先頭は "+" ですが、Lync ユーザーのダイヤルプランによる正規化を含む)。通話が緊急通話であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="43aa5-124">This dial string (less the leading “+”, but including any normalization done by the Lync user’s Dial Plan) signifies that a call is an emergency call.</span></span> <span data-ttu-id="43aa5-125">**緊急ダイヤル文字列**を使用すると、クライアントによって場所とコールバック情報が緊急電話に含まれるようになります。</span><span class="sxs-lookup"><span data-stu-id="43aa5-125">The **Emergency Dial String** causes the client to include location and callback information with the call.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="43aa5-126">組織で外部の回線アクセスプレフィックスを使用していない場合は、Lync プールサーバーで送信ルーティングに通話を送信する前に、対応するダイヤルプランの正規化ルールを作成して、911文字列に "+" を追加する必要はありません。"+" は、場所ポリシーの結果として Lync クライアントによって自動的に付加されます。</span><span class="sxs-lookup"><span data-stu-id="43aa5-126">If your organization does not use an external line access prefix, you do not need to create a corresponding Dial Plan normalization rule that adds a “+” to the 911 string prior to sending the call to Outbound Routing on a Lync pool server; the “+” will be automatically prepended by the Lync client as a result of the location policy.</span></span> <span data-ttu-id="43aa5-127">ただし、サイトで外部アクセスプレフィックスが使用されている場合は、その外部アクセスプレフィックスを取り除き、"+" を追加する、該当するダイヤルプランポリシーに正規化ルールを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="43aa5-127">However, if your site uses an external access prefix, you need to add a normalization rule to the applicable Dial Plan policy that strips the external access prefix and adds the “+”.</span></span> <span data-ttu-id="43aa5-128">たとえば、自分の場所で外部アクセスプレフィックス9を使用していて、ユーザー&nbsp;が 9 911 にダイヤルして緊急通話を発信している場合、クライアントはそのダイヤルプラン911ポリシーを使って、発信者の位置情報プロファイルのルートによってダイヤルされた番号を評価します。</span><span class="sxs-lookup"><span data-stu-id="43aa5-128">For example, if your location uses an external access prefix of 9 and a user dials 9&nbsp;911 to place an emergency call, the client will use its Dial Plan policy to normalize this to +911 before the dialed number is evaluated by the routes in the caller’s location profile.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="43aa5-129">**緊急ダイヤルの文字列マスク**</span><span class="sxs-lookup"><span data-stu-id="43aa5-129">**Emergency Dial String Masks**</span></span>  
    <span data-ttu-id="43aa5-130">指定された**緊急ダイヤル文字列**に変換されたダイヤル文字列のセミコロン区切りのリスト。</span><span class="sxs-lookup"><span data-stu-id="43aa5-130">A semicolon-separated list of dial strings that is translated into the specified **Emergency Dial String**.</span></span> <span data-ttu-id="43aa5-131">たとえば、ヨーロッパのほとんどの緊急サービス番号である112を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="43aa5-131">For example, you may want to add 112, which is the emergency service number for most of Europe.</span></span> <span data-ttu-id="43aa5-132">ヨーロッパの Lync ユーザーは、911が米国の緊急電話番号であることを認識していませんが、112をダイヤルして、同じ結果を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="43aa5-132">A visiting Lync user from Europe may not know that 911 is the U.S. emergency number, but they can dial 112 and get the same result.</span></span> <span data-ttu-id="43aa5-133">緊急ダイヤルの文字列の場合と同様に、各番号の前に "+" を含めないでください。また、外部回線のアクセスコードを使用している場合は、ユーザーのダイヤルプランポリシーに正規化ルールが適用されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="43aa5-133">As with the Emergency Dial String, do not include a “+” before each number, and if you use external line access codes, be sure there are normalization rules in the user’s Dial Plan policy to strip off the access code digit.</span></span>

<!-- end list -->

  - <span data-ttu-id="43aa5-134">**PSTN 使用法**</span><span class="sxs-lookup"><span data-stu-id="43aa5-134">**PSTN Usage**</span></span>  
    <span data-ttu-id="43aa5-135">PSTN 使用法の名前です。PSTN 使用法には、緊急電話がどの SIP トランク、PSTN ゲートウェイ、または ELIN ゲートウェイを通るかを決定するルーティング パスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="43aa5-135">The name of the PSTN Usage that contains the routing paths that determine which SIP trunk, PSTN gateway, or ELIN gateway emergency calls will go to.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="43aa5-p109">場所ポリシーに割り当てられる使用法は 1 つだけです。この PSTN 使用法は、ユーザーの音声ポリシーに割り当てられた PSTN 使用法より優先されますが、緊急ダイヤル文字列または緊急ダイヤル文字列マスクの 1 つに発信する通話にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="43aa5-p109">Only one usage can be assigned to a location policy. This PSTN Usage overrides the PSTN Usages assigned to the user’s voice policy, but applies only to calls placed to the Emergency Dial String or to one of the Emergency Dial String Masks.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="43aa5-138">**通知 URI**</span><span class="sxs-lookup"><span data-stu-id="43aa5-138">**Notification URI**</span></span>  
    <span data-ttu-id="43aa5-p110">緊急電話が発信されたときに、インスタント メッセージング (IM) 通知を受信するセキュリティ担当者の 1 つ以上の SIP URI を指定します。配布グループがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="43aa5-p110">Specifies one or more SIP URIs of the security personnel who receive an instant messaging (IM) notification when an emergency call is placed. Distribution groups are supported.</span></span>

<!-- end list -->

  - <span data-ttu-id="43aa5-141">**会議 URI**</span><span class="sxs-lookup"><span data-stu-id="43aa5-141">**Conference URI**</span></span>  
    <span data-ttu-id="43aa5-142">緊急電話が発信されたときに、参加することが必要な DID (Direct Inward Dialing) の番号 (通常はセキュリティ デスクの電話番号) を指定します。</span><span class="sxs-lookup"><span data-stu-id="43aa5-142">Specifies a direct inward dialing (DID) number (typically, a security desk number) that should be conferenced in when an emergency call is placed.</span></span>

<!-- end list -->

  - <span data-ttu-id="43aa5-143">**会議モード**</span><span class="sxs-lookup"><span data-stu-id="43aa5-143">**Conference Mode**</span></span>  
    <span data-ttu-id="43aa5-144">会議 URI が単方向または双方向の通信を使用して緊急電話に参加するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="43aa5-144">Specifies if the conference URI will be conferenced into the emergency call by using one-way or two-way communication.</span></span>

<!-- end list -->

  - <span data-ttu-id="43aa5-145">**場所の更新間隔**</span><span class="sxs-lookup"><span data-stu-id="43aa5-145">**Location Refresh Interval**</span></span>  
    <span data-ttu-id="43aa5-146">位置情報サービスからの位置情報更新に対するクライアント要求の時間 (時間) を指定します。</span><span class="sxs-lookup"><span data-stu-id="43aa5-146">Specifies the amount of time (in hours) between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="43aa5-147">値は、1 ～ 12 の範囲で任意の値に設定できます。</span><span class="sxs-lookup"><span data-stu-id="43aa5-147">The value can be set to any value between 1 and 12.</span></span> <span data-ttu-id="43aa5-148">既定値は 4 です。</span><span class="sxs-lookup"><span data-stu-id="43aa5-148">The default value is 4.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

