---
title: 'Lync Server 2013: 場所のポリシーの作成または変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying a location policy
ms:assetid: 10338418-4da4-42df-b231-f52098c08dae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687971(v=OCS.15)
ms:contentKeyID: 49733557
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f87bf9aff433b70bc50b3fcff209ecd14ea268e0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516784"
---
# <a name="creating-or-modifying-a-location-policy-in-lync-server-2013"></a><span data-ttu-id="f8595-102">Lync Server 2013 での場所のポリシーの作成または変更</span><span class="sxs-lookup"><span data-stu-id="f8595-102">Creating or modifying a location policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8595-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f8595-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f8595-104">Lync Server 2013 では、場所のポリシーを使用して、強化された 9-1-1 (E9-1-1) の機能に関連する設定と、ユーザーまたは連絡先の場所の設定を適用できます。</span><span class="sxs-lookup"><span data-stu-id="f8595-104">In Lync Server 2013, you can use the location policy to apply settings that relate to Enhanced 9-1-1 (E9-1-1) functionality and to location settings for users or contacts.</span></span> <span data-ttu-id="f8595-105">場所のポリシーには、ユーザーを E9-1-1 に対して有効にするかどうか、および有効にする場合、緊急電話の動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="f8595-105">The location policy determines whether a user is enabled for E9-1-1, and if so what the behavior is of an emergency call.</span></span> <span data-ttu-id="f8595-106">たとえば、場所ポリシーを使用して、緊急電話の番号 (米国の場合は 911)、社内セキュリティに自動的に通知するかどうか、および通話をルーティングする方法を定義できます。</span><span class="sxs-lookup"><span data-stu-id="f8595-106">For example, you can use the location policy to define what number constitutes an emergency call (for example, 911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="f8595-107">Lync Server 2013 コントロールパネルの [ **ネットワーク構成** ] グループから、場所のポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="f8595-107">You can configure location policies from the **Network Configuration** group in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="f8595-108">Lync Server コントロールパネルから、場所のポリシーを表示、作成、変更、または削除することができます。</span><span class="sxs-lookup"><span data-stu-id="f8595-108">From Lync Server Control Panel you can view, create, modify, or delete location policies.</span></span> <span data-ttu-id="f8595-109">場所のポリシーを作成または変更するには、このセクションの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="f8595-109">Use the procedures in this section to create or modify a location policy.</span></span> <span data-ttu-id="f8595-110">場所ポリシーの削除の詳細については、「 [Lync Server 2013 の場所ポリシーの削除](lync-server-2013-deleting-a-location-policy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8595-110">For details on deleting location policies, see [Deleting a location policy in Lync Server 2013](lync-server-2013-deleting-a-location-policy.md).</span></span>

<span data-ttu-id="f8595-111">Lync Server 2013 では、場所情報サービスからの場所の更新に関するクライアント要求間の既定の時間を上書きできます。</span><span class="sxs-lookup"><span data-stu-id="f8595-111">In Lync Server 2013, you can override the default amount of time between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="f8595-112">既定値は 4 時間です。</span><span class="sxs-lookup"><span data-stu-id="f8595-112">The default value is 4 hours.</span></span> <span data-ttu-id="f8595-113">LocationRefreshInterval パラメーターを指定して **コマンドレットを使用して** 、既定値を上書きします。</span><span class="sxs-lookup"><span data-stu-id="f8595-113">Use the **Set-CsLocationPolicy** cmdlet with the LocationRefreshInterval parameter to override the default value.</span></span>

<div>

