---
title: 'Lync Server 2013: Lync Phone Edition ログインのテスト'
description: 'Lync Server 2013: Lync Phone Edition のログインをテストします。'
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
ms.openlocfilehash: d21d65676c4f5e0f867c7d9556cdea50419be69b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575243"
---
# <a name="testing-lync-phone-edition-login-in-lync-server-2013"></a><span data-ttu-id="9c060-103">Lync Server 2013 での Lync Phone Edition ログインのテスト</span><span class="sxs-lookup"><span data-stu-id="9c060-103">Testing Lync Phone Edition login in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c060-104">_**トピックの最終更新日:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="9c060-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9c060-105">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="9c060-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="9c060-106">毎日</span><span class="sxs-lookup"><span data-stu-id="9c060-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c060-107">テストツール</span><span class="sxs-lookup"><span data-stu-id="9c060-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="9c060-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9c060-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c060-109">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="9c060-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="9c060-110">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c060-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="9c060-111">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには Test-CsPhoneBootstrap コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c060-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsPhoneBootstrap cmdlet.</span></span> <span data-ttu-id="9c060-112">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9c060-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPhoneBootstrap&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="9c060-113">説明</span><span class="sxs-lookup"><span data-stu-id="9c060-113">Description</span></span>

<span data-ttu-id="9c060-114">Test-CsPhoneBootstrap コマンドレットを使用すると、管理者は、特定のユーザー (自分に割り当てられた電話番号と PIN を使用して) が Lync 2013 Phone Edition 互換デバイスからシステムにログオンできるかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="9c060-114">The Test-CsPhoneBootstrap cmdlet enables administrators to verify that a given user—using the phone number and PIN assigned to him or her—can log on to the system from a Lync 2013 Phone Edition-compatible device.</span></span> <span data-ttu-id="9c060-115">(テストを実行するために実際に必要なデバイスはありません)。</span><span class="sxs-lookup"><span data-stu-id="9c060-115">(No device is actually needed to run the test.)</span></span>

<span data-ttu-id="9c060-116">Test-CsPhoneBootstrap でチェックを実行できるようにするには、テスト対象のユーザー アカウントをホストするレジストラー プールが DHCP を使用して検出できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c060-116">In order for Test-CsPhoneBootstrap to make its check, the Registrar pool that hosts the user account being tested must be discoverable using DHCP.</span></span> <span data-ttu-id="9c060-117">この方法でレジストラーが検出可能かどうかを判断するには、コマンドレット Get-CsRegistrarConfiguration を使用して、EnableDHCPServer プロパティの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="9c060-117">To determine whether a Registrar is discoverable in this manner, use the cmdlet Get-CsRegistrarConfiguration and check the value of the EnableDHCPServer property.</span></span> <span data-ttu-id="9c060-118">このプロパティが False に設定されている場合は、Set-CsRegistrarConfiguration を使用してプロパティ値を True に設定し、DHCP を使用してレジストラーを検出可能にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c060-118">If this property is set to False, you must use Set-CsRegistrarConfiguration to set the property value to True and make the Registrar discoverable using DHCP.</span></span> <span data-ttu-id="9c060-119">これは、エンタープライズ DHCP サーバーを使用して、Lync Server 固有のオプションを構成することによっても実行できます。</span><span class="sxs-lookup"><span data-stu-id="9c060-119">This can also be done by using Enterprise DHCP Server and configuring the Lync Server-specific options.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="9c060-120">テストの実行</span><span class="sxs-lookup"><span data-stu-id="9c060-120">Running the test</span></span>

<span data-ttu-id="9c060-121">Test-CsPhoneBootstrap コマンドレットを実行するには、少なくとも、有効な Lync Server ユーザーの電話番号とクライアント暗証番号 (PIN) を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c060-121">To run the Test-CsPhoneBootstrap cmdlet, you must, at a minimum, supply the phone number and client personal identification number (PIN) for a valid Lync Server user.</span></span> <span data-ttu-id="9c060-122">たとえば、次のコマンドは、電話番号12065551219と PIN 0712 を持つユーザーのログオン機能をテストします。</span><span class="sxs-lookup"><span data-stu-id="9c060-122">For example, this command tests the logon ability for the user who has the phone number 12065551219 and the PIN 0712:</span></span>

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712"

