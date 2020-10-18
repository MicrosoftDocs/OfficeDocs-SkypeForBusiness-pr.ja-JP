---
title: 'Lync Server 2013: ディレクターの証明書の構成'
description: 'Lync Server 2013: ディレクターの証明書を構成します。'
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
ms.openlocfilehash: cadc3f51b036120e21c3f1e6201f872aacafef69
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578073"
---
# <a name="configure-certificates-for-the-director-in-lync-server-2013"></a><span data-ttu-id="6441d-103">Lync Server 2013 でディレクターの証明書を構成する</span><span class="sxs-lookup"><span data-stu-id="6441d-103">Configure certificates for the Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6441d-104">_**トピックの最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="6441d-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6441d-105">証明書ウィザードを実行する場合、使用する証明書テンプレートの種類に対して適切なアクセス許可が割り当てられたグループのメンバーであるアカウントを使用してログインしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6441d-105">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="6441d-106">既定では、Lync Server 2013 証明書要求は Web サーバー証明書テンプレートを使用します。</span><span class="sxs-lookup"><span data-stu-id="6441d-106">By default, a Lync Server 2013 certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="6441d-107">RTCUniversalServerAdmins グループのメンバーであるアカウントおよびこのテンプレートを使用して証明書を要求する場合、そのテンプレートを使用するために必要な登録アクセス許可がそのグループに割り当てられていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6441d-107">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="6441d-108">各ディレクターは既定の証明書、Web 内部証明書、および Web 外部証明書を必要とします。</span><span class="sxs-lookup"><span data-stu-id="6441d-108">Each Director requires a default certificate, a web internal certificate, and a web external certificate.</span></span> <span data-ttu-id="6441d-109">ディレクターの証明書要件の詳細については、「計画」のドキュメントの「 [Lync Server 2013 の内部サーバーの証明書要件](lync-server-2013-certificate-requirements-for-internal-servers.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6441d-109">For details about the certificate requirements for Directors, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="6441d-p103">ディレクターの証明書を構成するには、次の手順を使用します。 各ディレクターでこの手順を繰り返します。 この手順のステップは、組織によって展開される内部エンタープライズ ルート証明機関 (CA) からの、オフライン要求処理で発行された証明書の構成方法について説明するものです。 外部 CA から証明書の取得の詳細については、サポート チームにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="6441d-p103">Use the following procedure to configure Director certificates. Repeat the procedure for each Director. The steps of this procedure describe how to configure a certificate from an Internal Enterprise Root certification authority (CA) deployed by your organization and with offline request processing. For details about obtaining certificates from an external CA, contact your support team.</span></span>

<div>

## <a name="to-configure-certificates-for-the-director-or-director-pool"></a><span data-ttu-id="6441d-114">ディレクターまたはディレクター プールの証明書を構成するには</span><span class="sxs-lookup"><span data-stu-id="6441d-114">To configure certificates for the Director or Director pool</span></span>

