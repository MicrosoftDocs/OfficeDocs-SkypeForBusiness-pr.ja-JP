---
title: 'Lync Server 2013: PSTN 電話の通話ルーティングのテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN phone call routing
ms:assetid: 301dd44d-03e9-41cd-9722-54e00365aa45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727302(v=OCS.15)
ms:contentKeyID: 63969598
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2dabe54fb2ba4df864d172015efb62ef161c77cb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-phone-call-routing-in-lync-server-2013"></a><span data-ttu-id="9f80f-102">Lync Server 2013 での PSTN 電話による通話ルーティングのテスト</span><span class="sxs-lookup"><span data-stu-id="9f80f-102">Testing PSTN phone call routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f80f-103">_**最終更新日:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="9f80f-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9f80f-104">確認のスケジュール</span><span class="sxs-lookup"><span data-stu-id="9f80f-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="9f80f-105">[毎日]</span><span class="sxs-lookup"><span data-stu-id="9f80f-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f80f-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="9f80f-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="9f80f-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9f80f-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f80f-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="9f80f-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="9f80f-109">Lync Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f80f-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="9f80f-110">Windows PowerShell のリモートインスタンスを使って実行する場合は、 <strong>CsInterTrunkRouting</strong>コマンドレットを実行するためのアクセス許可が与えられている RBAC の役割をユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f80f-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsInterTrunkRouting</strong> cmdlet.</span></span> <span data-ttu-id="9f80f-111">このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9f80f-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsInterTrunkRouting&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="9f80f-112">説明</span><span class="sxs-lookup"><span data-stu-id="9f80f-112">Description</span></span>

<span data-ttu-id="9f80f-113">**CsInterTrunkRouting**コマンドレットは、通話がある SIP から別の SIP にルーティングできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9f80f-113">The **Test-CsInterTrunkRouting** cmdlet verifies that calls can be routed from one SIP to another.</span></span> <span data-ttu-id="9f80f-114">これを行うには、コマンドレットに電話番号とトランク構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="9f80f-114">To do this, the cmdlet is given a phone number and a trunk configuration.</span></span> <span data-ttu-id="9f80f-115">**CsInterTrunkRouting**は、指定された番号について、一致するルートと一致する PSTN の使用状況を報告します。</span><span class="sxs-lookup"><span data-stu-id="9f80f-115">**Test-CsInterTrunkRouting** will then report back matching routes and matching PSTN usages for the specified number.</span></span> <span data-ttu-id="9f80f-116">Trunks には、指定した電話番号と一致する番号パターンがあり、trunks が少なくとも1つの PSTN 使用を共有している場合のみ、trunks 間で通話をルーティングできます。</span><span class="sxs-lookup"><span data-stu-id="9f80f-116">Note that calls can be routed between trunks only if the trunks have a number pattern that matches the specified phone number and only if the trunks share at least one PSTN usage.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="9f80f-117">テストの実行</span><span class="sxs-lookup"><span data-stu-id="9f80f-117">Running the test</span></span>

<span data-ttu-id="9f80f-118">次に示すコマンドは、ユーザーが Redmond サイトのトランク構成設定を使用して電話番号1-206-555-1219 に発信できるように、一致するルートと一致する電話の使用状況を返します。</span><span class="sxs-lookup"><span data-stu-id="9f80f-118">The commands shown below return the matching routes and matching phone usages that enable users to call the phone number 1-206-555-1219 using the trunk configuration settings for the Redmond site.</span></span>

    $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
    
    Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219" -TrunkConfiguration $trunk

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="9f80f-119">成功または失敗を確認する</span><span class="sxs-lookup"><span data-stu-id="9f80f-119">Determining success or failure</span></span>

<span data-ttu-id="9f80f-120">通話を別の SIP にルーティングできる場合は、次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9f80f-120">If calls can be routed from one SIP to another, you'll receive output similar to this:</span></span>

<span data-ttu-id="9f80f-121">FirstMatchingRoute MatchingUsage MatchingRoutes</span><span class="sxs-lookup"><span data-stu-id="9f80f-121">FirstMatchingRoute MatchingUsage MatchingRoutes</span></span>

<span data-ttu-id="9f80f-122">\------------------ ------------- --------------</span><span class="sxs-lookup"><span data-stu-id="9f80f-122">\------------------ ------------- --------------</span></span>

