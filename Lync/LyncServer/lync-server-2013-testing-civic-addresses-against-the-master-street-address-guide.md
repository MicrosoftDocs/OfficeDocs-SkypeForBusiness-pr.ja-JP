---
title: 主要住所の住所ガイドに対して都市の住所をテストする
description: 主要住所ガイドに対して、都市の住所をテストします。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing civic addresses against the master street address guide
ms:assetid: dc680de9-2a0f-4fd3-a99e-9bab0bc30ae5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690132(v=OCS.15)
ms:contentKeyID: 63969657
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16e0d721b70e3db175b2d23ddee6f59d13a13c4e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560703"
---
# <a name="testing-civic-addresses-against-the-master-street-address-guide-in-lync-server-2013"></a><span data-ttu-id="5e070-103">Lync Server 2013 の主要な住所の住所ガイドに対して都市の住所をテストする</span><span class="sxs-lookup"><span data-stu-id="5e070-103">Testing civic addresses against the master street address guide in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e070-104">_**トピックの最終更新日:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="5e070-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5e070-105">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="5e070-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="5e070-106">毎日</span><span class="sxs-lookup"><span data-stu-id="5e070-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e070-107">テストツール</span><span class="sxs-lookup"><span data-stu-id="5e070-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="5e070-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5e070-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e070-109">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="5e070-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="5e070-110">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e070-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="5e070-111">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには Test-CsRegistration コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e070-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="5e070-112">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5e070-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisCivicAddress &quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="5e070-113">説明</span><span class="sxs-lookup"><span data-stu-id="5e070-113">Description</span></span>

<span data-ttu-id="5e070-114">Test-CsLisCivicAddress コマンドレットは、場所情報サービス (LIS) データベースに追加された場所を確認するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="5e070-114">The Test-CsLisCivicAddress cmdlet is used to verify locations that were added to your Location Information service (LIS) database.</span></span> <span data-ttu-id="5e070-115">このコマンドレットは、E9-1-1 ネットワークルーティングプロバイダーに属している主要な住所の住所ガイド (MSAG) にある場所を比較することで機能します。</span><span class="sxs-lookup"><span data-stu-id="5e070-115">The cmdlet works by comparing locations against the locations found in the Master Street Address Guide (MSAG) that belongs to your E9-1-1 Network Routing Provider.</span></span> <span data-ttu-id="5e070-116">ネットワークルーティングプロバイダーがない場合、またはプロバイダーに到達できない場合、テストは失敗します。</span><span class="sxs-lookup"><span data-stu-id="5e070-116">If you do not have a network routing provider or if the provider cannot be reached, then your tests will fail.</span></span>

<span data-ttu-id="5e070-117">コマンドにオプションのスイッチパラメーター UpdateValidationStatus を追加すると、テストを渡すアドレスごとに、対応する MSAGValid database プロパティが True に設定されます。</span><span class="sxs-lookup"><span data-stu-id="5e070-117">If you add the optional switch parameter UpdateValidationStatus to your command, then the corresponding MSAGValid database property will be set to True for each address passing the test.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="5e070-118">テストの実行</span><span class="sxs-lookup"><span data-stu-id="5e070-118">Running the test</span></span>

<span data-ttu-id="5e070-119">Test-CsLisCivicAddress コマンドレットを使用して、個々のアドレスをテストしたり、複数のアドレスをテストしたりできます。</span><span class="sxs-lookup"><span data-stu-id="5e070-119">The Test-CsLisCivicAddress cmdlet can be used to test individual addresses or to test multiple addresses.</span></span> <span data-ttu-id="5e070-120">たとえば、次のコマンドは、Redmond、ワシントンにある1つのアドレスをテストします。</span><span class="sxs-lookup"><span data-stu-id="5e070-120">For example, this command tests a single address located in Redmond, WA:</span></span>

    Test-CsLisCivicAddress -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName Main -StreetSuffix St -PostDirectional "" -City Redmond -State WA -PostalCode 98052 -Country US -UpdateValidationStatus

<span data-ttu-id="5e070-121">次のコマンドは、LIS データベースに現在含まれているすべてのアドレスをテストします。</span><span class="sxs-lookup"><span data-stu-id="5e070-121">By comparison, this command tests all the addresses currently in your LIS database:</span></span>

    Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus

<span data-ttu-id="5e070-122">詳細については、「 [Test-CsRegistration](https://technet.microsoft.com/library/Gg412737(v=OCS.15)) コマンドレットのヘルプドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e070-122">For more information, see the Help documentation for the [Test-CsRegistration](https://technet.microsoft.com/library/Gg412737(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="5e070-123">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="5e070-123">Determining success or failure</span></span>

<span data-ttu-id="5e070-124">Test-CsLisCivicAddress は、指定されたアドレスに対して、成功または失敗の報告を返します。</span><span class="sxs-lookup"><span data-stu-id="5e070-124">Test-CsLisCivicAddress will report back Success or Failure for the supplied addresses.</span></span> <span data-ttu-id="5e070-125">アドレスが見つからない場合、またはサービスプロバイダーに接続できない場合、アドレステストは失敗します。</span><span class="sxs-lookup"><span data-stu-id="5e070-125">An address test will fail if the address cannot be found or if the service provider cannot be contacted.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="5e070-126">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="5e070-126">Reasons why the test might have failed</span></span>

<span data-ttu-id="5e070-127">Test-CsLisCivicAddress が失敗する可能性のある一般的な理由を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5e070-127">Here are some common reasons why Test-CsLisCivicAddress might fail:</span></span>

  - <span data-ttu-id="5e070-128">LIS サービスプロバイダーを使用できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5e070-128">The LIS service provider might not be available.</span></span> <span data-ttu-id="5e070-129">Get-CsLisConfiguration コマンドレットを実行して、LIS サービスプロバイダーの URL を取得できます。</span><span class="sxs-lookup"><span data-stu-id="5e070-129">You can retrieve the URL of your LIS service provider by running the Get-CsLisConfiguration cmdlet:</span></span>
    
        Get-CsLisConfiguration 
    
    <span data-ttu-id="5e070-130">その URL に ping を実行して、サービスプロバイダーが利用可能であることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="5e070-130">You can then ping that URL to verify that the service provider is available.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

