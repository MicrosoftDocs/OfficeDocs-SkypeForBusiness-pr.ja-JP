---
title: サイトに割り当てられている Kerberos アカウントの構成をテストする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing configuration of the Kerberos account assigned to a site
ms:assetid: a087d77e-c59e-44f5-9caa-ccfd41be7276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743837(v=OCS.15)
ms:contentKeyID: 63969637
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e12a780c4c900423b23eff6cdaae15ba15786b6c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848451"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-configuration-of-the-kerberos-account-assigned-to-a-site-in-lync-server-2013"></a><span data-ttu-id="5c8ff-102">Lync Server 2013 でサイトに割り当てられている Kerberos アカウントの構成をテストする</span><span class="sxs-lookup"><span data-stu-id="5c8ff-102">Testing configuration of the Kerberos account assigned to a site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5c8ff-103">_**最終更新日:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="5c8ff-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5c8ff-104">確認のスケジュール</span><span class="sxs-lookup"><span data-stu-id="5c8ff-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="5c8ff-105">[毎日]</span><span class="sxs-lookup"><span data-stu-id="5c8ff-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c8ff-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="5c8ff-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="5c8ff-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5c8ff-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c8ff-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="5c8ff-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="5c8ff-109">Lync Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c8ff-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="5c8ff-110">Windows PowerShell のリモートインスタンスを使って実行する場合は、CsKerberosAccountAssignment コマンドレットを実行するためのアクセス許可が与えられている RBAC の役割をユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c8ff-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsKerberosAccountAssignment cmdlet.</span></span> <span data-ttu-id="5c8ff-111">このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5c8ff-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsKerberosAccountAssignment&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="5c8ff-112">説明</span><span class="sxs-lookup"><span data-stu-id="5c8ff-112">Description</span></span>

<span data-ttu-id="5c8ff-113">CsKerberosAccountAssignment コマンドレットを使用すると、指定したサイトに Kerberos アカウントが関連付けられていること、アカウントが正しく構成されていること、アカウントが予期したとおりに動作していることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="5c8ff-113">The Test-CsKerberosAccountAssignment cmdlet enables you to verify that a Kerberos account is associated with a given site, that this account is configured correctly, and that the account is working as expected.</span></span> <span data-ttu-id="5c8ff-114">Kerberos アカウントは、インターネットインフォメーションサーバー (IIS) を実行しているサイト内のすべてのコンピューターの認証プリンシパルとして機能するコンピューターアカウントです。</span><span class="sxs-lookup"><span data-stu-id="5c8ff-114">Kerberos accounts are computer accounts that can serve as the authentication principal for all the computers in a site that are running Internet Information Server (IIS).</span></span> <span data-ttu-id="5c8ff-115">これらのアカウントは Kerberos 認証プロトコルを使用しているため、アカウントは Kerberos アカウントと呼ばれ、新しい認証プロセスは Kerberos web 認証と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="5c8ff-115">Because these accounts use the Kerberos authentication protocol, the accounts are known as Kerberos accounts, and the new authentication process is known as Kerberos web authentication.</span></span> <span data-ttu-id="5c8ff-116">これにより、1つのアカウントを使用してすべての IIS サーバーを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="5c8ff-116">This enables you to manage all IIS servers by using a single account.</span></span>

<span data-ttu-id="5c8ff-117">詳細については、「 [CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15))コマンドレットのヘルプドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c8ff-117">For more information, see the Help documentation for the [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="5c8ff-118">テストの実行</span><span class="sxs-lookup"><span data-stu-id="5c8ff-118">Running the Test</span></span>

<span data-ttu-id="5c8ff-119">既定では、CsKerberosAccountAssignment には、画面上に非常に小さな出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5c8ff-119">By default, Test-CsKerberosAccountAssignment displays very little output on-screen.</span></span> <span data-ttu-id="5c8ff-120">代わりに、コマンドレットによって返される情報は、HTML ファイルに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="5c8ff-120">Instead, information returned by the cmdlet is written to an HTML file.</span></span> <span data-ttu-id="5c8ff-121">このため、CsKerberosAccountAssignment を実行するたびに Verbose パラメーターと Report パラメーターを含めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5c8ff-121">Because of that, we recommend that you include the Verbose parameter and the Report parameter any time that you run Test-CsKerberosAccountAssignment.</span></span> <span data-ttu-id="5c8ff-122">Verbose パラメーターは、コマンドレットが実行されている間、画面上により詳細な出力を提供します。</span><span class="sxs-lookup"><span data-stu-id="5c8ff-122">The Verbose parameter will provide slightly more detailed output on-screen while the cmdlet runs.</span></span> <span data-ttu-id="5c8ff-123">レポートパラメーターを使用すると、CsKerberosAccountAssignment によって生成された HTML ファイルのファイルパスとファイル名を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5c8ff-123">The Report parameter allows you to specify a file path and file name for the HTML file generated by Test-CsKerberosAccountAssignment.</span></span> <span data-ttu-id="5c8ff-124">レポートパラメーターが含まれていない場合、HTML ファイルは [ユーザー] フォルダーに自動的に保存され、次のような名前が付けられます。 ce84964a-c4da-4622 2-ad34-361f、.html</span><span class="sxs-lookup"><span data-stu-id="5c8ff-124">If you do not include the Report parameter the HTML file will automatically be saved to your Users folder and be given a name similar to this: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span></span>

