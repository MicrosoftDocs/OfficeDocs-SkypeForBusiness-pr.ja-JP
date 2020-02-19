---
title: 主要住所の住所ガイドに対して都市の住所をテストする
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
ms.openlocfilehash: 7f9115e6bc0c65f589effc08ecd5f7b681208a54
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141473"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-civic-addresses-against-the-master-street-address-guide-in-lync-server-2013"></a><span data-ttu-id="3ccaa-102">Lync Server 2013 の主要な住所の住所ガイドに対して都市の住所をテストする</span><span class="sxs-lookup"><span data-stu-id="3ccaa-102">Testing civic addresses against the master street address guide in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ccaa-103">_**トピックの最終更新日:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="3ccaa-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3ccaa-104">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="3ccaa-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="3ccaa-105">毎日</span><span class="sxs-lookup"><span data-stu-id="3ccaa-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ccaa-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="3ccaa-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="3ccaa-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3ccaa-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ccaa-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="3ccaa-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="3ccaa-109">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ccaa-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="3ccaa-110">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、テスト用の登録コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ccaa-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="3ccaa-111">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3ccaa-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisCivicAddress &quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="3ccaa-112">説明</span><span class="sxs-lookup"><span data-stu-id="3ccaa-112">Description</span></span>

<span data-ttu-id="3ccaa-113">Test-csliscivicaddress コマンドレットは、場所情報サービス (LIS) データベースに追加された場所を確認するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="3ccaa-113">The Test-CsLisCivicAddress cmdlet is used to verify locations that were added to your Location Information service (LIS) database.</span></span> <span data-ttu-id="3ccaa-114">このコマンドレットは、E9-1-1 ネットワークルーティングプロバイダーに属している主要な住所の住所ガイド (MSAG) にある場所を比較することで機能します。</span><span class="sxs-lookup"><span data-stu-id="3ccaa-114">The cmdlet works by comparing locations against the locations found in the Master Street Address Guide (MSAG) that belongs to your E9-1-1 Network Routing Provider.</span></span> <span data-ttu-id="3ccaa-115">ネットワークルーティングプロバイダーがない場合、またはプロバイダーに到達できない場合、テストは失敗します。</span><span class="sxs-lookup"><span data-stu-id="3ccaa-115">If you do not have a network routing provider or if the provider cannot be reached, then your tests will fail.</span></span>

<span data-ttu-id="3ccaa-116">コマンドにオプションのスイッチパラメーター UpdateValidationStatus を追加すると、テストを渡すアドレスごとに、対応する MSAGValid database プロパティが True に設定されます。</span><span class="sxs-lookup"><span data-stu-id="3ccaa-116">If you add the optional switch parameter UpdateValidationStatus to your command, then the corresponding MSAGValid database property will be set to True for each address passing the test.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="3ccaa-117">テストの実行</span><span class="sxs-lookup"><span data-stu-id="3ccaa-117">Running the test</span></span>

<span data-ttu-id="3ccaa-118">Test-csliscivicaddress コマンドレットを使用して、個々のアドレスをテストしたり、複数のアドレスをテストしたりできます。</span><span class="sxs-lookup"><span data-stu-id="3ccaa-118">The Test-CsLisCivicAddress cmdlet can be used to test individual addresses or to test multiple addresses.</span></span> <span data-ttu-id="3ccaa-119">たとえば、次のコマンドは、Redmond、ワシントンにある1つのアドレスをテストします。</span><span class="sxs-lookup"><span data-stu-id="3ccaa-119">For example, this command tests a single address located in Redmond, WA:</span></span>

    Test-CsLisCivicAddress -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName Main -StreetSuffix St -PostDirectional "" -City Redmond -State WA -PostalCode 98052 -Country US -UpdateValidationStatus

<span data-ttu-id="3ccaa-120">次のコマンドは、LIS データベースに現在含まれているすべてのアドレスをテストします。</span><span class="sxs-lookup"><span data-stu-id="3ccaa-120">By comparison, this command tests all the addresses currently in your LIS database:</span></span>

    Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus

<span data-ttu-id="3ccaa-121">詳細については、「 [Test-CsRegistration](https://technet.microsoft.com/library/Gg412737(v=OCS.15))コマンドレットのヘルプドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ccaa-121">For more information, see the Help documentation for the [Test-CsRegistration](https://technet.microsoft.com/library/Gg412737(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="3ccaa-122">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="3ccaa-122">Determining success or failure</span></span>

<span data-ttu-id="3ccaa-123">Test-csliscivicaddress は、指定された住所に対して、成功または失敗を報告します。</span><span class="sxs-lookup"><span data-stu-id="3ccaa-123">Test-CsLisCivicAddress will report back Success or Failure for the supplied addresses.</span></span> <span data-ttu-id="3ccaa-124">アドレスが見つからない場合、またはサービスプロバイダーに接続できない場合、アドレステストは失敗します。</span><span class="sxs-lookup"><span data-stu-id="3ccaa-124">An address test will fail if the address cannot be found or if the service provider cannot be contacted.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="3ccaa-125">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="3ccaa-125">Reasons why the test might have failed</span></span>

<span data-ttu-id="3ccaa-126">Test-csliscivicaddress が失敗する可能性のある一般的な原因を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3ccaa-126">Here are some common reasons why Test-CsLisCivicAddress might fail:</span></span>

  - <span data-ttu-id="3ccaa-127">LIS サービスプロバイダーを使用できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3ccaa-127">The LIS service provider might not be available.</span></span> <span data-ttu-id="3ccaa-128">LIS サービスプロバイダーの URL を取得するには、Export-cslisconfiguration コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="3ccaa-128">You can retrieve the URL of your LIS service provider by running the Get-CsLisConfiguration cmdlet:</span></span>
    
        Get-CsLisConfiguration 
    
    <span data-ttu-id="3ccaa-129">その URL に ping を実行して、サービスプロバイダーが利用可能であることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="3ccaa-129">You can then ping that URL to verify that the service provider is available.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

