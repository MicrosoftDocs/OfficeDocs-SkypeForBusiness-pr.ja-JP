---
title: 'Lync Server 2013: PSTN 通話のルーティングのテスト'
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
ms.openlocfilehash: 8b831aef01d80a0d68a0eea06f429502026b7ccb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141333"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-pstn-phone-call-routing-in-lync-server-2013"></a><span data-ttu-id="c41ac-102">Lync Server 2013 での PSTN 通話のルーティングのテスト</span><span class="sxs-lookup"><span data-stu-id="c41ac-102">Testing PSTN phone call routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c41ac-103">_**トピックの最終更新日:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="c41ac-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c41ac-104">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="c41ac-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="c41ac-105">毎日</span><span class="sxs-lookup"><span data-stu-id="c41ac-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c41ac-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="c41ac-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="c41ac-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c41ac-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c41ac-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="c41ac-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="c41ac-109">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="c41ac-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="c41ac-110">Windows PowerShell のリモートインスタンスを使用して実行する場合は、 <strong>test-csintertrunkrouting</strong>コマンドレットを実行するためのアクセス許可を持つ RBAC の役割がユーザーに割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c41ac-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsInterTrunkRouting</strong> cmdlet.</span></span> <span data-ttu-id="c41ac-111">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c41ac-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsInterTrunkRouting&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="c41ac-112">説明</span><span class="sxs-lookup"><span data-stu-id="c41ac-112">Description</span></span>

<span data-ttu-id="c41ac-113">**Test-csintertrunkrouting**コマンドレットは、呼び出しがある SIP から別の SIP にルーティングできることを検証します。</span><span class="sxs-lookup"><span data-stu-id="c41ac-113">The **Test-CsInterTrunkRouting** cmdlet verifies that calls can be routed from one SIP to another.</span></span> <span data-ttu-id="c41ac-114">これを行うために、コマンドレットには電話番号とトランク構成が与えられます。</span><span class="sxs-lookup"><span data-stu-id="c41ac-114">To do this, the cmdlet is given a phone number and a trunk configuration.</span></span> <span data-ttu-id="c41ac-115">**Test-csintertrunkrouting**は、指定された番号について、一致するルートと一致する PSTN 使用法を報告します。</span><span class="sxs-lookup"><span data-stu-id="c41ac-115">**Test-CsInterTrunkRouting** will then report back matching routes and matching PSTN usages for the specified number.</span></span> <span data-ttu-id="c41ac-116">トランクには、指定された電話番号に一致する番号パターンがあり、トランクが少なくとも1つの PSTN 使用法を共有している場合にのみ、トランク間で通話をルーティングできることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c41ac-116">Note that calls can be routed between trunks only if the trunks have a number pattern that matches the specified phone number and only if the trunks share at least one PSTN usage.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="c41ac-117">テストの実行</span><span class="sxs-lookup"><span data-stu-id="c41ac-117">Running the test</span></span>

<span data-ttu-id="c41ac-118">次に示すコマンドは、ユーザーが Redmond サイトのトランク構成設定を使用して電話番号1-206-555-1219 を呼び出せるようにする、一致するルートと一致する電話使用法を返します。</span><span class="sxs-lookup"><span data-stu-id="c41ac-118">The commands shown below return the matching routes and matching phone usages that enable users to call the phone number 1-206-555-1219 using the trunk configuration settings for the Redmond site.</span></span>

    $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
    
    Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219" -TrunkConfiguration $trunk

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="c41ac-119">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="c41ac-119">Determining success or failure</span></span>

<span data-ttu-id="c41ac-120">通話がある SIP から別の SIP にルーティングできる場合は、次のような出力が得られます。</span><span class="sxs-lookup"><span data-stu-id="c41ac-120">If calls can be routed from one SIP to another, you'll receive output similar to this:</span></span>

<span data-ttu-id="c41ac-121">FirstMatchingRoute MatchingUsage MatchingRoutes</span><span class="sxs-lookup"><span data-stu-id="c41ac-121">FirstMatchingRoute MatchingUsage MatchingRoutes</span></span>

<span data-ttu-id="c41ac-122">\------------------ ------------- --------------</span><span class="sxs-lookup"><span data-stu-id="c41ac-122">\------------------ ------------- --------------</span></span>

<span data-ttu-id="c41ac-123">RedmondRoute LocalUsage {RedmondRoute}</span><span class="sxs-lookup"><span data-stu-id="c41ac-123">RedmondRoute LocalUsage {RedmondRoute}</span></span>

