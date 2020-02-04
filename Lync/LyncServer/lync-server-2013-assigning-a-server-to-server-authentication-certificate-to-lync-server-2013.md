---
title: サーバー間認証証明書を Lync Server 2013 に割り当てる
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
ms.openlocfilehash: 06372be3808f3855bc0172cc408308a0c9c9cab2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734017"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-a-server-to-server-authentication-certificate-to-microsoft-lync-server-2013"></a><span data-ttu-id="7b609-102">サーバー間認証証明書を Microsoft Lync Server 2013 に割り当てる</span><span class="sxs-lookup"><span data-stu-id="7b609-102">Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b609-103">_**最終更新日:** 2013-10-24_</span><span class="sxs-lookup"><span data-stu-id="7b609-103">_**Topic Last Modified:** 2013-10-24_</span></span>

<span data-ttu-id="7b609-104">サーバー間認証証明書が Microsoft Lync Server 2013 に既に割り当てられているかどうかを確認するには、Lync Server 2013 管理シェルから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7b609-104">To determine whether or not a server-to-server authentication certificate has already been assigned to Microsoft Lync Server 2013, run the following command from the Lync Server 2013 Management Shell:</span></span>

    Get-CsCertificate -Type OAuthTokenIssuer

<span data-ttu-id="7b609-105">証明書情報が返されない場合は、サーバー間認証を使用する前に、トークン発行元の証明書を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b609-105">If no certificate information is returned you must assign a token issuer certificate before you can use server-to-server authentication.</span></span> <span data-ttu-id="7b609-106">一般的な規則として、すべての Lync Server 2013 証明書を OAuthTokenIssuer 証明書として使うことができます。たとえば、Lync Server 2013 の既定の証明書は、OAuthTokenIssuer 証明書としても使うことができます。</span><span class="sxs-lookup"><span data-stu-id="7b609-106">As a general rule, any Lync Server 2013 certificate can be used as your OAuthTokenIssuer certificate; for example, your Lync Server 2013 default certificate can also be used as the OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="7b609-107">(OAUthTokenIssuer 証明書には、[件名] フィールドに SIP ドメイン名を含む Web サーバー証明書でもかまいません)。サーバー間認証に使用される証明書の主な2つの要件を次に示します。 1) 同じ証明書をすべてのフロントエンドサーバー上の OAuthTokenIssuer 証明書として構成する必要があります。および 2) 証明書は、2048ビット以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b609-107">(The OAUthTokenIssuer certificate can also be any Web server certificate that includes the name of your SIP domain in the Subject field.) The primary two requirements for the certificate used for server-to-server authentication are these: 1)the same certificate must be configured as the OAuthTokenIssuer certificate on all of your Front End Servers; and, 2) the certificate must be at least 2048 bits.</span></span>

<span data-ttu-id="7b609-108">サーバー対サーバーの認証に使用できる証明書がない場合は、新しい証明書をインポートして、その証明書をサーバー対サーバーの認証に使用します。</span><span class="sxs-lookup"><span data-stu-id="7b609-108">If you do not have a certificate that can be used for server-to-server authentication you can obtain a new certificate, import the new certificate, and then use that certificate for server-to-server authentication.</span></span> <span data-ttu-id="7b609-109">新しい証明書を要求して取得したら、いずれかのフロントエンドサーバーにログオンし、次のような Windows PowerShell コマンドを使用して、その証明書をインポートして割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="7b609-109">After you have requested and obtained the new certificate you can then log on to any one of your Front End Servers and use a Windows PowerShell command similar to this one to import and assign that certificate:</span></span>

    Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"

<span data-ttu-id="7b609-110">上記のコマンドパスパラメーターは、証明書ファイルへの完全なパスを表し、Password パラメーターは証明書に割り当てられたパスワードを表します。</span><span class="sxs-lookup"><span data-stu-id="7b609-110">In the preceding command the Path parameter represents the full path to the certificate file, and the Password parameter represents the password that was assigned to the certificate.</span></span> <span data-ttu-id="7b609-111">この手順は1回だけ実行する必要があります。 Lync Server のレプリケーションサービスは、証明書を解読してすべてのフロントエンドサーバーに展開する一連のスケジュールされたタスクを自動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="7b609-111">This procedure should be run just one time: Lync Server's replication service will then automatically create a set of scheduled tasks that will decrypt and deploy the certificate to all your Front End Servers.</span></span>

