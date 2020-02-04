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
ms.openlocfilehash: 48399ed2a6eba53707218295adcd1cbd11a5e32c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-or-configure-authentication-and-certification-on-iis-virtual-directories-in-lync-server-2013"></a><span data-ttu-id="d4579-102">Lync Server 2013 で IIS 仮想ディレクトリの認証と証明書を検証または構成する</span><span class="sxs-lookup"><span data-stu-id="d4579-102">Verify or configure authentication and certification on IIS virtual directories in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4579-103">_**最終更新日:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="d4579-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="d4579-104">インターネットインフォメーションサービス (IIS) 仮想ディレクトリで証明書を構成するか、証明書が正しく構成されていることを確認するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="d4579-104">Use the following procedure to configure the certificate on your Internet Information Services (IIS) virtual directories or verify that the certificate is configured correctly.</span></span> <span data-ttu-id="d4579-105">内部の Lync Server プールで IIS を実行している各サーバーと、オプションのディレクターまたはディレクタープールサーバーで、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d4579-105">Perform the following procedure on each server running IIS in your internal Lync Server pool and the optional Director.or Director pool servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d4579-106">次の手順では、IIS のすべての用途の Lync Server、内部 Web サイト、外部 Web サイトに使用される証明書を組み合わせて要求する手順を定義します。</span><span class="sxs-lookup"><span data-stu-id="d4579-106">The following procedure defines a procedure to request a combined certificate that is used for all purposes Lync Server, Internal Web Site and External Web Site in IIS.</span></span> <span data-ttu-id="d4579-107">Lync Server 2010 は、証明書の要求、インポート&nbsp;、および割り当てを管理するための、一連の Lync Server Management Shell Windows PowerShell コマンドレットを導入しました。</span><span class="sxs-lookup"><span data-stu-id="d4579-107">Lync Server 2010 introduced a set of Lync Server Management Shell&nbsp;Windows PowerShell cmdlets for the express purpose of managing certificate request, import, and assignment.</span></span> <span data-ttu-id="d4579-108">この手順では、要求を処理できる内部で展開された証明機関 (CA) があることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="d4579-108">The procedure assumes that there is an internally deployed certification authority (CA) that can process the request.</span></span> <span data-ttu-id="d4579-109">Lync Server の目的でパブリック証明書を使う場合、または CA でオフライン要求が必要な場合は、このトピックの「出力パラメーターについての詳細な構文」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4579-109">If you use public certificates for your Lync Server purposes, or your CA requires an offline request, see the detailed syntax in this topic for information on the –Output parameter.</span></span> <span data-ttu-id="d4579-110"><A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">要求-CsCertificate</A></span><span class="sxs-lookup"><span data-stu-id="d4579-110"><A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">Request-CsCertificate</A></span></span>



</div>

<div>

## <a name="to-configure-authentication-and-certificates-on-iis-virtual-directories"></a><span data-ttu-id="d4579-111">IIS 仮想ディレクトリで認証と証明書を構成するには</span><span class="sxs-lookup"><span data-stu-id="d4579-111">To configure authentication and certificates on IIS virtual directories</span></span>

1.  <span data-ttu-id="d4579-112">次の手順を完了するには、web サービスがインストールされていて、ローカル管理者であるコンピューター (フロントエンドサーバーまたはディレクター) にログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4579-112">To successfully complete the following, you must be logged on to the computer (Front End Server or Director) where the web services are installed and be a local administrator.</span></span> <span data-ttu-id="d4579-113">証明機関が組織の証明機関である場合は、証明機関に対する**読み取り**と**登録**のアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4579-113">You must have the **read** and **enroll** permissions on the certification authority that you will be requesting certificates from, if the certification authority is your organization’s certification authority.</span></span> <span data-ttu-id="d4579-114">オフライン証明書の要求を構成して送信する場合は、証明機関に対するアクセス許可は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="d4579-114">You do not need permissions to the certification authority if you will configure and send an offline certificate request.</span></span>

