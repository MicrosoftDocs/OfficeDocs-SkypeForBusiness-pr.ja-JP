---
title: 'Lync Server 2013: Lync Phone Edition のログインをテストする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing Lync Phone Edition login
ms:assetid: 1ccde6bf-9a2d-4fcf-b81f-1bc9fee2cfbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690128(v=OCS.15)
ms:contentKeyID: 63969583
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb2cf0dae748cf82e83e86389abf55c55c8c70e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848443"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-phone-edition-login-in-lync-server-2013"></a><span data-ttu-id="fa2d4-102">Lync Server 2013 での Lync Phone Edition のログインのテスト</span><span class="sxs-lookup"><span data-stu-id="fa2d4-102">Testing Lync Phone Edition login in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa2d4-103">_**最終更新日:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="fa2d4-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa2d4-104">確認のスケジュール</span><span class="sxs-lookup"><span data-stu-id="fa2d4-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="fa2d4-105">[毎日]</span><span class="sxs-lookup"><span data-stu-id="fa2d4-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa2d4-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="fa2d4-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="fa2d4-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fa2d4-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa2d4-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="fa2d4-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="fa2d4-109">Lync Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa2d4-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="fa2d4-110">Windows PowerShell のリモートインスタンスを使って実行する場合は、テスト-CsPhoneBootstrap コマンドレットを実行する権限を持つ RBAC の役割をユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa2d4-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsPhoneBootstrap cmdlet.</span></span> <span data-ttu-id="fa2d4-111">このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fa2d4-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPhoneBootstrap&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="fa2d4-112">説明</span><span class="sxs-lookup"><span data-stu-id="fa2d4-112">Description</span></span>

<span data-ttu-id="fa2d4-113">テスト-CsPhoneBootstrap コマンドレットを使用すると、管理者は、ユーザーが割り当てられた電話番号と PIN を使って、Lync 2013 Phone Edition 対応のデバイスからシステムにログオンできることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="fa2d4-113">The Test-CsPhoneBootstrap cmdlet enables administrators to verify that a given user—using the phone number and PIN assigned to him or her—can log on to the system from a Lync 2013 Phone Edition-compatible device.</span></span> <span data-ttu-id="fa2d4-114">(実際にテストを実行するために必要なデバイスはありません)。</span><span class="sxs-lookup"><span data-stu-id="fa2d4-114">(No device is actually needed to run the test.)</span></span>

<span data-ttu-id="fa2d4-115">テスト用の CsPhoneBootstrap をチェックするために、テスト対象のユーザーアカウントをホストしているレジストラープールは、DHCP を使って検出できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa2d4-115">In order for Test-CsPhoneBootstrap to make its check, the Registrar pool that hosts the user account being tested must be discoverable using DHCP.</span></span> <span data-ttu-id="fa2d4-116">この方法でレジストラーが検出可能かどうかを判断するには、コマンドレット CsRegistrarConfiguration を使用して、EnableDHCPServer プロパティの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="fa2d4-116">To determine whether a Registrar is discoverable in this manner, use the cmdlet Get-CsRegistrarConfiguration and check the value of the EnableDHCPServer property.</span></span> <span data-ttu-id="fa2d4-117">このプロパティが False に設定されている場合は、CsRegistrarConfiguration を使用してプロパティ値を True に設定し、DHCP を使用してレジストラーを検出できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa2d4-117">If this property is set to False, you must use Set-CsRegistrarConfiguration to set the property value to True and make the Registrar discoverable using DHCP.</span></span> <span data-ttu-id="fa2d4-118">また、エンタープライズ DHCP サーバーを使用して、Lync Server 固有のオプションを構成することでも実行できます。</span><span class="sxs-lookup"><span data-stu-id="fa2d4-118">This can also be done by using Enterprise DHCP Server and configuring the Lync Server-specific options.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="fa2d4-119">テストの実行</span><span class="sxs-lookup"><span data-stu-id="fa2d4-119">Running the test</span></span>

<span data-ttu-id="fa2d4-120">テスト-CsPhoneBootstrap コマンドレットを実行するには、少なくとも、有効な Lync Server ユーザーの電話番号とクライアントの暗証番号 (PIN) を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa2d4-120">To run the Test-CsPhoneBootstrap cmdlet, you must, at a minimum, supply the phone number and client personal identification number (PIN) for a valid Lync Server user.</span></span> <span data-ttu-id="fa2d4-121">たとえば、次のコマンドは、電話番号12065551219と PIN 0712 を持っているユーザーのログオン機能をテストします。</span><span class="sxs-lookup"><span data-stu-id="fa2d4-121">For example, this command tests the logon ability for the user who has the phone number 12065551219 and the PIN 0712:</span></span>

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712"

