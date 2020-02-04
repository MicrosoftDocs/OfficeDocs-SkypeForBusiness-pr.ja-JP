---
title: 'Lync Server 2013: Lync Server 2013 サーバーの証明書を確認する'
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
ms.openlocfilehash: af0a80df18a4fc6e27200d1ac04476fcea798b9b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733997"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-lync-server-2013-server-certificates"></a><span data-ttu-id="fc534-102">Lync Server 2013 サーバー証明書を確認する</span><span class="sxs-lookup"><span data-stu-id="fc534-102">Check Lync Server 2013 server certificates</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc534-103">_**最終更新日:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="fc534-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fc534-104">確認のスケジュール</span><span class="sxs-lookup"><span data-stu-id="fc534-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="fc534-105">毎月</span><span class="sxs-lookup"><span data-stu-id="fc534-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc534-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="fc534-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="fc534-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fc534-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc534-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="fc534-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="fc534-109">Lync Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc534-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="fc534-110">Windows PowerShell のリモートインスタンスを使って実行する場合、ユーザーには、CsCertificate の取得コマンドレットを実行するためのアクセス許可が与えられた RBAC の役割を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc534-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Get-CsCertificate cmdlet.</span></span> <span data-ttu-id="fc534-111">このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fc534-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Get-CsCertificate&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="fc534-112">説明</span><span class="sxs-lookup"><span data-stu-id="fc534-112">Description</span></span>

<span data-ttu-id="fc534-113">CsCertificate コマンドレットを使用すると、Lync Server の各証明書に関する情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="fc534-113">The Get-CsCertificate cmdlet enables you to retrieve information about each of your Lync Server certificates.</span></span> <span data-ttu-id="fc534-114">これは特に重要です。証明書には有効期限があります。</span><span class="sxs-lookup"><span data-stu-id="fc534-114">That’s especially important because certificates have a built-in expiration date.</span></span> <span data-ttu-id="fc534-115">たとえば、プライベートに発行された証明書は通常、12か月後に期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="fc534-115">For example,, privately-issued certificates typically expire after 12 months.</span></span> <span data-ttu-id="fc534-116">いずれかの Lync Server 証明書の有効期限が切れている場合は、その証明書が更新または置き換えられるまで、付属の機能が失われます。</span><span class="sxs-lookup"><span data-stu-id="fc534-116">If any of your Lync Server certificates expire then you'll lose the accompanying functionality until that certificate is renewed or replaced.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="fc534-117">テストの実行</span><span class="sxs-lookup"><span data-stu-id="fc534-117">Running the test</span></span>

<span data-ttu-id="fc534-118">Lync Server の各証明書に関する情報を取得するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fc534-118">To return information about each of your Lync Server certificates just run the following command:</span></span>

`Get-CsCertificate`

<span data-ttu-id="fc534-119">または、有効期限日に基づいて、返送証明書情報をフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="fc534-119">Or, you can filter the return certificate information based on expiration date.</span></span> <span data-ttu-id="fc534-120">たとえば、次のコマンドは、返されるデータを有効期限が切れた証明書 (2014 年6月1日以降は使用できません) に制限します。</span><span class="sxs-lookup"><span data-stu-id="fc534-120">For example, this command limits the returned data to certificates that expire (cannot be used after) June 1, 2014:</span></span>

`Get-CsCertificate | Where-Object {$_.NotAfter -lt "6/1/2014"}`

<span data-ttu-id="fc534-121">詳細については、「CsCertificate を取得する」コマンドレットのヘルプドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc534-121">For more information, see the Help documentation for the Get-CsCertificate cmdlet.</span></span>

<span data-ttu-id="fc534-122">ここでは、テスト用の Csコマンドレットは存在しますが、管理者にとってはあまり役に立ちません。</span><span class="sxs-lookup"><span data-stu-id="fc534-122">Note that, although the Test-CsCertificateConfiguration cmdlet exists, it is not very useful to administrators.</span></span> <span data-ttu-id="fc534-123">(その代わりに、このコマンドレットは証明書ウィザードで主に使用されます)。このコマンドレットは動作しますが、次の出力例に示すように、返される情報は最小限の値になります。</span><span class="sxs-lookup"><span data-stu-id="fc534-123">(Instead, that cmdlet is primarily used by the Certificate wizard.) Although the cmdlet works, the information that it returns is of minimal value as shown in the following output example:</span></span>

