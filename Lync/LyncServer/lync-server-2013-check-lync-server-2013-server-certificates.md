---
title: 'Lync Server 2013: Lync Server 2013 サーバー証明書の確認'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check server certificates
ms:assetid: 7b0474e8-0efe-47f0-84eb-a1ba575dabfd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725210(v=OCS.15)
ms:contentKeyID: 63969620
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b874c83adb2a1ddb511d8c6980cb12f01e0ef68
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151087"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="check-lync-server-2013-server-certificates"></a><span data-ttu-id="76138-102">Lync Server 2013 のサーバー証明書を確認する</span><span class="sxs-lookup"><span data-stu-id="76138-102">Check Lync Server 2013 server certificates</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76138-103">_**トピックの最終更新日:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="76138-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="76138-104">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="76138-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="76138-105">毎月</span><span class="sxs-lookup"><span data-stu-id="76138-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76138-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="76138-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="76138-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="76138-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76138-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="76138-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="76138-109">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="76138-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="76138-110">Windows PowerShell のリモートインスタンスを使用して実行する場合は、ユーザーに、CsCertificate コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="76138-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Get-CsCertificate cmdlet.</span></span> <span data-ttu-id="76138-111">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="76138-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Get-CsCertificate&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="76138-112">説明</span><span class="sxs-lookup"><span data-stu-id="76138-112">Description</span></span>

<span data-ttu-id="76138-113">Get-help Certificate コマンドレットを使用すると、各 Lync Server 証明書に関する情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="76138-113">The Get-CsCertificate cmdlet enables you to retrieve information about each of your Lync Server certificates.</span></span> <span data-ttu-id="76138-114">証明書には有効期限が組み込まれているため、これは特に重要です。</span><span class="sxs-lookup"><span data-stu-id="76138-114">That’s especially important because certificates have a built-in expiration date.</span></span> <span data-ttu-id="76138-115">たとえば、非公開で発行された証明書は、通常12か月後に期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="76138-115">For example,, privately-issued certificates typically expire after 12 months.</span></span> <span data-ttu-id="76138-116">いずれかの Lync Server 証明書の有効期限が切れた場合は、その証明書が更新または置き換えられるまで、付随する機能が失われます。</span><span class="sxs-lookup"><span data-stu-id="76138-116">If any of your Lync Server certificates expire then you'll lose the accompanying functionality until that certificate is renewed or replaced.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="76138-117">テストの実行</span><span class="sxs-lookup"><span data-stu-id="76138-117">Running the test</span></span>

<span data-ttu-id="76138-118">各 Lync Server 証明書に関する情報を戻すには、次のコマンドを実行するだけです。</span><span class="sxs-lookup"><span data-stu-id="76138-118">To return information about each of your Lync Server certificates just run the following command:</span></span>

`Get-CsCertificate`

<span data-ttu-id="76138-119">または、有効期限の日付に基づいて、返却証明書の情報をフィルター処理することができます。</span><span class="sxs-lookup"><span data-stu-id="76138-119">Or, you can filter the return certificate information based on expiration date.</span></span> <span data-ttu-id="76138-120">たとえば、次のコマンドは、返されるデータを、有効期限が切れた (後で使用することができない) 証明書 (2014 年6月1日) に制限します。</span><span class="sxs-lookup"><span data-stu-id="76138-120">For example, this command limits the returned data to certificates that expire (cannot be used after) June 1, 2014:</span></span>

`Get-CsCertificate | Where-Object {$_.NotAfter -lt "6/1/2014"}`

<span data-ttu-id="76138-121">詳細については、「Get-help Certificate コマンドレットのヘルプドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76138-121">For more information, see the Help documentation for the Get-CsCertificate cmdlet.</span></span>

