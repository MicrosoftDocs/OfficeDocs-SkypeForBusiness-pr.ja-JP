---
title: 'Lync Server 2013: IIS 仮想ディレクトリの認証と証明書を検証または構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify or configure authentication and certification on IIS virtual directories
ms:assetid: 3ca90be0-1d64-447c-807a-3a2ee3bf625e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429702(v=OCS.15)
ms:contentKeyID: 48183883
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca51a3c597be40c679a7b131f87775876a63811d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211753"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-or-configure-authentication-and-certification-on-iis-virtual-directories-in-lync-server-2013"></a><span data-ttu-id="c2e81-102">Lync Server 2013 で IIS 仮想ディレクトリの認証と証明書を検証または構成する</span><span class="sxs-lookup"><span data-stu-id="c2e81-102">Verify or configure authentication and certification on IIS virtual directories in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2e81-103">_**トピックの最終更新日:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="c2e81-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="c2e81-104">次の手順を使用して、インターネットインフォメーションサービス (IIS) 仮想ディレクトリの証明書を構成するか、証明書が正しく構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c2e81-104">Use the following procedure to configure the certificate on your Internet Information Services (IIS) virtual directories or verify that the certificate is configured correctly.</span></span> <span data-ttu-id="c2e81-105">内部の Lync Server プールとオプションのディレクターまたはディレクタープールサーバーで、IIS を実行している各サーバーで以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c2e81-105">Perform the following procedure on each server running IIS in your internal Lync Server pool and the optional Director.or Director pool servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c2e81-106">次の手順では、IIS のすべての目的の Lync Server、内部 Web サイト、および外部 Web サイトに使用される証明書の組み合わせを要求する手順を定義します。</span><span class="sxs-lookup"><span data-stu-id="c2e81-106">The following procedure defines a procedure to request a combined certificate that is used for all purposes Lync Server, Internal Web Site and External Web Site in IIS.</span></span> <span data-ttu-id="c2e81-107">Lync Server 2010 証明書の要求、インポート、および&nbsp;割り当てを管理するための、一連の Lync Server 管理シェル Windows PowerShell コマンドレットが導入されました。</span><span class="sxs-lookup"><span data-stu-id="c2e81-107">Lync Server 2010 introduced a set of Lync Server Management Shell&nbsp;Windows PowerShell cmdlets for the express purpose of managing certificate request, import, and assignment.</span></span> <span data-ttu-id="c2e81-108">手順は、要求を処理できる、内部展開された証明機関 (CA) が存在することを前提としています。</span><span class="sxs-lookup"><span data-stu-id="c2e81-108">The procedure assumes that there is an internally deployed certification authority (CA) that can process the request.</span></span> <span data-ttu-id="c2e81-109">Lync Server の目的でパブリック証明書を使用する場合、または CA がオフライン要求を必要とする場合は、このトピックの詳細な構文を参照して、-Output パラメーターに関する情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2e81-109">If you use public certificates for your Lync Server purposes, or your CA requires an offline request, see the detailed syntax in this topic for information on the –Output parameter.</span></span> <span data-ttu-id="c2e81-110"><A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">要求-CsCertificate</A></span><span class="sxs-lookup"><span data-stu-id="c2e81-110"><A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">Request-CsCertificate</A></span></span>



</div>

<div>

## <a name="to-configure-authentication-and-certificates-on-iis-virtual-directories"></a><span data-ttu-id="c2e81-111">IIS 仮想ディレクトリの認証と証明書を構成するには</span><span class="sxs-lookup"><span data-stu-id="c2e81-111">To configure authentication and certificates on IIS virtual directories</span></span>

1.  <span data-ttu-id="c2e81-112">次の手順を正常に完了するには、web サービスがインストールされていて、ローカル管理者であるコンピューター (フロントエンドサーバーまたはディレクター) にログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2e81-112">To successfully complete the following, you must be logged on to the computer (Front End Server or Director) where the web services are installed and be a local administrator.</span></span> <span data-ttu-id="c2e81-113">証明書の要求先の証明機関が組織の証明機関の場合は、その証明機関に対して**読み取り**と**登録**のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="c2e81-113">You must have the **read** and **enroll** permissions on the certification authority that you will be requesting certificates from, if the certification authority is your organization’s certification authority.</span></span> <span data-ttu-id="c2e81-114">オフライン証明書要求を構成および送信する場合は、証明機関に対するアクセス許可は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="c2e81-114">You do not need permissions to the certification authority if you will configure and send an offline certificate request.</span></span>