2.  <span data-ttu-id="d4579-115">[**スタート**] をクリックし、[**すべてのプログラム**]、[**管理ツール**]、[**インターネットインフォメーションサービス (IIS) マネージャー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4579-115">Click **Start**, select **All Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

3.  <span data-ttu-id="d4579-116">**インターネットインフォメーションサービス (IIS) マネージャー**で、[ **ServerName**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="d4579-116">In **Internet Information Services (IIS) Manager**, select **ServerName**.</span></span> <span data-ttu-id="d4579-117">**機能ビュー**で、[**サーバー証明書**] を選択し、右クリックして [**機能を開く**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d4579-117">In **Features View**, select **Server Certificates**, right-click and select **Open Feature**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="d4579-118">[サーバー証明書] 機能ビューで、サーバーに割り当てられている証明書がある場合は、ここに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d4579-118">In the Server Certificates Feature View, if there are certificates assigned to the server, they will appear here.</span></span> <span data-ttu-id="d4579-119">IIS で外部 Web サイトの要件を満たす証明書がある場合は、その証明書を再利用することができます。</span><span class="sxs-lookup"><span data-stu-id="d4579-119">If there is a certificate that matches the requirements for the External Web Site in IIS, you can re-use that certificate.</span></span> <span data-ttu-id="d4579-120">証明書を表示するには、証明書を右クリックし、[<STRONG>表示.</STRONG> ..] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d4579-120">To view a certificate, right-click the certificate and select <STRONG>View…</STRONG></span></span>

    
    </div>

4.  <span data-ttu-id="d4579-121">証明書を要求するフロントエンドサーバーまたはディレクターで、[**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4579-121">On the Front End Server or Director that you are requesting the certificate for, click **Start**, select **All Programs**, select **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

5.  <span data-ttu-id="d4579-122">Lync Server 管理シェルで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d4579-122">In the Lync Server Management Shell, type the following:</span></span>
    
        Get-CsCertificate
    
    <span data-ttu-id="d4579-123">出力は、コンピューターの個人証明書ストアの現在のサーバー上にある証明書の一覧です。</span><span class="sxs-lookup"><span data-stu-id="d4579-123">The output is a list of the certificates that are currently on the server in the Computer Personal certificate store.</span></span> <span data-ttu-id="d4579-124">結合された証明書 (つまり、既定の web サービスの内部と web サービスの外部が同じ証明書を使用している場合) では、Use プロパティに Default、WebWebServicesExternal Internal、およびが設定されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d4579-124">Note that in the combined certificate (that is, where the default, web services internal and web services external are using the same certificate) you will see that the Use property will be populated with Default, WebServicesInternal and WebServicesExternal.</span></span> <span data-ttu-id="d4579-125">また、Thumbprint プロパティは、それぞれの使用の種類に対して同じになります。</span><span class="sxs-lookup"><span data-stu-id="d4579-125">Also, the Thumbprint property will be the same for each of the Use types.</span></span> <span data-ttu-id="d4579-126">次の例では、CsCertificate の出力例を示します。</span><span class="sxs-lookup"><span data-stu-id="d4579-126">An example output of Get-CsCertificate is shown in this example:</span></span>
    
    <span data-ttu-id="d4579-127">![現在の証明書の状態での CsCertificate 情報の取得](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "現在の証明書の状態での CsCertificate 情報の取得")</span><span class="sxs-lookup"><span data-stu-id="d4579-127">![Get-CsCertificate info on current scert status](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "Get-CsCertificate info on current scert status")</span></span>

6.  <span data-ttu-id="d4579-128">Lync Server 管理シェルで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d4579-128">In the Lync Server Management Shell, type the following:</span></span>
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA <CA Server FQDN\CA Instance> -Verbose -DomainName "<FQDN entries to be added to the Subject Alternative Name>"
    
    <span data-ttu-id="d4579-129">次の例のように、完全なコマンドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d4579-129">Where the full command would appear like following example:</span></span>
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA dc01.contoso.net\contoso-DC01-CA -Verbose -DomainName "LyncdiscoverInternal.Contoso.com,Lyncdiscover.Contoso.com"
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="d4579-130">既定では、要求-CsCertificate は、サブジェクト名にサーバーまたはプールの名前を付けて、サブジェクトの代替名にサーバーの FQDN、プールの FQDN、URL の Fqdn、および内部と外部の web サービスの Fqdn を入力します。</span><span class="sxs-lookup"><span data-stu-id="d4579-130">By default, Request-CsCertificate will populate the subject name with the server or pool name and populate entries in the subject alternative name with the server FQDN, pool FQDN, Simple URL FQDNs, and internal and external web services FQDNs.</span></span> <span data-ttu-id="d4579-131">これは、展開でトポロジドキュメントを参照することで行われます。</span><span class="sxs-lookup"><span data-stu-id="d4579-131">It does this by referencing to the topology document in your deployment.</span></span> <span data-ttu-id="d4579-132">存在しない値があり、– Verbose パラメーターを指定している場合は、別の名前の計算値と実際の値が異なっていることが通知されますが、どの値が失われているかは通知されません。</span><span class="sxs-lookup"><span data-stu-id="d4579-132">If there is a missing value and you have specified the –Verbose parameter, you will be notified that the computed and actual values for alternative names are different, but it does not inform you which values are missing.</span></span> <span data-ttu-id="d4579-133">これにより、コマンドレットで参照される計算値全体が提供されます。</span><span class="sxs-lookup"><span data-stu-id="d4579-133">It does supply you with the entire computed value that the cmdlet references.</span></span> <span data-ttu-id="d4579-134">出力で計算された代替名の文字列を使用して、すべての値を含む新しい証明書を再要求します。</span><span class="sxs-lookup"><span data-stu-id="d4579-134">Use the computed alternative names string in the output to re-request a new certificate that will include all values.</span></span>

    
    </div>
    
    <span data-ttu-id="d4579-135">![要求-CsCertifica を使用した証明書要求の出力](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "要求-CsCertifica を使用した証明書要求の出力")</span><span class="sxs-lookup"><span data-stu-id="d4579-135">![Output from cert request using Request-CsCertifica](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "Output from cert request using Request-CsCertifica")</span></span>

7.  <span data-ttu-id="d4579-136">Lync Server 管理シェルで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d4579-136">In the Lync Server Management Shell, type the following:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Thumbprint of certificate to use>
    
    <span data-ttu-id="d4579-137">次の例のように、完全なコマンドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d4579-137">Where the full command would appear like following example:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint 466D9BB0E8B928B65AF38FA2D9F41E1B301ECE9D
    
    <span data-ttu-id="d4579-138">Set-CsCertificate コマンドレットの出力では、(証明書の拇印によって識別される) 同じ証明書が、Default、WebServicesExternal、Webservices の内部使用法として割り当てられていることが示されます。</span><span class="sxs-lookup"><span data-stu-id="d4579-138">The output from the Set-CsCertificate cmdlet will show that the same certificate (identified by the thumbprint of the certificate) is assigned for the Default, WebServicesExternal and WebServicesInternal usage.</span></span>
    
    <span data-ttu-id="d4579-139">![IIS Web Ext での Set-CsCertificate からの出力](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "IIS Web Ext での Set-CsCertificate からの出力")</span><span class="sxs-lookup"><span data-stu-id="d4579-139">![Output from Set-CsCertificate on IIS WebExt](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "Output from Set-CsCertificate on IIS WebExt")</span></span>

</div>

<div>

## <a name="to-verify-or-configure-authentication-and-certificates-on-iis-virtual-directories"></a><span data-ttu-id="d4579-140">IIS 仮想ディレクトリで認証と証明書を確認または構成するには</span><span class="sxs-lookup"><span data-stu-id="d4579-140">To verify or configure authentication and certificates on IIS virtual directories</span></span>

1.  <span data-ttu-id="d4579-141">[**スタート**] をクリックし、[**すべてのプログラム**]、[**管理ツール**]、[**インターネットインフォメーションサービス (IIS) マネージャー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4579-141">Click **Start**, select **All Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

2.  <span data-ttu-id="d4579-142">**インターネットインフォメーションサービス (IIS) マネージャー**で、[ **ServerName**] を展開し、[**サイト**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="d4579-142">In **Internet Information Services (IIS) Manager**, expand **ServerName**, and then expand **Sites**.</span></span>

3.  <span data-ttu-id="d4579-143">[ **Lync Server 外部 Web サイト**] を右クリックし、[**バインドの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4579-143">Right-click **Lync Server External Web Site**, and then click **Edit Bindings**</span></span>

4.  <span data-ttu-id="d4579-144">Https がポート4443に関連付けられていることを確認し、[ **https**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4579-144">Verify that https is associated with port 4443, and then click **https**.</span></span>

5.  <span data-ttu-id="d4579-145">[HTTPS] エントリを選び、[**編集**] をクリックして、Lync Server WebServicesExternalCertificate がこのプロトコルにバインドされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d4579-145">Select the HTTPS entry, click **Edit**, and then verify that Lync Server WebServicesExternalCertificate is bound to this protocol.</span></span> <span data-ttu-id="d4579-146">要求された証明書が HTTPS バインドと適切に関連付けられていることを確認するために、Set-CsCertificate コマンドレットの拇印を比較します。</span><span class="sxs-lookup"><span data-stu-id="d4579-146">Compare the thumbprint from the Set-CsCertificate cmdlet to ensure that the expected certificate is correctly associated with the HTTPS binding.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d4579-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="d4579-147">See Also</span></span>


[<span data-ttu-id="d4579-148">Get-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="d4579-148">Get-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
[<span data-ttu-id="d4579-149">設定-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="d4579-149">Set-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