<span data-ttu-id="76138-122">なお、Test-Cs/cs/コマンドレットは存在していても、管理者にとってはあまり役に立たないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="76138-122">Note that, although the Test-CsCertificateConfiguration cmdlet exists, it is not very useful to administrators.</span></span> <span data-ttu-id="76138-123">(そのコマンドレットは、主に証明書ウィザードによって使用されます)。コマンドレットは動作しますが、次の出力例に示すように、返される情報は最小値です。</span><span class="sxs-lookup"><span data-stu-id="76138-123">(Instead, that cmdlet is primarily used by the Certificate wizard.) Although the cmdlet works, the information that it returns is of minimal value as shown in the following output example:</span></span>

<span data-ttu-id="76138-124">拇印の使用</span><span class="sxs-lookup"><span data-stu-id="76138-124">Thumbprint Use</span></span>

<span data-ttu-id="76138-125">\---------- ---</span><span class="sxs-lookup"><span data-stu-id="76138-125">\---------- ---</span></span>

<span data-ttu-id="76138-126">A9D51A2911C74FABFF7F2A8A994B20857D399107 の既定値</span><span class="sxs-lookup"><span data-stu-id="76138-126">A9D51A2911C74FABFF7F2A8A994B20857D399107 Default</span></span>

</div>

<div>

## <a name="reviewing-the-output"></a><span data-ttu-id="76138-127">出力の確認</span><span class="sxs-lookup"><span data-stu-id="76138-127">Reviewing the output</span></span>

<span data-ttu-id="76138-128">Get-help Certificate コマンドレットは、各 Lync Server 証明書について次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="76138-128">The Get-CsCertificate cmdlet returns information similar to the following for each of your Lync Server certificates:</span></span>

<span data-ttu-id="76138-129">発行者: CN = FabrikamCA</span><span class="sxs-lookup"><span data-stu-id="76138-129">Issuer : CN=FabrikamCA</span></span>

<span data-ttu-id="76138-130">NotAfter: 12/28/2015 3:35:41 PM</span><span class="sxs-lookup"><span data-stu-id="76138-130">NotAfter : 12/28/2015 3:35:41 PM</span></span>

<span data-ttu-id="76138-131">NotBefore: 1/2/2014 12:49:37 PM</span><span class="sxs-lookup"><span data-stu-id="76138-131">NotBefore : 1/2/2014 12:49:37 PM</span></span>

<span data-ttu-id="76138-132">シリアル: 611BB01200000000000C</span><span class="sxs-lookup"><span data-stu-id="76138-132">SerialNumber : 611BB01200000000000C</span></span>

