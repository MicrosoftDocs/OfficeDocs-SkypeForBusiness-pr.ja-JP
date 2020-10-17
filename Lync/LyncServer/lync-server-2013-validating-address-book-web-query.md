---
title: 'Lync Server 2013: アドレス帳 web クエリの検証'
description: 'Lync Server 2013: アドレス帳 web クエリの検証。'
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
ms.openlocfilehash: e73c39fc33f8d1851fc89d277333a94aaa137790
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547253"
---
# <a name="validating-address-book-web-query-in-lync-server-2013"></a><span data-ttu-id="97896-103">Lync Server 2013 でのアドレス帳 web クエリの検証</span><span class="sxs-lookup"><span data-stu-id="97896-103">Validating address book web query in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97896-104">_**トピックの最終更新日:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="97896-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="97896-105">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="97896-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="97896-106">毎日</span><span class="sxs-lookup"><span data-stu-id="97896-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97896-107">テストツール</span><span class="sxs-lookup"><span data-stu-id="97896-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="97896-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="97896-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97896-109">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="97896-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="97896-110">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="97896-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="97896-111">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには Test-CsAddressBookWebQuery コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="97896-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAddressBookWebQuery cmdlet.</span></span> <span data-ttu-id="97896-112">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="97896-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookWebQuery&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="97896-113">説明</span><span class="sxs-lookup"><span data-stu-id="97896-113">Description</span></span>

<span data-ttu-id="97896-114">Test-CsAddressBookWebQuery コマンドレットを使用すると、管理者は、ユーザーがアドレス帳 Web クエリサービスを使用して特定の連絡先を検索できることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="97896-114">The Test-CsAddressBookWebQuery cmdlet enables administrators to verify that users can use the Address Book Web Query service to search for a specific contact.</span></span> <span data-ttu-id="97896-115">コマンドレットを実行すると、Test-CsAddressBookWebQuery によって最初に認証される Web チケットサービスに接続されます。</span><span class="sxs-lookup"><span data-stu-id="97896-115">When you run the cmdlet, Test-CsAddressBookWebQuery will first connect to the Web Ticket service to be authenticated.</span></span> <span data-ttu-id="97896-116">認証が成功した場合、コマンドレットはアドレス帳 Web クエリサービスに接続し、指定された連絡先を検索します。</span><span class="sxs-lookup"><span data-stu-id="97896-116">If authentication is successful, the cmdlet will then connect to the Address Book Web Query service and search for the specified contact.</span></span> <span data-ttu-id="97896-117">その連絡先が見つかった場合、コマンドレットはその情報をローカルコンピューターに返します。</span><span class="sxs-lookup"><span data-stu-id="97896-117">If that contact is found, the cmdlet will attempt to return that information to the local computer.</span></span> <span data-ttu-id="97896-118">このテストは、これらの手順をすべて完了できる場合にのみ、成功としてマークされます。</span><span class="sxs-lookup"><span data-stu-id="97896-118">The test will be marked a success only if all those steps can be completed.</span></span>

<span data-ttu-id="97896-119">詳細については、「 [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) コマンドレットのヘルプドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97896-119">For more information, see the Help documentation for the [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="97896-120">テストの実行</span><span class="sxs-lookup"><span data-stu-id="97896-120">Running the test</span></span>

<span data-ttu-id="97896-121">Test-CsAddressBookWebQuery コマンドレットを実行するには、事前に構成されたテストアカウントを使用するか (「Lync Server テストを実行するためのテストアカウントをセットアップする」を参照)、Lync Server が有効になっているすべてのユーザーのアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="97896-121">The Test-CsAddressBookWebQuery cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="97896-122">このチェックをテストアカウントを使用して実行するには、Lync Server プールの FQDN と、検索の対象として機能するユーザーの SIP アドレスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97896-122">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool and the SIP address of the user acting as the target of the search.</span></span> <span data-ttu-id="97896-123">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="97896-123">For example:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com"

