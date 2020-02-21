---
title: Lync Server 2013 へのサーバー間認証証明書の割り当て
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013
ms:assetid: c7413954-2504-47f4-a073-44548aff1c0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205253(v=OCS.15)
ms:contentKeyID: 48185367
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 952f4c1b14ce7260d4b320ea7feacddb9a85a8f0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203303"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assigning-a-server-to-server-authentication-certificate-to-microsoft-lync-server-2013"></a><span data-ttu-id="ff016-102">サーバー間認証証明書を Microsoft Lync Server 2013 に割り当てる</span><span class="sxs-lookup"><span data-stu-id="ff016-102">Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff016-103">_**トピックの最終更新日:** 2013-10-24_</span><span class="sxs-lookup"><span data-stu-id="ff016-103">_**Topic Last Modified:** 2013-10-24_</span></span>

<span data-ttu-id="ff016-104">サーバー間認証証明書が Microsoft Lync Server 2013 に既に割り当てられているかどうかを確認するには、Lync Server 2013 管理シェルから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ff016-104">To determine whether or not a server-to-server authentication certificate has already been assigned to Microsoft Lync Server 2013, run the following command from the Lync Server 2013 Management Shell:</span></span>

    Get-CsCertificate -Type OAuthTokenIssuer

<span data-ttu-id="ff016-105">証明書情報が返されない場合は、サーバー間認証を使用する前に、トークン発行元証明書を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff016-105">If no certificate information is returned you must assign a token issuer certificate before you can use server-to-server authentication.</span></span> <span data-ttu-id="ff016-106">一般的なルールとして、すべての Lync Server 2013 証明書を OAuthTokenIssuer 証明書として使用できます。たとえば、Lync Server 2013 の既定の証明書を OAuthTokenIssuer 証明書として使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="ff016-106">As a general rule, any Lync Server 2013 certificate can be used as your OAuthTokenIssuer certificate; for example, your Lync Server 2013 default certificate can also be used as the OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="ff016-107">(OAUthTokenIssuer 証明書は、[件名] フィールドに SIP ドメインの名前が含まれる Web サーバー証明書でもかまいません)。サーバー間認証に使用される証明書の主な2つの要件は次のとおりです。 1) すべてのフロントエンドサーバー上の OAuthTokenIssuer 証明書と同じ証明書を構成する必要があります。そして 2) 証明書は、少なくとも2048ビットでなければなりません。</span><span class="sxs-lookup"><span data-stu-id="ff016-107">(The OAUthTokenIssuer certificate can also be any Web server certificate that includes the name of your SIP domain in the Subject field.) The primary two requirements for the certificate used for server-to-server authentication are these: 1)the same certificate must be configured as the OAuthTokenIssuer certificate on all of your Front End Servers; and, 2) the certificate must be at least 2048 bits.</span></span>

<span data-ttu-id="ff016-p102">サーバー対サーバーの認証に使用できる証明書がない場合は、新しい証明書をインポートして、その証明書をサーバー対サーバーの認証に使用します。新しい証明書を要求して取得した後で、フロントエンド サーバーのどれかにログオンし、次のような Windows PowerShell コマンドを使用して証明書をインポートして割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ff016-p102">If you do not have a certificate that can be used for server-to-server authentication you can obtain a new certificate, import the new certificate, and then use that certificate for server-to-server authentication. After you have requested and obtained the new certificate you can then log on to any one of your Front End Servers and use a Windows PowerShell command similar to this one to import and assign that certificate:</span></span>

    Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"

<span data-ttu-id="ff016-p103">前述のコマンドの Path パラメーターは、証明書ファイルへの完全なパスを表し、Password パラメーターは、その証明書に割り当てられたパスワードを表します。この手順は、1 回だけ実行します。Lync Server のレプリケーション サービスが自動的に作成する一連のスケジュールされたタスクによって、証明書が復号化されてすべてのフロントエンド サーバーに展開されます。</span><span class="sxs-lookup"><span data-stu-id="ff016-p103">In the preceding command the Path parameter represents the full path to the certificate file, and the Password parameter represents the password that was assigned to the certificate. This procedure should be run just one time: Lync Server's replication service will then automatically create a set of scheduled tasks that will decrypt and deploy the certificate to all your Front End Servers.</span></span>

