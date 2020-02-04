---
title: 'Lync Server 2013: ディレクターの証明書の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates for the Director
ms:assetid: 22988186-15ae-43b1-92f4-0adb3b75a7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398296(v=OCS.15)
ms:contentKeyID: 48183612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fccab201ee9ab16b0195bc2780c37ab85f0519e9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739387"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-the-director-in-lync-server-2013"></a><span data-ttu-id="d8041-102">Lync Server 2013 でのディレクターの証明書の構成</span><span class="sxs-lookup"><span data-stu-id="d8041-102">Configure certificates for the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8041-103">_**最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="d8041-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d8041-104">証明書ウィザードを実行するときは、使用する証明書テンプレートの種類に対して適切な権限が割り当てられているグループのメンバーであるアカウントを使用してログインしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d8041-104">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="d8041-105">既定では、Lync Server 2013 証明書の要求では、Web サーバー証明書テンプレートが使用されます。</span><span class="sxs-lookup"><span data-stu-id="d8041-105">By default, a Lync Server 2013 certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="d8041-106">RTCUniversalServerAdmins グループのメンバーであるアカウントを使用して、このテンプレートを使用して証明書を要求する場合は、そのテンプレートを使用するために必要な登録権限がグループに割り当てられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d8041-106">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="d8041-107">各ディレクターには、既定の証明書、web 内部証明書、web 外部証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="d8041-107">Each Director requires a default certificate, a web internal certificate, and a web external certificate.</span></span> <span data-ttu-id="d8041-108">ディレクターの証明書要件の詳細については、計画ドキュメントの「 [Lync Server 2013 の内部サーバーの証明書要件](lync-server-2013-certificate-requirements-for-internal-servers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8041-108">For details about the certificate requirements for Directors, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="d8041-109">ディレクター証明書を構成するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="d8041-109">Use the following procedure to configure Director certificates.</span></span> <span data-ttu-id="d8041-110">各ディレクターについて手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="d8041-110">Repeat the procedure for each Director.</span></span> <span data-ttu-id="d8041-111">この手順では、組織によって展開され、オフライン要求処理を使用して、内部のエンタープライズルート証明機関 (CA) から証明書を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d8041-111">The steps of this procedure describe how to configure a certificate from an Internal Enterprise Root certification authority (CA) deployed by your organization and with offline request processing.</span></span> <span data-ttu-id="d8041-112">外部 CA から証明書を取得する方法について詳しくは、サポートチームにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="d8041-112">For details about obtaining certificates from an external CA, contact your support team.</span></span>

<div>

## <a name="to-configure-certificates-for-the-director-or-director-pool"></a><span data-ttu-id="d8041-113">ディレクターまたはディレクタープールの証明書を構成するには</span><span class="sxs-lookup"><span data-stu-id="d8041-113">To configure certificates for the Director or Director pool</span></span>

