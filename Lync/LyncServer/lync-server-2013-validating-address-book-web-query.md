---
title: 'Lync Server 2013: アドレス帳 web クエリの検証'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating address book web query
ms:assetid: e6ae0a5a-e131-4cfe-9a33-6e611831072d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720925(v=OCS.15)
ms:contentKeyID: 63969662
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 548ec62a56de829955647a696e33578b9ab3dfd8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212590"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validating-address-book-web-query-in-lync-server-2013"></a><span data-ttu-id="69c4f-102">Lync Server 2013 でのアドレス帳 web クエリの検証</span><span class="sxs-lookup"><span data-stu-id="69c4f-102">Validating address book web query in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69c4f-103">_**トピックの最終更新日:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="69c4f-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69c4f-104">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="69c4f-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="69c4f-105">毎日</span><span class="sxs-lookup"><span data-stu-id="69c4f-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69c4f-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="69c4f-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="69c4f-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="69c4f-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69c4f-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="69c4f-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="69c4f-109">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="69c4f-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="69c4f-110">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、テスト-CsAddressBookWebQuery コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="69c4f-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAddressBookWebQuery cmdlet.</span></span> <span data-ttu-id="69c4f-111">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="69c4f-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookWebQuery&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="69c4f-112">説明</span><span class="sxs-lookup"><span data-stu-id="69c4f-112">Description</span></span>

<span data-ttu-id="69c4f-113">Test-CsAddressBookWebQuery コマンドレットを使用すると、管理者は、ユーザーがアドレス帳 Web クエリサービスを使用して特定の連絡先を検索できることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="69c4f-113">The Test-CsAddressBookWebQuery cmdlet enables administrators to verify that users can use the Address Book Web Query service to search for a specific contact.</span></span> <span data-ttu-id="69c4f-114">コマンドレットを実行すると、最初に認証を行うために Web チケットサービスに接続されます。</span><span class="sxs-lookup"><span data-stu-id="69c4f-114">When you run the cmdlet, Test-CsAddressBookWebQuery will first connect to the Web Ticket service to be authenticated.</span></span> <span data-ttu-id="69c4f-115">認証が成功した場合、コマンドレットはアドレス帳 Web クエリサービスに接続し、指定された連絡先を検索します。</span><span class="sxs-lookup"><span data-stu-id="69c4f-115">If authentication is successful, the cmdlet will then connect to the Address Book Web Query service and search for the specified contact.</span></span> <span data-ttu-id="69c4f-116">その連絡先が見つかった場合、コマンドレットはその情報をローカルコンピューターに返します。</span><span class="sxs-lookup"><span data-stu-id="69c4f-116">If that contact is found, the cmdlet will attempt to return that information to the local computer.</span></span> <span data-ttu-id="69c4f-117">このテストは、これらの手順をすべて完了できる場合にのみ、成功としてマークされます。</span><span class="sxs-lookup"><span data-stu-id="69c4f-117">The test will be marked a success only if all those steps can be completed.</span></span>

<span data-ttu-id="69c4f-118">詳細については、「 [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery)コマンドレットのヘルプドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69c4f-118">For more information, see the Help documentation for the [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="69c4f-119">テストの実行</span><span class="sxs-lookup"><span data-stu-id="69c4f-119">Running the test</span></span>

<span data-ttu-id="69c4f-120">Test-CsAddressBookWebQuery コマンドレットは、事前に構成されたテストアカウント (「Lync Server テストを実行するためのテストアカウントの設定」を参照)、または Lync Server が有効になっているユーザーのアカウントのいずれかを使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="69c4f-120">The Test-CsAddressBookWebQuery cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="69c4f-121">このチェックをテストアカウントを使用して実行するには、Lync Server プールの FQDN と、検索の対象として機能するユーザーの SIP アドレスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69c4f-121">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool and the SIP address of the user acting as the target of the search.</span></span> <span data-ttu-id="69c4f-122">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="69c4f-122">For example:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com"

