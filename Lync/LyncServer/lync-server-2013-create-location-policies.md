---
title: 'Lync Server 2013: 場所のポリシーを作成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create location policies
ms:assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413006(v=OCS.15)
ms:contentKeyID: 48185794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f420d3b634df79411bbc72cd4c029f9b5d97e19
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833851"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-location-policies-in-lync-server-2013"></a><span data-ttu-id="6ddb9-102">Lync Server 2013 で位置情報のポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="6ddb9-102">Create location policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ddb9-103">_**最終更新日:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="6ddb9-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="6ddb9-104">Lync Server は、位置情報ポリシーを使用して、クライアントの登録中に E9-1 の Lync クライアントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="6ddb9-104">Lync Server uses a location policy to enable Lync clients for E9-1-1 during client registration.</span></span> <span data-ttu-id="6ddb9-105">場所ポリシーには、E9-1-1 の実装方法を定義する設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6ddb9-105">A location policy contains the settings that define how E9-1-1 will be implemented.</span></span>

<span data-ttu-id="6ddb9-p102">グローバルの場所のポリシーを編集して、マークされた新しい場所のポリシーを作成できます。場所のポリシーが関連付けられたサブネット内部に配置されていない場合や、場所のポリシーが直接割り当てられていない場合に、クライアントはグローバル ポリシーを取得します。マークされたポリシーは、サブネットまたはユーザーに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="6ddb9-p102">You can edit the global location policy and create new tagged location policies. A client obtains a global policy when it is not located within a subnet with an associated location policy, or when the client has not been directly assigned a location policy. Tagged policies are assigned to subnets or users.</span></span>

<span data-ttu-id="6ddb9-109">場所のポリシーを作成するには、作成するユーザーが RTCUniversalServerAdmins グループまたは CsVoiceAdministrator 管理者役割のメンバーか、あるいは同等の管理者権限とアクセス許可を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ddb9-109">To create a location policy, you must use an account that is a member of the RTCUniversalServerAdmins group, or is a member of the CsVoiceAdministrator administrative role, or has equivalent administrator rights and permissions.</span></span>

