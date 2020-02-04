---
title: 'Lync Server 2013: 位置情報ポリシーの作成または変更'
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
ms.openlocfilehash: 1648e845fc3759e7083c2443013f89fb49c1b00f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740177"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-a-location-policy-in-lync-server-2013"></a><span data-ttu-id="63bad-102">Lync Server 2013 で位置情報ポリシーを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="63bad-102">Creating or modifying a location policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63bad-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="63bad-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="63bad-104">Lync Server 2013 では、位置情報ポリシーを使用して、強化された 9-1-1 (E9) 機能と、ユーザーまたは連絡先の位置設定に関連する設定を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="63bad-104">In Lync Server 2013, you can use the location policy to apply settings that relate to Enhanced 9-1-1 (E9-1-1) functionality and to location settings for users or contacts.</span></span> <span data-ttu-id="63bad-105">位置情報ポリシーは、ユーザーが E9 に対して有効になっているかどうかを決定し、場合によっては緊急通話の動作を確認します。</span><span class="sxs-lookup"><span data-stu-id="63bad-105">The location policy determines whether a user is enabled for E9-1-1, and if so what the behavior is of an emergency call.</span></span> <span data-ttu-id="63bad-106">たとえば、位置情報ポリシーを使用して、緊急通話 (米国の911など)、企業のセキュリティに自動的に通知するかどうか、および通話のルーティング方法を定義できます。</span><span class="sxs-lookup"><span data-stu-id="63bad-106">For example, you can use the location policy to define what number constitutes an emergency call (for example, 911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="63bad-107">Lync Server 2013 コントロールパネルの [**ネットワーク構成**] グループから、場所のポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="63bad-107">You can configure location policies from the **Network Configuration** group in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="63bad-108">Lync Server コントロールパネルから、場所のポリシーの表示、作成、変更、または削除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="63bad-108">From Lync Server Control Panel you can view, create, modify, or delete location policies.</span></span> <span data-ttu-id="63bad-109">位置情報ポリシーを作成または変更するには、このセクションの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="63bad-109">Use the procedures in this section to create or modify a location policy.</span></span> <span data-ttu-id="63bad-110">場所のポリシーの削除の詳細については、「 [Lync Server 2013 で位置情報ポリシーを削除する](lync-server-2013-deleting-a-location-policy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63bad-110">For details on deleting location policies, see [Deleting a location policy in Lync Server 2013](lync-server-2013-deleting-a-location-policy.md).</span></span>

<span data-ttu-id="63bad-111">Lync Server 2013 では、場所情報サービスからの場所の更新に対するクライアント要求間の既定の時間を上書きすることができます。</span><span class="sxs-lookup"><span data-stu-id="63bad-111">In Lync Server 2013, you can override the default amount of time between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="63bad-112">既定値は4時間です。</span><span class="sxs-lookup"><span data-stu-id="63bad-112">The default value is 4 hours.</span></span> <span data-ttu-id="63bad-113">LocationRefreshInterval パラメーターを指定して**Set-CsLocationPolicy**コマンドレットを使用すると、既定値を上書きできます。</span><span class="sxs-lookup"><span data-stu-id="63bad-113">Use the **Set-CsLocationPolicy** cmdlet with the LocationRefreshInterval parameter to override the default value.</span></span>

<div>

