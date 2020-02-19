---
title: 'Lync Server 2013: Lync クライアント認証のテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Client authentication
ms:assetid: e22114cb-4456-4e5f-93ab-51592c4a8209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689120(v=OCS.15)
ms:contentKeyID: 63969659
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c1b1e1a5b13ace725d0fa38a5c2f4b5227cf0ae
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141403"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-lync-client-authentication-in-lync-server-2013"></a><span data-ttu-id="9ddd5-102">Lync Server 2013 での Lync クライアント認証のテスト</span><span class="sxs-lookup"><span data-stu-id="9ddd5-102">Testing Lync Client authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ddd5-103">_**トピックの最終更新日:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="9ddd5-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ddd5-104">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="9ddd5-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="9ddd5-105">毎日</span><span class="sxs-lookup"><span data-stu-id="9ddd5-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ddd5-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="9ddd5-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="9ddd5-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9ddd5-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ddd5-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="9ddd5-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="9ddd5-109">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ddd5-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="9ddd5-110">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、テスト用の CsClientAuth コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ddd5-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsClientAuth cmdlet.</span></span> <span data-ttu-id="9ddd5-111">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9ddd5-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsClientAuth&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="9ddd5-112">説明</span><span class="sxs-lookup"><span data-stu-id="9ddd5-112">Description</span></span>

<span data-ttu-id="9ddd5-113">Test-CsClientAuth コマンドレットを使用すると、ユーザーがクライアント証明書を使用して Lync Server にログオンできるかどうかを判断できます。また、Test-CsClientAuth コマンドレットを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="9ddd5-113">The Test-CsClientAuth cmdlet enables you to determine whether a user can log on to the Lync Server by using a client certificate, you can run the Test-CsClientAuth cmdlet.</span></span> <span data-ttu-id="9ddd5-114">Test-CsClientAuth を呼び出した後、コマンドレットは証明書プロビジョニングサービスに接続し、指定されたユーザーのクライアント証明書のコピーをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="9ddd5-114">After calling Test-CsClientAuth, the cmdlet will contact the certificate provisioning service and download a copy of any client certificates for the specified user.</span></span> <span data-ttu-id="9ddd5-115">クライアント証明書を検出してダウンロードできる場合は、その証明書を使用してログオンを試行します。</span><span class="sxs-lookup"><span data-stu-id="9ddd5-115">If a client certificate can be found and downloaded, Test-CsClientAuth will then attempt to log on by using that certificate.</span></span> <span data-ttu-id="9ddd5-116">ログオンに成功すると、テスト-CsClientAuth はログオフし、テストが成功したことを報告します。</span><span class="sxs-lookup"><span data-stu-id="9ddd5-116">If logon succeeds, Test-CsClientAuth will log off and report that the test succeeded.</span></span> <span data-ttu-id="9ddd5-117">証明書が見つからないかダウンロードできない場合、またはダウンロードした証明書を使用してログオンできない場合、Test-CsClientAuth はテストが失敗したことを報告します。</span><span class="sxs-lookup"><span data-stu-id="9ddd5-117">If a certificate cannot be found or downloaded, or if the cmdlet is unable to logon using that certificate, then Test-CsClientAuth will report that the test failed.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="9ddd5-118">テストの実行</span><span class="sxs-lookup"><span data-stu-id="9ddd5-118">Running the test</span></span>

