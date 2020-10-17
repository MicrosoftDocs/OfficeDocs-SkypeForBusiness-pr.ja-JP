---
title: 'Lync Server 2013: Lync Server 2013 サーバー証明書の確認'
description: 'Lync Server 2013: Lync Server 2013 サーバー証明書を確認します。'
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
ms.openlocfilehash: 641651cb425b4fe8bd820bcebfa277084233bb1d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543593"
---
# <a name="check-lync-server-2013-server-certificates"></a><span data-ttu-id="6d6d3-103">Lync Server 2013 のサーバー証明書を確認する</span><span class="sxs-lookup"><span data-stu-id="6d6d3-103">Check Lync Server 2013 server certificates</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d6d3-104">_**トピックの最終更新日:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="6d6d3-104">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6d6d3-105">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="6d6d3-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="6d6d3-106">毎月</span><span class="sxs-lookup"><span data-stu-id="6d6d3-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d6d3-107">テストツール</span><span class="sxs-lookup"><span data-stu-id="6d6d3-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="6d6d3-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6d6d3-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d6d3-109">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="6d6d3-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="6d6d3-110">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d6d3-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="6d6d3-111">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには Get-CsCertificate コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d6d3-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Get-CsCertificate cmdlet.</span></span> <span data-ttu-id="6d6d3-112">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6d6d3-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Get-CsCertificate&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="6d6d3-113">説明</span><span class="sxs-lookup"><span data-stu-id="6d6d3-113">Description</span></span>

<span data-ttu-id="6d6d3-114">Get-CsCertificate コマンドレットを使用すると、各 Lync Server 証明書に関する情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="6d6d3-114">The Get-CsCertificate cmdlet enables you to retrieve information about each of your Lync Server certificates.</span></span> <span data-ttu-id="6d6d3-115">証明書には有効期限が組み込まれているため、これは特に重要です。</span><span class="sxs-lookup"><span data-stu-id="6d6d3-115">That’s especially important because certificates have a built-in expiration date.</span></span> <span data-ttu-id="6d6d3-116">たとえば、非公開で発行された証明書は、通常12か月後に期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="6d6d3-116">For example,, privately-issued certificates typically expire after 12 months.</span></span> <span data-ttu-id="6d6d3-117">いずれかの Lync Server 証明書の有効期限が切れた場合は、その証明書が更新または置き換えられるまで、付随する機能が失われます。</span><span class="sxs-lookup"><span data-stu-id="6d6d3-117">If any of your Lync Server certificates expire then you'll lose the accompanying functionality until that certificate is renewed or replaced.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="6d6d3-118">テストの実行</span><span class="sxs-lookup"><span data-stu-id="6d6d3-118">Running the test</span></span>

<span data-ttu-id="6d6d3-119">各 Lync Server 証明書に関する情報を戻すには、次のコマンドを実行するだけです。</span><span class="sxs-lookup"><span data-stu-id="6d6d3-119">To return information about each of your Lync Server certificates just run the following command:</span></span>

`Get-CsCertificate`

<span data-ttu-id="6d6d3-120">または、有効期限の日付に基づいて、返却証明書の情報をフィルター処理することができます。</span><span class="sxs-lookup"><span data-stu-id="6d6d3-120">Or, you can filter the return certificate information based on expiration date.</span></span> <span data-ttu-id="6d6d3-121">たとえば、次のコマンドは、返されるデータを、有効期限が切れた (後で使用することができない) 証明書 (2014 年6月1日) に制限します。</span><span class="sxs-lookup"><span data-stu-id="6d6d3-121">For example, this command limits the returned data to certificates that expire (cannot be used after) June 1, 2014:</span></span>

`Get-CsCertificate | Where-Object {$_.NotAfter -lt "6/1/2014"}`

<span data-ttu-id="6d6d3-122">詳細については、Get-CsCertificate コマンドレットのヘルプドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d6d3-122">For more information, see the Help documentation for the Get-CsCertificate cmdlet.</span></span>