<span data-ttu-id="97896-124">実際のユーザーアカウントを使用してこのチェックを実行するには、有効なユーザー名とパスワードを含む Windows PowerShell 資格情報オブジェクトを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97896-124">To run this check using an actual user account, you must create a Windows PowerShell credentials object that contains a valid user name and password.</span></span> <span data-ttu-id="97896-125">次に、この資格情報オブジェクトと、コードで Test-CsAddressBookWebQuery を呼び出したときにアカウントに割り当てられた SIP アドレスを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="97896-125">You must then include that credentials object and the SIP address assigned to the account when the code calls Test-CsAddressBookWebQuery:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="97896-126">詳細については、「 [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) コマンドレットのヘルプドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97896-126">For more information, see the Help documentation for the [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="97896-127">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="97896-127">Determining success or failure</span></span>

<span data-ttu-id="97896-128">指定したユーザーがアドレス帳サービスに接続して、対象のユーザーアドレスを取得できる場合は、次のような出力が返されます。 Result プロパティには、Success というマークが付けられています。</span><span class="sxs-lookup"><span data-stu-id="97896-128">If the specified user can connect to the Address Book Service and retrieve the targeted user address, you'll return output similar to this with the Result property marked as Success:</span></span>

<span data-ttu-id="97896-129">TargetUri https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="97896-129">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="97896-130">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="97896-130">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="97896-131">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="97896-131">Result : Success</span></span>

<span data-ttu-id="97896-132">待機時間:00:00: 06.2611356</span><span class="sxs-lookup"><span data-stu-id="97896-132">Latency : 00:00:06.2611356</span></span>

<span data-ttu-id="97896-133">エラー</span><span class="sxs-lookup"><span data-stu-id="97896-133">Error :</span></span>

<span data-ttu-id="97896-134">分析</span><span class="sxs-lookup"><span data-stu-id="97896-134">Diagnosis :</span></span>

<span data-ttu-id="97896-135">指定したユーザーが接続できない場合、またはターゲットユーザーのアドレスを取得できない場合、結果は失敗として表示され、追加情報が Error および診断プロパティに記録されます。</span><span class="sxs-lookup"><span data-stu-id="97896-135">If the specified user can't connect or if the target user address cannot be retrieved, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="97896-136">TargetUri https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="97896-136">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="97896-137">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="97896-137">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="97896-138">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="97896-138">Result : Failure</span></span>

<span data-ttu-id="97896-139">待機時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="97896-139">Latency : 00:00:00</span></span>

<span data-ttu-id="97896-140">エラー: アドレス帳 Web サービスの要求が応答コードを使用して失敗しました</span><span class="sxs-lookup"><span data-stu-id="97896-140">Error : Address Book Web service request has failed with response code</span></span>

<span data-ttu-id="97896-141">NoEntryFound。</span><span class="sxs-lookup"><span data-stu-id="97896-141">NoEntryFound.</span></span>

<span data-ttu-id="97896-142">分析</span><span class="sxs-lookup"><span data-stu-id="97896-142">Diagnosis :</span></span>

<span data-ttu-id="97896-143">前の出力には、ターゲットユーザーが見つからないためにテストが失敗したことが示されます。</span><span class="sxs-lookup"><span data-stu-id="97896-143">The previous output states that the test failed because the target user couldn't be found.</span></span> <span data-ttu-id="97896-144">有効な SIP アドレスが Test-CsAddressBookWebQuery に渡されたかどうかを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="97896-144">You can determine whether or not a valid SIP address was passed to Test-CsAddressBookWebQuery by running a command similar to the following:</span></span>

    Get-CsUser | Where-Object {$_.SipAddress -eq "sip:davidlongmire@litwareinc.com"

<span data-ttu-id="97896-145">Test-CsAddressBookWebQuery が失敗した場合は、次のようにして、Verbose パラメーターを含むテストを再実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="97896-145">If Test-CsAddressBookWebQuery fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -Verbose

<span data-ttu-id="97896-146">Verbose パラメーターが含まれている場合、Test-CsAddressBookWebQuery は、指定されたユーザーが Lync Server にログオンできるかどうかを確認している間に試行された各アクションのステップごとの手順を返します。</span><span class="sxs-lookup"><span data-stu-id="97896-146">When the Verbose parameter is included, Test-CsAddressBookWebQuery will return a step-by-step account of each action it tried while checking the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="97896-147">たとえば、次の出力は、Test-CsAddressBookWebQuery がアドレス帳サービスに接続できたが、対象の SIP アドレスを特定できなかったことを示しています。</span><span class="sxs-lookup"><span data-stu-id="97896-147">For example, this output indicates that Test-CsAddressBookWebQuery was able to connect to the Address Book Service, but was not able to locate the target SIP address:</span></span>

<span data-ttu-id="97896-148">' QueryAddressBookWebService ' アクティビティを開始しました。</span><span class="sxs-lookup"><span data-stu-id="97896-148">'QueryAddressBookWebService' activity started.</span></span>

<span data-ttu-id="97896-149">アドレス帳 Web クエリサービスを呼び出す。</span><span class="sxs-lookup"><span data-stu-id="97896-149">Calling Address Book Web Query Service.</span></span> <span data-ttu-id="97896-150">ABWS URL =</span><span class="sxs-lookup"><span data-stu-id="97896-150">ABWS URL =</span></span>

https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

<span data-ttu-id="97896-151">アドレス帳のクエリ例外: アドレス帳 Web サービスの要求が失敗しました。応答コードの NoEntryFound が見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="97896-151">Address book query exception : Address Book Web service request has failed with response code NoEntryFound.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="97896-152">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="97896-152">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="97896-153">Test-CsAddressBookWebQuery が失敗する可能性のある一般的な理由を次に示します。</span><span class="sxs-lookup"><span data-stu-id="97896-153">Here are some common reasons why Test-CsAddressBookWebQuery might fail:</span></span>

  - <span data-ttu-id="97896-154">無効なユーザーアカウントが指定されています。</span><span class="sxs-lookup"><span data-stu-id="97896-154">You specified an invalid user account.</span></span> <span data-ttu-id="97896-155">ユーザーアカウントが存在することを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="97896-155">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="97896-156">ユーザーアカウントは有効ですが、アカウントは現在 Lync Server で有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="97896-156">The user account is valid, but the account is not currently enabled for Lync Server.</span></span> <span data-ttu-id="97896-157">ユーザーアカウントが Lync Server に対して有効になっていることを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="97896-157">To verify that a user account has been enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="97896-158">Enabled プロパティが False に設定されている場合は、ユーザーが Lync Server で現在有効になっていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="97896-158">If the Enabled property is set to False that means that the user is not currently enabled for Lync Server.</span></span>

  - <span data-ttu-id="97896-159">ターゲットユーザーがアドレス帳に登録されていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="97896-159">The target user might not be in the Address Book.</span></span>

  - <span data-ttu-id="97896-160">アドレス帳が完全に更新され、レプリケートされていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="97896-160">The Address Book might not have fully updated and replicated.</span></span> <span data-ttu-id="97896-161">次のコマンドを実行して、組織内のすべてのアドレス帳サーバーを強制的に更新することができます。</span><span class="sxs-lookup"><span data-stu-id="97896-161">You can force an update of all the Address Book Servers in your organization by running the following command:</span></span>
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