<span data-ttu-id="9ddd5-119">Lync Server が有効になっているすべてのユーザーのアカウントを使用して、CsClientAuth コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="9ddd5-119">The Test-CsClientAuth cmdlet is run by using the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="9ddd5-120">実際のユーザーアカウントを使用してこのチェックを実行するには、まず、アカウント名とパスワードを含む Windows PowerShell credentials オブジェクトを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ddd5-120">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="9ddd5-121">次に、システムが Test-CsClientAuth を呼び出すときに、その資格情報オブジェクトと、そのアカウントに割り当てられた SIP アドレスを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ddd5-121">You must then include that credentials object and the SIP address assigned to the account when the system calls Test-CsClientAuth:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="9ddd5-122">詳細については、「 [Test-CsClientAuth](https://technet.microsoft.com/library/gg398712\(v=ocs.14\).aspx)コマンドレットのヘルプドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ddd5-122">For more information, see the Help documentation for the [Test-CsClientAuth](https://technet.microsoft.com/library/gg398712\(v=ocs.14\).aspx) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="9ddd5-123">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="9ddd5-123">Determining success or failure</span></span>

<span data-ttu-id="9ddd5-124">指定したユーザーがクライアント証明書を使用して Lync Server にログオンできる場合は、次のような出力が返されます。 Result プロパティは Success とマークされてい**ます。**</span><span class="sxs-lookup"><span data-stu-id="9ddd5-124">If the specified user can log on to Lync Server by using a client certificate, you will receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="9ddd5-125">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9ddd5-125">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="9ddd5-126">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="9ddd5-126">Result : Success</span></span>

<span data-ttu-id="9ddd5-127">待機時間:00:00: 06.8630376</span><span class="sxs-lookup"><span data-stu-id="9ddd5-127">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="9ddd5-128">エラー</span><span class="sxs-lookup"><span data-stu-id="9ddd5-128">Error :</span></span>

<span data-ttu-id="9ddd5-129">分析</span><span class="sxs-lookup"><span data-stu-id="9ddd5-129">Diagnosis :</span></span>

<span data-ttu-id="9ddd5-130">指定したユーザーがログオンできない場合、結果は失敗として表示され、追加情報が Error および診断プロパティに記録されます。</span><span class="sxs-lookup"><span data-stu-id="9ddd5-130">If the specified user can not log on, the Result will be shown as Failure and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="9ddd5-131">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9ddd5-131">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="9ddd5-132">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="9ddd5-132">Result : Failure</span></span>

<span data-ttu-id="9ddd5-133">待機時間:00:00: 03.3645259</span><span class="sxs-lookup"><span data-stu-id="9ddd5-133">Latency : 00:00:03.3645259</span></span>

<span data-ttu-id="9ddd5-134">エラー: 指定されたユーザーの CS 証明書をダウンロードできませんでした。</span><span class="sxs-lookup"><span data-stu-id="9ddd5-134">Error : Could not download a CS Certificate for the given user.</span></span> <span data-ttu-id="9ddd5-135">かどうかを確認</span><span class="sxs-lookup"><span data-stu-id="9ddd5-135">Check if</span></span>

<span data-ttu-id="9ddd5-136">指定された uri と資格情報が正しいこと。</span><span class="sxs-lookup"><span data-stu-id="9ddd5-136">provided uri and credentials are correct.</span></span>

<span data-ttu-id="9ddd5-137">分析</span><span class="sxs-lookup"><span data-stu-id="9ddd5-137">Diagnosis :</span></span>

<span data-ttu-id="9ddd5-138">たとえば、指定されたユーザーの有効なクライアント証明書が見つからないため、テストが失敗したことが上記の出力に示されます。</span><span class="sxs-lookup"><span data-stu-id="9ddd5-138">For example, the previous output states that the test failed because a valid client certificate couldn't be located for the specified user.</span></span> <span data-ttu-id="9ddd5-139">次のようにコマンドを実行することによって、ユーザーに対して発行されたクライアント証明書の一覧を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="9ddd5-139">You can return a list of the client certificates issued to a user by running a command as follows:</span></span>

    Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

<span data-ttu-id="9ddd5-140">Test-CsClientAuth に障害が発生した場合は、次のように詳細パラメーターを含めて、テストを再実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9ddd5-140">If Test-CsClientAuth fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -Verbose

<span data-ttu-id="9ddd5-141">Verbose パラメーターが指定されている場合、テスト-CsClientAuth は、指定されたユーザーが Lync Server にログオンできるかどうかを確認したときに試行された各アクションのステップバイステップのアカウントを返します。</span><span class="sxs-lookup"><span data-stu-id="9ddd5-141">When the Verbose parameter is included, Test-CsClientAuth will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="9ddd5-142">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9ddd5-142">For example:</span></span>

<span data-ttu-id="9ddd5-143">ユーザーの CS 証明書をダウンロードしようとしています: kenmyer@litwareinc.com endpoint: STEpid</span><span class="sxs-lookup"><span data-stu-id="9ddd5-143">Trying to download a CS certificate for User : kenmyer@litwareinc.com endpoint : STEpid</span></span>

<span data-ttu-id="9ddd5-144">Web サービス url:https://atl-cs-001.litwareinc.com:443/CertProv/CertprovisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="9ddd5-144">Web Service url : https://atl-cs-001.litwareinc.com:443/CertProv/CertprovisioningService.svc</span></span>

<span data-ttu-id="9ddd5-145">Web サービスから CS 証明書をダウンロードできませんでした。</span><span class="sxs-lookup"><span data-stu-id="9ddd5-145">Could not download a CS certificate from web service.</span></span>

<span data-ttu-id="9ddd5-146">確かめ</span><span class="sxs-lookup"><span data-stu-id="9ddd5-146">CHECK:</span></span>

<span data-ttu-id="9ddd5-147">\-Web サービスの url が有効で、web サービスが機能している</span><span class="sxs-lookup"><span data-stu-id="9ddd5-147">\- Web service url is valid and the web services are functional</span></span>

<span data-ttu-id="9ddd5-148">\-PhoneNo\\\\Pin を使用して認証する場合は、ユーザーの uri と一致していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9ddd5-148">\- If using PhoneNo\\\\Pin to authenticate, make sure they match the user uri</span></span>

<span data-ttu-id="9ddd5-149">\-NTLM\\Kerberos 認証を使用している場合は、有効な資格情報を入力してください。</span><span class="sxs-lookup"><span data-stu-id="9ddd5-149">\- If using NTLM\\Kerberos auth, make sure you provided valid credentials</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="9ddd5-150">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="9ddd5-150">Reasons why the test might have failed</span></span>

<span data-ttu-id="9ddd5-151">次に、Test-CsClientAuth が失敗する主な理由を示します。</span><span class="sxs-lookup"><span data-stu-id="9ddd5-151">Here are some common reasons why Test-CsClientAuth might fail:</span></span>

  - <span data-ttu-id="9ddd5-152">無効なユーザーアカウントが指定されました。</span><span class="sxs-lookup"><span data-stu-id="9ddd5-152">You specified a user account that was not valid.</span></span> <span data-ttu-id="9ddd5-153">ユーザーアカウントが存在することを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9ddd5-153">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="9ddd5-154">ユーザーアカウントは有効ですが、アカウントは現在 Lync Server に対して有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="9ddd5-154">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="9ddd5-155">ユーザーアカウントが Lync Server に対して有効になっていることを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9ddd5-155">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="9ddd5-156">Enabled プロパティが False に設定されている場合は、ユーザーが現在 Lync Server に対して有効になっていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="9ddd5-156">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="9ddd5-157">テストユーザーが有効なクライアント証明書を持っていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9ddd5-157">The test user might not have a valid client certificate.</span></span> <span data-ttu-id="9ddd5-158">次のようなコマンドを使用して、ユーザーに割り当てられているクライアント証明書に関する情報を戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="9ddd5-158">You can return information about the client certificates assigned to a user by using a command similar to this:</span></span>
    
        Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