<span data-ttu-id="ff016-p104">または、既存の証明書をサーバー対サーバーの認証の証明書として使用することもできます (前述したように、既定の証明書をサーバー対サーバーの認証の証明書として使用できます)。次の 2 つの Windows PowerShell コマンドを実行すると、既定の証明書の Thumbprint プロパティの値が取得され、その値を使用して、既定の証明書がサーバー対サーバーの認証の証明書として設定されます。</span><span class="sxs-lookup"><span data-stu-id="ff016-p104">Alternatively, you can use an existing certificate as your server-to-server authentication certificate. (As noted, the default certificate can be used as the server-to-server authentication certificate.) The following pair of Windows PowerShell commands retrieve the value of the default certificate's Thumbprint property, then use that value to make the default certificate the server-to-server authentication certificate:</span></span>

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x

<span data-ttu-id="ff016-p105">1 つ目のコマンドでは、取得された証明書がグローバルなサーバー対サーバーの認証の証明書として機能するように構成されます。つまり、その証明書はすべてのフロントエンド サーバーにレプリケートされ、使用されます。この場合も、このコマンドはいずれかのフロントエンド サーバーで 1 回だけ実行します。すべてのフロントエンド サーバーで同じ証明書を使用する必要がありますが、各フロントエンド サーバーで OAuthTokenIssuer 証明書を構成する必要はありません。そうではなく、証明書を 1 回構成し、Lync Server のレプリケーション サーバーに各サーバーに対して証明書をコピーさせます。</span><span class="sxs-lookup"><span data-stu-id="ff016-p105">In the preceding command, the retrieved certificate is configured to function as the global server-to-server authentication certificate; that means that the certificate will be replicated to, and used by, all your Front End Servers. Again, this command should only be run one time, and only on one of your Front End Servers. Although all Front End Servers must use the same certificate, you should not configure the OAuthTokenIssuer certificate on each Front End Server. Instead, configure the certificate once, then let Lync Server's replication server take care of copying that certificate to each server.</span></span>

<span data-ttu-id="ff016-118">この証明書を対象とする証明書を取得し、その証明書を現在の OAuthTokenIssuer 証明書として機能するように直ちに設定します。</span><span class="sxs-lookup"><span data-stu-id="ff016-118">The Set-CsCertificate cmdlet takes the certificate in question and immediately configures that certificate to act as the current OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="ff016-119">(Lync Server 2013 は、証明書の種類が現在の証明書と以前の証明書という2つのコピーを保持します。)新しい証明書を OAuthTokenIssuer 証明書としてすぐに機能させる必要がある場合は、コマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff016-119">(Lync Server 2013 keeps two copies of a certificate type: the current certificate and the previous certificate.) If you need the new certificate to immediately begin to act as the OAuthTokenIssuer certificate then you should use the Set-CsCertificate cmdlet.</span></span>

<span data-ttu-id="ff016-p107">Set-CsCertificate コマンドレットを使用して、新しい証明書を "ロール" することもできます。証明書の "ロール" とは、指定した時点から新しい証明書を現在の OAuthTokenIssuer 証明書にするように構成することを意味します。たとえば、次のコマンドを実行すると、既定の証明書が取得してから、2012 年 7 月 1 日付けでその証明書が現在の OAuthTokenIssuer 証明書になるように構成します。</span><span class="sxs-lookup"><span data-stu-id="ff016-p107">You can also use the Set-CsCertificate cmdlet to "roll" a new certificate. "Rolling" a certificate simply means that you configure a new certificate to become the current OAuthTokenIssuer certificate at a specified point in time. For example, this command retrieves the default certificate and then configure that certificate to take over as the current OAuthTokenIssuer certificate as of July 1, 2012:</span></span>

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2012" -Roll

<span data-ttu-id="ff016-123">2012 年 7 月 1 日になると、新しい証明書が現在の OAuthTokenIssuer 証明書として構成され、"古い" OAuthTokenIssuer 証明書は以前の証明書として構成されます。</span><span class="sxs-lookup"><span data-stu-id="ff016-123">On July 1, 2012 the new certificate will be configured as the current OAuthTokenIssuer certificate and the "old" OAuthTokenIssuer certificate will be configured as the previous certificate.</span></span>