<span data-ttu-id="fc534-124">拇印の使用</span><span class="sxs-lookup"><span data-stu-id="fc534-124">Thumbprint Use</span></span>

<span data-ttu-id="fc534-125">\---------- ---</span><span class="sxs-lookup"><span data-stu-id="fc534-125">\---------- ---</span></span>

<span data-ttu-id="fc534-126">A9D51A2911C74FABFF7F2A8A994B20857D399107 の既定値</span><span class="sxs-lookup"><span data-stu-id="fc534-126">A9D51A2911C74FABFF7F2A8A994B20857D399107 Default</span></span>

</div>

<div>

## <a name="reviewing-the-output"></a><span data-ttu-id="fc534-127">出力を確認する</span><span class="sxs-lookup"><span data-stu-id="fc534-127">Reviewing the output</span></span>

<span data-ttu-id="fc534-128">各 Lync Server 証明書について、次のような情報が返されます。</span><span class="sxs-lookup"><span data-stu-id="fc534-128">The Get-CsCertificate cmdlet returns information similar to the following for each of your Lync Server certificates:</span></span>

<span data-ttu-id="fc534-129">発行者: CN = FabrikamCA</span><span class="sxs-lookup"><span data-stu-id="fc534-129">Issuer : CN=FabrikamCA</span></span>

<span data-ttu-id="fc534-130">NotAfter: 12/28/2015 3:35:41 PM</span><span class="sxs-lookup"><span data-stu-id="fc534-130">NotAfter : 12/28/2015 3:35:41 PM</span></span>

<span data-ttu-id="fc534-131">NotBefore: 1/2/2014 12:49:37 PM</span><span class="sxs-lookup"><span data-stu-id="fc534-131">NotBefore : 1/2/2014 12:49:37 PM</span></span>

<span data-ttu-id="fc534-132">シリアル: 611BB01200000000000C</span><span class="sxs-lookup"><span data-stu-id="fc534-132">SerialNumber : 611BB01200000000000C</span></span>

