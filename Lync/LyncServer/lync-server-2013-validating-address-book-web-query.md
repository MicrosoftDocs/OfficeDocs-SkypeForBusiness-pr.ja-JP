---
title: 'Lync Server 2013: アドレス帳の web クエリの検証'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Validating address book web query
ms:assetid: e6ae0a5a-e131-4cfe-9a33-6e611831072d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720925(v=OCS.15)
ms:contentKeyID: 63969662
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44c43b4332be67bb164f21a2bb07459d61b23e85
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848255"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-address-book-web-query-in-lync-server-2013"></a><span data-ttu-id="a976c-102">Lync Server 2013 でのアドレス帳 web クエリの検証</span><span class="sxs-lookup"><span data-stu-id="a976c-102">Validating address book web query in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a976c-103">_**最終更新日:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="a976c-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a976c-104">確認のスケジュール</span><span class="sxs-lookup"><span data-stu-id="a976c-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="a976c-105">[毎日]</span><span class="sxs-lookup"><span data-stu-id="a976c-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a976c-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="a976c-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="a976c-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a976c-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a976c-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="a976c-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="a976c-109">Lync Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a976c-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="a976c-110">Windows PowerShell のリモートインスタンスを使って実行する場合、ユーザーには、テスト-CsAddressBookWebQuery コマンドレットを実行するアクセス許可が与えられた RBAC の役割を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a976c-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAddressBookWebQuery cmdlet.</span></span> <span data-ttu-id="a976c-111">このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a976c-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookWebQuery&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="a976c-112">説明</span><span class="sxs-lookup"><span data-stu-id="a976c-112">Description</span></span>

<span data-ttu-id="a976c-113">ユーザーがアドレス帳 Web クエリサービスを使用して特定の連絡先を検索できることを、管理者が確認できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a976c-113">The Test-CsAddressBookWebQuery cmdlet enables administrators to verify that users can use the Address Book Web Query service to search for a specific contact.</span></span> <span data-ttu-id="a976c-114">コマンドレットを実行すると、まず、テスト用の Web チケットサービスに接続して認証されます。</span><span class="sxs-lookup"><span data-stu-id="a976c-114">When you run the cmdlet, Test-CsAddressBookWebQuery will first connect to the Web Ticket service to be authenticated.</span></span> <span data-ttu-id="a976c-115">認証が成功すると、コマンドレットはアドレス帳 Web クエリサービスに接続し、指定された連絡先を検索します。</span><span class="sxs-lookup"><span data-stu-id="a976c-115">If authentication is successful, the cmdlet will then connect to the Address Book Web Query service and search for the specified contact.</span></span> <span data-ttu-id="a976c-116">その連絡先が見つかった場合、コマンドレットはローカルコンピューターにその情報を返します。</span><span class="sxs-lookup"><span data-stu-id="a976c-116">If that contact is found, the cmdlet will attempt to return that information to the local computer.</span></span> <span data-ttu-id="a976c-117">テストは、すべての手順が完了した場合にのみ成功としてマークされます。</span><span class="sxs-lookup"><span data-stu-id="a976c-117">The test will be marked a success only if all those steps can be completed.</span></span>

<span data-ttu-id="a976c-118">詳細については、「[テスト-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery)コマンドレットのヘルプドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a976c-118">For more information, see the Help documentation for the [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="a976c-119">テストの実行</span><span class="sxs-lookup"><span data-stu-id="a976c-119">Running the test</span></span>

<span data-ttu-id="a976c-120">テスト-CsAddressBookWebQuery コマンドレットは、事前に定義されたテストアカウント (「Lync Server テストを実行するためにテストアカウントをセットアップする」を参照)、または Lync Server を有効にしているユーザーのアカウントを使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="a976c-120">The Test-CsAddressBookWebQuery cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="a976c-121">テストアカウントを使用してこのチェックを実行するには、Lync Server プールの FQDN と、検索のターゲットとして機能しているユーザーの SIP アドレスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a976c-121">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool and the SIP address of the user acting as the target of the search.</span></span> <span data-ttu-id="a976c-122">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a976c-122">For example:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com"