<span data-ttu-id="9f80f-123">RedmondRoute LocalUsage {RedmondRoute}</span><span class="sxs-lookup"><span data-stu-id="9f80f-123">RedmondRoute LocalUsage {RedmondRoute}</span></span>

<span data-ttu-id="9f80f-124">テストが成功しなかった場合は、次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9f80f-124">If the test did not succeed, you'll receive output similar to this:</span></span>

<span data-ttu-id="9f80f-125">CsInterTrunkRouting: パラメーターでの引数変換を処理できません</span><span class="sxs-lookup"><span data-stu-id="9f80f-125">Test-CsInterTrunkRouting : Cannot process argument transformation on parameter</span></span>

<span data-ttu-id="9f80f-126">'TrunkConfiguration'.</span><span class="sxs-lookup"><span data-stu-id="9f80f-126">'TrunkConfiguration'.</span></span> <span data-ttu-id="9f80f-127">TrunkConfigurationsetting (パラメーター) が無効です。</span><span class="sxs-lookup"><span data-stu-id="9f80f-127">Invalid TrunkConfigurationsetting (parameter).</span></span> <span data-ttu-id="9f80f-128">を指定する</span><span class="sxs-lookup"><span data-stu-id="9f80f-128">Specify a</span></span>

<span data-ttu-id="9f80f-129">有効な設定 (パラメーター) を入力してからやり直してください。</span><span class="sxs-lookup"><span data-stu-id="9f80f-129">valid setting (parameter) and then try again.</span></span>

<span data-ttu-id="9f80f-130">行: 1 char:79</span><span class="sxs-lookup"><span data-stu-id="9f80f-130">At line:1 char:79</span></span>

<span data-ttu-id="9f80f-131">\+CsInterTrunkRouting-TargetNumber "tel: + 12065551219"</span><span class="sxs-lookup"><span data-stu-id="9f80f-131">\+ Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219"</span></span>

<span data-ttu-id="9f80f-132">\-TrunkConfiguration $t...</span><span class="sxs-lookup"><span data-stu-id="9f80f-132">\-TrunkConfiguration $t ...</span></span>

\+

~~

<span data-ttu-id="9f80f-133">\+カテゴリ情報: InvalidData: (:)\[CsInterTrunkRouting\]、Par</span><span class="sxs-lookup"><span data-stu-id="9f80f-133">\+ CategoryInfo : InvalidData: (:) \[Test-CsInterTrunkRouting\], Par</span></span>

<span data-ttu-id="9f80f-134">Ameterbindingargumentの例外</span><span class="sxs-lookup"><span data-stu-id="9f80f-134">ameterBindingArgumentTransformationException</span></span>

<span data-ttu-id="9f80f-135">\+FullyQualifiedErrorId: Parameterargumentトランスエラー、Microsoft R</span><span class="sxs-lookup"><span data-stu-id="9f80f-135">\+ FullyQualifiedErrorId : ParameterArgumentTransformationError,Microsoft.R</span></span>

<span data-ttu-id="9f80f-136">tc.TestOcsInterTrunkRoutingCmdlet を管理します。</span><span class="sxs-lookup"><span data-stu-id="9f80f-136">tc.Management.Voice.Cmdlets.TestOcsInterTrunkRoutingCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="9f80f-137">テストに失敗した可能性がある理由</span><span class="sxs-lookup"><span data-stu-id="9f80f-137">Reasons why the test might have failed</span></span>

<span data-ttu-id="9f80f-138">次に **、テスト-CsInterTrunkRouting**が失敗する可能性がある一般的な理由を示します。</span><span class="sxs-lookup"><span data-stu-id="9f80f-138">Here are some common reasons why **Test-CsInterTrunkRouting** might fail:</span></span>

  - <span data-ttu-id="9f80f-139">無効なパラメーターが指定されました。</span><span class="sxs-lookup"><span data-stu-id="9f80f-139">You specified invalid parameters.</span></span> <span data-ttu-id="9f80f-140">トランクがまだ正しく構成されておらず、指定されたターゲット番号が間違っているか、無効である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9f80f-140">The trunk might not yet be correctly configured and the specified target number might be incorrect or invalid.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9f80f-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="9f80f-141">See Also</span></span>


[<span data-ttu-id="9f80f-142">Get-CsTrunk</span><span class="sxs-lookup"><span data-stu-id="9f80f-142">Get-CsTrunk</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk)  
[<span data-ttu-id="9f80f-143">Get-CsTrunkConfiguration</span><span class="sxs-lookup"><span data-stu-id="9f80f-143">Get-CsTrunkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