<span data-ttu-id="fc534-133">Subject: CN = LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="fc534-133">Subject : CN=LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="fc534-134">代替: {sip.fabrikam.com、LYNC-SE.fabrikam.com、</span><span class="sxs-lookup"><span data-stu-id="fc534-134">AlternativeNames : {sip.fabrikam.com, LYNC-SE.fabrikam.com,</span></span>

<span data-ttu-id="fc534-135">meet.fabrikam.com、admin.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="fc534-135">meet.fabrikam.com, admin.fabrikam.com...}</span></span>

<span data-ttu-id="fc534-136">拇印: A9D51A2911C74FABFF7F2A8A994B20857D399107</span><span class="sxs-lookup"><span data-stu-id="fc534-136">Thumbprint : A9D51A2911C74FABFF7F2A8A994B20857D399107</span></span>

<span data-ttu-id="fc534-137">使用: 既定</span><span class="sxs-lookup"><span data-stu-id="fc534-137">Use : Default</span></span>

<span data-ttu-id="fc534-138">ルールとして、Lync Server の証明書に関連する主な問題には、証明書が適用される時期 (NotBefore)、または期限切れになったとき (NotAfter) など、日付と時刻が含まれます。</span><span class="sxs-lookup"><span data-stu-id="fc534-138">As a rule, the top issues involving Lync Server certificates involve dates and times, such as when certificates take effect (NotBefore) or when they expire (NotAfter).</span></span> <span data-ttu-id="fc534-139">このような日付と時刻は重要であるため、証明書の使用、証明書のシリアル番号、証明書の有効期限などの情報に、返されるデータを制限することができます。これにより、すべての証明書を簡単に確認して、期限切れにすることができます。</span><span class="sxs-lookup"><span data-stu-id="fc534-139">Because these dates and times are so important, you might want to limit the returned data to information such as the certificate use, the certificate serial number, and the certificate expiration date; then you can quickly review all the certificates and when they will expire.</span></span> <span data-ttu-id="fc534-140">その情報だけを返すには、次のようなオプションと共にコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="fc534-140">To return just that information, use the command together with the options as shown:</span></span>

`Get-CsCertificate | Select-Object Use, SerialNumber, NotAfter | Sort-Object NotAfter`

<span data-ttu-id="fc534-141">このコマンドを実行すると、次のようなデータが返されます。証明書は有効期限の順に並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="fc534-141">That command returns data similar to the following, with the certificates sorted in order of their expiration date:</span></span>

<span data-ttu-id="fc534-142">以降のシリアルで使用</span><span class="sxs-lookup"><span data-stu-id="fc534-142">Use SerialNumber NotAfter</span></span>

<span data-ttu-id="fc534-143">\--- ------------ --------</span><span class="sxs-lookup"><span data-stu-id="fc534-143">\--- ------------ --------</span></span>

<span data-ttu-id="fc534-144">既定の 611BB01200000000000C 12/28/2015 3:35:41 PM</span><span class="sxs-lookup"><span data-stu-id="fc534-144">Default 611BB01200000000000C 12/28/2015 3:35:41 PM</span></span>

<span data-ttu-id="fc534-145">Webservices Interal 32980AA20BBB20000191 02/15/2016 2:16:12 PM</span><span class="sxs-lookup"><span data-stu-id="fc534-145">WebServicesInteral 32980AA20BBB20000191 02/15/2016 2:16:12 PM</span></span>

<span data-ttu-id="fc534-146">WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM</span><span class="sxs-lookup"><span data-stu-id="fc534-146">WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM</span></span>

<span data-ttu-id="fc534-147">証明書の問題がある場合は、証明書に対して構成されている代替の内容を確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fc534-147">If you have certificate problems, you might want to review the AlternativeNames configured for a certificate.</span></span> <span data-ttu-id="fc534-148">一見したところ、問題に思えるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="fc534-148">At first glance, that seems to be a problem.</span></span> <span data-ttu-id="fc534-149">既定では、コンソールウィンドウのサイズに応じて、ユーザーがすべての名前を表示できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="fc534-149">By default, and depending on the size of your console window, Get-CsCertificate might not be able to display all the names:</span></span>

<span data-ttu-id="fc534-150">代替: {sip.fabrikam.com、LYNC.fabrikam.com、</span><span class="sxs-lookup"><span data-stu-id="fc534-150">AlternativeNames : {sip.fabrikam.com, LYNC.fabrikam.com,</span></span>

<span data-ttu-id="fc534-151">meet.fabrikam.com の場合は、fabrika</span><span class="sxs-lookup"><span data-stu-id="fc534-151">meet.fabrikam.com, admin.fabrika...}</span></span>

<span data-ttu-id="fc534-152">証明書に割り当てられている代替名をすべて表示するには、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="fc534-152">To see all the alternative names assigned to a certificate use a command similar to this one:</span></span>

`Get-CsCertificate | Where-Object {$_.SerialNumber -eq "611BB01200000000000C"} | Select-Object -ExpandProperty AlternativeNames`

<span data-ttu-id="fc534-153">これにより、証明書のすべての代替名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fc534-153">That should show you all of the alternative names on the certificate:</span></span>

<span data-ttu-id="fc534-154">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="fc534-154">sip.fabrikam.com</span></span>

<span data-ttu-id="fc534-155">LYNC.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="fc534-155">LYNC.fabrikam.com</span></span>

<span data-ttu-id="fc534-156">meet.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="fc534-156">meet.fabrikam.com</span></span>

<span data-ttu-id="fc534-157">admin.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="fc534-157">admin.fabrikam.com</span></span>

<span data-ttu-id="fc534-158">LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="fc534-158">LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="fc534-159">Dialin.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="fc534-159">Dialin.fabrikam.com</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fc534-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="fc534-160">See Also</span></span>


[<span data-ttu-id="fc534-161">Get-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="fc534-161">Get-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