<span data-ttu-id="7b609-112">または、既存の証明書をサーバー間認証証明書として使うこともできます。</span><span class="sxs-lookup"><span data-stu-id="7b609-112">Alternatively, you can use an existing certificate as your server-to-server authentication certificate.</span></span> <span data-ttu-id="7b609-113">(前述のように、既定の証明書をサーバー間認証証明書として使用できます。)次のペアの Windows PowerShell コマンドは、既定の証明書の拇印プロパティの値を取得し、その値を使って、サーバー間認証証明書の既定の証明書を作成します。</span><span class="sxs-lookup"><span data-stu-id="7b609-113">(As noted, the default certificate can be used as the server-to-server authentication certificate.) The following pair of Windows PowerShell commands retrieve the value of the default certificate's Thumbprint property, then use that value to make the default certificate the server-to-server authentication certificate:</span></span>

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x

<span data-ttu-id="7b609-114">上のコマンドでは、取得された証明書がグローバルサーバー間認証証明書として機能するように構成されています。これは、証明書がすべてのフロントエンドサーバーにレプリケートされ、使用されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="7b609-114">In the preceding command, the retrieved certificate is configured to function as the global server-to-server authentication certificate; that means that the certificate will be replicated to, and used by, all your Front End Servers.</span></span> <span data-ttu-id="7b609-115">このコマンドは、1つのフロントエンドサーバーでのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="7b609-115">Again, this command should only be run one time, and only on one of your Front End Servers.</span></span> <span data-ttu-id="7b609-116">フロントエンドサーバーはすべて同じ証明書を使用する必要がありますが、各フロントエンドサーバーで OAuthTokenIssuer 証明書を構成しないでください。</span><span class="sxs-lookup"><span data-stu-id="7b609-116">Although all Front End Servers must use the same certificate, you should not configure the OAuthTokenIssuer certificate on each Front End Server.</span></span> <span data-ttu-id="7b609-117">代わりに、証明書を1回構成して、Lync Server のレプリケーションサーバーがその証明書を各サーバーにコピーできるようにします。</span><span class="sxs-lookup"><span data-stu-id="7b609-117">Instead, configure the certificate once, then let Lync Server's replication server take care of copying that certificate to each server.</span></span>

<span data-ttu-id="7b609-118">設定-CsCertificate コマンドレットは、該当する証明書を受け取り、現在の OAuthTokenIssuer 証明書として動作するようにその証明書を直ちに構成します。</span><span class="sxs-lookup"><span data-stu-id="7b609-118">The Set-CsCertificate cmdlet takes the certificate in question and immediately configures that certificate to act as the current OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="7b609-119">(Lync Server 2013 では、証明書の種類は、現在の証明書と前の証明書の2つのコピーが保持されます)。新しい証明書を直ちに OAuthTokenIssuer 証明書として使用する必要がある場合は、Set-CsCertificate コマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b609-119">(Lync Server 2013 keeps two copies of a certificate type: the current certificate and the previous certificate.) If you need the new certificate to immediately begin to act as the OAuthTokenIssuer certificate then you should use the Set-CsCertificate cmdlet.</span></span>

<span data-ttu-id="7b609-120">Set-CsCertificate コマンドレットを使用して、新しい証明書を "ロール" することもできます。</span><span class="sxs-lookup"><span data-stu-id="7b609-120">You can also use the Set-CsCertificate cmdlet to "roll" a new certificate.</span></span> <span data-ttu-id="7b609-121">証明書の "ロール" とは、指定した時点から新しい証明書を現在の OAuthTokenIssuer 証明書にするように構成することを意味します。</span><span class="sxs-lookup"><span data-stu-id="7b609-121">"Rolling" a certificate simply means that you configure a new certificate to become the current OAuthTokenIssuer certificate at a specified point in time.</span></span> <span data-ttu-id="7b609-122">たとえば、次のコマンドは、既定の証明書を取得し、2012年7月1日の時点で、現在の OAuthTokenIssuer 証明書としてその証明書を設定するように構成します。</span><span class="sxs-lookup"><span data-stu-id="7b609-122">For example, this command retrieves the default certificate and then configure that certificate to take over as the current OAuthTokenIssuer certificate as of July 1, 2012:</span></span>

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2012" -Roll

<span data-ttu-id="7b609-123">2012年7月1日に、新しい証明書は現在の OAuthTokenIssuer 証明書として構成され、"old" OAuthTokenIssuer 証明書は前の証明書として構成されます。</span><span class="sxs-lookup"><span data-stu-id="7b609-123">On July 1, 2012 the new certificate will be configured as the current OAuthTokenIssuer certificate and the "old" OAuthTokenIssuer certificate will be configured as the previous certificate.</span></span>