<span data-ttu-id="a976c-123">実際のユーザーアカウントを使用してこのチェックを実行するには、有効なユーザー名とパスワードを含む Windows PowerShell 資格情報オブジェクトを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a976c-123">To run this check using an actual user account, you must create a Windows PowerShell credentials object that contains a valid user name and password.</span></span> <span data-ttu-id="a976c-124">次に、コードが Test-CsAddressBookWebQuery を呼び出したときに、アカウントに割り当てられている資格情報オブジェクトと SIP アドレスを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="a976c-124">You must then include that credentials object and the SIP address assigned to the account when the code calls Test-CsAddressBookWebQuery:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="a976c-125">詳細については、「[テスト-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery)コマンドレットのヘルプドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a976c-125">For more information, see the Help documentation for the [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="a976c-126">成功または失敗を確認する</span><span class="sxs-lookup"><span data-stu-id="a976c-126">Determining success or failure</span></span>

<span data-ttu-id="a976c-127">指定したユーザーがアドレス帳サービスに接続し、ターゲットユーザーアドレスを取得できる場合は、次のような出力が返されます。これは、Success とマークされた Result プロパティによって返されます。</span><span class="sxs-lookup"><span data-stu-id="a976c-127">If the specified user can connect to the Address Book Service and retrieve the targeted user address, you'll return output similar to this with the Result property marked as Success:</span></span>

<span data-ttu-id="a976c-128">TargetUri :https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="a976c-128">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="a976c-129">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a976c-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="a976c-130">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="a976c-130">Result : Success</span></span>

<span data-ttu-id="a976c-131">待ち時間:00:00: 06.2611356</span><span class="sxs-lookup"><span data-stu-id="a976c-131">Latency : 00:00:06.2611356</span></span>

<span data-ttu-id="a976c-132">誤差</span><span class="sxs-lookup"><span data-stu-id="a976c-132">Error :</span></span>

<span data-ttu-id="a976c-133">診断</span><span class="sxs-lookup"><span data-stu-id="a976c-133">Diagnosis :</span></span>

<span data-ttu-id="a976c-134">指定したユーザーが接続できない場合、またはターゲットのユーザーアドレスを取得できない場合は、結果がエラーとして表示され、エラーと診断のプロパティに追加情報が記録されます。</span><span class="sxs-lookup"><span data-stu-id="a976c-134">If the specified user can't connect or if the target user address cannot be retrieved, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="a976c-135">TargetUri :https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="a976c-135">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="a976c-136">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a976c-136">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="a976c-137">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="a976c-137">Result : Failure</span></span>

<span data-ttu-id="a976c-138">待ち時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="a976c-138">Latency : 00:00:00</span></span>

<span data-ttu-id="a976c-139">エラー: アドレス帳 Web サービスの要求は応答コードで失敗しました</span><span class="sxs-lookup"><span data-stu-id="a976c-139">Error : Address Book Web service request has failed with response code</span></span>

<span data-ttu-id="a976c-140">NoEntryFound。</span><span class="sxs-lookup"><span data-stu-id="a976c-140">NoEntryFound.</span></span>

<span data-ttu-id="a976c-141">診断</span><span class="sxs-lookup"><span data-stu-id="a976c-141">Diagnosis :</span></span>

<span data-ttu-id="a976c-142">前の出力では、ターゲットユーザーが見つからなかったため、テストが失敗したことが示されます。</span><span class="sxs-lookup"><span data-stu-id="a976c-142">The previous output states that the test failed because the target user couldn't be found.</span></span> <span data-ttu-id="a976c-143">次のようなコマンドを実行することで、有効な SIP アドレスが CsAddressBookWebQuery に渡されたかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="a976c-143">You can determine whether or not a valid SIP address was passed to Test-CsAddressBookWebQuery by running a command similar to the following:</span></span>

    Get-CsUser | Where-Object {$_.SipAddress -eq "sip:davidlongmire@litwareinc.com"

<span data-ttu-id="a976c-144">テスト-CsAddressBookWebQuery が失敗した場合は、Verbose パラメーターも含めて、テストを再実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a976c-144">If Test-CsAddressBookWebQuery fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -Verbose

<span data-ttu-id="a976c-145">Verbose パラメーターが含まれている場合は、指定したユーザーが Lync Server にログオンする機能を確認している間に、テスト-CsAddressBookWebQuery によって実行された各操作のステップバイステップのアカウントが返されます。</span><span class="sxs-lookup"><span data-stu-id="a976c-145">When the Verbose parameter is included, Test-CsAddressBookWebQuery will return a step-by-step account of each action it tried while checking the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="a976c-146">たとえば、次の出力は、テスト-CsAddressBookWebQuery がアドレス帳サービスに接続できましたが、ターゲット SIP アドレスが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="a976c-146">For example, this output indicates that Test-CsAddressBookWebQuery was able to connect to the Address Book Service, but was not able to locate the target SIP address:</span></span>

<span data-ttu-id="a976c-147">' QueryAddressBookWebService ' アクティビティが開始されました。</span><span class="sxs-lookup"><span data-stu-id="a976c-147">'QueryAddressBookWebService' activity started.</span></span>

<span data-ttu-id="a976c-148">アドレス帳 Web クエリサービスを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a976c-148">Calling Address Book Web Query Service.</span></span> <span data-ttu-id="a976c-149">ABWS URL =</span><span class="sxs-lookup"><span data-stu-id="a976c-149">ABWS URL =</span></span>

https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

<span data-ttu-id="a976c-150">アドレス帳のクエリ例外: アドレス帳 Web サービスの要求は、応答コード NoEntryFound で失敗しました。</span><span class="sxs-lookup"><span data-stu-id="a976c-150">Address book query exception : Address Book Web service request has failed with response code NoEntryFound.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="a976c-151">テストに失敗した可能性がある理由</span><span class="sxs-lookup"><span data-stu-id="a976c-151">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="a976c-152">次に、テストまたは CsAddressBookWebQuery が失敗する可能性がある一般的な理由を示します。</span><span class="sxs-lookup"><span data-stu-id="a976c-152">Here are some common reasons why Test-CsAddressBookWebQuery might fail:</span></span>

  - <span data-ttu-id="a976c-153">無効なユーザアカウントを指定しました。</span><span class="sxs-lookup"><span data-stu-id="a976c-153">You specified an invalid user account.</span></span> <span data-ttu-id="a976c-154">次のようなコマンドを実行すると、ユーザーアカウントが存在するかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="a976c-154">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="a976c-155">ユーザーアカウントは有効ですが、アカウントは現在 Lync Server では有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="a976c-155">The user account is valid, but the account is not currently enabled for Lync Server.</span></span> <span data-ttu-id="a976c-156">Lync Server のユーザーアカウントが有効になっていることを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a976c-156">To verify that a user account has been enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="a976c-157">Enabled プロパティが False に設定されている場合は、ユーザーが現在 Lync Server に対して有効になっていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="a976c-157">If the Enabled property is set to False that means that the user is not currently enabled for Lync Server.</span></span>

  - <span data-ttu-id="a976c-158">ターゲットユーザーがアドレス帳に登録されていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a976c-158">The target user might not be in the Address Book.</span></span>

  - <span data-ttu-id="a976c-159">アドレス帳が完全に更新されて複製されていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a976c-159">The Address Book might not have fully updated and replicated.</span></span> <span data-ttu-id="a976c-160">次のコマンドを実行して、組織内のすべてのアドレス帳サーバーを強制的に更新することができます。</span><span class="sxs-lookup"><span data-stu-id="a976c-160">You can force an update of all the Address Book Servers in your organization by running the following command:</span></span>
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

