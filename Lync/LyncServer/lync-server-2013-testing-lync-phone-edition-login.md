---
title: 'Lync Server 2013: Lync Phone Edition ログインのテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Phone Edition login
ms:assetid: 1ccde6bf-9a2d-4fcf-b81f-1bc9fee2cfbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690128(v=OCS.15)
ms:contentKeyID: 63969583
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbacccabc98829c90e01dc49099b65b829274c82
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034587"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-phone-edition-login-in-lync-server-2013"></a><span data-ttu-id="71372-102">Lync Server 2013 での Lync Phone Edition ログインのテスト</span><span class="sxs-lookup"><span data-stu-id="71372-102">Testing Lync Phone Edition login in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71372-103">_**トピックの最終更新日:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="71372-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="71372-104">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="71372-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="71372-105">毎日</span><span class="sxs-lookup"><span data-stu-id="71372-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71372-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="71372-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="71372-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="71372-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71372-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="71372-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="71372-109">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="71372-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="71372-110">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、テスト-CsPhoneBootstrap コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="71372-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsPhoneBootstrap cmdlet.</span></span> <span data-ttu-id="71372-111">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="71372-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPhoneBootstrap&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="71372-112">説明</span><span class="sxs-lookup"><span data-stu-id="71372-112">Description</span></span>

<span data-ttu-id="71372-113">Test-CsPhoneBootstrap コマンドレットを使用すると、管理者は、特定のユーザー (自分に割り当てられている電話番号と PIN を使用) が Lync 2013 Phone Edition 互換デバイスからシステムにログオンできるかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="71372-113">The Test-CsPhoneBootstrap cmdlet enables administrators to verify that a given user—using the phone number and PIN assigned to him or her—can log on to the system from a Lync 2013 Phone Edition-compatible device.</span></span> <span data-ttu-id="71372-114">(テストを実行するために実際に必要なデバイスはありません)。</span><span class="sxs-lookup"><span data-stu-id="71372-114">(No device is actually needed to run the test.)</span></span>

<span data-ttu-id="71372-115">Test-CsPhoneBootstrap でチェックを実行できるようにするには、テスト対象のユーザー アカウントをホストするレジストラー プールが DHCP を使用して検出できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="71372-115">In order for Test-CsPhoneBootstrap to make its check, the Registrar pool that hosts the user account being tested must be discoverable using DHCP.</span></span> <span data-ttu-id="71372-116">この方法でレジストラーが検出可能かどうかを判断するには、コマンドレット Get-csregistrarconfiguration を使用して、EnableDHCPServer プロパティの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="71372-116">To determine whether a Registrar is discoverable in this manner, use the cmdlet Get-CsRegistrarConfiguration and check the value of the EnableDHCPServer property.</span></span> <span data-ttu-id="71372-117">このプロパティが False に設定されている場合は、Get-csregistrarconfiguration を使用してプロパティ値を True に設定し、DHCP を使用してレジストラーを検出可能にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="71372-117">If this property is set to False, you must use Set-CsRegistrarConfiguration to set the property value to True and make the Registrar discoverable using DHCP.</span></span> <span data-ttu-id="71372-118">これは、エンタープライズ DHCP サーバーを使用して、Lync Server 固有のオプションを構成することによっても実行できます。</span><span class="sxs-lookup"><span data-stu-id="71372-118">This can also be done by using Enterprise DHCP Server and configuring the Lync Server-specific options.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="71372-119">テストの実行</span><span class="sxs-lookup"><span data-stu-id="71372-119">Running the test</span></span>

<span data-ttu-id="71372-120">Test-CsPhoneBootstrap コマンドレットを実行するには、少なくとも、有効な Lync Server ユーザーの電話番号とクライアント暗証番号 (PIN) を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71372-120">To run the Test-CsPhoneBootstrap cmdlet, you must, at a minimum, supply the phone number and client personal identification number (PIN) for a valid Lync Server user.</span></span> <span data-ttu-id="71372-121">たとえば、次のコマンドは、電話番号12065551219と PIN 0712 を持つユーザーのログオン機能をテストします。</span><span class="sxs-lookup"><span data-stu-id="71372-121">For example, this command tests the logon ability for the user who has the phone number 12065551219 and the PIN 0712:</span></span>

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712"