<span data-ttu-id="76138-133">件名: CN = LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="76138-133">Subject : CN=LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="76138-134">代替の [ベンダー]: {sip.fabrikam.com, LYNC-SE.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="76138-134">AlternativeNames : {sip.fabrikam.com, LYNC-SE.fabrikam.com,</span></span>

<span data-ttu-id="76138-135">meet.fabrikam.com、admin.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="76138-135">meet.fabrikam.com, admin.fabrikam.com...}</span></span>

<span data-ttu-id="76138-136">Thumbprint: A9D51A2911C74FABFF7F2A8A994B20857D399107</span><span class="sxs-lookup"><span data-stu-id="76138-136">Thumbprint : A9D51A2911C74FABFF7F2A8A994B20857D399107</span></span>

<span data-ttu-id="76138-137">Use: Default</span><span class="sxs-lookup"><span data-stu-id="76138-137">Use : Default</span></span>

<span data-ttu-id="76138-138">原則として、Lync Server 証明書に関連する主な問題には、証明書が有効になったときや期限切れになったとき (NotAfter) など、日付と時刻が含まれます。</span><span class="sxs-lookup"><span data-stu-id="76138-138">As a rule, the top issues involving Lync Server certificates involve dates and times, such as when certificates take effect (NotBefore) or when they expire (NotAfter).</span></span> <span data-ttu-id="76138-139">これらの日付と時刻が重要であるため、返されるデータを証明書の使用、証明書のシリアル番号、証明書の有効期限などの情報に制限することをお勧めします。これにより、すべての証明書とその期限が切れるまでの時間をすばやく確認できます。</span><span class="sxs-lookup"><span data-stu-id="76138-139">Because these dates and times are so important, you might want to limit the returned data to information such as the certificate use, the certificate serial number, and the certificate expiration date; then you can quickly review all the certificates and when they will expire.</span></span> <span data-ttu-id="76138-140">その情報のみを返すには、次のようなオプションを使用してコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="76138-140">To return just that information, use the command together with the options as shown:</span></span>

`Get-CsCertificate | Select-Object Use, SerialNumber, NotAfter | Sort-Object NotAfter`

<span data-ttu-id="76138-141">このコマンドは、証明書が有効期限の順に並べ替えられた状態で、次のようなデータを返します。</span><span class="sxs-lookup"><span data-stu-id="76138-141">That command returns data similar to the following, with the certificates sorted in order of their expiration date:</span></span>

<span data-ttu-id="76138-142">シリアルの使用</span><span class="sxs-lookup"><span data-stu-id="76138-142">Use SerialNumber NotAfter</span></span>

<span data-ttu-id="76138-143">\--- ------------ --------</span><span class="sxs-lookup"><span data-stu-id="76138-143">\--- ------------ --------</span></span>

<span data-ttu-id="76138-144">Default 611BB01200000000000C 12/28/2015 3:35:41 PM</span><span class="sxs-lookup"><span data-stu-id="76138-144">Default 611BB01200000000000C 12/28/2015 3:35:41 PM</span></span>

<span data-ttu-id="76138-145">Webサービス Interal 32980AA20BBB20000191 02/15/2016 2:16:12 PM</span><span class="sxs-lookup"><span data-stu-id="76138-145">WebServicesInteral 32980AA20BBB20000191 02/15/2016 2:16:12 PM</span></span>

<span data-ttu-id="76138-146">WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM</span><span class="sxs-lookup"><span data-stu-id="76138-146">WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM</span></span>

<span data-ttu-id="76138-147">証明書に問題がある場合は、証明書に対して構成された代替のベンダーを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="76138-147">If you have certificate problems, you might want to review the AlternativeNames configured for a certificate.</span></span> <span data-ttu-id="76138-148">一見すると、問題があるように見えます。</span><span class="sxs-lookup"><span data-stu-id="76138-148">At first glance, that seems to be a problem.</span></span> <span data-ttu-id="76138-149">既定では、コンソールウィンドウのサイズによっては、を取得すると、すべての名前を表示できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="76138-149">By default, and depending on the size of your console window, Get-CsCertificate might not be able to display all the names:</span></span>

<span data-ttu-id="76138-150">代替の [ベンダー]: {sip.fabrikam.com, LYNC.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="76138-150">AlternativeNames : {sip.fabrikam.com, LYNC.fabrikam.com,</span></span>

<span data-ttu-id="76138-151">meet.fabrikam.com, fabrika...}</span><span class="sxs-lookup"><span data-stu-id="76138-151">meet.fabrikam.com, admin.fabrika...}</span></span>

<span data-ttu-id="76138-152">証明書に割り当てられているすべての代替名を表示するには、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="76138-152">To see all the alternative names assigned to a certificate use a command similar to this one:</span></span>

`Get-CsCertificate | Where-Object {$_.SerialNumber -eq "611BB01200000000000C"} | Select-Object -ExpandProperty AlternativeNames`

<span data-ttu-id="76138-153">これにより、証明書のすべての代替名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="76138-153">That should show you all of the alternative names on the certificate:</span></span>

<span data-ttu-id="76138-154">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="76138-154">sip.fabrikam.com</span></span>

<span data-ttu-id="76138-155">LYNC.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="76138-155">LYNC.fabrikam.com</span></span>

<span data-ttu-id="76138-156">meet.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="76138-156">meet.fabrikam.com</span></span>

<span data-ttu-id="76138-157">admin.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="76138-157">admin.fabrikam.com</span></span>

<span data-ttu-id="76138-158">LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="76138-158">LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="76138-159">Dialin.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="76138-159">Dialin.fabrikam.com</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="76138-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="76138-160">See Also</span></span>


[<span data-ttu-id="76138-161">-CsCertificate の取得</span><span class="sxs-lookup"><span data-stu-id="76138-161">Get-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