## <a name="to-create-a-new-location-policy-in-lync-server-control-panel"></a><span data-ttu-id="f8595-114">Lync Server コントロールパネルで新しい場所のポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="f8595-114">To create a new location policy in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="f8595-115">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="f8595-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f8595-116">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f8595-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f8595-117">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8595-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f8595-118">左側のナビゲーション バーで [**ネットワーク構成**] をクリックし、[**場所のポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8595-118">In the left navigation bar, click **Network Configuration** and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="f8595-119">[ **場所のポリシー** ] ページで、[ **新規** ] をクリックし、作成するポリシーの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="f8595-119">On the **Location Policy** page, click **New** and then select the type of policy you want to create:</span></span>
    
      - <span data-ttu-id="f8595-120">サイトポリシーを作成するには、[ **サイトポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8595-120">To create a site policy, click **Site policy**.</span></span> <span data-ttu-id="f8595-121">[ **サイトの選択**] で、ポリシーを適用するサイトを選択し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8595-121">In **Select a Site**, choose the site to which you want the policy applied and click **OK**.</span></span> <span data-ttu-id="f8595-122">[ **新しい場所ポリシー** ] ページの [ **範囲** ] フィールドに値の **サイト**が含まれ、[ **名前** ] フィールドに選択したサイトの名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8595-122">On the **New Location Policy** page, the **Scope** field contains the value **Site**, and the **Name** field contains the name of the site you chose.</span></span> <span data-ttu-id="f8595-123">これらのフィールドのいずれかを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="f8595-123">You cannot modify either of these fields.</span></span> <span data-ttu-id="f8595-124">サイトポリシーは、指定されたサイトのすべてのユーザーに自動的に適用され、それらのユーザーのグローバルポリシーを上書きします。</span><span class="sxs-lookup"><span data-stu-id="f8595-124">A site policy is automatically applied to all users on the specified site and overrides the global policy for those users.</span></span>
    
      - <span data-ttu-id="f8595-125">**ユーザーポリシー**を作成するには、[**ユーザーポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8595-125">To create a **User policy**, click **User policy**.</span></span> <span data-ttu-id="f8595-126">**新しい場所のポリシー**で、[**範囲**] フィールドに値**User**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8595-126">In the **New Location Policy**, the **Scope** field contains the value **User**.</span></span> <span data-ttu-id="f8595-127">この値を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="f8595-127">You cannot modify this value.</span></span> <span data-ttu-id="f8595-128">[ **名前** ] フィールドに、このポリシーを付与する名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="f8595-128">In the **Name** field, type the name you want to give this policy.</span></span> <span data-ttu-id="f8595-129">ユーザーポリシーは、どのユーザーにも自動的に適用されることはありません。</span><span class="sxs-lookup"><span data-stu-id="f8595-129">A user policy does not automatically apply to any users.</span></span> <span data-ttu-id="f8595-130">ユーザーポリシーを作成した後、ポリシーを適用するユーザーまたはネットワークサイトに手動でポリシーを付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8595-130">After creating the user policy, you must manually grant the policy to the users or network sites to which you want to policy to apply.</span></span>

5.  <span data-ttu-id="f8595-131">残りのフィールドに、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f8595-131">Fill in the remaining fields as follows:</span></span>
    
      - <span data-ttu-id="f8595-132">**拡張緊急サービス**     を有効にするこのポリシーに関連付けられたユーザーの E9-1-1 を有効にするには、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="f8595-132">**Enable enhanced emergency services**   Select this check box to enable the users associated with this policy for E9-1-1.</span></span> <span data-ttu-id="f8595-133">緊急サービスが有効になっている場合、Lync Server クライアントは登録時に場所情報を取得し、緊急電話が行われるときにその情報を含めます。</span><span class="sxs-lookup"><span data-stu-id="f8595-133">When emergency services are enabled, Lync Server clients will retrieve location information on registration and include that information when an emergency call is made.</span></span>
    
      - <span data-ttu-id="f8595-134">**場所**    次のいずれかの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="f8595-134">**Location**   Specify one of the following values:</span></span>
        
          - <span data-ttu-id="f8595-135">**必須**    クライアントが新しい場所に登録するときに、場所情報を入力するようにユーザーに求められます。</span><span class="sxs-lookup"><span data-stu-id="f8595-135">**Required**   The user will be prompted to input location information when the client registers at a new location.</span></span> <span data-ttu-id="f8595-136">ユーザーは、情報を入力せずにプロンプトを閉じることができます。</span><span class="sxs-lookup"><span data-stu-id="f8595-136">The user can dismiss the prompt without entering any information.</span></span> <span data-ttu-id="f8595-137">情報が入力されている場合は、緊急電話の発信者が緊急電話に応答してから、公衆安全応答ポイント (PSAP) オペレーター (つまり911オペレーター) にルーティングされる前に場所が確認されます。</span><span class="sxs-lookup"><span data-stu-id="f8595-137">If information is entered, an emergency call will first be answered by the emergency services provider to verify the location before being routed to the Public Safety Answering Point (PSAP) operator (that is, the 911 operator).</span></span>
        
          - <span data-ttu-id="f8595-138">必須では**ありません**    ユーザーは場所の入力を求められません。</span><span class="sxs-lookup"><span data-stu-id="f8595-138">**Not Required**   The user will not be prompted for a location.</span></span> <span data-ttu-id="f8595-139">場所情報を持たない通話が行われると、緊急サービスプロバイダーは通話に応答し、場所を要求します。</span><span class="sxs-lookup"><span data-stu-id="f8595-139">When a call is made with no location information, the emergency services provider will answer the call and ask for a location.</span></span>
        
          - <span data-ttu-id="f8595-140">**免責事項**    このオプションは**必要**と同じですが、場所情報を入力せずにユーザーがプロンプトを閉じることができない点が異なります。</span><span class="sxs-lookup"><span data-stu-id="f8595-140">**Disclaimer**   This option is the same as **Required** except that the user cannot dismiss the prompt without entering location information.</span></span> <span data-ttu-id="f8595-141">ユーザーは引き続き緊急通話を完了できますが、情報を入力しないと他の通話を完了できません。</span><span class="sxs-lookup"><span data-stu-id="f8595-141">The user can still complete an emergency call, but no other calls can be completed without entering the information.</span></span> <span data-ttu-id="f8595-142">さらに、免責事項のテキストがユーザーに表示され、ユーザーに対して、場所情報の入力が拒否された結果を通知できます。</span><span class="sxs-lookup"><span data-stu-id="f8595-142">In addition, disclaimer text will be displayed to the user that can alert them to the consequences of declining to enter location information.</span></span> <span data-ttu-id="f8595-143">免責事項のテキストを設定するには、Lync Server 管理シェルを使用して、Microsoft.rtc.management.writableconfig.policy.location.enhancedemergencyservicedisclaimer 型パラメーターを使用して、 **set-CsLocationPolicy** コマンドレットまたは **新しい-cslocationpolicy** コマンドレットを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8595-143">To set the disclaimer text, you must use Lync Server Management Shell to run the **Set-CsLocationPolicy** cmdlet or the **New-CsLocationPolicy** cmdlet with the EnhancedEmergencyServiceDisclaimer parameter.</span></span> <span data-ttu-id="f8595-144">詳細については、「Lync Server Management Shell」のドキュメントの「 [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) 」または「 [New-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8595-144">For details, see [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) or [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy) in the Lync Server Management Shell documentation.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="f8595-145">Lync Server 2013 では、場所ポリシーを使用して、組織全体に対してグローバルな免責事項のみを指定する Lync Server 2010 とは異なり、ロケールやユーザーの異なるセットに異なる免責事項を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="f8595-145">In Lync Server 2013, you can use location policy to set different disclaimers for different locales or different sets of users, unlike in Lync Server 2010 where you could specify only a global disclaimer for the entire organization.</span></span>

            
            </div>
    
      - <span data-ttu-id="f8595-146">**緊急サービスの場所のみ**     を使用するLync は、さまざまな理由で場所情報を使用できます (たとえば、現在の場所のチームメイトに通知します)。</span><span class="sxs-lookup"><span data-stu-id="f8595-146">**Use location for emergency services only**   Lync can use location information for various reasons (for example, to notify teammates of your current location).</span></span> <span data-ttu-id="f8595-147">このチェックボックスをオンにすると、緊急電話でのみ場所情報を使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="f8595-147">Select this check box to ensure location information is available only for use with an emergency call.</span></span>
    
      - <span data-ttu-id="f8595-148">**PSTN 使用法**    このプロファイルを使用して、クライアントからの緊急電話のルーティングに使用する音声ルートを決定するために使用される公衆交換電話網 (PSTN) の使用法。</span><span class="sxs-lookup"><span data-stu-id="f8595-148">**PSTN usage**   The public switched telephone network (PSTN) usage that will be used to determine which voice route will be used to route emergency calls from clients using this profile.</span></span> <span data-ttu-id="f8595-149">この使用法に関連付けられているルートは、緊急通話に専用の SIP トランクまたは緊急電話を最も近い公衆安全応答ポイント (PSAP) にルーティングする緊急位置識別番号 (ELIN) ゲートウェイを指している必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8595-149">The route associated with this usage should point to a SIP trunk dedicated to emergency calls or to an Emergency Location Identification Number (ELIN) gateway that routes emergency calls to the nearest Public Safety Answering Point (PSAP).</span></span>
    
      - <span data-ttu-id="f8595-150">**緊急ダイヤル番号**    緊急サービスに接続するためにダイヤルされる番号。</span><span class="sxs-lookup"><span data-stu-id="f8595-150">**Emergency dial number**   The number that is dialed to reach emergency services.</span></span> <span data-ttu-id="f8595-151">米国の場合、この値は 911 です。</span><span class="sxs-lookup"><span data-stu-id="f8595-151">In the United States this value is 911.</span></span> <span data-ttu-id="f8595-152">この文字列は 0 ～ 9 の数字で構成されている必要があり、1 ～ 10 桁の長さにすることができます。</span><span class="sxs-lookup"><span data-stu-id="f8595-152">The string must be made of the digits 0 through 9 and can be from 1 to 10 digits in length.</span></span>
    
      - <span data-ttu-id="f8595-153">**緊急ダイヤルマスク**    ダイヤルするときに、緊急ダイヤル番号の値に変換する数値を指定します。</span><span class="sxs-lookup"><span data-stu-id="f8595-153">**Emergency dial mask**   A number that you want to translate into the value of the emergency dial number value when it is dialed.</span></span> <span data-ttu-id="f8595-154">たとえば、このフィールドに212の値を入力し、エマージェンシーダイヤル番号フィールドの値が911の場合、ユーザーが212をダイヤルすると、その呼び出しは911に対して行われます。</span><span class="sxs-lookup"><span data-stu-id="f8595-154">For example, if you enter a value of 212 in this field and the emergency dial number field has a value of 911, if a user dials 212 the call will be made to 911.</span></span> <span data-ttu-id="f8595-155">これにより、代替の緊急電話番号をダイヤルすることができます (たとえば、ある国や地域の他のユーザーが、現在の国または地域の番号ではなく、その国または地域の電話番号をダイヤルしようとした場合など)。</span><span class="sxs-lookup"><span data-stu-id="f8595-155">This allows for alternate emergency numbers to be dialed and still have the call reach emergency services (for example, if someone from a country or region with a different emergency number attempts to dial that country or region’s number rather than the number for the country or region they are currently in).</span></span> <span data-ttu-id="f8595-156">値をセミコロン (;) で区切って複数の緊急ダイヤル マスクを定義できます。</span><span class="sxs-lookup"><span data-stu-id="f8595-156">You can define multiple emergency dial masks by separating the values with semicolons.</span></span> <span data-ttu-id="f8595-157">例: 212; 414。</span><span class="sxs-lookup"><span data-stu-id="f8595-157">For example, 212;414.</span></span> <span data-ttu-id="f8595-158">この文字列の長さの上限は 100 文字です。</span><span class="sxs-lookup"><span data-stu-id="f8595-158">Maximum length of the string is 100 characters.</span></span> <span data-ttu-id="f8595-159">各文字は 0 ～ 9 の数字である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8595-159">Each character must be a digit 0 through 9.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="f8595-160">指定したダイヤルマスク値が、コールパークオービット範囲の数値と同じでないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="f8595-160">Ensure that the specified dial mask value is not the same as a number in a call park orbit range.</span></span> <span data-ttu-id="f8595-161">コールパークルーティングは、緊急ダイヤル文字列変換よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="f8595-161">Call park routing will take precedence over emergency dial string conversion.</span></span> <span data-ttu-id="f8595-162">既存のコールパークオービット範囲を表示するには、左側のナビゲーションバーで [ <STRONG>音声機能</STRONG> ] をクリックし、[ <STRONG>コールパーク</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8595-162">To see the existing call park orbit ranges, click <STRONG>Voice Features</STRONG> in the left navigation bar and then click <STRONG>Call Park</STRONG>.</span></span> <span data-ttu-id="f8595-163">詳細については、「 <A href="lync-server-2013-configure-phone-number-extensions-for-parking-calls.md">Lync Server 2013 でのパーキング呼び出しの内線電話番号を構成する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8595-163">For details, see <A href="lync-server-2013-configure-phone-number-extensions-for-parking-calls.md">Configure phone number extensions for parking calls in Lync Server 2013</A>.</span></span>

        
        </div>
    
      - <span data-ttu-id="f8595-164">**通知 URI**    緊急電話が発信されたときに通知される1つまたは複数の SIP Uri (Uniform Resource Identifier)。</span><span class="sxs-lookup"><span data-stu-id="f8595-164">**Notification URI**   One or more SIP Uniform Resource Identifiers (URIs) to be notified when an emergency call is made.</span></span> <span data-ttu-id="f8595-165">たとえば、会社の警備室は緊急呼び出しの都度、インスタント メッセージによる通知を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="f8595-165">For example, the company security office could be notified through an instant message whenever an emergency call is made.</span></span> <span data-ttu-id="f8595-166">発信者の場所が入手可能な場合は、通知の中にその場所が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f8595-166">If the caller’s location is available that location will be included in the notification.</span></span> <span data-ttu-id="f8595-167">複数の SIP Uri をコンマ区切りのリストとして含めることができます。</span><span class="sxs-lookup"><span data-stu-id="f8595-167">Multiple SIP URIs can be included as a comma-separated list.</span></span> <span data-ttu-id="f8595-168">たとえば、「sip: security@litwareinc .com」、「sip: kmyer@litwareinc」のようになります。</span><span class="sxs-lookup"><span data-stu-id="f8595-168">For example, "sip:security@litwareinc.com","sip:kmyer@litwareinc.com".</span></span> <span data-ttu-id="f8595-169">配布リストがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f8595-169">Distribution lists are supported.</span></span> <span data-ttu-id="f8595-170">文字列は、1 ~ 256 文字の長さにする必要があり、先頭に "sip:" を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8595-170">The string must be from 1 to 256 characters in length and must begin with the prefix "sip:".</span></span> <span data-ttu-id="f8595-171">[通知 URI] フィールドをクリックする前に、例が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8595-171">Before you click in the Notification URI field an example is displayed.</span></span>
    
      - <span data-ttu-id="f8595-172">**会議 URI**    作成された緊急電話に一方向するために、サードパーティの SIP URI (この場合は電話番号)。</span><span class="sxs-lookup"><span data-stu-id="f8595-172">**Conference URI**   The SIP URI, in this case the telephone number, of a third party that will be conferenced in to any emergency calls that are made.</span></span> <span data-ttu-id="f8595-173">たとえば、会社のセキュリティ事務所では、緊急電話が発信されたときに通話を受信したり、その通話に参加したり ([ **電話会議モード** ] フィールドに指定されている値によって) したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="f8595-173">For example, the company security office could receive a call when an emergency call is made and listen in or participate in that call (depending on the value supplied in the **Conference mode** field).</span></span> <span data-ttu-id="f8595-174">この文字列は 1 ～ 256 文字の長さで、プレフィックス sip: で始まっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8595-174">The string must be from 1 to 256 characters in length and must begin with the prefix sip:.</span></span> <span data-ttu-id="f8595-175">このフィールドの内側をクリックすると、例が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8595-175">An example is displayed until you click inside this field.</span></span>
    
      - <span data-ttu-id="f8595-176">**電話会議モード**    [**電話会議 URI** ] フィールドに値を指定すると、電話**会議モード**はサードパーティが通話に参加できるかどうか、またはのみを聞くことができるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="f8595-176">**Conference mode**   If you specify a value in the **Conference URI** field, the **Conference mode** determines whether a third party can participate in the call or can only listen in.</span></span> <span data-ttu-id="f8595-177">次のいずれかのオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="f8595-177">Specify one of the following options:</span></span>
        
          - <span data-ttu-id="f8595-178">**一ウェイ**    第三者は、発信者と PSAP オペレーターの会話を聞くことしかできません。</span><span class="sxs-lookup"><span data-stu-id="f8595-178">**One-way**   A third party can only listen to the conversation between the caller and the PSAP operator.</span></span>
        
          - <span data-ttu-id="f8595-179">**双方向**    第三者は、発信者と PSAP オペレーターの通話に参加して参加することができます。</span><span class="sxs-lookup"><span data-stu-id="f8595-179">**Two-way**   A third party can listen in and participate in the call between the caller and the PSAP operator.</span></span>

6.  <span data-ttu-id="f8595-180">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8595-180">Click **Commit**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f8595-181">ユーザーポリシーを作成すると、最初にそのポリシーはユーザーまたはネットワークサイトに適用されません。</span><span class="sxs-lookup"><span data-stu-id="f8595-181">When you create a user policy, initially that policy does not apply to any users or network sites.</span></span> <span data-ttu-id="f8595-182">ユーザーにポリシーを適用するには、左側のナビゲーションバーで [ <STRONG>ユーザー</STRONG> ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8595-182">To apply the policy to a user, click <STRONG>Users</STRONG> in the left navigation bar.</span></span> <span data-ttu-id="f8595-183">ポリシーを適用するユーザーを検索します。</span><span class="sxs-lookup"><span data-stu-id="f8595-183">Find the user to which you want to apply the policy.</span></span> <span data-ttu-id="f8595-184">[<STRONG>編集</STRONG>] メニューの [<STRONG>詳細の表示</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8595-184">On the <STRONG>Edit</STRONG> menu, click <STRONG>Show details</STRONG>.</span></span> <span data-ttu-id="f8595-185">[ <STRONG>Lync Server ユーザーの編集</STRONG> ] ページで、[ <STRONG>場所のポリシー</STRONG> ] ドロップダウンリストから新しい場所のポリシーを選択し、[ <STRONG>確定</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8595-185">On the <STRONG>Edit Lync Server User</STRONG> page, select the new location policy from the <STRONG>Location policy</STRONG> drop-down list and then click <STRONG>Commit</STRONG>.</span></span><BR><span data-ttu-id="f8595-186">ポリシーをネットワークサイトに適用するには、左側のナビゲーションバーで [ <STRONG>ネットワーク構成</STRONG> ] をクリックし、[ <STRONG>サイト</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8595-186">To apply the policy to a network site, click <STRONG>Network Configuration</STRONG> in the left navigation bar and then click <STRONG>Site</STRONG>.</span></span> <span data-ttu-id="f8595-187">ポリシーを適用するネットワークサイトを検索します。</span><span class="sxs-lookup"><span data-stu-id="f8595-187">Find the network site to which you want to apply the policy.</span></span> <span data-ttu-id="f8595-188">[<STRONG>編集</STRONG>] メニューの [<STRONG>詳細の表示</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8595-188">On the <STRONG>Edit</STRONG> menu, click <STRONG>Show details</STRONG>.</span></span> <span data-ttu-id="f8595-189">[ <STRONG>サイトの編集</STRONG>] で、[ <STRONG>場所のポリシー</STRONG> ] ドロップダウンリストから新しい場所のポリシーを選択し、[ <STRONG>確定</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8595-189">In <STRONG>Edit Site</STRONG>, select the new location policy from the <STRONG>Location policy</STRONG> drop-down list and then click <STRONG>Commit</STRONG>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-a-location-policy-in-lync-server-control-panel"></a><span data-ttu-id="f8595-190">Lync Server コントロールパネルで場所のポリシーを変更するには</span><span class="sxs-lookup"><span data-stu-id="f8595-190">To modify a location policy in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="f8595-191">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="f8595-191">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f8595-192">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f8595-192">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f8595-193">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8595-193">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f8595-194">左側のナビゲーション バーで [**ネットワーク構成**] をクリックし、[**場所のポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8595-194">In the left navigation bar, click **Network Configuration** and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="f8595-195">[**場所のポリシー**] ページで、変更する場所のポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="f8595-195">On the **Location Policy** page, select the location policy that you want to modify.</span></span>

5.  <span data-ttu-id="f8595-196">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8595-196">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="f8595-197">[ **場所ポリシーの編集** ] ページで、必要に応じてフィールドを変更します (詳細については、このトピックで前述した「新しい場所のポリシーを作成するには」の手順5を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="f8595-197">On the **Edit Location Policy** page, modify the fields as necessary (for details, see Step 5 in the "To create a new location policy" procedures earlier in this topic).</span></span>

7.  <span data-ttu-id="f8595-198">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8595-198">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f8595-199">関連項目</span><span class="sxs-lookup"><span data-stu-id="f8595-199">See Also</span></span>


[<span data-ttu-id="f8595-200">Lync Server 2013 での場所のポリシーの削除</span><span class="sxs-lookup"><span data-stu-id="f8595-200">Deleting a location policy in Lync Server 2013</span></span>](lync-server-2013-deleting-a-location-policy.md)  


[<span data-ttu-id="f8595-201">Lync Server 2013 の場所ポリシーの定義</span><span class="sxs-lookup"><span data-stu-id="f8595-201">Defining the location policy for Lync Server 2013</span></span>](lync-server-2013-defining-the-location-policy.md)  


[<span data-ttu-id="f8595-202">Lync Server 2013 でのパーキング呼び出しの内線電話番号の構成</span><span class="sxs-lookup"><span data-stu-id="f8595-202">Configure phone number extensions for parking calls in Lync Server 2013</span></span>](lync-server-2013-configure-phone-number-extensions-for-parking-calls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

