---
title: サイトに割り当てられた Kerberos アカウントの構成をテストする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing configuration of the Kerberos account assigned to a site
ms:assetid: a087d77e-c59e-44f5-9caa-ccfd41be7276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743837(v=OCS.15)
ms:contentKeyID: 63969637
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08477e9902a1410a98516a79fe5fdd01c5e94214
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504124"
---
# <a name="testing-configuration-of-the-kerberos-account-assigned-to-a-site-in-lync-server-2013"></a><span data-ttu-id="8fa32-102">Lync Server 2013 のサイトに割り当てられた Kerberos アカウントの構成をテストする</span><span class="sxs-lookup"><span data-stu-id="8fa32-102">Testing configuration of the Kerberos account assigned to a site in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8fa32-103">_**トピックの最終更新日:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="8fa32-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8fa32-104">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="8fa32-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="8fa32-105">毎日</span><span class="sxs-lookup"><span data-stu-id="8fa32-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8fa32-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="8fa32-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="8fa32-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8fa32-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8fa32-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="8fa32-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="8fa32-109">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fa32-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="8fa32-110">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには Test-CsKerberosAccountAssignment コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fa32-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsKerberosAccountAssignment cmdlet.</span></span> <span data-ttu-id="8fa32-111">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="8fa32-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsKerberosAccountAssignment&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="8fa32-112">説明</span><span class="sxs-lookup"><span data-stu-id="8fa32-112">Description</span></span>

<span data-ttu-id="8fa32-113">Test-CsKerberosAccountAssignment コマンドレットを使用すると、Kerberos アカウントが特定のサイトに関連付けられていること、このアカウントが正しく構成されていること、およびアカウントが期待どおりに動作していることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="8fa32-113">The Test-CsKerberosAccountAssignment cmdlet enables you to verify that a Kerberos account is associated with a given site, that this account is configured correctly, and that the account is working as expected.</span></span> <span data-ttu-id="8fa32-114">Kerberos アカウントは、インターネットインフォメーションサービス (IIS) を実行しているサイト内のすべてのコンピューターの認証プリンシパルとして機能するコンピューターアカウントです。</span><span class="sxs-lookup"><span data-stu-id="8fa32-114">Kerberos accounts are computer accounts that can serve as the authentication principal for all the computers in a site that are running Internet Information Server (IIS).</span></span> <span data-ttu-id="8fa32-115">これらのアカウントは kerberos 認証プロトコルを使用するため、アカウントは Kerberos アカウントと呼ばれ、新しい認証プロセスは Kerberos web 認証と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="8fa32-115">Because these accounts use the Kerberos authentication protocol, the accounts are known as Kerberos accounts, and the new authentication process is known as Kerberos web authentication.</span></span> <span data-ttu-id="8fa32-116">これにより、1つのアカウントを使用してすべての IIS サーバーを管理できるようになります。</span><span class="sxs-lookup"><span data-stu-id="8fa32-116">This enables you to manage all IIS servers by using a single account.</span></span>

<span data-ttu-id="8fa32-117">詳細については、 [get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) コマンドレットのヘルプドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fa32-117">For more information, see the Help documentation for the [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="8fa32-118">テストの実行</span><span class="sxs-lookup"><span data-stu-id="8fa32-118">Running the Test</span></span>

<span data-ttu-id="8fa32-119">既定では、Test-CsKerberosAccountAssignment 画面に表示される出力はほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="8fa32-119">By default, Test-CsKerberosAccountAssignment displays very little output on-screen.</span></span> <span data-ttu-id="8fa32-120">代わりに、コマンドレットによって返される情報は、HTML ファイルに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="8fa32-120">Instead, information returned by the cmdlet is written to an HTML file.</span></span> <span data-ttu-id="8fa32-121">そのため、Get-cskerberosaccountassignment を実行するたびに Verbose パラメーターと Report パラメーターを含めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8fa32-121">Because of that, we recommend that you include the Verbose parameter and the Report parameter any time that you run Test-CsKerberosAccountAssignment.</span></span> <span data-ttu-id="8fa32-122">Verbose パラメーターは、コマンドレットの実行中に画面により詳細な出力を提供します。</span><span class="sxs-lookup"><span data-stu-id="8fa32-122">The Verbose parameter will provide slightly more detailed output on-screen while the cmdlet runs.</span></span> <span data-ttu-id="8fa32-123">Report パラメーターを使用すると、Get-cskerberosaccountassignment によって生成された HTML ファイルのファイルパスとファイル名を指定できます。</span><span class="sxs-lookup"><span data-stu-id="8fa32-123">The Report parameter allows you to specify a file path and file name for the HTML file generated by Test-CsKerberosAccountAssignment.</span></span> <span data-ttu-id="8fa32-124">Report パラメーターを指定しない場合、HTML ファイルは自動的にユーザーのフォルダーに保存され、次のような名前が付けられます。 ce84964a-c4da-4622-ad34-c54ff3ed361f.html。</span><span class="sxs-lookup"><span data-stu-id="8fa32-124">If you do not include the Report parameter the HTML file will automatically be saved to your Users folder and be given a name similar to this: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span></span>

