---
title: マスター番地の住所ガイドに照らして都市の住所をテストする
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
ms.openlocfilehash: 37d6aa1443dc2e062aa099237d9b25f2b33e32b2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745813"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-civic-addresses-against-the-master-street-address-guide-in-lync-server-2013"></a><span data-ttu-id="1f4ea-102">Lync Server 2013 の主要住所ガイドに照らして、都市の住所をテストする</span><span class="sxs-lookup"><span data-stu-id="1f4ea-102">Testing civic addresses against the master street address guide in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f4ea-103">_**最終更新日:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="1f4ea-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1f4ea-104">確認のスケジュール</span><span class="sxs-lookup"><span data-stu-id="1f4ea-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="1f4ea-105">[毎日]</span><span class="sxs-lookup"><span data-stu-id="1f4ea-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f4ea-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="1f4ea-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="1f4ea-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1f4ea-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f4ea-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="1f4ea-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="1f4ea-109">Lync Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f4ea-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="1f4ea-110">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、CsRegistration コマンドレットを実行するためのアクセス許可が与えられた RBAC の役割を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f4ea-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="1f4ea-111">このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1f4ea-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisCivicAddress &quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="1f4ea-112">説明</span><span class="sxs-lookup"><span data-stu-id="1f4ea-112">Description</span></span>

<span data-ttu-id="1f4ea-113">CsLisCivicAddress コマンドレットを使用して、位置情報サービス (LIS) データベースに追加された場所を確認します。</span><span class="sxs-lookup"><span data-stu-id="1f4ea-113">The Test-CsLisCivicAddress cmdlet is used to verify locations that were added to your Location Information service (LIS) database.</span></span> <span data-ttu-id="1f4ea-114">このコマンドレットを実行するには、E9 のネットワークルーティングプロバイダーに属している主要な住所ガイド (MSAG) で見つかった場所を比較します。</span><span class="sxs-lookup"><span data-stu-id="1f4ea-114">The cmdlet works by comparing locations against the locations found in the Master Street Address Guide (MSAG) that belongs to your E9-1-1 Network Routing Provider.</span></span> <span data-ttu-id="1f4ea-115">ネットワークルーティングプロバイダーを持っていない場合、またはプロバイダーに接続できない場合、テストは失敗します。</span><span class="sxs-lookup"><span data-stu-id="1f4ea-115">If you do not have a network routing provider or if the provider cannot be reached, then your tests will fail.</span></span>

<span data-ttu-id="1f4ea-116">コマンドにオプションのスイッチパラメーター UpdateValidationStatus を追加した場合、テストを渡す各アドレスについて、対応する MSAGValid な database プロパティが True に設定されます。</span><span class="sxs-lookup"><span data-stu-id="1f4ea-116">If you add the optional switch parameter UpdateValidationStatus to your command, then the corresponding MSAGValid database property will be set to True for each address passing the test.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="1f4ea-117">テストの実行</span><span class="sxs-lookup"><span data-stu-id="1f4ea-117">Running the test</span></span>

<span data-ttu-id="1f4ea-118">CsLisCivicAddress コマンドレットを使用して、個々のアドレスのテストや複数のアドレスのテストを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="1f4ea-118">The Test-CsLisCivicAddress cmdlet can be used to test individual addresses or to test multiple addresses.</span></span> <span data-ttu-id="1f4ea-119">たとえば、このコマンドは、Redmond、WA にある1つのアドレスをテストします。</span><span class="sxs-lookup"><span data-stu-id="1f4ea-119">For example, this command tests a single address located in Redmond, WA:</span></span>

    Test-CsLisCivicAddress -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName Main -StreetSuffix St -PostDirectional "" -City Redmond -State WA -PostalCode 98052 -Country US -UpdateValidationStatus

<span data-ttu-id="1f4ea-120">このコマンドでは、現在の LIS データベースにあるすべてのアドレスがテストされます。</span><span class="sxs-lookup"><span data-stu-id="1f4ea-120">By comparison, this command tests all the addresses currently in your LIS database:</span></span>

    Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus

<span data-ttu-id="1f4ea-121">詳細については、「 [CsRegistration のテスト](https://technet.microsoft.com/en-us/library/Gg412737(v=OCS.15))」コマンドレットのヘルプドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f4ea-121">For more information, see the Help documentation for the [Test-CsRegistration](https://technet.microsoft.com/en-us/library/Gg412737(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="1f4ea-122">成功または失敗を確認する</span><span class="sxs-lookup"><span data-stu-id="1f4ea-122">Determining success or failure</span></span>

<span data-ttu-id="1f4ea-123">CsLisCivicAddress によって、提供されたアドレスのバックの成功または失敗が報告されます。</span><span class="sxs-lookup"><span data-stu-id="1f4ea-123">Test-CsLisCivicAddress will report back Success or Failure for the supplied addresses.</span></span> <span data-ttu-id="1f4ea-124">アドレスが見つからない場合、またはサービスプロバイダに接続できない場合、住所テストは失敗します。</span><span class="sxs-lookup"><span data-stu-id="1f4ea-124">An address test will fail if the address cannot be found or if the service provider cannot be contacted.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="1f4ea-125">テストに失敗した可能性がある理由</span><span class="sxs-lookup"><span data-stu-id="1f4ea-125">Reasons why the test might have failed</span></span>

<span data-ttu-id="1f4ea-126">次に、テスト-CsLisCivicAddress が失敗する可能性がある一般的な理由を示します。</span><span class="sxs-lookup"><span data-stu-id="1f4ea-126">Here are some common reasons why Test-CsLisCivicAddress might fail:</span></span>

  - <span data-ttu-id="1f4ea-127">LIS サービスプロバイダーが利用できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1f4ea-127">The LIS service provider might not be available.</span></span> <span data-ttu-id="1f4ea-128">CsLisConfiguration コマンドレットを実行して、LIS サービスプロバイダーの URL を取得できます。</span><span class="sxs-lookup"><span data-stu-id="1f4ea-128">You can retrieve the URL of your LIS service provider by running the Get-CsLisConfiguration cmdlet:</span></span>
    
        Get-CsLisConfiguration 
    
    <span data-ttu-id="1f4ea-129">その URL に ping して、サービスプロバイダが利用可能であることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="1f4ea-129">You can then ping that URL to verify that the service provider is available.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