<span data-ttu-id="69c4f-123">実際のユーザーアカウントを使用してこのチェックを実行するには、有効なユーザー名とパスワードを含む Windows PowerShell 資格情報オブジェクトを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69c4f-123">To run this check using an actual user account, you must create a Windows PowerShell credentials object that contains a valid user name and password.</span></span> <span data-ttu-id="69c4f-124">次に、この資格情報オブジェクトと、コードで Test-CsAddressBookWebQuery を呼び出したときにアカウントに割り当てられた SIP アドレスを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="69c4f-124">You must then include that credentials object and the SIP address assigned to the account when the code calls Test-CsAddressBookWebQuery:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="69c4f-125">詳細については、「 [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery)コマンドレットのヘルプドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69c4f-125">For more information, see the Help documentation for the [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="69c4f-126">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="69c4f-126">Determining success or failure</span></span>

<span data-ttu-id="69c4f-127">指定したユーザーがアドレス帳サービスに接続して、対象のユーザーアドレスを取得できる場合は、次のような出力が返されます。 Result プロパティには、Success というマークが付けられています。</span><span class="sxs-lookup"><span data-stu-id="69c4f-127">If the specified user can connect to the Address Book Service and retrieve the targeted user address, you'll return output similar to this with the Result property marked as Success:</span></span>

<span data-ttu-id="69c4f-128">TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="69c4f-128">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="69c4f-129">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="69c4f-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="69c4f-130">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="69c4f-130">Result : Success</span></span>

<span data-ttu-id="69c4f-131">待機時間:00:00: 06.2611356</span><span class="sxs-lookup"><span data-stu-id="69c4f-131">Latency : 00:00:06.2611356</span></span>

<span data-ttu-id="69c4f-132">エラー</span><span class="sxs-lookup"><span data-stu-id="69c4f-132">Error :</span></span>

<span data-ttu-id="69c4f-133">分析</span><span class="sxs-lookup"><span data-stu-id="69c4f-133">Diagnosis :</span></span>

<span data-ttu-id="69c4f-134">指定したユーザーが接続できない場合、またはターゲットユーザーのアドレスを取得できない場合、結果は失敗として表示され、追加情報が Error および診断プロパティに記録されます。</span><span class="sxs-lookup"><span data-stu-id="69c4f-134">If the specified user can't connect or if the target user address cannot be retrieved, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="69c4f-135">TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="69c4f-135">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="69c4f-136">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="69c4f-136">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="69c4f-137">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="69c4f-137">Result : Failure</span></span>

<span data-ttu-id="69c4f-138">待機時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="69c4f-138">Latency : 00:00:00</span></span>

<span data-ttu-id="69c4f-139">エラー: アドレス帳 Web サービスの要求が応答コードを使用して失敗しました</span><span class="sxs-lookup"><span data-stu-id="69c4f-139">Error : Address Book Web service request has failed with response code</span></span>

<span data-ttu-id="69c4f-140">NoEntryFound。</span><span class="sxs-lookup"><span data-stu-id="69c4f-140">NoEntryFound.</span></span>

<span data-ttu-id="69c4f-141">分析</span><span class="sxs-lookup"><span data-stu-id="69c4f-141">Diagnosis :</span></span>

<span data-ttu-id="69c4f-142">前の出力には、ターゲットユーザーが見つからないためにテストが失敗したことが示されます。</span><span class="sxs-lookup"><span data-stu-id="69c4f-142">The previous output states that the test failed because the target user couldn't be found.</span></span> <span data-ttu-id="69c4f-143">次のようなコマンドを実行することにより、有効な SIP アドレスが Test-CsAddressBookWebQuery に渡されたかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="69c4f-143">You can determine whether or not a valid SIP address was passed to Test-CsAddressBookWebQuery by running a command similar to the following:</span></span>

    Get-CsUser | Where-Object {$_.SipAddress -eq "sip:davidlongmire@litwareinc.com"

<span data-ttu-id="69c4f-144">Test-CsAddressBookWebQuery が失敗した場合は、次のように詳細なパラメーターを含めて、テストを再実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="69c4f-144">If Test-CsAddressBookWebQuery fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -Verbose

<span data-ttu-id="69c4f-145">Verbose パラメーターを指定すると、指定されたユーザーが Lync Server にログオンできるかどうかを確認している間に実行しようとした各操作のステップごとのアカウントが返されます。</span><span class="sxs-lookup"><span data-stu-id="69c4f-145">When the Verbose parameter is included, Test-CsAddressBookWebQuery will return a step-by-step account of each action it tried while checking the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="69c4f-146">たとえば、次の出力は、Test-CsAddressBookWebQuery がアドレス帳サービスに接続できたが、対象の SIP アドレスを見つけられなかったことを示しています。</span><span class="sxs-lookup"><span data-stu-id="69c4f-146">For example, this output indicates that Test-CsAddressBookWebQuery was able to connect to the Address Book Service, but was not able to locate the target SIP address:</span></span>

<span data-ttu-id="69c4f-147">' QueryAddressBookWebService ' アクティビティを開始しました。</span><span class="sxs-lookup"><span data-stu-id="69c4f-147">'QueryAddressBookWebService' activity started.</span></span>

<span data-ttu-id="69c4f-148">アドレス帳 Web クエリサービスを呼び出す。</span><span class="sxs-lookup"><span data-stu-id="69c4f-148">Calling Address Book Web Query Service.</span></span> <span data-ttu-id="69c4f-149">ABWS URL =</span><span class="sxs-lookup"><span data-stu-id="69c4f-149">ABWS URL =</span></span>

https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

<span data-ttu-id="69c4f-150">アドレス帳のクエリ例外: アドレス帳 Web サービスの要求が失敗しました。応答コードの NoEntryFound が見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="69c4f-150">Address book query exception : Address Book Web service request has failed with response code NoEntryFound.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="69c4f-151">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="69c4f-151">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="69c4f-152">次に、Test-CsAddressBookWebQuery が失敗する主な理由を示します。</span><span class="sxs-lookup"><span data-stu-id="69c4f-152">Here are some common reasons why Test-CsAddressBookWebQuery might fail:</span></span>

  - <span data-ttu-id="69c4f-153">無効なユーザーアカウントが指定されています。</span><span class="sxs-lookup"><span data-stu-id="69c4f-153">You specified an invalid user account.</span></span> <span data-ttu-id="69c4f-154">ユーザーアカウントが存在することを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="69c4f-154">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="69c4f-155">ユーザーアカウントは有効ですが、アカウントは現在 Lync Server で有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="69c4f-155">The user account is valid, but the account is not currently enabled for Lync Server.</span></span> <span data-ttu-id="69c4f-156">ユーザーアカウントが Lync Server に対して有効になっていることを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="69c4f-156">To verify that a user account has been enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="69c4f-157">Enabled プロパティが False に設定されている場合は、ユーザーが Lync Server で現在有効になっていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="69c4f-157">If the Enabled property is set to False that means that the user is not currently enabled for Lync Server.</span></span>

  - <span data-ttu-id="69c4f-158">ターゲットユーザーがアドレス帳に登録されていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="69c4f-158">The target user might not be in the Address Book.</span></span>

  - <span data-ttu-id="69c4f-159">アドレス帳が完全に更新され、レプリケートされていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="69c4f-159">The Address Book might not have fully updated and replicated.</span></span> <span data-ttu-id="69c4f-160">次のコマンドを実行して、組織内のすべてのアドレス帳サーバーを強制的に更新することができます。</span><span class="sxs-lookup"><span data-stu-id="69c4f-160">You can force an update of all the Address Book Servers in your organization by running the following command:</span></span>
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