<span data-ttu-id="c41ac-124">テストが成功しなかった場合は、次のような出力が得られます。</span><span class="sxs-lookup"><span data-stu-id="c41ac-124">If the test did not succeed, you'll receive output similar to this:</span></span>

<span data-ttu-id="c41ac-125">Test-csintertrunkrouting: パラメーターの引数変換を処理できません</span><span class="sxs-lookup"><span data-stu-id="c41ac-125">Test-CsInterTrunkRouting : Cannot process argument transformation on parameter</span></span>

<span data-ttu-id="c41ac-126">' Microsoft.rtc.management.writableconfig.settings.trunkconfiguration.trunkconfiguration 型 '。</span><span class="sxs-lookup"><span data-stu-id="c41ac-126">'TrunkConfiguration'.</span></span> <span data-ttu-id="c41ac-127">TrunkConfigurationsetting (パラメーター) が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="c41ac-127">Invalid TrunkConfigurationsetting (parameter).</span></span> <span data-ttu-id="c41ac-128">を指定する</span><span class="sxs-lookup"><span data-stu-id="c41ac-128">Specify a</span></span>

<span data-ttu-id="c41ac-129">有効な設定 (パラメーター) を指定してから、もう一度実行してください。</span><span class="sxs-lookup"><span data-stu-id="c41ac-129">valid setting (parameter) and then try again.</span></span>

<span data-ttu-id="c41ac-130">行: 1 文字:79</span><span class="sxs-lookup"><span data-stu-id="c41ac-130">At line:1 char:79</span></span>

<span data-ttu-id="c41ac-131">\+Test-csintertrunkrouting-TargetNumber "tel: + 12065551219 など"</span><span class="sxs-lookup"><span data-stu-id="c41ac-131">\+ Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219"</span></span>

<span data-ttu-id="c41ac-132">\-Microsoft.rtc.management.writableconfig.settings.trunkconfiguration.trunkconfiguration 型 $t</span><span class="sxs-lookup"><span data-stu-id="c41ac-132">\-TrunkConfiguration $t ...</span></span>

\+

~~

<span data-ttu-id="c41ac-133">\+カテゴリ情報: InvalidData: (:)\[Test-csintertrunkrouting\]、Par</span><span class="sxs-lookup"><span data-stu-id="c41ac-133">\+ CategoryInfo : InvalidData: (:) \[Test-CsInterTrunkRouting\], Par</span></span>

<span data-ttu-id="c41ac-134">Ameterbindingargumentの例外</span><span class="sxs-lookup"><span data-stu-id="c41ac-134">ameterBindingArgumentTransformationException</span></span>

<span data-ttu-id="c41ac-135">\+FullyQualifiedErrorId: Parameterargumentトランスエラー、Microsoft R</span><span class="sxs-lookup"><span data-stu-id="c41ac-135">\+ FullyQualifiedErrorId : ParameterArgumentTransformationError,Microsoft.R</span></span>

<span data-ttu-id="c41ac-136">c.TestOcsInterTrunkRoutingCmdlet の管理</span><span class="sxs-lookup"><span data-stu-id="c41ac-136">tc.Management.Voice.Cmdlets.TestOcsInterTrunkRoutingCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="c41ac-137">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="c41ac-137">Reasons why the test might have failed</span></span>

<span data-ttu-id="c41ac-138">**Test-csintertrunkrouting**が失敗する可能性のある一般的な原因を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c41ac-138">Here are some common reasons why **Test-CsInterTrunkRouting** might fail:</span></span>

  - <span data-ttu-id="c41ac-139">無効なパラメーターを指定しました。</span><span class="sxs-lookup"><span data-stu-id="c41ac-139">You specified invalid parameters.</span></span> <span data-ttu-id="c41ac-140">トランクが正しく構成されていない可能性があり、指定されたターゲット番号が正しくないか、無効である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c41ac-140">The trunk might not yet be correctly configured and the specified target number might be incorrect or invalid.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c41ac-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="c41ac-141">See Also</span></span>


[<span data-ttu-id="c41ac-142">取得-CsTrunk</span><span class="sxs-lookup"><span data-stu-id="c41ac-142">Get-CsTrunk</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk)  
[<span data-ttu-id="c41ac-143">Get-cstrunkconfiguration</span><span class="sxs-lookup"><span data-stu-id="c41ac-143">Get-CsTrunkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