<span data-ttu-id="7b609-124">Windows PowerShell を使用しない場合は、[証明書] MMC コンソールを使用して、1つのフロントエンドサーバーから証明書をエクスポートし、その同じ証明書を他のすべてのフロントエンドサーバーにインポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="7b609-124">If you do not want to use Windows PowerShell you can also use the Certificates MMC console to export a certificate from one Front End Server and then import that same certificate on all your other Front End Servers.</span></span> <span data-ttu-id="7b609-125">これを行う場合は、証明書とともに秘密キーを必ずエクスポートしてください。</span><span class="sxs-lookup"><span data-stu-id="7b609-125">If you do this, make sure that you export the private key along with the certificate itself.</span></span>

<div>


> [!WARNING]
> <span data-ttu-id="7b609-126">この場合は、各フロントエンドサーバーで手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b609-126">In this case, the procedure must be performed on each Front End Server.</span></span> <span data-ttu-id="7b609-127">この方法で証明書をエクスポートおよびインポートするときに、Lync Server 2013 では、各フロントエンドサーバーに証明書が複製されることはありません。</span><span class="sxs-lookup"><span data-stu-id="7b609-127">When exporting and importing certificates in this manner Lync Server 2013 will not replicate that certificate to each Front End Server.</span></span>



</div>

<span data-ttu-id="7b609-128">証明書がすべてのフロントエンドサーバーにインポートされたら、Windows PowerShell の代わりに Lync Server 展開ウィザードを使用して証明書を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="7b609-128">After the certificate has been imported to all your Front End Servers, that certificate can then be assigned by using the Lync Server Deployment Wizard instead of Windows PowerShell.</span></span> <span data-ttu-id="7b609-129">展開ウィザードを使用して証明書を割り当てるには、展開ウィザードがインストールされているコンピューターで以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="7b609-129">To assign a certificate by using the Deployment Wizard, complete the following steps on a computer where the Deployment Wizard has been installed:</span></span>

1.  <span data-ttu-id="7b609-130">[スタート] をクリックし、[すべてのプログラム] をクリックし、[ **Microsoft Lync server 2013**] をクリックして、[ **Lync server Deployment Wizard**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7b609-130">Click Start, click All Programs, click **Microsoft Lync Server 2013**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="7b609-131">展開ウィザードで、[ **Lync Server System のインストールまたは更新**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7b609-131">In the Deployment Wizard, click **Install or Update Lync Server System**.</span></span>

3.  <span data-ttu-id="7b609-132">Microsoft Lync Server 2013 ページで、「**手順 3: 証明書の要求、インストール、または割り当て**を行う」の下にある [**実行**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="7b609-132">On the Microsoft Lync Server 2013 page, click the **Run** button under the heading **Step 3: Request, Install or Assign Certificates**.</span></span> <span data-ttu-id="7b609-133">(注: このコンピューターに既に証明書をインストールしている場合は、[**実行**] ボタンは**もう一度 [実行**] というラベルが付けられます。)</span><span class="sxs-lookup"><span data-stu-id="7b609-133">(Note: If you have already installed certificates on this computer then the **Run** button will be labeled **Run Again**.)</span></span>

4.  <span data-ttu-id="7b609-134">証明書ウィザードで、**OAuthTokenIssuer** 証明書を選択してから [**割り当て**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7b609-134">In the Certificate Wizard, select the **OAuthTokenIssuer** certificate and then click **Assign**.</span></span>

5.  <span data-ttu-id="7b609-135">証明書の割り当てウィザードの [**証明書の割り当て**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7b609-135">In the Certificate Assignment wizard, on the **Certificate Assignment** page, click **Next**.</span></span>

6.  <span data-ttu-id="7b609-136">[**証明書ストア**] ページで、サーバー対サーバーの認証に使用する証明書を選択して [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7b609-136">On the **Certificate Store** page, select the certificate to be used for server-to-server authentication and then click **Next**.</span></span>

7.  <span data-ttu-id="7b609-137">[証明書の割り当ての概要] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7b609-137">On the Certificate Assignment Summary page, click **Next**.</span></span>

8.  <span data-ttu-id="7b609-138">[コマンドを実行しています] ページで、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7b609-138">On the Executing Commands page, click **Finish**.</span></span>

9.  <span data-ttu-id="7b609-139">証明書ウィザードと展開ウィザードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="7b609-139">Close the Certificate Wizard and the Deployment Wizard.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