<span data-ttu-id="71372-122">より包括的なチェックを行うには、ユーザーの SIP アドレスを含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="71372-122">For a more comprehensive check, you can also include the user’s SIP address.</span></span> <span data-ttu-id="71372-123">その場合、テストが成功するには、電話番号、クライアント PIN、および SIP アドレスをすべて有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="71372-123">In that case, the phone number, client PIN, and SIP address must all be valid for the test to succeed:</span></span>

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -UserSipAddress "sip:kenmyer@litwareinc.com"

<span data-ttu-id="71372-124">詳細については、「 [Test-CsPhoneBootstrap](https://docs.microsoft.com/powershell/module/skype/Test-CsPhoneBootstrap)コマンドレットのヘルプドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71372-124">For more information, see the Help documentation for the [Test-CsPhoneBootstrap](https://docs.microsoft.com/powershell/module/skype/Test-CsPhoneBootstrap) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="71372-125">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="71372-125">Determining success or failure</span></span>

<span data-ttu-id="71372-126">指定されたユーザーが Lync Server に接続できた場合は、次のような出力が得られます。 Result プロパティは Success としてマークされてい**ます。**</span><span class="sxs-lookup"><span data-stu-id="71372-126">If the specified user was able to connect to Lync Server, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="71372-127">TargetUrihttps://atl-cs-001.litwareinc.com:443/CertProv/</span><span class="sxs-lookup"><span data-stu-id="71372-127">TargetUri : https://atl-cs-001.litwareinc.com:443/CertProv/</span></span>

<span data-ttu-id="71372-128">Certプロビジョニングサービス svc</span><span class="sxs-lookup"><span data-stu-id="71372-128">CertProvisioningService.svc</span></span>

<span data-ttu-id="71372-129">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="71372-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="71372-130">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="71372-130">Result : Success</span></span>

<span data-ttu-id="71372-131">待機時間:00:00: 06.3981276</span><span class="sxs-lookup"><span data-stu-id="71372-131">Latency : 00:00:06.3981276</span></span>

<span data-ttu-id="71372-132">エラー</span><span class="sxs-lookup"><span data-stu-id="71372-132">Error :</span></span>

<span data-ttu-id="71372-133">分析</span><span class="sxs-lookup"><span data-stu-id="71372-133">Diagnosis :</span></span>

<span data-ttu-id="71372-134">指定したユーザーが接続を確立できなかった場合、結果はエラーとして表示され、追加情報が Error および診断プロパティに記録されます。</span><span class="sxs-lookup"><span data-stu-id="71372-134">If the specified user was not able to make a connection, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="71372-135">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="71372-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="71372-136">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="71372-136">Result : Failure</span></span>

<span data-ttu-id="71372-137">待機時間:00:00: 04.1993845</span><span class="sxs-lookup"><span data-stu-id="71372-137">Latency : 00:00:04.1993845</span></span>

<span data-ttu-id="71372-138">エラー: Web チケットサービスの応答が受信されませんでした。</span><span class="sxs-lookup"><span data-stu-id="71372-138">Error : ERROR - No response received for Web-Ticket service.</span></span>

<span data-ttu-id="71372-139">分析</span><span class="sxs-lookup"><span data-stu-id="71372-139">Diagnosis :</span></span>

<span data-ttu-id="71372-140">前回の出力では、Web チケットサービスが応答しなかったため、テストが失敗したことが示されます。</span><span class="sxs-lookup"><span data-stu-id="71372-140">The previous output states that the test failed because the Web Ticket service did not respond.</span></span> <span data-ttu-id="71372-141">これは、サービス自体に問題があるか、または SIP アドレス、電話番号、またはテスト/CsPhoneBootstrap に渡されたクライアント PIN が原因である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="71372-141">This could be due to a problem with the service itself, or it might be due to the SIP address, phone number, or client PIN passed to Test-CsPhoneBootstrap.</span></span> <span data-ttu-id="71372-142">次のようなコマンドを使用して、ユーザーの SIP アドレスと電話番号を確認できます。</span><span class="sxs-lookup"><span data-stu-id="71372-142">You can verify the user’s SIP address and phone number by using a command similar to this one:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, LineUri

<span data-ttu-id="71372-143">また、次のコマンドを使用して、ユーザーが有効な PIN を持っていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="71372-143">And you can verify that the user has a valid PIN by using a command as follows:</span></span>

    Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com" 

<span data-ttu-id="71372-144">テスト-CsPhoneBootstrap が失敗した場合は、次のように詳細なパラメーターを含めて、テストを再実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="71372-144">If Test-CsPhoneBootstrap fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -Verbose

<span data-ttu-id="71372-145">Verbose パラメーターを指定すると、指定されたユーザーが Lync Server にログオンできるかどうかを確認したときに実行された各操作のステップバイステップのアカウントが返されます。</span><span class="sxs-lookup"><span data-stu-id="71372-145">When the Verbose parameter is included, Test-CsPhoneBootstrap will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="71372-146">たとえば、正しくない PIN が含まれているセッションで、ログオンが失敗した場合の出力の一部を次に示します。</span><span class="sxs-lookup"><span data-stu-id="71372-146">For example, here is a portion of the output for an unsuccessful logon, a session in which an incorrect PIN was included:</span></span>

<span data-ttu-id="71372-147">\\内線番号での pin 認証の使用: 12065551219 ピン: 0712</span><span class="sxs-lookup"><span data-stu-id="71372-147">Using PIN auth with Phone\\Ext : 12065551219 Pin : 0712</span></span>

<span data-ttu-id="71372-148">Web チケットを取得できませんでした</span><span class="sxs-lookup"><span data-stu-id="71372-148">Could not get web ticket</span></span>

<span data-ttu-id="71372-149">確かめ</span><span class="sxs-lookup"><span data-stu-id="71372-149">CHECK :</span></span>

<span data-ttu-id="71372-150">\-Web サービスの url が有効で、web サービスが機能している</span><span class="sxs-lookup"><span data-stu-id="71372-150">\- Web service url is valid and the web services are functional</span></span>

<span data-ttu-id="71372-151">\-PhoneNo\\PIN を使用して認証する場合は、ユーザーの uri と一致していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="71372-151">\- If using PhoneNo\\PIN to authenticate, make sure they match the user uri</span></span>

<span data-ttu-id="71372-152">\-NTLM\\Kerberos 認証を使用している場合は、有効な資格情報を入力してください。</span><span class="sxs-lookup"><span data-stu-id="71372-152">\- If using NTLM\\Kerberos auth, make sure you provided valid credentials</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="71372-153">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="71372-153">Reasons why the test might have failed</span></span>

<span data-ttu-id="71372-154">テスト、CsPhoneBootstrap が失敗する原因としては、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="71372-154">Here are some common reasons why Test-CsPhoneBootstrap might fail:</span></span>

  - <span data-ttu-id="71372-155">無効な SIP アドレスを指定した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="71372-155">You might have specified a SIP address that is not valid.</span></span> <span data-ttu-id="71372-156">次のようなコマンドを使用して、SIP アドレスが正しいことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="71372-156">You can verify that a SIP address is correct by using a command such as this one:</span></span>
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="71372-157">無効な PIN が指定されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="71372-157">You might have specified a PIN that is not valid.</span></span> <span data-ttu-id="71372-158">ユーザーの PIN 番号を取得することはできませんが、次のようなコマンドを使用して、少なくともユーザーが PIN 番号を持っていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="71372-158">Although you can't retrieve the user’s PIN number, you can verify that the user at least has a PIN number by using a command similar to this:</span></span>
    
        Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="71372-159">無効な電話番号が指定されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="71372-159">You might have specified a phone number that is not valid.</span></span> <span data-ttu-id="71372-160">ユーザーの電話を確認するには、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="71372-160">You can verify a user’s phone by using a command similar to the following:</span></span>
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object LineUri

  - <span data-ttu-id="71372-161">レジストラープールは DHCP 対応になっていません。</span><span class="sxs-lookup"><span data-stu-id="71372-161">The Registrar pool is not DHCP-enabled.</span></span> <span data-ttu-id="71372-162">レジストラープールが DHCP に対して有効になっているかどうかを確認するには、Get-csregistrarconfiguration コマンドレットを実行し、EnableDHCPServer プロパティの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="71372-162">To determine whether your Registrar pool is enabled for DHCP, run the Get-CsRegistrarConfiguration cmdlet and check the value of the EnableDHCPServer property.</span></span> <span data-ttu-id="71372-163">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="71372-163">For example:</span></span>
    
        Get-CsRegistrarConfiguration -Identity "global"

</div>

</div>

<span> </span>

</div>

</div>

</div>