<span data-ttu-id="6d6d3-123">Test-CsCertificateConfiguration コマンドレットは存在していても、管理者にとってはあまり役に立たないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6d6d3-123">Note that, although the Test-CsCertificateConfiguration cmdlet exists, it is not very useful to administrators.</span></span> <span data-ttu-id="6d6d3-124">(そのコマンドレットは、主に証明書ウィザードによって使用されます)。コマンドレットは動作しますが、次の出力例に示すように、返される情報は最小値です。</span><span class="sxs-lookup"><span data-stu-id="6d6d3-124">(Instead, that cmdlet is primarily used by the Certificate wizard.) Although the cmdlet works, the information that it returns is of minimal value as shown in the following output example:</span></span>

<span data-ttu-id="6d6d3-125">拇印の使用</span><span class="sxs-lookup"><span data-stu-id="6d6d3-125">Thumbprint Use</span></span>

<span data-ttu-id="6d6d3-126">\---------- ---</span><span class="sxs-lookup"><span data-stu-id="6d6d3-126">\---------- ---</span></span>

<span data-ttu-id="6d6d3-127">A9D51A2911C74FABFF7F2A8A994B20857D399107 の既定値</span><span class="sxs-lookup"><span data-stu-id="6d6d3-127">A9D51A2911C74FABFF7F2A8A994B20857D399107 Default</span></span>

</div>

<div>

## <a name="reviewing-the-output"></a><span data-ttu-id="6d6d3-128">出力の確認</span><span class="sxs-lookup"><span data-stu-id="6d6d3-128">Reviewing the output</span></span>

<span data-ttu-id="6d6d3-129">Get-CsCertificate コマンドレットは、それぞれの Lync Server 証明書について次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="6d6d3-129">The Get-CsCertificate cmdlet returns information similar to the following for each of your Lync Server certificates:</span></span>

<span data-ttu-id="6d6d3-130">発行者: CN = FabrikamCA</span><span class="sxs-lookup"><span data-stu-id="6d6d3-130">Issuer : CN=FabrikamCA</span></span>

<span data-ttu-id="6d6d3-131">NotAfter: 12/28/2015 3:35:41 PM</span><span class="sxs-lookup"><span data-stu-id="6d6d3-131">NotAfter : 12/28/2015 3:35:41 PM</span></span>

<span data-ttu-id="6d6d3-132">NotBefore: 1/2/2014 12:49:37 PM</span><span class="sxs-lookup"><span data-stu-id="6d6d3-132">NotBefore : 1/2/2014 12:49:37 PM</span></span>

<span data-ttu-id="6d6d3-133">シリアル: 611BB01200000000000C</span><span class="sxs-lookup"><span data-stu-id="6d6d3-133">SerialNumber : 611BB01200000000000C</span></span>