2.  <span data-ttu-id="c2e81-115">[**スタート**] ボタンをクリックし、[**すべてのプログラム**] を選択します。次に、[**管理ツール**] を選択し、[**インターネット インフォメーション サービス (IIS) マネージャー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c2e81-115">Click **Start**, select **All Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

3.  <span data-ttu-id="c2e81-p104">[**インターネット インフォメーション サービス (IIS) マネージャー**] で、[**<サーバー名>**] を選択します。[**機能ビュー**] で、[**サーバー証明書**] を選択し、[**機能を開く**] を右クリックして選択します。</span><span class="sxs-lookup"><span data-stu-id="c2e81-p104">In **Internet Information Services (IIS) Manager**, select **ServerName**. In **Features View**, select **Server Certificates**, right-click and select **Open Feature**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="c2e81-p105">サーバーに割り当てられている証明書がある場合は、サーバー証明書の機能ビューにそれが表示されます。IIS 内の外部 Web サイトの要件に一致する証明書がある場合は、その証明書を再利用できます。証明書を表示するには、証明書を右クリックし、[<STRONG>表示</STRONG>] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2e81-p105">In the Server Certificates Feature View, if there are certificates assigned to the server, they will appear here. If there is a certificate that matches the requirements for the External Web Site in IIS, you can re-use that certificate. To view a certificate, right-click the certificate and select <STRONG>View…</STRONG></span></span>

    
    </div>

4.  <span data-ttu-id="c2e81-121">証明書を要求しているフロントエンドサーバーまたはディレクターで、[**スタート**] をクリックし、[**すべてのプログラム**] を選択し、[ **Microsoft lync server 2013**] を選択して、[ **lync server 管理シェル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c2e81-121">On the Front End Server or Director that you are requesting the certificate for, click **Start**, select **All Programs**, select **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

5.  <span data-ttu-id="c2e81-122">Lync Server 管理シェルで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="c2e81-122">In the Lync Server Management Shell, type the following:</span></span>
    
        Get-CsCertificate
    
    <span data-ttu-id="c2e81-p106">出力は、コンピューターの個人証明書ストア内のサーバーに現在ある、証明書の一覧です。共同証明書 (つまり、既定、内部 Web サービス、および外部 Web サービスが同じ証明書を使用している) では、Use プロパティに Default、WebServicesInternal、および WebServicesExternal が設定されることに注意してください。また、Thumbprint プロパティも、各 Use タイプで同じになります。Get-CsCertificate の出力例を、次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="c2e81-p106">The output is a list of the certificates that are currently on the server in the Computer Personal certificate store. Note that in the combined certificate (that is, where the default, web services internal and web services external are using the same certificate) you will see that the Use property will be populated with Default, WebServicesInternal and WebServicesExternal. Also, the Thumbprint property will be the same for each of the Use types. An example output of Get-CsCertificate is shown in this example:</span></span>
    
    <span data-ttu-id="c2e81-127">![現在の scert の状態での [CsCertificate info] を取得する](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "現在の scert の状態での [CsCertificate info] を取得する")</span><span class="sxs-lookup"><span data-stu-id="c2e81-127">![Get-CsCertificate info on current scert status](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "Get-CsCertificate info on current scert status")</span></span>

6.  <span data-ttu-id="c2e81-128">Lync Server 管理シェルで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="c2e81-128">In the Lync Server Management Shell, type the following:</span></span>
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA <CA Server FQDN\CA Instance> -Verbose -DomainName "<FQDN entries to be added to the Subject Alternative Name>"
    
    <span data-ttu-id="c2e81-129">コマンド全体は次の例のようになります。</span><span class="sxs-lookup"><span data-stu-id="c2e81-129">Where the full command would appear like following example:</span></span>
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA dc01.contoso.net\contoso-DC01-CA -Verbose -DomainName "LyncdiscoverInternal.Contoso.com,Lyncdiscover.Contoso.com"
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="c2e81-p107">既定では、Request-CsCertificate によって、サブジェクト名にはサーバー名またはプール名が設定され、サブジェクトの別名内のエントリにはサーバーの FQDN、プールの FQDN、簡易 URL の FQDN、および内部 Web サービスと外部 Web サービスの FQDN が設定されます。これは、展開のトポロジ ドキュメントを参照することによって行われます。不足している値があり、–Verbose パラメーターが指定されている場合、別名の計算値と実際値が異なるというメッセージが表示されますが、どの値が不足しているかを示すメッセージは表示されません。コマンドレットが参照する計算値全体が提供されます。出力内の計算された別名文字列を使用して、すべての値を含む新しい証明書を再度要求します。</span><span class="sxs-lookup"><span data-stu-id="c2e81-p107">By default, Request-CsCertificate will populate the subject name with the server or pool name and populate entries in the subject alternative name with the server FQDN, pool FQDN, Simple URL FQDNs, and internal and external web services FQDNs. It does this by referencing to the topology document in your deployment. If there is a missing value and you have specified the –Verbose parameter, you will be notified that the computed and actual values for alternative names are different, but it does not inform you which values are missing. It does supply you with the entire computed value that the cmdlet references. Use the computed alternative names string in the output to re-request a new certificate that will include all values.</span></span>

    
    </div>
    
    <span data-ttu-id="c2e81-135">![要求を使用した証明書要求の出力 CsCertifica](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "要求を使用した証明書要求の出力 CsCertifica")</span><span class="sxs-lookup"><span data-stu-id="c2e81-135">![Output from cert request using Request-CsCertifica](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "Output from cert request using Request-CsCertifica")</span></span>

7.  <span data-ttu-id="c2e81-136">Lync Server 管理シェルで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="c2e81-136">In the Lync Server Management Shell, type the following:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Thumbprint of certificate to use>
    
    <span data-ttu-id="c2e81-137">コマンド全体は次の例のようになります。</span><span class="sxs-lookup"><span data-stu-id="c2e81-137">Where the full command would appear like following example:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint 466D9BB0E8B928B65AF38FA2D9F41E1B301ECE9D
    
    <span data-ttu-id="c2e81-138">Set-CsCertificate コマンドレットからの出力には、Default、WebServicesExternal、および WebServicesInternal の使用に対して同じ証明書 (証明書の拇印で識別) が割り当てられることが示されます。</span><span class="sxs-lookup"><span data-stu-id="c2e81-138">The output from the Set-CsCertificate cmdlet will show that the same certificate (identified by the thumbprint of the certificate) is assigned for the Default, WebServicesExternal and WebServicesInternal usage.</span></span>
    
    <span data-ttu-id="c2e81-139">![IIS WebExt での Set-CsCertificate からの出力](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "IIS WebExt での Set-CsCertificate からの出力")</span><span class="sxs-lookup"><span data-stu-id="c2e81-139">![Output from Set-CsCertificate on IIS WebExt](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "Output from Set-CsCertificate on IIS WebExt")</span></span>

</div>

<div>

## <a name="to-verify-or-configure-authentication-and-certificates-on-iis-virtual-directories"></a><span data-ttu-id="c2e81-140">IIS 仮想ディレクトリの認証と証明書を検証または構成するには</span><span class="sxs-lookup"><span data-stu-id="c2e81-140">To verify or configure authentication and certificates on IIS virtual directories</span></span>

1.  <span data-ttu-id="c2e81-141">[**スタート**] ボタンをクリックし、[**すべてのプログラム**] を選択します。次に、[**管理ツール**] を選択し、[**インターネット インフォメーション サービス (IIS) マネージャー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c2e81-141">Click **Start**, select **All Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

2.  <span data-ttu-id="c2e81-142">**インターネットインフォメーションサービス (IIS) マネージャー**で、 **ServerName**を展開し、[**サイト**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="c2e81-142">In **Internet Information Services (IIS) Manager**, expand **ServerName**, and then expand **Sites**.</span></span>

3.  <span data-ttu-id="c2e81-143">[**Lync Server の外部 Web サイト**] を右クリックし、[**バインドの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c2e81-143">Right-click **Lync Server External Web Site**, and then click **Edit Bindings**</span></span>

4.  <span data-ttu-id="c2e81-144">https がポート 4443 と関連付けられていることを確認し、[**https**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c2e81-144">Verify that https is associated with port 4443, and then click **https**.</span></span>

5.  <span data-ttu-id="c2e81-145">HTTPS エントリを選択し、[**編集**] をクリックして、Lync Server WebServicesExternalCertificate がこのプロトコルにバインドされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c2e81-145">Select the HTTPS entry, click **Edit**, and then verify that Lync Server WebServicesExternalCertificate is bound to this protocol.</span></span> <span data-ttu-id="c2e81-146">Set-CsCertificate コマンドレットからの拇印を比較して、予期される証明書が HTTPS バインドに適切に関連付けられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c2e81-146">Compare the thumbprint from the Set-CsCertificate cmdlet to ensure that the expected certificate is correctly associated with the HTTPS binding.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c2e81-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="c2e81-147">See Also</span></span>


[<span data-ttu-id="c2e81-148">-CsCertificate の取得</span><span class="sxs-lookup"><span data-stu-id="c2e81-148">Get-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
[<span data-ttu-id="c2e81-149">設定-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="c2e81-149">Set-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