<span data-ttu-id="5c8ff-125">また、CsKerberosAccountAssignment を実行するときに、サイト Id を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c8ff-125">You must also specify a site Identity when you run Test-CsKerberosAccountAssignment.</span></span> <span data-ttu-id="5c8ff-126">Kerberos アカウントは、サイトの範囲で割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="5c8ff-126">Kerberos accounts are assigned at the site scope.</span></span>

<span data-ttu-id="5c8ff-127">次のコマンドは、CsKerberosAccountAssignment を実行し、出力を C:\\Logs\\KerberosTest という名前のファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="5c8ff-127">The following command runs Test-CsKerberosAccountAssignment and saves the output to a file that is named C:\\Logs\\KerberosTest.html:</span></span>

    Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "C:\Logs\KerberosTest.html" -Verbose

<span data-ttu-id="5c8ff-128">詳細については、「 [CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15))コマンドレットのヘルプドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c8ff-128">For more information, see the Help documentation for the [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="5c8ff-129">成功または失敗を確認する</span><span class="sxs-lookup"><span data-stu-id="5c8ff-129">Determining Success or Failure</span></span>

<span data-ttu-id="5c8ff-130">CsKerberosAccountAssignment コマンドレットでは、成功または失敗を示す単純な通知は返されません。</span><span class="sxs-lookup"><span data-stu-id="5c8ff-130">The Test-CsKerberosAccountAssignment cmdlet does not return a simple indication of success or failure.</span></span> <span data-ttu-id="5c8ff-131">代わりに、Internet Explorer を使用して生成された HTML ファイルを表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c8ff-131">Instead, you must view the generated HTML file by using Internet Explorer.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="5c8ff-132">テストに失敗した可能性がある理由</span><span class="sxs-lookup"><span data-stu-id="5c8ff-132">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="5c8ff-133">次に、テスト-CsKerberosAccountAssignment が失敗する可能性がある一般的な理由を示します。</span><span class="sxs-lookup"><span data-stu-id="5c8ff-133">Here are some common reasons why Test-CsKerberosAccountAssignment might fail:</span></span>

  - <span data-ttu-id="5c8ff-134">指定したサイト Id が間違っている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5c8ff-134">You might have specified an incorrect site Identity.</span></span> <span data-ttu-id="5c8ff-135">有効なサイト Id のリストを返すには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="5c8ff-135">To return a list of valid site Identity, use this command:</span></span>
    
        Get-CsSite | Select-Identity Identity
    
    <span data-ttu-id="5c8ff-136">サイト Id は、通常、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="5c8ff-136">A site Identity typically looks as follows:</span></span>
    
    <span data-ttu-id="5c8ff-137">サイト: レドモンド</span><span class="sxs-lookup"><span data-stu-id="5c8ff-137">site:Redmond</span></span>

  - <span data-ttu-id="5c8ff-138">指定したサイトには、Kerberos アカウントが割り当てられていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5c8ff-138">The specified site might not have a Kerberos account assigned to it.</span></span> <span data-ttu-id="5c8ff-139">次のようなコマンドを実行することで、サイトに Kerberos アカウントが割り当てられているかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="5c8ff-139">You can determine whether or not a Kerberos account is assigned to a site by running a command similar to this:</span></span>
    
        Get-CsKerberosAccountAssignment -Identity "site:Redmond"

  - <span data-ttu-id="5c8ff-140">Kerberos アカウントのパスワードが有効でない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5c8ff-140">Your Kerberos account might have a password that isn't valid.</span></span> <span data-ttu-id="5c8ff-141">レポートで次のエラーメッセージが表示された場合は、おそらく Kerberos アカウントのパスワードを再設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c8ff-141">If you receive the following error message in report, you'll probably have to reset the Kerberos account password:</span></span>
    
    <span data-ttu-id="5c8ff-142">InvalidKerberosConfiguration: Kerberos 構成が無効です。</span><span class="sxs-lookup"><span data-stu-id="5c8ff-142">InvalidKerberosConfiguration: The Kerberos configuration is invalid.</span></span>
    
    <span data-ttu-id="5c8ff-143">InvalidKerberosConfiguration: atl-cs001.litwareinc.com の Kerberos 構成が無効です。</span><span class="sxs-lookup"><span data-stu-id="5c8ff-143">InvalidKerberosConfiguration: The Kerberos configuration on atl-cs001.litwareinc.com is invalid.</span></span> <span data-ttu-id="5c8ff-144">期待される割り当て済みアカウント\\は litwareinc kerberostest です。</span><span class="sxs-lookup"><span data-stu-id="5c8ff-144">The expected assigned account is litwareinc\\kerberostest.</span></span> <span data-ttu-id="5c8ff-145">アカウントの有効期限が切れていないこと、およびコンピューター上の構成されたパスワードが、アカウントの Active Directory パスワードと一致していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5c8ff-145">Ensure that the account has not expired, and the configured password on the machine matches the Active Directory password of the account.</span></span>
    
    <span data-ttu-id="5c8ff-146">パスワードを設定するには、 [set-Csker"@ Accountpassword](https://technet.microsoft.com/en-us/library/Gg398659(v=OCS.15)) " コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="5c8ff-146">You can set the password using the [Set-CsKerberosAccountPassword](https://technet.microsoft.com/en-us/library/Gg398659(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