<span data-ttu-id="6d6d3-134">件名: CN = LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="6d6d3-134">Subject : CN=LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="6d6d3-135">代替の [ベンダー]: {sip.fabrikam.com, LYNC-SE.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="6d6d3-135">AlternativeNames : {sip.fabrikam.com, LYNC-SE.fabrikam.com,</span></span>

<span data-ttu-id="6d6d3-136">meet.fabrikam.com、admin.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="6d6d3-136">meet.fabrikam.com, admin.fabrikam.com...}</span></span>

<span data-ttu-id="6d6d3-137">Thumbprint: A9D51A2911C74FABFF7F2A8A994B20857D399107</span><span class="sxs-lookup"><span data-stu-id="6d6d3-137">Thumbprint : A9D51A2911C74FABFF7F2A8A994B20857D399107</span></span>

<span data-ttu-id="6d6d3-138">Use: Default</span><span class="sxs-lookup"><span data-stu-id="6d6d3-138">Use : Default</span></span>

<span data-ttu-id="6d6d3-139">原則として、Lync Server 証明書に関連する主な問題には、証明書が有効になったときや期限切れになったとき (NotAfter) など、日付と時刻が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6d6d3-139">As a rule, the top issues involving Lync Server certificates involve dates and times, such as when certificates take effect (NotBefore) or when they expire (NotAfter).</span></span> <span data-ttu-id="6d6d3-140">これらの日付と時刻が重要であるため、返されるデータを証明書の使用、証明書のシリアル番号、証明書の有効期限などの情報に制限することをお勧めします。これにより、すべての証明書とその期限が切れるまでの時間をすばやく確認できます。</span><span class="sxs-lookup"><span data-stu-id="6d6d3-140">Because these dates and times are so important, you might want to limit the returned data to information such as the certificate use, the certificate serial number, and the certificate expiration date; then you can quickly review all the certificates and when they will expire.</span></span> <span data-ttu-id="6d6d3-141">その情報のみを返すには、次のようなオプションを使用してコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="6d6d3-141">To return just that information, use the command together with the options as shown:</span></span>

`Get-CsCertificate | Select-Object Use, SerialNumber, NotAfter | Sort-Object NotAfter`

<span data-ttu-id="6d6d3-142">このコマンドは、証明書が有効期限の順に並べ替えられた状態で、次のようなデータを返します。</span><span class="sxs-lookup"><span data-stu-id="6d6d3-142">That command returns data similar to the following, with the certificates sorted in order of their expiration date:</span></span>

<span data-ttu-id="6d6d3-143">シリアルの使用</span><span class="sxs-lookup"><span data-stu-id="6d6d3-143">Use SerialNumber NotAfter</span></span>

<span data-ttu-id="6d6d3-144">\--- ------------ --------</span><span class="sxs-lookup"><span data-stu-id="6d6d3-144">\--- ------------ --------</span></span>

<span data-ttu-id="6d6d3-145">Default 611BB01200000000000C 12/28/2015 3:35:41 PM</span><span class="sxs-lookup"><span data-stu-id="6d6d3-145">Default 611BB01200000000000C 12/28/2015 3:35:41 PM</span></span>

<span data-ttu-id="6d6d3-146">Webサービス Interal 32980AA20BBB20000191 02/15/2016 2:16:12 PM</span><span class="sxs-lookup"><span data-stu-id="6d6d3-146">WebServicesInteral 32980AA20BBB20000191 02/15/2016 2:16:12 PM</span></span>

<span data-ttu-id="6d6d3-147">WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM</span><span class="sxs-lookup"><span data-stu-id="6d6d3-147">WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM</span></span>

<span data-ttu-id="6d6d3-148">証明書に問題がある場合は、証明書に対して構成された代替のベンダーを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d6d3-148">If you have certificate problems, you might want to review the AlternativeNames configured for a certificate.</span></span> <span data-ttu-id="6d6d3-149">一見すると、問題があるように見えます。</span><span class="sxs-lookup"><span data-stu-id="6d6d3-149">At first glance, that seems to be a problem.</span></span> <span data-ttu-id="6d6d3-150">既定では、コンソールウィンドウのサイズによっては、Get-CsCertificate ですべての名前を表示できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="6d6d3-150">By default, and depending on the size of your console window, Get-CsCertificate might not be able to display all the names:</span></span>

<span data-ttu-id="6d6d3-151">代替の [ベンダー]: {sip.fabrikam.com, LYNC.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="6d6d3-151">AlternativeNames : {sip.fabrikam.com, LYNC.fabrikam.com,</span></span>

<span data-ttu-id="6d6d3-152">meet.fabrikam.com, fabrika...}</span><span class="sxs-lookup"><span data-stu-id="6d6d3-152">meet.fabrikam.com, admin.fabrika...}</span></span>

<span data-ttu-id="6d6d3-153">証明書に割り当てられているすべての代替名を表示するには、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="6d6d3-153">To see all the alternative names assigned to a certificate use a command similar to this one:</span></span>

`Get-CsCertificate | Where-Object {$_.SerialNumber -eq "611BB01200000000000C"} | Select-Object -ExpandProperty AlternativeNames`

<span data-ttu-id="6d6d3-154">これにより、証明書のすべての代替名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6d6d3-154">That should show you all of the alternative names on the certificate:</span></span>

<span data-ttu-id="6d6d3-155">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="6d6d3-155">sip.fabrikam.com</span></span>

<span data-ttu-id="6d6d3-156">LYNC.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="6d6d3-156">LYNC.fabrikam.com</span></span>

<span data-ttu-id="6d6d3-157">meet.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="6d6d3-157">meet.fabrikam.com</span></span>

<span data-ttu-id="6d6d3-158">admin.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="6d6d3-158">admin.fabrikam.com</span></span>

<span data-ttu-id="6d6d3-159">LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="6d6d3-159">LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="6d6d3-160">Dialin.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="6d6d3-160">Dialin.fabrikam.com</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6d6d3-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="6d6d3-161">See Also</span></span>


[<span data-ttu-id="6d6d3-162">-CsCertificate の取得</span><span class="sxs-lookup"><span data-stu-id="6d6d3-162">Get-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

