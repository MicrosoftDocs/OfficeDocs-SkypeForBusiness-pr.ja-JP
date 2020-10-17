---
title: 'Lync Server 2013: PSTN 通話のルーティングのテスト'
description: 'Lync Server 2013: PSTN 電話の呼び出しのルーティングをテストします。'
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
ms.openlocfilehash: da931b43176932a9b6781fa27318e83e6994548c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556273"
---
# <a name="testing-pstn-phone-call-routing-in-lync-server-2013"></a><span data-ttu-id="0d7bf-103">Lync Server 2013 での PSTN 通話のルーティングのテスト</span><span class="sxs-lookup"><span data-stu-id="0d7bf-103">Testing PSTN phone call routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d7bf-104">_**トピックの最終更新日:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="0d7bf-104">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0d7bf-105">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="0d7bf-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="0d7bf-106">毎日</span><span class="sxs-lookup"><span data-stu-id="0d7bf-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d7bf-107">テストツール</span><span class="sxs-lookup"><span data-stu-id="0d7bf-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="0d7bf-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0d7bf-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d7bf-109">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="0d7bf-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="0d7bf-110">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d7bf-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="0d7bf-111">Windows PowerShell のリモートインスタンスを使用して実行する場合は、 <strong>test-csintertrunkrouting</strong> コマンドレットを実行するためのアクセス許可を持つ RBAC の役割がユーザーに割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d7bf-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsInterTrunkRouting</strong> cmdlet.</span></span> <span data-ttu-id="0d7bf-112">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0d7bf-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsInterTrunkRouting&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="0d7bf-113">説明</span><span class="sxs-lookup"><span data-stu-id="0d7bf-113">Description</span></span>

<span data-ttu-id="0d7bf-114">**Test-csintertrunkrouting**コマンドレットは、呼び出しがある SIP から別の SIP にルーティングできることを検証します。</span><span class="sxs-lookup"><span data-stu-id="0d7bf-114">The **Test-CsInterTrunkRouting** cmdlet verifies that calls can be routed from one SIP to another.</span></span> <span data-ttu-id="0d7bf-115">これを行うために、コマンドレットには電話番号とトランク構成が与えられます。</span><span class="sxs-lookup"><span data-stu-id="0d7bf-115">To do this, the cmdlet is given a phone number and a trunk configuration.</span></span> <span data-ttu-id="0d7bf-116">**Test-csintertrunkrouting** は、指定された番号について、一致するルートと一致する PSTN 使用法を報告します。</span><span class="sxs-lookup"><span data-stu-id="0d7bf-116">**Test-CsInterTrunkRouting** will then report back matching routes and matching PSTN usages for the specified number.</span></span> <span data-ttu-id="0d7bf-117">トランクには、指定された電話番号に一致する番号パターンがあり、トランクが少なくとも1つの PSTN 使用法を共有している場合にのみ、トランク間で通話をルーティングできることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0d7bf-117">Note that calls can be routed between trunks only if the trunks have a number pattern that matches the specified phone number and only if the trunks share at least one PSTN usage.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="0d7bf-118">テストの実行</span><span class="sxs-lookup"><span data-stu-id="0d7bf-118">Running the test</span></span>

<span data-ttu-id="0d7bf-119">次に示すコマンドは、ユーザーが Redmond サイトのトランク構成設定を使用して電話番号1-206-555-1219 を呼び出せるようにする、一致するルートと一致する電話使用法を返します。</span><span class="sxs-lookup"><span data-stu-id="0d7bf-119">The commands shown below return the matching routes and matching phone usages that enable users to call the phone number 1-206-555-1219 using the trunk configuration settings for the Redmond site.</span></span>

    $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
    
    Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219" -TrunkConfiguration $trunk

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="0d7bf-120">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="0d7bf-120">Determining success or failure</span></span>

<span data-ttu-id="0d7bf-121">通話がある SIP から別の SIP にルーティングできる場合は、次のような出力が得られます。</span><span class="sxs-lookup"><span data-stu-id="0d7bf-121">If calls can be routed from one SIP to another, you'll receive output similar to this:</span></span>

<span data-ttu-id="0d7bf-122">FirstMatchingRoute MatchingUsage MatchingRoutes</span><span class="sxs-lookup"><span data-stu-id="0d7bf-122">FirstMatchingRoute MatchingUsage MatchingRoutes</span></span>

<span data-ttu-id="0d7bf-123">\------------------ ------------- --------------</span><span class="sxs-lookup"><span data-stu-id="0d7bf-123">\------------------ ------------- --------------</span></span>