<span data-ttu-id="8fa32-125">Get-cskerberosaccountassignment を実行するときに、サイト Id も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fa32-125">You must also specify a site Identity when you run Test-CsKerberosAccountAssignment.</span></span> <span data-ttu-id="8fa32-126">Kerberos アカウントは、サイトスコープで割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="8fa32-126">Kerberos accounts are assigned at the site scope.</span></span>

<span data-ttu-id="8fa32-127">次のコマンドは Test-CsKerberosAccountAssignment を実行し、出力を C: LogsKerberosTest.html という名前のファイルに保存し \\ \\ ます。</span><span class="sxs-lookup"><span data-stu-id="8fa32-127">The following command runs Test-CsKerberosAccountAssignment and saves the output to a file that is named C:\\Logs\\KerberosTest.html:</span></span>

    Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "C:\Logs\KerberosTest.html" -Verbose

<span data-ttu-id="8fa32-128">詳細については、 [get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) コマンドレットのヘルプドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fa32-128">For more information, see the Help documentation for the [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="8fa32-129">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="8fa32-129">Determining Success or Failure</span></span>

<span data-ttu-id="8fa32-130">Test-CsKerberosAccountAssignment コマンドレットは、成功または失敗の簡単な指示を返しません。</span><span class="sxs-lookup"><span data-stu-id="8fa32-130">The Test-CsKerberosAccountAssignment cmdlet does not return a simple indication of success or failure.</span></span> <span data-ttu-id="8fa32-131">代わりに、生成された HTML ファイルを Internet Explorer を使用して表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fa32-131">Instead, you must view the generated HTML file by using Internet Explorer.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="8fa32-132">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="8fa32-132">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="8fa32-133">Test-CsKerberosAccountAssignment が失敗する可能性のある一般的な理由を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8fa32-133">Here are some common reasons why Test-CsKerberosAccountAssignment might fail:</span></span>

  - <span data-ttu-id="8fa32-134">正しくないサイト Id が指定されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8fa32-134">You might have specified an incorrect site Identity.</span></span> <span data-ttu-id="8fa32-135">有効なサイト Id の一覧を返すには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="8fa32-135">To return a list of valid site Identity, use this command:</span></span>
    
        Get-CsSite | Select-Identity Identity
    
    <span data-ttu-id="8fa32-136">サイト Id は通常、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="8fa32-136">A site Identity typically looks as follows:</span></span>
    
    <span data-ttu-id="8fa32-137">サイト: Redmond</span><span class="sxs-lookup"><span data-stu-id="8fa32-137">site:Redmond</span></span>

  - <span data-ttu-id="8fa32-138">指定したサイトに Kerberos アカウントが割り当てられていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8fa32-138">The specified site might not have a Kerberos account assigned to it.</span></span> <span data-ttu-id="8fa32-139">次のようなコマンドを実行することによって、サイトに Kerberos アカウントが割り当てられているかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="8fa32-139">You can determine whether or not a Kerberos account is assigned to a site by running a command similar to this:</span></span>
    
        Get-CsKerberosAccountAssignment -Identity "site:Redmond"

  - <span data-ttu-id="8fa32-140">Kerberos アカウントに有効ではないパスワードが設定されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8fa32-140">Your Kerberos account might have a password that isn't valid.</span></span> <span data-ttu-id="8fa32-141">次のエラーメッセージがレポートに表示された場合は、Kerberos アカウントのパスワードをリセットする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fa32-141">If you receive the following error message in report, you'll probably have to reset the Kerberos account password:</span></span>
    
    <span data-ttu-id="8fa32-142">InvalidKerberosConfiguration: Kerberos 構成が無効です。</span><span class="sxs-lookup"><span data-stu-id="8fa32-142">InvalidKerberosConfiguration: The Kerberos configuration is invalid.</span></span>
    
    <span data-ttu-id="8fa32-143">InvalidKerberosConfiguration: atl-cs001.litwareinc.com 上の Kerberos 構成が無効です。</span><span class="sxs-lookup"><span data-stu-id="8fa32-143">InvalidKerberosConfiguration: The Kerberos configuration on atl-cs001.litwareinc.com is invalid.</span></span> <span data-ttu-id="8fa32-144">必要な割り当て済みアカウントが litwareinc kerberostest である \\ 。</span><span class="sxs-lookup"><span data-stu-id="8fa32-144">The expected assigned account is litwareinc\\kerberostest.</span></span> <span data-ttu-id="8fa32-145">アカウントの有効期限が切れていないこと、およびコンピューター上の構成されたパスワードがアカウントの Active Directory パスワードと一致することを確認します。</span><span class="sxs-lookup"><span data-stu-id="8fa32-145">Ensure that the account has not expired, and the configured password on the machine matches the Active Directory password of the account.</span></span>
    
    <span data-ttu-id="8fa32-146">パスワードを設定するには、 [set-Cskerの Osaccountpassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15)) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="8fa32-146">You can set the password using the [Set-CsKerberosAccountPassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