<span data-ttu-id="9c060-123">より包括的なチェックを行うには、ユーザーの SIP アドレスを含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="9c060-123">For a more comprehensive check, you can also include the user’s SIP address.</span></span> <span data-ttu-id="9c060-124">その場合、テストが成功するには、電話番号、クライアント PIN、および SIP アドレスをすべて有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c060-124">In that case, the phone number, client PIN, and SIP address must all be valid for the test to succeed:</span></span>

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -UserSipAddress "sip:kenmyer@litwareinc.com"

<span data-ttu-id="9c060-125">詳細については、「 [Test-CsPhoneBootstrap](https://docs.microsoft.com/powershell/module/skype/Test-CsPhoneBootstrap) コマンドレットのヘルプドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c060-125">For more information, see the Help documentation for the [Test-CsPhoneBootstrap](https://docs.microsoft.com/powershell/module/skype/Test-CsPhoneBootstrap) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="9c060-126">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="9c060-126">Determining success or failure</span></span>

<span data-ttu-id="9c060-127">指定されたユーザーが Lync Server に接続できた場合は、次のような出力が得られます。 Result プロパティは Success としてマークされてい **ます。**</span><span class="sxs-lookup"><span data-stu-id="9c060-127">If the specified user was able to connect to Lync Server, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="9c060-128">TargetUri https://atl-cs-001.litwareinc.com:443/CertProv/</span><span class="sxs-lookup"><span data-stu-id="9c060-128">TargetUri : https://atl-cs-001.litwareinc.com:443/CertProv/</span></span>

<span data-ttu-id="9c060-129">Certプロビジョニングサービス svc</span><span class="sxs-lookup"><span data-stu-id="9c060-129">CertProvisioningService.svc</span></span>

<span data-ttu-id="9c060-130">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9c060-130">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="9c060-131">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="9c060-131">Result : Success</span></span>

<span data-ttu-id="9c060-132">待機時間:00:00: 06.3981276</span><span class="sxs-lookup"><span data-stu-id="9c060-132">Latency : 00:00:06.3981276</span></span>

<span data-ttu-id="9c060-133">エラー</span><span class="sxs-lookup"><span data-stu-id="9c060-133">Error :</span></span>

<span data-ttu-id="9c060-134">分析</span><span class="sxs-lookup"><span data-stu-id="9c060-134">Diagnosis :</span></span>

<span data-ttu-id="9c060-135">指定したユーザーが接続を確立できなかった場合、結果はエラーとして表示され、追加情報が Error および診断プロパティに記録されます。</span><span class="sxs-lookup"><span data-stu-id="9c060-135">If the specified user was not able to make a connection, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="9c060-136">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9c060-136">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="9c060-137">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="9c060-137">Result : Failure</span></span>

<span data-ttu-id="9c060-138">待機時間:00:00: 04.1993845</span><span class="sxs-lookup"><span data-stu-id="9c060-138">Latency : 00:00:04.1993845</span></span>

<span data-ttu-id="9c060-139">エラー: Web-Ticket サービスの応答が受信されませんでした。</span><span class="sxs-lookup"><span data-stu-id="9c060-139">Error : ERROR - No response received for Web-Ticket service.</span></span>

<span data-ttu-id="9c060-140">分析</span><span class="sxs-lookup"><span data-stu-id="9c060-140">Diagnosis :</span></span>

<span data-ttu-id="9c060-141">前回の出力では、Web チケットサービスが応答しなかったため、テストが失敗したことが示されます。</span><span class="sxs-lookup"><span data-stu-id="9c060-141">The previous output states that the test failed because the Web Ticket service did not respond.</span></span> <span data-ttu-id="9c060-142">これは、サービス自体に問題があるか、または SIP アドレス、電話番号、またはテスト/CsPhoneBootstrap に渡されたクライアント PIN が原因である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9c060-142">This could be due to a problem with the service itself, or it might be due to the SIP address, phone number, or client PIN passed to Test-CsPhoneBootstrap.</span></span> <span data-ttu-id="9c060-143">次のようなコマンドを使用して、ユーザーの SIP アドレスと電話番号を確認できます。</span><span class="sxs-lookup"><span data-stu-id="9c060-143">You can verify the user’s SIP address and phone number by using a command similar to this one:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, LineUri

<span data-ttu-id="9c060-144">また、次のコマンドを使用して、ユーザーが有効な PIN を持っていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="9c060-144">And you can verify that the user has a valid PIN by using a command as follows:</span></span>

    Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com" 

<span data-ttu-id="9c060-145">Test-CsPhoneBootstrap が失敗した場合は、次のようにして、Verbose パラメーターを含むテストを再実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9c060-145">If Test-CsPhoneBootstrap fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -Verbose

<span data-ttu-id="9c060-146">Verbose パラメーターが含まれている場合、Test-CsPhoneBootstrap は、指定されたユーザーが Lync Server にログオンできるかどうかを確認したときに実行された各アクションのステップバイステップのアカウントを返します。</span><span class="sxs-lookup"><span data-stu-id="9c060-146">When the Verbose parameter is included, Test-CsPhoneBootstrap will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="9c060-147">たとえば、正しくない PIN が含まれているセッションで、ログオンが失敗した場合の出力の一部を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9c060-147">For example, here is a portion of the output for an unsuccessful logon, a session in which an incorrect PIN was included:</span></span>

<span data-ttu-id="9c060-148">内線番号での PIN 認証の使用 \\ : 12065551219 ピン: 0712</span><span class="sxs-lookup"><span data-stu-id="9c060-148">Using PIN auth with Phone\\Ext : 12065551219 Pin : 0712</span></span>

<span data-ttu-id="9c060-149">Web チケットを取得できませんでした</span><span class="sxs-lookup"><span data-stu-id="9c060-149">Could not get web ticket</span></span>

<span data-ttu-id="9c060-150">確かめ</span><span class="sxs-lookup"><span data-stu-id="9c060-150">CHECK :</span></span>

<span data-ttu-id="9c060-151">\- Web サービスの url が有効で、web サービスが機能している</span><span class="sxs-lookup"><span data-stu-id="9c060-151">\- Web service url is valid and the web services are functional</span></span>

<span data-ttu-id="9c060-152">\- PhoneNo PIN を使用して \\ 認証する場合は、ユーザーの uri と一致していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9c060-152">\- If using PhoneNo\\PIN to authenticate, make sure they match the user uri</span></span>

<span data-ttu-id="9c060-153">\- NTLM Kerberos 認証を使用している場合は \\ 、有効な資格情報を入力してください。</span><span class="sxs-lookup"><span data-stu-id="9c060-153">\- If using NTLM\\Kerberos auth, make sure you provided valid credentials</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="9c060-154">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="9c060-154">Reasons why the test might have failed</span></span>

<span data-ttu-id="9c060-155">Test-CsPhoneBootstrap が失敗する可能性のある一般的な理由を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9c060-155">Here are some common reasons why Test-CsPhoneBootstrap might fail:</span></span>

  - <span data-ttu-id="9c060-156">無効な SIP アドレスを指定した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9c060-156">You might have specified a SIP address that is not valid.</span></span> <span data-ttu-id="9c060-157">次のようなコマンドを使用して、SIP アドレスが正しいことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="9c060-157">You can verify that a SIP address is correct by using a command such as this one:</span></span>
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="9c060-158">無効な PIN が指定されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9c060-158">You might have specified a PIN that is not valid.</span></span> <span data-ttu-id="9c060-159">ユーザーの PIN 番号を取得することはできませんが、次のようなコマンドを使用して、少なくともユーザーが PIN 番号を持っていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="9c060-159">Although you can't retrieve the user’s PIN number, you can verify that the user at least has a PIN number by using a command similar to this:</span></span>
    
        Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="9c060-160">無効な電話番号が指定されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9c060-160">You might have specified a phone number that is not valid.</span></span> <span data-ttu-id="9c060-161">ユーザーの電話を確認するには、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="9c060-161">You can verify a user’s phone by using a command similar to the following:</span></span>
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object LineUri

  - <span data-ttu-id="9c060-162">レジストラープールは DHCP 対応になっていません。</span><span class="sxs-lookup"><span data-stu-id="9c060-162">The Registrar pool is not DHCP-enabled.</span></span> <span data-ttu-id="9c060-163">レジストラープールが DHCP に対して有効になっているかどうかを確認するには、Get-CsRegistrarConfiguration コマンドレットを実行し、EnableDHCPServer プロパティの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="9c060-163">To determine whether your Registrar pool is enabled for DHCP, run the Get-CsRegistrarConfiguration cmdlet and check the value of the EnableDHCPServer property.</span></span> <span data-ttu-id="9c060-164">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9c060-164">For example:</span></span>
    
        Get-CsRegistrarConfiguration -Identity "global"

</div>

</div>

<span> </span>

</div>

</div>

</div>