<span data-ttu-id="0d7bf-124">RedmondRoute LocalUsage {RedmondRoute}</span><span class="sxs-lookup"><span data-stu-id="0d7bf-124">RedmondRoute LocalUsage {RedmondRoute}</span></span>

<span data-ttu-id="0d7bf-125">テストが成功しなかった場合は、次のような出力が得られます。</span><span class="sxs-lookup"><span data-stu-id="0d7bf-125">If the test did not succeed, you'll receive output similar to this:</span></span>

<span data-ttu-id="0d7bf-126">Test-CsInterTrunkRouting: パラメーターの引数変換を処理できません</span><span class="sxs-lookup"><span data-stu-id="0d7bf-126">Test-CsInterTrunkRouting : Cannot process argument transformation on parameter</span></span>

<span data-ttu-id="0d7bf-127">' Microsoft.rtc.management.writableconfig.settings.trunkconfiguration.trunkconfiguration 型 '。</span><span class="sxs-lookup"><span data-stu-id="0d7bf-127">'TrunkConfiguration'.</span></span> <span data-ttu-id="0d7bf-128">TrunkConfigurationsetting (パラメーター) が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="0d7bf-128">Invalid TrunkConfigurationsetting (parameter).</span></span> <span data-ttu-id="0d7bf-129">を指定する</span><span class="sxs-lookup"><span data-stu-id="0d7bf-129">Specify a</span></span>

<span data-ttu-id="0d7bf-130">有効な設定 (パラメーター) を指定してから、もう一度実行してください。</span><span class="sxs-lookup"><span data-stu-id="0d7bf-130">valid setting (parameter) and then try again.</span></span>

<span data-ttu-id="0d7bf-131">行: 1 文字:79</span><span class="sxs-lookup"><span data-stu-id="0d7bf-131">At line:1 char:79</span></span>

<span data-ttu-id="0d7bf-132">\+ Test-CsInterTrunkRouting-TargetNumber "tel: + 12065551219 など"</span><span class="sxs-lookup"><span data-stu-id="0d7bf-132">\+ Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219"</span></span>

<span data-ttu-id="0d7bf-133">\-Microsoft.rtc.management.writableconfig.settings.trunkconfiguration.trunkconfiguration 型 $t</span><span class="sxs-lookup"><span data-stu-id="0d7bf-133">\-TrunkConfiguration $t ...</span></span>

\+

~~

<span data-ttu-id="0d7bf-134">\+ カテゴリ情報: InvalidData: (:) \[Test-csintertrunkrouting \] 、Par</span><span class="sxs-lookup"><span data-stu-id="0d7bf-134">\+ CategoryInfo : InvalidData: (:) \[Test-CsInterTrunkRouting\], Par</span></span>

<span data-ttu-id="0d7bf-135">Ameterbindingargumentの例外</span><span class="sxs-lookup"><span data-stu-id="0d7bf-135">ameterBindingArgumentTransformationException</span></span>

<span data-ttu-id="0d7bf-136">\+ FullyQualifiedErrorId: Parameterargumentトランスエラー、Microsoft R</span><span class="sxs-lookup"><span data-stu-id="0d7bf-136">\+ FullyQualifiedErrorId : ParameterArgumentTransformationError,Microsoft.R</span></span>

<span data-ttu-id="0d7bf-137">c.TestOcsInterTrunkRoutingCmdlet の管理</span><span class="sxs-lookup"><span data-stu-id="0d7bf-137">tc.Management.Voice.Cmdlets.TestOcsInterTrunkRoutingCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="0d7bf-138">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="0d7bf-138">Reasons why the test might have failed</span></span>

<span data-ttu-id="0d7bf-139">**Test-csintertrunkrouting**が失敗する可能性のある一般的な原因を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0d7bf-139">Here are some common reasons why **Test-CsInterTrunkRouting** might fail:</span></span>

  - <span data-ttu-id="0d7bf-140">無効なパラメーターを指定しました。</span><span class="sxs-lookup"><span data-stu-id="0d7bf-140">You specified invalid parameters.</span></span> <span data-ttu-id="0d7bf-141">トランクが正しく構成されていない可能性があり、指定されたターゲット番号が正しくないか、無効である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0d7bf-141">The trunk might not yet be correctly configured and the specified target number might be incorrect or invalid.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0d7bf-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="0d7bf-142">See Also</span></span>


[<span data-ttu-id="0d7bf-143">取得-CsTrunk</span><span class="sxs-lookup"><span data-stu-id="0d7bf-143">Get-CsTrunk</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk)  
[<span data-ttu-id="0d7bf-144">Get-cstrunkconfiguration</span><span class="sxs-lookup"><span data-stu-id="0d7bf-144">Get-CsTrunkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