<span data-ttu-id="6ddb9-110">場所のポリシーの詳細については、「 [Lync Server 2013 の位置情報ポリシーを定義](lync-server-2013-defining-the-location-policy.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ddb9-110">For a complete description of Location policies, see [Defining the location policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span></span> <span data-ttu-id="6ddb9-111">この手順のコマンドレットは、次の値を使用して定義された位置情報ポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="6ddb9-111">Cmdlets in this procedure use a location policy defined using the following values:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6ddb9-112">要素</span><span class="sxs-lookup"><span data-stu-id="6ddb9-112">Element</span></span></th>
<th><span data-ttu-id="6ddb9-113">値</span><span class="sxs-lookup"><span data-stu-id="6ddb9-113">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6ddb9-114">EnhancedEmergencyServicesEnabled</span><span class="sxs-lookup"><span data-stu-id="6ddb9-114">EnhancedEmergencyServicesEnabled</span></span></p></td>
<td><p><span data-ttu-id="6ddb9-115"><strong>True</strong></span><span class="sxs-lookup"><span data-stu-id="6ddb9-115"><strong>True</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ddb9-116">LocationRequired</span><span class="sxs-lookup"><span data-stu-id="6ddb9-116">LocationRequired</span></span></p></td>
<td><p><span data-ttu-id="6ddb9-117"><strong>Disclaimer</strong></span><span class="sxs-lookup"><span data-stu-id="6ddb9-117"><strong>Disclaimer</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ddb9-118">EnhancedEmergencyServiceDisclaimer</span><span class="sxs-lookup"><span data-stu-id="6ddb9-118">EnhancedEmergencyServiceDisclaimer</span></span></p></td>
<td><p><span data-ttu-id="6ddb9-p104">会社のポリシーで場所の設定が要求されています。場所を設定しない場合、緊急サービスが緊急時に発見できません。場所を設定してください。</span><span class="sxs-lookup"><span data-stu-id="6ddb9-p104">Your company policy requires you to set a location. If you do not set a location, emergency services will not be able to locate you in an emergency. Please set a location.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ddb9-122">UseLocationForE911Only</span><span class="sxs-lookup"><span data-stu-id="6ddb9-122">UseLocationForE911Only</span></span></p></td>
<td><p><span data-ttu-id="6ddb9-123"><strong>False</strong></span><span class="sxs-lookup"><span data-stu-id="6ddb9-123"><strong>False</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ddb9-124">PstnUsage</span><span class="sxs-lookup"><span data-stu-id="6ddb9-124">PstnUsage</span></span></p></td>
<td><p><span data-ttu-id="6ddb9-125"><strong>EmergencyUsage</strong></span><span class="sxs-lookup"><span data-stu-id="6ddb9-125"><strong>EmergencyUsage</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ddb9-126">EmergencyDialString</span><span class="sxs-lookup"><span data-stu-id="6ddb9-126">EmergencyDialString</span></span></p></td>
<td><p><span data-ttu-id="6ddb9-127"><strong>911</strong></span><span class="sxs-lookup"><span data-stu-id="6ddb9-127"><strong>911</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ddb9-128">EmergencyDialMask</span><span class="sxs-lookup"><span data-stu-id="6ddb9-128">EmergencyDialMask</span></span></p></td>
<td><p><span data-ttu-id="6ddb9-129"><strong>112</strong></span><span class="sxs-lookup"><span data-stu-id="6ddb9-129"><strong>112</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ddb9-130">NotificationUri</span><span class="sxs-lookup"><span data-stu-id="6ddb9-130">NotificationUri</span></span></p></td>
<td><p><span data-ttu-id="6ddb9-131"><strong>sip:security@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="6ddb9-131"><strong>sip:security@litwareinc.com</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ddb9-132">ConferenceUri</span><span class="sxs-lookup"><span data-stu-id="6ddb9-132">ConferenceUri</span></span></p></td>
<td><p><span data-ttu-id="6ddb9-133"><strong>sip:+14255550123@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="6ddb9-133"><strong>sip:+14255550123@litwareinc.com</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ddb9-134">ConferenceMode</span><span class="sxs-lookup"><span data-stu-id="6ddb9-134">ConferenceMode</span></span></p></td>
<td><p><span data-ttu-id="6ddb9-135"><strong>twoway</strong></span><span class="sxs-lookup"><span data-stu-id="6ddb9-135"><strong>twoway</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ddb9-136">LocationRefreshInterval</span><span class="sxs-lookup"><span data-stu-id="6ddb9-136">LocationRefreshInterval</span></span></p></td>
<td><p><span data-ttu-id="6ddb9-137"><strong>2</strong></span><span class="sxs-lookup"><span data-stu-id="6ddb9-137"><strong>2</strong></span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6ddb9-138">場所のポリシーの使用について詳しくは、次のコマンドレットの Lync Server 管理シェルに関するドキュメントをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6ddb9-138">For details about working with location policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="6ddb9-139">New-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="6ddb9-139">New-CsLocationPolicy</span></span>

  - <span data-ttu-id="6ddb9-140">Get-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="6ddb9-140">Get-CsLocationPolicy</span></span>

  - <span data-ttu-id="6ddb9-141">Set-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="6ddb9-141">Set-CsLocationPolicy</span></span>

  - <span data-ttu-id="6ddb9-142">Remove-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="6ddb9-142">Remove-CsLocationPolicy</span></span>

  - <span data-ttu-id="6ddb9-143">許可-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="6ddb9-143">Grant-CsLocationPolicy</span></span>

<div>

## <a name="to-create-location-policies"></a><span data-ttu-id="6ddb9-144">場所のポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="6ddb9-144">To create location policies</span></span>

1.  <span data-ttu-id="6ddb9-145">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="6ddb9-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6ddb9-146"><STRONG>PstnUsage</STRONG> の設定がグローバルの PstnUsages 一覧にあらかじめ存在していない場合、CsLocationPolicy は失敗します。</span><span class="sxs-lookup"><span data-stu-id="6ddb9-146">CsLocationPolicy will fail if the setting for <STRONG>PstnUsage</STRONG> is not already in the Global list of PstnUsages.</span></span>

    
    </div>

2.  <span data-ttu-id="6ddb9-147">オプションで、次のコマンドレットを実行して、グローバルの場所のポリシーを編集します。</span><span class="sxs-lookup"><span data-stu-id="6ddb9-147">Optionally, run the following cmdlet to edit the global Location Policy:</span></span>
    
        Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2

3.  <span data-ttu-id="6ddb9-148">次のコマンドレットを実行してマークされた場所のポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="6ddb9-148">Run the following to create a tagged Location Policy.</span></span>
    
        New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2

4.  <span data-ttu-id="6ddb9-149">次のコマンドレットを実行して、ステップ 3 で作成したマークされた場所のポリシーをユーザー ポリシーに適用します。</span><span class="sxs-lookup"><span data-stu-id="6ddb9-149">Run the following cmdlet to apply the tagged Location Policy created in step 3 to a user policy.</span></span>
    
        (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond

</div>

</div>

<span> </span>

</div>

</div>

</div>