## <a name="to-create-a-new-location-policy-in-lync-server-control-panel"></a><span data-ttu-id="63bad-114">Lync Server コントロールパネルで新しい場所のポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="63bad-114">To create a new location policy in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="63bad-115">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="63bad-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="63bad-116">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="63bad-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="63bad-117">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="63bad-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="63bad-118">左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**場所のポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63bad-118">In the left navigation bar, click **Network Configuration** and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="63bad-119">[**場所のポリシー** ] ページで、[**新規**] をクリックし、作成するポリシーの種類を選びます。</span><span class="sxs-lookup"><span data-stu-id="63bad-119">On the **Location Policy** page, click **New** and then select the type of policy you want to create:</span></span>
    
      - <span data-ttu-id="63bad-120">サイトポリシーを作成するには、[**サイトポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63bad-120">To create a site policy, click **Site policy**.</span></span> <span data-ttu-id="63bad-121">[**サイトの選択**] で、ポリシーを適用するサイトを選択し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63bad-121">In **Select a Site**, choose the site to which you want the policy applied and click **OK**.</span></span> <span data-ttu-id="63bad-122">[**新しい場所ポリシー** ] ページの [**範囲**] フィールドには値の**サイト**が表示され、[**名前**] フィールドには選択したサイトの名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="63bad-122">On the **New Location Policy** page, the **Scope** field contains the value **Site**, and the **Name** field contains the name of the site you chose.</span></span> <span data-ttu-id="63bad-123">これらのフィールドのいずれかを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="63bad-123">You cannot modify either of these fields.</span></span> <span data-ttu-id="63bad-124">サイトポリシーは、指定されたサイトのすべてのユーザーに自動的に適用され、それらのユーザーのグローバルポリシーを上書きします。</span><span class="sxs-lookup"><span data-stu-id="63bad-124">A site policy is automatically applied to all users on the specified site and overrides the global policy for those users.</span></span>
    
      - <span data-ttu-id="63bad-125">**ユーザーポリシー**を作成するには、[**ユーザーポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63bad-125">To create a **User policy**, click **User policy**.</span></span> <span data-ttu-id="63bad-126">**新しい場所のポリシー**では、[**スコープ**] フィールドには [**ユーザー**] という値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="63bad-126">In the **New Location Policy**, the **Scope** field contains the value **User**.</span></span> <span data-ttu-id="63bad-127">この値は変更できません。</span><span class="sxs-lookup"><span data-stu-id="63bad-127">You cannot modify this value.</span></span> <span data-ttu-id="63bad-128">[**名前**] フィールドに、このポリシーに付ける名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="63bad-128">In the **Name** field, type the name you want to give this policy.</span></span> <span data-ttu-id="63bad-129">ユーザーポリシーは、どのユーザーにも自動的には適用されません。</span><span class="sxs-lookup"><span data-stu-id="63bad-129">A user policy does not automatically apply to any users.</span></span> <span data-ttu-id="63bad-130">ユーザーポリシーを作成した後、ポリシーを適用するユーザーまたはネットワークサイトにポリシーを手動で付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63bad-130">After creating the user policy, you must manually grant the policy to the users or network sites to which you want to policy to apply.</span></span>

5.  <span data-ttu-id="63bad-131">残りのフィールドには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="63bad-131">Fill in the remaining fields as follows:</span></span>
    
      - <span data-ttu-id="63bad-132">**[強化**   された緊急電話サービスを有効にする] このチェックボックスをオンにすると、E9 に対してこのポリシーに関連付けられたユーザーが有効になります。</span><span class="sxs-lookup"><span data-stu-id="63bad-132">**Enable enhanced emergency services**   Select this check box to enable the users associated with this policy for E9-1-1.</span></span> <span data-ttu-id="63bad-133">緊急電話サービスが有効になっている場合、Lync Server クライアントは、登録時に位置情報を取得し、緊急通話が行われたときにその情報を含めます。</span><span class="sxs-lookup"><span data-stu-id="63bad-133">When emergency services are enabled, Lync Server clients will retrieve location information on registration and include that information when an emergency call is made.</span></span>
    
      - <span data-ttu-id="63bad-134">**Location**   次のいずれかの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="63bad-134">**Location**   Specify one of the following values:</span></span>
        
          - <span data-ttu-id="63bad-135">**必須**   ユーザーは、新しい場所にクライアントが登録したときに位置情報を入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="63bad-135">**Required**   The user will be prompted to input location information when the client registers at a new location.</span></span> <span data-ttu-id="63bad-136">ユーザーは、情報を入力せずにプロンプトを閉じることができます。</span><span class="sxs-lookup"><span data-stu-id="63bad-136">The user can dismiss the prompt without entering any information.</span></span> <span data-ttu-id="63bad-137">情報が入力されている場合、緊急通話は、安全な応答ポイント (PSAP) オペレーター (つまり、911演算子) にルーティングされる前に、緊急サービスプロバイダーから最初に応答されます。</span><span class="sxs-lookup"><span data-stu-id="63bad-137">If information is entered, an emergency call will first be answered by the emergency services provider to verify the location before being routed to the Public Safety Answering Point (PSAP) operator (that is, the 911 operator).</span></span>
        
          - <span data-ttu-id="63bad-138">**必要ありません**   。ユーザーは場所の入力を求められることはありません。</span><span class="sxs-lookup"><span data-stu-id="63bad-138">**Not Required**   The user will not be prompted for a location.</span></span> <span data-ttu-id="63bad-139">所在地情報を指定せずに通話を発信すると、緊急サービスプロバイダーは、通話に応答して場所を求めます。</span><span class="sxs-lookup"><span data-stu-id="63bad-139">When a call is made with no location information, the emergency services provider will answer the call and ask for a location.</span></span>
        
          - <span data-ttu-id="63bad-140">**免責**   このオプションは、ユーザーが位置情報を入力せずにプロンプトを閉じることができないことを除き、**必須**と同じです。</span><span class="sxs-lookup"><span data-stu-id="63bad-140">**Disclaimer**   This option is the same as **Required** except that the user cannot dismiss the prompt without entering location information.</span></span> <span data-ttu-id="63bad-141">ユーザーは引き続き緊急通話を完了できますが、情報を入力しなければ、その他の通話を完了することはできません。</span><span class="sxs-lookup"><span data-stu-id="63bad-141">The user can still complete an emergency call, but no other calls can be completed without entering the information.</span></span> <span data-ttu-id="63bad-142">また、免責テキストはユーザーに対して表示され、ユーザーに対して、場所情報の入力を拒否された結果を通知することができます。</span><span class="sxs-lookup"><span data-stu-id="63bad-142">In addition, disclaimer text will be displayed to the user that can alert them to the consequences of declining to enter location information.</span></span> <span data-ttu-id="63bad-143">免責事項のテキストを設定するには、Lync Server 管理シェルを使用して、EnhancedEmergencyServiceDisclaimer パラメーターを使って、 **set-CsLocationPolicy**コマンドレットまたは**新しい-cslocationpolicy**コマンドレットを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63bad-143">To set the disclaimer text, you must use Lync Server Management Shell to run the **Set-CsLocationPolicy** cmdlet or the **New-CsLocationPolicy** cmdlet with the EnhancedEmergencyServiceDisclaimer parameter.</span></span> <span data-ttu-id="63bad-144">詳細については、「Lync Server 管理シェルのドキュメント」の「 [CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) 」または「[新規](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63bad-144">For details, see [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) or [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy) in the Lync Server Management Shell documentation.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="63bad-145">Lync server 2013 では、地域ポリシーを使用して、組織全体のグローバル免責事項のみを指定できる Lync Server 2010 の場合とは異なり、さまざまなロケールまたはユーザーのセットに異なる免責事項を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="63bad-145">In Lync Server 2013, you can use location policy to set different disclaimers for different locales or different sets of users, unlike in Lync Server 2010 where you could specify only a global disclaimer for the entire organization.</span></span>

            
            </div>
    
      - <span data-ttu-id="63bad-146">**緊急サービスの場所を使用**   するさまざまな理由 (たとえば、現在の所在地のチームメンバーに通知するなど) についてのみ、Lync で所在地情報を使用できます。</span><span class="sxs-lookup"><span data-stu-id="63bad-146">**Use location for emergency services only**   Lync can use location information for various reasons (for example, to notify teammates of your current location).</span></span> <span data-ttu-id="63bad-147">このチェックボックスをオンにすると、緊急通話でのみ位置情報を使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="63bad-147">Select this check box to ensure location information is available only for use with an emergency call.</span></span>
    
      - <span data-ttu-id="63bad-148">**[Pstn 使用状況]**   このプロファイルを使って、クライアントから緊急通話をルーティングするために使用するボイスルートを決定するために使用される公衆交換電話網 (pstn) 使用。</span><span class="sxs-lookup"><span data-stu-id="63bad-148">**PSTN usage**   The public switched telephone network (PSTN) usage that will be used to determine which voice route will be used to route emergency calls from clients using this profile.</span></span> <span data-ttu-id="63bad-149">この使用に関連付けられているルートは、緊急通報専用の SIP トランクか、緊急通話を最も近い公安 (PSAP) にルーティングする緊急電話番号 (ELIN) のゲートウェイを指している必要があります。</span><span class="sxs-lookup"><span data-stu-id="63bad-149">The route associated with this usage should point to a SIP trunk dedicated to emergency calls or to an Emergency Location Identification Number (ELIN) gateway that routes emergency calls to the nearest Public Safety Answering Point (PSAP).</span></span>
    
      - <span data-ttu-id="63bad-150">**緊急電話番号**   緊急電話サービスにダイヤルする番号。</span><span class="sxs-lookup"><span data-stu-id="63bad-150">**Emergency dial number**   The number that is dialed to reach emergency services.</span></span> <span data-ttu-id="63bad-151">米国の場合、この値は911です。</span><span class="sxs-lookup"><span data-stu-id="63bad-151">In the United States this value is 911.</span></span> <span data-ttu-id="63bad-152">文字列は、0 ~ 9 の数字で構成する必要があります。長さは 1 ~ 10 桁です。</span><span class="sxs-lookup"><span data-stu-id="63bad-152">The string must be made of the digits 0 through 9 and can be from 1 to 10 digits in length.</span></span>
    
      - <span data-ttu-id="63bad-153">**緊急ダイヤルのマスク**   ダイヤルされたときに緊急ダイヤル番号の値に変換する番号。</span><span class="sxs-lookup"><span data-stu-id="63bad-153">**Emergency dial mask**   A number that you want to translate into the value of the emergency dial number value when it is dialed.</span></span> <span data-ttu-id="63bad-154">たとえば、このフィールドに「212」という値を入力し、[緊急電話番号] フィールドに911という値を入力した場合、ユーザーが212をダイヤルすると、その通話は911になります。</span><span class="sxs-lookup"><span data-stu-id="63bad-154">For example, if you enter a value of 212 in this field and the emergency dial number field has a value of 911, if a user dials 212 the call will be made to 911.</span></span> <span data-ttu-id="63bad-155">これにより、別の緊急電話番号をダイヤルしても、緊急サービスに通話を接続させることができます (緊急電話番号が異なる国または地域のユーザーが、現在滞在している国または地域の電話番号ではなく、その国または地域の電話番号をダイヤルしようとした場合など)。</span><span class="sxs-lookup"><span data-stu-id="63bad-155">This allows for alternate emergency numbers to be dialed and still have the call reach emergency services (for example, if someone from a country or region with a different emergency number attempts to dial that country or region’s number rather than the number for the country or region they are currently in).</span></span> <span data-ttu-id="63bad-156">値をセミコロン (;) で区切って複数の緊急ダイヤル マスクを定義できます。</span><span class="sxs-lookup"><span data-stu-id="63bad-156">You can define multiple emergency dial masks by separating the values with semicolons.</span></span> <span data-ttu-id="63bad-157">たとえば、212;414 のように入力します。</span><span class="sxs-lookup"><span data-stu-id="63bad-157">For example, 212;414.</span></span> <span data-ttu-id="63bad-158">文字列の最大の長さは、100文字です。</span><span class="sxs-lookup"><span data-stu-id="63bad-158">Maximum length of the string is 100 characters.</span></span> <span data-ttu-id="63bad-159">各文字は 0 ～ 9 の数字である必要があります。</span><span class="sxs-lookup"><span data-stu-id="63bad-159">Each character must be a digit 0 through 9.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="63bad-160">指定したダイヤルマスクの値が、呼び出しパークの範囲内の番号と同じでないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="63bad-160">Ensure that the specified dial mask value is not the same as a number in a call park orbit range.</span></span> <span data-ttu-id="63bad-161">コールパークルーティングは、緊急ダイヤルの文字列変換よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="63bad-161">Call park routing will take precedence over emergency dial string conversion.</span></span> <span data-ttu-id="63bad-162">既存のコールパークの範囲を確認するには、左側のナビゲーションバーで [<STRONG>音声機能</STRONG>] をクリックし、[<STRONG>通話パーク</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63bad-162">To see the existing call park orbit ranges, click <STRONG>Voice Features</STRONG> in the left navigation bar and then click <STRONG>Call Park</STRONG>.</span></span> <span data-ttu-id="63bad-163">詳細については、「 <A href="lync-server-2013-configure-phone-number-extensions-for-parking-calls.md">Lync Server 2013 でのパーキング通話用に電話番号の内線番号を設定する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63bad-163">For details, see <A href="lync-server-2013-configure-phone-number-extensions-for-parking-calls.md">Configure phone number extensions for parking calls in Lync Server 2013</A>.</span></span>

        
        </div>
    
      - <span data-ttu-id="63bad-164">\*\*\*\*   緊急通話が行われたときに通知される1つ以上の SIP Uniform resource identifier (uri) です。</span><span class="sxs-lookup"><span data-stu-id="63bad-164">**Notification URI**   One or more SIP Uniform Resource Identifiers (URIs) to be notified when an emergency call is made.</span></span> <span data-ttu-id="63bad-165">たとえば、緊急通話が行われるたびに、インスタントメッセージを通じて会社のセキュリティオフィスに通知を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="63bad-165">For example, the company security office could be notified through an instant message whenever an emergency call is made.</span></span> <span data-ttu-id="63bad-166">発信者の所在地が利用可能な場合は、その場所が通知に含まれます。</span><span class="sxs-lookup"><span data-stu-id="63bad-166">If the caller’s location is available that location will be included in the notification.</span></span> <span data-ttu-id="63bad-167">複数の SIP Uri をコンマ区切りリストとして含めることができます。</span><span class="sxs-lookup"><span data-stu-id="63bad-167">Multiple SIP URIs can be included as a comma-separated list.</span></span> <span data-ttu-id="63bad-168">たとえば、"sip: security@litwareinc"、"sip: kmyer@litwareinc" のようになります。</span><span class="sxs-lookup"><span data-stu-id="63bad-168">For example, "sip:security@litwareinc.com","sip:kmyer@litwareinc.com".</span></span> <span data-ttu-id="63bad-169">配布リストがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="63bad-169">Distribution lists are supported.</span></span> <span data-ttu-id="63bad-170">文字列は、1 ~ 256 文字の長さで、先頭が "sip:" で始まる必要があります。</span><span class="sxs-lookup"><span data-stu-id="63bad-170">The string must be from 1 to 256 characters in length and must begin with the prefix "sip:".</span></span> <span data-ttu-id="63bad-171">通知 URI フィールドをクリックする前に、例が表示されます。</span><span class="sxs-lookup"><span data-stu-id="63bad-171">Before you click in the Notification URI field an example is displayed.</span></span>
    
      - <span data-ttu-id="63bad-172">**[会議 URI**   ] は、発信された緊急通話に conferenced されるサードパーティの SIP URI (この場合は電話番号) です。</span><span class="sxs-lookup"><span data-stu-id="63bad-172">**Conference URI**   The SIP URI, in this case the telephone number, of a third party that will be conferenced in to any emergency calls that are made.</span></span> <span data-ttu-id="63bad-173">たとえば、会社のセキュリティに関する office では、緊急通話が発信された場合に着信があったり、その通話に参加したり (**会議モード**フィールドに指定されている値に応じて) 参加したりする場合があります。</span><span class="sxs-lookup"><span data-stu-id="63bad-173">For example, the company security office could receive a call when an emergency call is made and listen in or participate in that call (depending on the value supplied in the **Conference mode** field).</span></span> <span data-ttu-id="63bad-174">文字列は、1 ~ 256 文字の長さで、先頭が「sip:」で始まる必要があります。</span><span class="sxs-lookup"><span data-stu-id="63bad-174">The string must be from 1 to 256 characters in length and must begin with the prefix sip:.</span></span> <span data-ttu-id="63bad-175">例は、このフィールド内をクリックするまで表示されます。</span><span class="sxs-lookup"><span data-stu-id="63bad-175">An example is displayed until you click inside this field.</span></span>
    
      - <span data-ttu-id="63bad-176">**会議モード**   [**会議 URI** ] フィールドで値を指定した場合、**会議モード**では、サードパーティが通話に参加できるか、または受信のみ可能かを指定します。</span><span class="sxs-lookup"><span data-stu-id="63bad-176">**Conference mode**   If you specify a value in the **Conference URI** field, the **Conference mode** determines whether a third party can participate in the call or can only listen in.</span></span> <span data-ttu-id="63bad-177">次のいずれかのオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="63bad-177">Specify one of the following options:</span></span>
        
          - <span data-ttu-id="63bad-178">**一方通行**   の第三者は、発信者と psap 演算子の間でのみ会話を聞くことができます。</span><span class="sxs-lookup"><span data-stu-id="63bad-178">**One-way**   A third party can only listen to the conversation between the caller and the PSAP operator.</span></span>
        
          - <span data-ttu-id="63bad-179">**この2つの方法**   では、発信者と psap 演算子の間で通話をリッスンして参加することができます。</span><span class="sxs-lookup"><span data-stu-id="63bad-179">**Two-way**   A third party can listen in and participate in the call between the caller and the PSAP operator.</span></span>

6.  <span data-ttu-id="63bad-180">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63bad-180">Click **Commit**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="63bad-181">ユーザーポリシーを作成すると、最初にそのポリシーはどのユーザーまたはネットワークサイトにも適用されません。</span><span class="sxs-lookup"><span data-stu-id="63bad-181">When you create a user policy, initially that policy does not apply to any users or network sites.</span></span> <span data-ttu-id="63bad-182">ユーザーにポリシーを適用するには、左側のナビゲーションバーで [<STRONG>ユーザー</STRONG> ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63bad-182">To apply the policy to a user, click <STRONG>Users</STRONG> in the left navigation bar.</span></span> <span data-ttu-id="63bad-183">ポリシーを適用するユーザーを見つけます。</span><span class="sxs-lookup"><span data-stu-id="63bad-183">Find the user to which you want to apply the policy.</span></span> <span data-ttu-id="63bad-184">[<STRONG>編集</STRONG>] メニューの [<STRONG>詳細の表示</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63bad-184">On the <STRONG>Edit</STRONG> menu, click <STRONG>Show details</STRONG>.</span></span> <span data-ttu-id="63bad-185">[ <STRONG>Lync Server ユーザーの編集</STRONG>] ページで、[<STRONG>場所のポリシー</STRONG> ] ドロップダウンリストから新しい場所のポリシーを選び、[<STRONG>コミット</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63bad-185">On the <STRONG>Edit Lync Server User</STRONG> page, select the new location policy from the <STRONG>Location policy</STRONG> drop-down list and then click <STRONG>Commit</STRONG>.</span></span><BR><span data-ttu-id="63bad-186">ネットワークサイトにポリシーを適用するには、左側のナビゲーションバーで [<STRONG>ネットワーク構成</STRONG>] をクリックし、[<STRONG>サイト</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63bad-186">To apply the policy to a network site, click <STRONG>Network Configuration</STRONG> in the left navigation bar and then click <STRONG>Site</STRONG>.</span></span> <span data-ttu-id="63bad-187">ポリシーを適用するネットワークサイトを見つけます。</span><span class="sxs-lookup"><span data-stu-id="63bad-187">Find the network site to which you want to apply the policy.</span></span> <span data-ttu-id="63bad-188">[<STRONG>編集</STRONG>] メニューの [<STRONG>詳細の表示</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63bad-188">On the <STRONG>Edit</STRONG> menu, click <STRONG>Show details</STRONG>.</span></span> <span data-ttu-id="63bad-189">[<STRONG>サイトの編集</STRONG>] で、[<STRONG>場所のポリシー</STRONG> ] ドロップダウンリストから新しい場所のポリシーを選び、[<STRONG>コミット</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63bad-189">In <STRONG>Edit Site</STRONG>, select the new location policy from the <STRONG>Location policy</STRONG> drop-down list and then click <STRONG>Commit</STRONG>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-a-location-policy-in-lync-server-control-panel"></a><span data-ttu-id="63bad-190">Lync Server コントロールパネルで位置情報のポリシーを変更するには</span><span class="sxs-lookup"><span data-stu-id="63bad-190">To modify a location policy in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="63bad-191">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="63bad-191">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="63bad-192">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="63bad-192">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="63bad-193">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="63bad-193">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="63bad-194">左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**場所のポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63bad-194">In the left navigation bar, click **Network Configuration** and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="63bad-195">[**場所のポリシー** ] ページで、変更する場所のポリシーを選びます。</span><span class="sxs-lookup"><span data-stu-id="63bad-195">On the **Location Policy** page, select the location policy that you want to modify.</span></span>

5.  <span data-ttu-id="63bad-196">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63bad-196">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="63bad-197">[**場所ポリシーの編集**] ページで、必要に応じてフィールドを変更します (詳細については、このトピックで前述した「新しい位置情報ポリシーを作成する」の手順5を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="63bad-197">On the **Edit Location Policy** page, modify the fields as necessary (for details, see Step 5 in the "To create a new location policy" procedures earlier in this topic).</span></span>

7.  <span data-ttu-id="63bad-198">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63bad-198">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="63bad-199">関連項目</span><span class="sxs-lookup"><span data-stu-id="63bad-199">See Also</span></span>


[<span data-ttu-id="63bad-200">Lync Server 2013 で位置情報ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="63bad-200">Deleting a location policy in Lync Server 2013</span></span>](lync-server-2013-deleting-a-location-policy.md)  


[<span data-ttu-id="63bad-201">Lync Server 2013 の位置情報ポリシーの定義</span><span class="sxs-lookup"><span data-stu-id="63bad-201">Defining the location policy for Lync Server 2013</span></span>](lync-server-2013-defining-the-location-policy.md)  


[<span data-ttu-id="63bad-202">Lync Server 2013 でのパーキング通話用の電話番号の内線番号を構成する</span><span class="sxs-lookup"><span data-stu-id="63bad-202">Configure phone number extensions for parking calls in Lync Server 2013</span></span>](lync-server-2013-configure-phone-number-extensions-for-parking-calls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