<span data-ttu-id="fa2d4-122">さらに包括的なチェックを行うには、ユーザーの SIP アドレスを含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="fa2d4-122">For a more comprehensive check, you can also include the user’s SIP address.</span></span> <span data-ttu-id="fa2d4-123">その場合、テストが成功するには、電話番号、クライアント PIN、および SIP アドレスがすべて有効である必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa2d4-123">In that case, the phone number, client PIN, and SIP address must all be valid for the test to succeed:</span></span>

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -UserSipAddress "sip:kenmyer@litwareinc.com"

<span data-ttu-id="fa2d4-124">詳細については、「[テスト-CsPhoneBootstrap](https://docs.microsoft.com/powershell/module/skype/Test-CsPhoneBootstrap)コマンドレット」のヘルプドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa2d4-124">For more information, see the Help documentation for the [Test-CsPhoneBootstrap](https://docs.microsoft.com/powershell/module/skype/Test-CsPhoneBootstrap) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="fa2d4-125">成功または失敗を確認する</span><span class="sxs-lookup"><span data-stu-id="fa2d4-125">Determining success or failure</span></span>

<span data-ttu-id="fa2d4-126">指定したユーザーが Lync Server に接続できた場合は、次のような出力が表示され、Result プロパティは Success とマークされ**ます。**</span><span class="sxs-lookup"><span data-stu-id="fa2d4-126">If the specified user was able to connect to Lync Server, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="fa2d4-127">TargetUri :https://atl-cs-001.litwareinc.com:443/CertProv/</span><span class="sxs-lookup"><span data-stu-id="fa2d4-127">TargetUri : https://atl-cs-001.litwareinc.com:443/CertProv/</span></span>

<span data-ttu-id="fa2d4-128">Certservices .svc</span><span class="sxs-lookup"><span data-stu-id="fa2d4-128">CertProvisioningService.svc</span></span>

<span data-ttu-id="fa2d4-129">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="fa2d4-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="fa2d4-130">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="fa2d4-130">Result : Success</span></span>

<span data-ttu-id="fa2d4-131">待ち時間:00:00: 06.3981276</span><span class="sxs-lookup"><span data-stu-id="fa2d4-131">Latency : 00:00:06.3981276</span></span>

<span data-ttu-id="fa2d4-132">誤差</span><span class="sxs-lookup"><span data-stu-id="fa2d4-132">Error :</span></span>

<span data-ttu-id="fa2d4-133">診断</span><span class="sxs-lookup"><span data-stu-id="fa2d4-133">Diagnosis :</span></span>

<span data-ttu-id="fa2d4-134">指定したユーザーが接続できなかった場合は、結果がエラーとして表示され、エラーと診断のプロパティに追加情報が記録されます。</span><span class="sxs-lookup"><span data-stu-id="fa2d4-134">If the specified user was not able to make a connection, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="fa2d4-135">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="fa2d4-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="fa2d4-136">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="fa2d4-136">Result : Failure</span></span>

<span data-ttu-id="fa2d4-137">待ち時間:00:00: 04.1993845</span><span class="sxs-lookup"><span data-stu-id="fa2d4-137">Latency : 00:00:04.1993845</span></span>

<span data-ttu-id="fa2d4-138">エラー: Web チケットサービスの応答がありませんでした。</span><span class="sxs-lookup"><span data-stu-id="fa2d4-138">Error : ERROR - No response received for Web-Ticket service.</span></span>

<span data-ttu-id="fa2d4-139">診断</span><span class="sxs-lookup"><span data-stu-id="fa2d4-139">Diagnosis :</span></span>

<span data-ttu-id="fa2d4-140">前回の出力では、Web チケットサービスが応答しなかったため、テストが失敗したことが示されます。</span><span class="sxs-lookup"><span data-stu-id="fa2d4-140">The previous output states that the test failed because the Web Ticket service did not respond.</span></span> <span data-ttu-id="fa2d4-141">これは、サービス自体で問題が発生したか、または SIP アドレス、電話番号、またはクライアント PIN がテスト用の CsPhoneBootstrap に渡されたことが原因である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fa2d4-141">This could be due to a problem with the service itself, or it might be due to the SIP address, phone number, or client PIN passed to Test-CsPhoneBootstrap.</span></span> <span data-ttu-id="fa2d4-142">次のようなコマンドを使用して、ユーザーの SIP アドレスと電話番号を確認できます。</span><span class="sxs-lookup"><span data-stu-id="fa2d4-142">You can verify the user’s SIP address and phone number by using a command similar to this one:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, LineUri

<span data-ttu-id="fa2d4-143">また、次のようにコマンドを使用して、ユーザーが有効な PIN を持っていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="fa2d4-143">And you can verify that the user has a valid PIN by using a command as follows:</span></span>

    Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com" 

<span data-ttu-id="fa2d4-144">テスト用の CsPhoneBootstrap が失敗した場合は、Verbose パラメーターなどのテストを再実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fa2d4-144">If Test-CsPhoneBootstrap fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -Verbose

<span data-ttu-id="fa2d4-145">Verbose パラメーターが含まれている場合は、指定したユーザーが Lync Server にログオンする機能を確認したときに、テスト CsPhoneBootstrap からステップバイステップのアカウントが返されます。</span><span class="sxs-lookup"><span data-stu-id="fa2d4-145">When the Verbose parameter is included, Test-CsPhoneBootstrap will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="fa2d4-146">たとえば、次の例は、正常に行われなかったログオンの出力を示しています。このセッションでは、不正な PIN が含まれています。</span><span class="sxs-lookup"><span data-stu-id="fa2d4-146">For example, here is a portion of the output for an unsuccessful logon, a session in which an incorrect PIN was included:</span></span>

<span data-ttu-id="fa2d4-147">内線番号での PIN\\認証の使用: 12065551219 ピン: 0712</span><span class="sxs-lookup"><span data-stu-id="fa2d4-147">Using PIN auth with Phone\\Ext : 12065551219 Pin : 0712</span></span>

<span data-ttu-id="fa2d4-148">Web チケットを取得できませんでした</span><span class="sxs-lookup"><span data-stu-id="fa2d4-148">Could not get web ticket</span></span>

<span data-ttu-id="fa2d4-149">調べ</span><span class="sxs-lookup"><span data-stu-id="fa2d4-149">CHECK :</span></span>

<span data-ttu-id="fa2d4-150">\-Web サービスの url が有効であり、web サービスが機能している</span><span class="sxs-lookup"><span data-stu-id="fa2d4-150">\- Web service url is valid and the web services are functional</span></span>

<span data-ttu-id="fa2d4-151">\-認証に PhoneNo\\PIN を使用している場合は、ユーザーの uri と一致することを確認します。</span><span class="sxs-lookup"><span data-stu-id="fa2d4-151">\- If using PhoneNo\\PIN to authenticate, make sure they match the user uri</span></span>

<span data-ttu-id="fa2d4-152">\-NTLM\\Kerberos 認証を使用している場合は、有効な資格情報を指定していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="fa2d4-152">\- If using NTLM\\Kerberos auth, make sure you provided valid credentials</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="fa2d4-153">テストに失敗した可能性がある理由</span><span class="sxs-lookup"><span data-stu-id="fa2d4-153">Reasons why the test might have failed</span></span>

<span data-ttu-id="fa2d4-154">テスト用の CsPhoneBootstrap が失敗する可能性がある一般的な理由を次に示します。</span><span class="sxs-lookup"><span data-stu-id="fa2d4-154">Here are some common reasons why Test-CsPhoneBootstrap might fail:</span></span>

  - <span data-ttu-id="fa2d4-155">有効でない SIP アドレスが指定された可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fa2d4-155">You might have specified a SIP address that is not valid.</span></span> <span data-ttu-id="fa2d4-156">次のようなコマンドを使用して、SIP アドレスが正しいことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="fa2d4-156">You can verify that a SIP address is correct by using a command such as this one:</span></span>
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="fa2d4-157">無効な PIN を指定した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fa2d4-157">You might have specified a PIN that is not valid.</span></span> <span data-ttu-id="fa2d4-158">ユーザーの PIN 番号を取得することはできませんが、次のようなコマンドを使用して、ユーザーの PIN 番号が少なくなっていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="fa2d4-158">Although you can't retrieve the user’s PIN number, you can verify that the user at least has a PIN number by using a command similar to this:</span></span>
    
        Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="fa2d4-159">無効な電話番号を指定した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fa2d4-159">You might have specified a phone number that is not valid.</span></span> <span data-ttu-id="fa2d4-160">次のようなコマンドを使用して、ユーザーの電話を確認できます。</span><span class="sxs-lookup"><span data-stu-id="fa2d4-160">You can verify a user’s phone by using a command similar to the following:</span></span>
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object LineUri

  - <span data-ttu-id="fa2d4-161">レジストラープールは DHCP 対応ではありません。</span><span class="sxs-lookup"><span data-stu-id="fa2d4-161">The Registrar pool is not DHCP-enabled.</span></span> <span data-ttu-id="fa2d4-162">レジストラープールが DHCP に対して有効になっているかどうかを確認するには、CsRegistrarConfiguration コマンドレットを実行して、EnableDHCPServer プロパティの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="fa2d4-162">To determine whether your Registrar pool is enabled for DHCP, run the Get-CsRegistrarConfiguration cmdlet and check the value of the EnableDHCPServer property.</span></span> <span data-ttu-id="fa2d4-163">例:</span><span class="sxs-lookup"><span data-stu-id="fa2d4-163">For example:</span></span>
    
        Get-CsRegistrarConfiguration -Identity "global"

</div>

</div>

<span> </span>

</div>

</div>

</div>