1.  <span data-ttu-id="6441d-115">Lync Server 展開ウィザードで、[ **ステップ 3: 証明書の要求、インストール、または割り当て**] の横にある [ **実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6441d-115">In the Lync Server Deployment Wizard, next to **Step 3: Request, Install or Assign Certificates**, click **Run**.</span></span>

2.  <span data-ttu-id="6441d-116">**証明書ウィザード**のページで **[要求]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6441d-116">On the **Certificate Wizard** page, click **Request**.</span></span>

3.  <span data-ttu-id="6441d-117">[**証明書要求**] ページで [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6441d-117">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="6441d-118">[**要求を後で送信または今すぐ送信**] ページで、既定の [**要求をすぐにオンライン証明機関に送信する**] オプションをそのまま使用して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6441d-118">On the **Delayed or Immediate Requests** page, accept the default **Send the request immediately to an online certification authority** option, and then click **Next**.</span></span>

5.  <span data-ttu-id="6441d-119">[**証明機関 (CA) を選択してください**] ページで、使用する内部の Windows 認証機関をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6441d-119">On the **Choose a Certification Authority (CA)** page, click the internal Windows certification authority that you want to use, and then click **Next**.</span></span>

6.  <span data-ttu-id="6441d-120">[**証明機関のアカウント**] ページに、ログオンに使用したアカウントに証明書を要求するための十分な権限がない場合に使用する代替資格情報を指定して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6441d-120">On the **Certification Authority Account** page, specify alternate credentials to be used if the account you are logged on with does not have sufficient authority to request the certificate, and then click **Next**.</span></span>

7.  <span data-ttu-id="6441d-121">[**代替証明書テンプレートの指定**] ページで [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6441d-121">On the **Specify Alternate Certificate Template** page, click **Next**.</span></span>

8.  <span data-ttu-id="6441d-122">[**名前およびセキュリティの設定**] ページで、[**フレンドリ名**] を指定し、2048 ビット長のキーを選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6441d-122">On the **Name and Security Settings** page, you can specify a **Friendly Name**, accept the 2048-bit key length, and then click **Next**.</span></span>

9.  <span data-ttu-id="6441d-123">[**組織情報**] ページで、必要に応じて組織情報を指定し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6441d-123">On the **Organization Information** page, optionally specify organization information, and then click **Next**.</span></span>

10. <span data-ttu-id="6441d-124">[**地理情報**] ページで、必要に応じて地理情報を指定し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6441d-124">On the **Geographical Information** page, optionally specify geographical information, and then click **Next**.</span></span>

11. <span data-ttu-id="6441d-125">[**サブジェクト名/サブジェクトの別名**] ページで [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6441d-125">On the **Subject Name / Subject Alternative Names** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6441d-126">サブジェクトの別名リスト一覧には、ディレクターをインストールするコンピューター名 (ディレクターが 1 つの場合は) またはディレクターのプール名、および組織用に構成された簡易 URL 名が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6441d-126">The subject alternative name list should contain the name of the computer on which you are installing the Director (if a single Director) or the Director pool name, and the simple URL names configured for the organization.</span></span>

    
    </div>

12. <span data-ttu-id="6441d-127">[**サブジェクト代替名 (SAN) の SIP ドメイン設定**] ページで、ディレクターが処理するすべてのドメインについて [**構成済み SIP ドメイン**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6441d-127">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the **Configured SIP Domains** for all domains that you want the Director to handle, and then click **Next**.</span></span>

13. <span data-ttu-id="6441d-128">[**追加のサブジェクトの別名の構成**] ページで、必要なサブジェクトの別名を追加し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6441d-128">On the **Configure Additional Subject Alternative Names** page, add any additional required subject alternative names, and then click **Next**.</span></span>

14. <span data-ttu-id="6441d-129">[**証明書要求の概要**] ページで [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6441d-129">On the **Certificate Request Summary** page, click **Next**.</span></span>

15. <span data-ttu-id="6441d-130">[**コマンドの実行**] ページで、コマンドの実行が終了した後に [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6441d-130">On the **Executing Commands** page, click **Next** after the commands have finished running.</span></span>

16. <span data-ttu-id="6441d-131">[**オンライン証明書要求の状態**] ページで [**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6441d-131">On the **Online Certificate Request Status** page, click **Finish**.</span></span>

17. <span data-ttu-id="6441d-132">[**証明書の割り当て**] ページで [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6441d-132">On the **Certificate Assignment** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6441d-133">証明書を表示する場合は、一覧で証明書をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="6441d-133">if you want to view the certificate, double-click the certificate in the list.</span></span>

    
    </div>

18. <span data-ttu-id="6441d-134">[**証明書の割り当ての概要**] ページで [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6441d-134">On the **Certificate Assignment Summary** page, click **Next**.</span></span>

19. <span data-ttu-id="6441d-135">[**コマンドの実行**] ページで、コマンドの実行が終了した後に [**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6441d-135">On the **Executing Commands** page, click **Finish** after the commands have finished running.</span></span>

20. <span data-ttu-id="6441d-136">**証明書ウィザード**のページで [**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6441d-136">On the **Certificate Wizard** page, click **Close**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