<span data-ttu-id="ff016-p108">Windows PowerShell を使用したくない場合は、証明書 MMC コンソールを使用して 1 台のフロントエンド サーバーから証明書をエクスポートしてから、同じ証明書を他のすべてのフロントエンド サーバーにインポートします。これを行う場合は、証明書とともに秘密キーを必ずエクスポートしてください。</span><span class="sxs-lookup"><span data-stu-id="ff016-p108">If you do not want to use Windows PowerShell you can also use the Certificates MMC console to export a certificate from one Front End Server and then import that same certificate on all your other Front End Servers. If you do this, make sure that you export the private key along with the certificate itself.</span></span>

<div>


> [!WARNING]
> <span data-ttu-id="ff016-126">この場合、この手順を各フロントエンド サーバーで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff016-126">In this case, the procedure must be performed on each Front End Server.</span></span> <span data-ttu-id="ff016-127">この方法で証明書をエクスポートおよびインポートする場合、Lync Server 2013 は各フロントエンドサーバーに証明書をレプリケートしません。</span><span class="sxs-lookup"><span data-stu-id="ff016-127">When exporting and importing certificates in this manner Lync Server 2013 will not replicate that certificate to each Front End Server.</span></span>



</div>

<span data-ttu-id="ff016-128">すべてのフロントエンドサーバーに証明書をインポートした後、その証明書を Windows PowerShell ではなく Lync Server 展開ウィザードを使用して割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="ff016-128">After the certificate has been imported to all your Front End Servers, that certificate can then be assigned by using the Lync Server Deployment Wizard instead of Windows PowerShell.</span></span> <span data-ttu-id="ff016-129">展開ウィザードを使用して証明書を割り当てるには、展開ウィザードがインストールされているコンピューターで以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ff016-129">To assign a certificate by using the Deployment Wizard, complete the following steps on a computer where the Deployment Wizard has been installed:</span></span>

1.  <span data-ttu-id="ff016-130">[スタート]、[すべてのプログラム]、[ **Microsoft Lync server 2013**]、[ **Lync server 展開ウィザード**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="ff016-130">Click Start, click All Programs, click **Microsoft Lync Server 2013**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="ff016-131">展開ウィザードで、[**Lync Server システムのインストールまたは更新**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ff016-131">In the Deployment Wizard, click **Install or Update Lync Server System**.</span></span>

3.  <span data-ttu-id="ff016-132">[Microsoft Lync Server 2013] ページで、[**ステップ 3: 証明書の要求、インストール、または割り当て**] の下にある [**実行**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ff016-132">On the Microsoft Lync Server 2013 page, click the **Run** button under the heading **Step 3: Request, Install or Assign Certificates**.</span></span> <span data-ttu-id="ff016-133">(メモ: このコンピューターに既に証明書をインストールしている場合は、[**実行**] ボタンに [**再実行**] と表示されます。)</span><span class="sxs-lookup"><span data-stu-id="ff016-133">(Note: If you have already installed certificates on this computer then the **Run** button will be labeled **Run Again**.)</span></span>

4.  <span data-ttu-id="ff016-134">証明書ウィザードで、**OAuthTokenIssuer** 証明書を選択してから [**割り当て**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ff016-134">In the Certificate Wizard, select the **OAuthTokenIssuer** certificate and then click **Assign**.</span></span>

5.  <span data-ttu-id="ff016-135">証明書の割り当てウィザードの [**証明書の割り当て**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ff016-135">In the Certificate Assignment wizard, on the **Certificate Assignment** page, click **Next**.</span></span>

6.  <span data-ttu-id="ff016-136">[**証明書ストア**] ページで、サーバー対サーバーの認証に使用する証明書を選択して [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ff016-136">On the **Certificate Store** page, select the certificate to be used for server-to-server authentication and then click **Next**.</span></span>

7.  <span data-ttu-id="ff016-137">[証明書の割り当ての概要] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ff016-137">On the Certificate Assignment Summary page, click **Next**.</span></span>

8.  <span data-ttu-id="ff016-138">[コマンドを実行しています] ページで、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ff016-138">On the Executing Commands page, click **Finish**.</span></span>

9.  <span data-ttu-id="ff016-139">証明書ウィザードと展開ウィザードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="ff016-139">Close the Certificate Wizard and the Deployment Wizard.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