1.  <span data-ttu-id="d8041-114">Lync Server 展開ウィザードで、[**手順 3: 証明書の要求、証明書のセットアップ、または割り当て**] の横にある [**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8041-114">In the Lync Server Deployment Wizard, next to **Step 3: Request, Install or Assign Certificates**, click **Run**.</span></span>

2.  <span data-ttu-id="d8041-115">**証明書ウィザード**のページで [**要求**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8041-115">On the **Certificate Wizard** page, click **Request**.</span></span>

3.  <span data-ttu-id="d8041-116">[**証明書の要求**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8041-116">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="d8041-117">[**遅延または即時要求**] ページで、既定の [**オンライン証明機関に直ちに要求を送信する**] オプションを受け入れ、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8041-117">On the **Delayed or Immediate Requests** page, accept the default **Send the request immediately to an online certification authority** option, and then click **Next**.</span></span>

5.  <span data-ttu-id="d8041-118">[**証明機関 (CA) の選択**] ページで、使用する内部の Windows 証明機関をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8041-118">On the **Choose a Certification Authority (CA)** page, click the internal Windows certification authority that you want to use, and then click **Next**.</span></span>

6.  <span data-ttu-id="d8041-119">[**証明機関アカウント**] ページで、ログオンしているアカウントに証明書を要求するための十分な権限がない場合に使用する代替資格情報を指定して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8041-119">On the **Certification Authority Account** page, specify alternate credentials to be used if the account you are logged on with does not have sufficient authority to request the certificate, and then click **Next**.</span></span>

7.  <span data-ttu-id="d8041-120">[**代替証明書テンプレートの指定**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8041-120">On the **Specify Alternate Certificate Template** page, click **Next**.</span></span>

8.  <span data-ttu-id="d8041-121">[**名前とセキュリティの設定**] ページで、**フレンドリ名**を指定し、2048ビットのキーの長さをそのまま使用して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8041-121">On the **Name and Security Settings** page, you can specify a **Friendly Name**, accept the 2048-bit key length, and then click **Next**.</span></span>

9.  <span data-ttu-id="d8041-122">[**組織の情報**] ページで、必要に応じて組織の情報を指定し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8041-122">On the **Organization Information** page, optionally specify organization information, and then click **Next**.</span></span>

10. <span data-ttu-id="d8041-123">[**地理情報**] ページで、必要に応じて地理情報を指定し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8041-123">On the **Geographical Information** page, optionally specify geographical information, and then click **Next**.</span></span>

11. <span data-ttu-id="d8041-124">[**サブジェクト名/サブジェクト別の名前**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8041-124">On the **Subject Name / Subject Alternative Names** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d8041-125">[件名の代替名] の一覧には、ディレクターをインストールするコンピューター (単一のディレクターの場合) またはディレクタープールの名前、および組織で構成されている単純な URL 名が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8041-125">The subject alternative name list should contain the name of the computer on which you are installing the Director (if a single Director) or the Director pool name, and the simple URL names configured for the organization.</span></span>

    
    </div>

12. <span data-ttu-id="d8041-126">[**サブジェクト代替名 (san)] ページの SIP ドメイン設定**で、監督が処理するすべてのドメインに対し**て構成されている sip ドメイン**を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8041-126">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the **Configured SIP Domains** for all domains that you want the Director to handle, and then click **Next**.</span></span>

13. <span data-ttu-id="d8041-127">[**追加のサブジェクト代替名の構成**] ページで、必要な件名の代替名を追加し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8041-127">On the **Configure Additional Subject Alternative Names** page, add any additional required subject alternative names, and then click **Next**.</span></span>

14. <span data-ttu-id="d8041-128">[**証明書の要求の概要**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8041-128">On the **Certificate Request Summary** page, click **Next**.</span></span>

15. <span data-ttu-id="d8041-129">[**コマンドの実行**] ページで、コマンドの実行が完了したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8041-129">On the **Executing Commands** page, click **Next** after the commands have finished running.</span></span>

16. <span data-ttu-id="d8041-130">[**オンライン証明書の要求の状態**] ページで、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8041-130">On the **Online Certificate Request Status** page, click **Finish**.</span></span>

17. <span data-ttu-id="d8041-131">[**証明書の割り当て**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8041-131">On the **Certificate Assignment** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d8041-132">証明書を表示する場合は、一覧で証明書をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8041-132">if you want to view the certificate, double-click the certificate in the list.</span></span>

    
    </div>

18. <span data-ttu-id="d8041-133">[**証明書の割り当ての概要**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8041-133">On the **Certificate Assignment Summary** page, click **Next**.</span></span>

19. <span data-ttu-id="d8041-134">[**コマンドの実行**] ページで、コマンドの実行が完了したら [**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8041-134">On the **Executing Commands** page, click **Finish** after the commands have finished running.</span></span>

20. <span data-ttu-id="d8041-135">**証明書ウィザード**のページで、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8041-135">On the **Certificate Wizard** page, click **Close**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

