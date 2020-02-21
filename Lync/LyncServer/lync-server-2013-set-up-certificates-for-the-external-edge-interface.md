---
title: 'Lync Server 2013: 外部エッジインターフェイスの証明書の設定'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up certificates for the external edge interface
ms:assetid: 5d78182c-88d8-4483-95ad-74b17f2d5fac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398409(v=OCS.15)
ms:contentKeyID: 48184287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec2bad8f01e773d50f8d722ddbbf4be0757cb31d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200610"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-external-edge-interface-for-lync-server-2013"></a><span data-ttu-id="d5074-102">Lync Server 2013 の外部エッジインターフェイス用の証明書の設定</span><span class="sxs-lookup"><span data-stu-id="d5074-102">Set up certificates for the external edge interface for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5074-103">_**トピックの最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="d5074-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d5074-104">証明書ウィザードを実行する場合、使用する証明書テンプレートの種類に対して適切なアクセス許可が割り当てられたグループのメンバーであるアカウントを使用してログインしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d5074-104">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="d5074-105">既定では、Lync Server 証明書要求は Web サーバー証明書テンプレートを使用します。</span><span class="sxs-lookup"><span data-stu-id="d5074-105">By default, a Lync Server certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="d5074-106">RTCUniversalServerAdmins グループのメンバーであるアカウントおよびこのテンプレートを使用して証明書を要求する場合、そのテンプレートを使用するために必要な登録アクセス許可がそのグループに割り当てられていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d5074-106">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="d5074-107">各エッジ サーバーでは、境界ネットワークとインターネット間のインターフェイスでパブリック証明書が必要です。また、証明書のサブジェクトの別名にアクセス エッジ サービスと Web 会議エッジ サービスの完全修飾ドメイン名 (FQDN) の外部名が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5074-107">Each Edge Server requires a public certificate on the interface between the perimeter network and the Internet, and the certificate’s subject alternative name must contain the external names of the Access Edge service and Web Conferencing Edge service fully qualified domain names (FQDNs).</span></span>

<span data-ttu-id="d5074-108">この他の証明書の要件の詳細については、「 [Lync Server 2013 の外部ユーザーアクセスの証明書要件](lync-server-2013-certificate-requirements-for-external-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5074-108">For details about this and other certificate requirements, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<span data-ttu-id="d5074-109">統合コミュニケーション証明書の特定の要件に準拠した証明書を提供し、Microsoft と提携して Lync Server 2013 証明書ウィザードと共に動作するようにする場合は、「Microsoft サポート技術情報の記事929395、「Exchange Server および Communications Server 用の統合コミュニケーション証明書[https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834)パートナー」 () を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5074-109">For a list of public certification authorities (CAs) that provide certificates that comply with specific requirements for unified communications certificates and have partnered with Microsoft to ensure they work with the Lync Server 2013 Certificate Wizard, see Microsoft Knowledge Base article 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

<div>

## <a name="configuring-certificates-on-the-external-interfaces"></a><span data-ttu-id="d5074-110">外部インターフェイスの証明書を構成するには</span><span class="sxs-lookup"><span data-stu-id="d5074-110">Configuring Certificates on the External Interfaces</span></span>

<span data-ttu-id="d5074-111">1 つのサイトの外部エッジ インターフェイスに証明書を設定するには、このセクションの手順を使用して次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d5074-111">To set up a certificate on the external edge interface at a site, use the procedures in this section to do the following:</span></span>

  - <span data-ttu-id="d5074-112">エッジ サーバーの外部インターフェイスの証明書要求を作成します。</span><span class="sxs-lookup"><span data-stu-id="d5074-112">Create the certificate request for the external interface of the Edge Server.</span></span>

  - <span data-ttu-id="d5074-113">要求をパブリック CA に送信します。</span><span class="sxs-lookup"><span data-stu-id="d5074-113">Submit the request to your public CA.</span></span>

  - <span data-ttu-id="d5074-114">各エッジ サーバーの外部インターフェイス用の証明書をインポートします。</span><span class="sxs-lookup"><span data-stu-id="d5074-114">Import the certificate for the external interface of each Edge Server.</span></span>

  - <span data-ttu-id="d5074-115">各エッジ サーバーの外部インターフェイスに証明書を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d5074-115">Assign the certificate for the external interface of each Edge Server.</span></span>

  - <span data-ttu-id="d5074-p102">展開に複数のエッジ サーバーが含まれる場合は、証明書とその秘密キーをエクスポートして他のエッジ サーバーにコピーします。 次に、各エッジ サーバーにインポートし、前に説明した手順に従って割り当てます。各エッジ サーバーでこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="d5074-p102">If your deployment includes multiple Edge Servers, export the certificate along with its private key, and then copy it to the other Edge Servers. Then, for each Edge Server, import it and assign it as previously described. Repeat this procedure for each Edge Server.</span></span>

<span data-ttu-id="d5074-p103">パブリック証明機関 (CA) 発行のパブリック証明書を直接要求できます (パブリック CA の Web サイトからなど)。 このセクションの手順では、大部分の証明書タスクに証明書ウィザードを使用しています。 パブリック CA 発行の証明書を直接要求するときは、要求に応じて各手順を変更し、証明書を転送、インポートして、証明書チェーンもインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5074-p103">You can request public certificates directly from a public certification authority (CA) (such as from the website of a public CA). The procedures in this section use the Certificate Wizard for most certificate tasks. If you chose to request a certificate directly from a public CA, then you will need to modify each procedure as appropriate to request, transport, and import the certificate and also to import the certificate chain.</span></span>

<span data-ttu-id="d5074-p104">外部 CA 発行の証明書を要求するときは、指定する資格情報にその CA 発行の証明書を要求する権限が設定されている必要があります。 各 CA には、証明書の要求、発行、管理、および読み込みを許可する資格情報 (特定のユーザーやグループの名前) を定義しているセキュリティ ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="d5074-p104">When you request a certificate from an External CA, the credentials provided must have rights to request a certificate from that CA. Each CA has a security policy that defines which credentials (that is, specific user and group names) are allowed to request, issue, manage, or read certificates.</span></span>

<span data-ttu-id="d5074-124">証明書に Microsoft 管理コンソール (MMC) を使用して証明書チェーンと証明書をインポートするときは、それらをコンピューターの証明書ストアにインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5074-124">If you decide to use the Certificates Microsoft Management Console (MMC) to import the certificate chain and certificate, you must import them to the certificate store for the computer.</span></span> <span data-ttu-id="d5074-125">ユーザーまたはサービス証明書ストアにインポートした場合、Lync Server 2013 証明書ウィザードでその証明書を割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="d5074-125">If you import them to the user or service certificate store, the certificate will not be available for assignment in the Lync Server 2013 Certificate Wizard.</span></span>

<div>

## <a name="to-create-the-certificate-request-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="d5074-126">エッジ サーバーの外部インターフェイスの証明書要求を作成するには</span><span class="sxs-lookup"><span data-stu-id="d5074-126">To create the certificate request for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="d5074-127">エッジ サーバーの展開ウィザードで、**[ステップ 3: 証明書の要求、インストール、または割り当て]** の横にある **[再実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5074-127">On the Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d5074-128">組織で AOL とのパブリック インスタント メッセージング (IM) 接続をサポートする必要がある場合は、Lync Server 展開ウィザードを使用して証明書を要求することはできません。</span><span class="sxs-lookup"><span data-stu-id="d5074-128">If your organization wants to support public instant messaging (IM) connectivity with AOL, you cannot use the Lync Server Deployment Wizard to request the certificate.</span></span> <span data-ttu-id="d5074-129">代わりに、このトピックの後半で説明している「AOL とのパブリック IM 接続をサポートするために、エッジ サーバーの外部インターフェイス用に証明書要求を作成するには」の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d5074-129">Instead, perform the steps in the “To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL” procedure later in this topic.</span></span><BR><span data-ttu-id="d5074-130">プール内の1つの場所に複数のエッジサーバーがある場合は、いずれかのエッジサーバーで Lync Server 2013 証明書ウィザードを実行できます。</span><span class="sxs-lookup"><span data-stu-id="d5074-130">If you have multiple Edge Servers in one location in a pool, you can run the Lync Server 2013 Certificate Wizard on any one of the Edge Servers.</span></span>

    
    </div>

2.  <span data-ttu-id="d5074-131">[**利用可能な証明書タスク**] ページで、[**新しい証明書要求を作成する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5074-131">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="d5074-132">[**証明書の要求**] ページで、[**外部エッジの証明書**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5074-132">On the **Certificate Request** page, click **External Edge Certificate**.</span></span>

4.  <span data-ttu-id="d5074-133">[**要求を後で送信または今すぐ送信**] ページで、[**要求を準備して後で送信する**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d5074-133">On the **Delayed or Immediate Request** page, select the **Prepare the request now, but send it later** check box.</span></span>

5.  <span data-ttu-id="d5074-134">[**証明書要求ファイル**] ページで、要求を保存するファイルの完全なパスとファイル名を入力します (たとえば、c:\\cert\_外部\_edge. .cer)。</span><span class="sxs-lookup"><span data-stu-id="d5074-134">On the **Certificate Request File** page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

6.  <span data-ttu-id="d5074-135">[**代替証明書テンプレートの指定**] ページで、既定の WebServer テンプレート以外のテンプレートを使用するには、[**選択した証明機関に別の証明書テンプレートを使用する**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d5074-135">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected certification authority** check box.</span></span>

7.  <span data-ttu-id="d5074-136">[**名前およびセキュリティの設定**] ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d5074-136">On the **Name and Security Settings** page, do the following:</span></span>
    
      - <span data-ttu-id="d5074-137">**[フレンドリ名]** に、証明書の表示名を入力します。</span><span class="sxs-lookup"><span data-stu-id="d5074-137">In **Friendly name**, type a display name for the certificate.</span></span>
    
      - <span data-ttu-id="d5074-138">**[ビット長]** で、ビット長を指定します (通常は既定値の **[2048]**)。</span><span class="sxs-lookup"><span data-stu-id="d5074-138">In **Bit length**, specify the bit length (typically, the default of **2048**).</span></span>
    
      - <span data-ttu-id="d5074-139">**[証明書の秘密キーをエクスポート可能にする]** チェック ボックスがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d5074-139">Verify that the **Mark certificate private key as exportable** check box is selected.</span></span>

8.  <span data-ttu-id="d5074-140">[**組織情報**] ページで、組織の名前と組織単位 (部や課など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="d5074-140">On the **Organization Information** page, type the name for the organization and the organizational unit (for example, a division or department).</span></span>

9.  <span data-ttu-id="d5074-141">[**地理情報**] ページで、場所情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="d5074-141">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="d5074-p107">[**サブジェクト名/サブジェクト代替名**] ページに、ウィザードによって自動的に設定される情報が表示されます。追加のサブジェクトの別名が必要な場合、次の 2 つの手順で指定します。</span><span class="sxs-lookup"><span data-stu-id="d5074-p107">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed. If additional subject alternative names are needed, you specify them in the next two steps.</span></span>

11. <span data-ttu-id="d5074-144">[**サブジェクト代替名 (san) の Sip ドメイン設定**] ページで、[ドメイン] チェックボックスをオンにして sip を追加します。\<microsoft.rtc.management.xds.sipdomain\>エントリをサブジェクトの別名一覧に入力します。</span><span class="sxs-lookup"><span data-stu-id="d5074-144">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the domain check box to add a sip.\<sipdomain\> entry to the subject alternative names list.</span></span>

12. <span data-ttu-id="d5074-145">**[追加のサブジェクト代替名の構成]** ページで、必要な追加のサブジェクトの別名を指定します。</span><span class="sxs-lookup"><span data-stu-id="d5074-145">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>

13. <span data-ttu-id="d5074-146">**[要求の概要]** ページで、要求を生成するために使用する証明書情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="d5074-146">On the **Request Summary** page, review the certificate information to be used to generate the request.</span></span>

14. <span data-ttu-id="d5074-147">コマンドの実行が終了したら、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d5074-147">After the commands finish running, do the following:</span></span>
    
      - <span data-ttu-id="d5074-148">証明書要求のログを表示するには、**[ログの表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5074-148">To view the log for the certificate request, click **View Log**.</span></span>
    
      - <span data-ttu-id="d5074-149">証明書要求を完了するには、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5074-149">To complete the certificate request, click **Next**.</span></span>

15. <span data-ttu-id="d5074-150">**[証明書要求ファイル]** ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d5074-150">On the **Certificate Request File** page, do the following:</span></span>
    
      - <span data-ttu-id="d5074-151">生成した証明書の署名要求 (CSR) ファイルを表示するには、**[表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5074-151">To view the generated certificate signing request (CSR) file, click **View**.</span></span>
    
      - <span data-ttu-id="d5074-152">ウィザードを閉じるには、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5074-152">To close the wizard, click **Finish**.</span></span>

16. <span data-ttu-id="d5074-153">出力ファイルを、パブリック CA に送信できる場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="d5074-153">Copy the output file to a location where you can submit it to the public CA.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a><span data-ttu-id="d5074-154">AOL とのパブリック IM 接続をサポートするために、エッジ サーバーの外部インターフェイス用に証明書要求を作成するには</span><span class="sxs-lookup"><span data-stu-id="d5074-154">To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL</span></span>

1.  <span data-ttu-id="d5074-155">必要なテンプレートが CA で利用できる場合は、エッジサーバーで次の Windows PowerShell コマンドレットを使用して証明書を要求します。</span><span class="sxs-lookup"><span data-stu-id="d5074-155">When the required template is available to the CA, use the following Windows PowerShell cmdlet from at the Edge Server to request the certificate:</span></span>
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    <span data-ttu-id="d5074-156">Lync Server 2013 で提供されるテンプレートの既定の証明書名は、Web サーバーです。</span><span class="sxs-lookup"><span data-stu-id="d5074-156">The default certificate name of the template provided in Lync Server 2013 is Web Server.</span></span> <span data-ttu-id="d5074-157">既定のテンプレート\<とは\>異なるテンプレートを使用する必要がある場合にのみ、テンプレート名を指定します。</span><span class="sxs-lookup"><span data-stu-id="d5074-157">Only specify the \<template name\> if you need to use a template that is different from the default template.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d5074-158">組織で AOL とのパブリック IM 接続をサポートする必要がある場合は、証明書ウィザードではなく Windows PowerShell を使用して、アクセスエッジサービスの外部エッジに証明書を割り当てるよう要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5074-158">If your organization wants to support public IM connectivity with AOL, you must use Windows PowerShell instead of the Certificate Wizard to request the certificate to be assigned to the external edge for the Access Edge service.</span></span> <span data-ttu-id="d5074-159">これは、証明書ウィザードが証明書を要求するために使用する Lync Server 2013 Web サーバーテンプレートは、クライアント EKU 構成をサポートしていないためです。</span><span class="sxs-lookup"><span data-stu-id="d5074-159">This is because the Lync Server 2013 Web Server template that the Certificate Wizard uses to request a certificate does not support client EKU configuration.</span></span> <span data-ttu-id="d5074-160">Windows PowerShell を使用して証明書を作成する前に、CA 管理者はクライアント EKU をサポートする新しいテンプレートを作成して展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5074-160">Before using Windows PowerShell to create the certificate, the CA administrator must create and deploy a new template that supports client EKU.</span></span>

    
    </div>

</div>

<div>

## <a name="to-submit-a-request-to-a-public-certification-authority"></a><span data-ttu-id="d5074-161">要求をパブリック証明機関に送信するには</span><span class="sxs-lookup"><span data-stu-id="d5074-161">To submit a request to a public certification authority</span></span>

1.  <span data-ttu-id="d5074-162">出力ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="d5074-162">Open the output file.</span></span>

2.  <span data-ttu-id="d5074-163">証明書の署名要求 (CSR) の内容をコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="d5074-163">Copy and paste the contents of the Certificate Signing Request (CSR).</span></span>

3.  <span data-ttu-id="d5074-164">メッセージが表示されたら、以下を指定します。</span><span class="sxs-lookup"><span data-stu-id="d5074-164">If prompted, specify the following:</span></span>
    
      - <span data-ttu-id="d5074-165">サーバー プラットフォームとして **Microsoft**。</span><span class="sxs-lookup"><span data-stu-id="d5074-165">**Microsoft** as the server platform.</span></span>
    
      - <span data-ttu-id="d5074-166">バージョンとして **IIS**。</span><span class="sxs-lookup"><span data-stu-id="d5074-166">**IIS** as the version.</span></span>
    
      - <span data-ttu-id="d5074-167">用途として **Web サーバー**。</span><span class="sxs-lookup"><span data-stu-id="d5074-167">**Web Server** as the usage type.</span></span>
    
      - <span data-ttu-id="d5074-168">応答形式として **PKCS7**。</span><span class="sxs-lookup"><span data-stu-id="d5074-168">**PKCS7** as the response format.</span></span>

4.  <span data-ttu-id="d5074-169">これらの情報がパブリック CA によって検証された後、証明書に必要なテキストを含む電子メール メッセージが送られてきます。</span><span class="sxs-lookup"><span data-stu-id="d5074-169">When the public CA has verified your information, you will receive an email message containing text required for your certificate.</span></span>

5.  <span data-ttu-id="d5074-170">電子メール メッセージからテキストをコピーし、ローカル コンピューター上のテキスト ファイル (.txt) に保存します。</span><span class="sxs-lookup"><span data-stu-id="d5074-170">Copy the text from the email message and save the contents in a text file (.txt) on your local computer.</span></span>

</div>

<div>

## <a name="to-import-the-certificate-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="d5074-171">エッジ サーバーの外部インターフェイス用の証明書をインポートするには</span><span class="sxs-lookup"><span data-stu-id="d5074-171">To import the certificate for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="d5074-172">証明書要求を作成したのと同じエッジ サーバーに、Administrators グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="d5074-172">Log on as a member of the Administrators group to the same Edge Server on which you created the certificate request.</span></span>

2.  <span data-ttu-id="d5074-173">展開ウィザードの **[エッジ サーバーの展開]** ページで、**[ステップ 3:証明書の要求、インストール、または割り当て]** の横にある **[再実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5074-173">In the Deployment Wizard, on the **Deploy Edge Server** page, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

3.  <span data-ttu-id="d5074-174">**[利用可能な証明書タスク]** ページで、**[.p7b、pfx、または .cer ファイルから証明書をインポートする]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5074-174">On the **Available Certificate Tasks** page, click **Import a certificate from a .p7b, pfx or .cer file**.</span></span>

4.  <span data-ttu-id="d5074-p110">[**証明書のインポート**] ページで [**参照**] をクリックして、エッジ サーバーの外部インターフェイス用に要求した証明書を見つけて選択します (または、完全なパスとファイル名を入力します)。証明書に秘密キーが含まれる場合は、[**証明書ファイルに証明書の秘密キーが含まれる**] を選択し、秘密キーのパスワードを入力します。[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5074-p110">On the **Import Certificate** page, click **Browse** to locate and select the certificate that you requested for the external interface of the Edge Server (or, you can type the full path and file name). If the certificate contains a private key, select **Certificate file contains certificate’s private key** and type the password for the private key. Click **Next**.</span></span>

5.  <span data-ttu-id="d5074-178">[**証明書のインポートの概要**] ページで、概要を確認して [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5074-178">On **Import Certificate Summary** page, review the summary and then click **Next**.</span></span>

6.  <span data-ttu-id="d5074-179">[**コマンドを実行しています**] で、インポートの結果を確認し、必要に応じて [**ログの表示**] をクリックして詳細を表示します。次に、[**完了**] をクリックして証明書のインポートを完了します。</span><span class="sxs-lookup"><span data-stu-id="d5074-179">On **Executing Commands**, review the results of the import, click **View Log** for more information as needed, and then click **Finish** to complete the certificate import.</span></span>

7.  <span data-ttu-id="d5074-p111">エッジ サーバー プールを構成している場合は、この後の「プール内のエッジ サーバー用の証明書と秘密キーをエクスポートするには」の手順を実行し、証明書とその秘密キーをエクスポートします。エクスポートした証明書ファイルを他のエッジ サーバーにコピーし、それを各エッジ サーバーのコンピューターのストアにインポートします。</span><span class="sxs-lookup"><span data-stu-id="d5074-p111">If you are configuring an Edge Server pool, export the certificate with its private key as outlined in the “To export the certificate with the private key for Edge Servers in a pool” procedure later in this topic. Copy the exported certificate file to the other Edge Servers, and import it into the computer store on each Edge Server.</span></span>

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a><span data-ttu-id="d5074-182">プール内のエッジ サーバー用の証明書と秘密キーをエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="d5074-182">To export the certificate with the private key for Edge Servers in a pool</span></span>

1.  <span data-ttu-id="d5074-183">証明書をインポートしたのと同じエッジ サーバーに、Administrators グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="d5074-183">Log on as a member of the Administrators group to the same Edge Server on which you imported the certificate.</span></span>

2.  <span data-ttu-id="d5074-184">[**スタート**] ボタン、[**ファイル名を指定して実行**] の順にクリックし、「**MMC**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="d5074-184">Click **Start**, click **Run**, and type **MMC**.</span></span>

3.  <span data-ttu-id="d5074-185">Microsoft 管理コンソール (MMC) コンソールで、[**ファイル**] をクリックし、[**スナップインの追加と削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5074-185">In the Microsoft Management Console (MMC) console, click **File**, and then click **Add/Remove Snap-in**.</span></span>

4.  <span data-ttu-id="d5074-186">[**スナップインの追加と削除**] で、[**証明書**] をクリックし、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5074-186">In **Add or Remove Snap-ins**, click **Certificates**, and then click **Add**.</span></span>

5.  <span data-ttu-id="d5074-187">[**証明書スナップイン**] ダイアログ ボックスで、[**コンピューター アカウント**] を選択し、[**次へ**] をクリックします。[**コンピューターの選択**] で、[**ローカル コンピューター: (このコンソールを実行しているコンピューター)**] を選択し、[**完了**] をクリックします。[**OK**] をクリックして MMC コンソールの構成を完了します。</span><span class="sxs-lookup"><span data-stu-id="d5074-187">In the **Certificates** dialog box, select **Computer account**, click **Next**, select **Local computer: (the computer this console is running on)** in **Select Computer**, click **Finish** and then click **OK** to complete configuration of the MMC console.</span></span>

6.  <span data-ttu-id="d5074-188">[**証明書 (ローカル コンピューター)**] をダブルクリックして証明書ストアを展開し、[**個人**] をダブルクリックして、[**証明書**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5074-188">Double-click **Certificates (Local Computer)** to expand the certificate stores, double-click **Personal**, and then double-click **Certificates**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d5074-p112">ローカル コンピューターの個人の証明書ストアに証明書がない場合は、インポートした証明書に秘密キーが関連付けられていません。要求とインポートの手順を再確認してください。問題が解決しない場合は、証明機関の管理者またはプロバイダーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="d5074-p112">If there are no certificates in the Certificates Personal store for the local computer, there is no private key associated with the certificate that was imported. Review the request and import steps. If the problem persists, contact your certification authority administrator or provider.</span></span>

    
    </div>

7.  <span data-ttu-id="d5074-192">**ローカル コンピューターの個人の証明書ストア**で、エクスポートする証明書を右クリックし、[**すべてのタスク**] をクリックして、[**エクスポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5074-192">In the **Certificates Personal store for the local computer**, right-click the certificate that you are exporting, click **All Tasks**, and then click **Export**.</span></span>

8.  <span data-ttu-id="d5074-193">証明書のエクスポート ウィザードで、[**次へ**] をクリックし、[**はい、秘密キーをエクスポートします**] を選択して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5074-193">In the Certificate Export Wizard, click **Next**, select **Yes, export the private key**, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d5074-p113">[<STRONG>はい、秘密キーをエクスポートします</STRONG>] が無効になっていて選択できない場合、この証明書に関連付けられている秘密キーはエクスポート可能になっていません。エクスポートを続行するには、その前に証明書を再度要求して、証明書の秘密キーをエクスポート可能にする必要があります。証明機関の管理者またはプロバイダーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="d5074-p113">If the selection <STRONG>Yes, export the private key</STRONG> is not available, the private key associated with this certificate was not marked for export. You will need to request the certificate again, ensuring that the certificate is marked to allow for the export of the private key before you can continue with the export. Contact your certification authority administrator or provider.</span></span>

    
    </div>

9.  <span data-ttu-id="d5074-197">[エクスポートファイルの形式] ダイアログで、[ **Personal Information Exchange\#– PKCS 12 (]) を選択します。PFX)** を選択し、次のように選択します。</span><span class="sxs-lookup"><span data-stu-id="d5074-197">On the Export File Formats dialog, select **Personal Information Exchange – PKCS\#12 (.PFX)** and then select the following:</span></span>
    
      - <span data-ttu-id="d5074-198">可能であれば、証明書パスにあるすべての証明書を含める</span><span class="sxs-lookup"><span data-stu-id="d5074-198">Include all certificates in the certification path if possible</span></span>
    
      - <span data-ttu-id="d5074-199">すべての拡張プロパティをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="d5074-199">Export all extended properties</span></span>
        
        <div>
        

        > [!WARNING]  
        > <span data-ttu-id="d5074-p114">エッジ サーバーから証明書をエクスポートするとき、[<STRONG>正しくエクスポートされたときは秘密キーを削除する</STRONG>] をオンにしないでください。このオプションをオンにすると、このエッジ サーバーに証明書と秘密キーをインポートすることが必要になります。</span><span class="sxs-lookup"><span data-stu-id="d5074-p114">When exporting the certificate from an Edge server, do not select <STRONG>Delete the private key if the export is successful</STRONG>. Selecting this option will require that you import the certificate and the private key to this Edge server.</span></span>

        
        </div>

10. <span data-ttu-id="d5074-202">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5074-202">Click **Next**.</span></span>

11. <span data-ttu-id="d5074-203">秘密キーのパスワードを入力し、確認のために再度パスワードを入力して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5074-203">Type a password for the private key, type the password again to confirm, and then click **Next**.</span></span>

12. <span data-ttu-id="d5074-p115">エクスポートする証明書のパスとファイル名を入力し、ファイル拡張子に .pfx を指定します。このパスは、プール内の他のすべてのエッジ サーバーからアクセスできるパスにするか、USB フラッシュ ドライブなどリムーバブル メディアを使用して転送可能にする必要があります。[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5074-p115">Type a path and file name for the exported certificate, using a file extension of .pfx. The path must either be accessible to all other Edge servers in the pool or available to transport by means of removable media - for example, a USB flash drive. Click **Next**.</span></span>

13. <span data-ttu-id="d5074-207">[**証明書のエクスポート ウィザードの完了**] で概要を確認し、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5074-207">Review the summary in **Completing the Certificate Export Wizard**, and then click **Finish**.</span></span>

14. <span data-ttu-id="d5074-208">エクスポートの成功を示すダイアログ ボックスが表示されたら、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5074-208">In the successful export dialog box, click **OK**.</span></span>

15. <span data-ttu-id="d5074-209">前の「エッジ サーバーの外部インターフェイス用の証明書をインポートするには」に記載された手順に従って、エクスポートした証明書ファイルを他のエッジ サーバーにインポートします。</span><span class="sxs-lookup"><span data-stu-id="d5074-209">Import the exported certificate file to the other Edge servers following the steps outlined in the “To import the certificate for the external interface of the Edge Server” procedure earlier in this topic.</span></span>

</div>

<div>

## <a name="to-assign-the-certificate-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="d5074-210">エッジ サーバーの外部インターフェイス用の証明書を割り当てるには</span><span class="sxs-lookup"><span data-stu-id="d5074-210">To assign the certificate for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="d5074-211">各エッジ サーバーの展開ウィザードで、**[ステップ 3:証明書の要求、インストール、または割り当て]** の横にある **[再実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5074-211">On each Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

2.  <span data-ttu-id="d5074-212">**[利用可能な証明書タスク]** ページで、**[既存の証明書を割り当てる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5074-212">On the **Available Certificate Tasks** page, click **Assign an existing certificate**.</span></span>

3.  <span data-ttu-id="d5074-213">**[証明書の割り当て]** ページで、**[外部エッジ証明書]** をクリックし、**[証明書の使用法の詳細設定]** チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d5074-213">On the **Certificate Assignment** page, click **External Edge Certificate** and select the **Advanced Certificate Usages** check box.</span></span>

4.  <span data-ttu-id="d5074-214">**[証明書の使用法の詳細設定]** ページで、すべてのチェック ボックスをオンにして、すべての使用法に対して証明書を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d5074-214">On the **Advanced Certificate Usages** page, select all check boxes to assign the certificate for all usages.</span></span>

5.  <span data-ttu-id="d5074-215">**[証明書ストア]** ページで、対象のエッジ サーバーの外部インターフェイス用に要求してインポートしたパブリック証明書を選択します。</span><span class="sxs-lookup"><span data-stu-id="d5074-215">On the **Certificate Store** page, select the public certificate that you requested and imported for the external interface of the Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d5074-216">要求してインポートした証明書が一覧に表示されない場合、トラブルシューティング方法の 1 つとして、証明書のサブジェクト名とサブジェクトの別名が証明書のすべての要件を満たしているかどうか確認することが挙げられます。上記の手順を使用せずに証明書と証明書チェーンを手動でインポートした場合は、証明書が正しい証明書ストア (ユーザーまたはサービスの証明書ストアではなく、コンピューターの証明書ストア) にあるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="d5074-216">If the certificate you requested and imported is not in the list, one of the trouble shooting methods is to verify that subject name and subject alternative names of the certificate meet all requirements for the certificate and, if you manually imported the certificate and certificate chain instead of using the preceding procedures, that the certificate is in the correct certificate store (the computer certificate store, not the user or service certificate store).</span></span>

    
    </div>

6.  <span data-ttu-id="d5074-217">**[証明書割り当ての概要]** ページで設定を確認し、**[次へ]** をクリックして証明書を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d5074-217">On the **Certificate Assignment Summary** page, review your settings, and then click **Next** to assign the certificates.</span></span>

7.  <span data-ttu-id="d5074-218">ウィザードの完了ページで **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5074-218">On the wizard completion page, click **Finish**.</span></span>

8.  <span data-ttu-id="d5074-219">このエッジに証明書を割り当てる手順を実行した後で、各サーバーで証明書スナップインを開き、**[証明書 (ローカル コンピュータ)]**、**[個人]** を順に展開して、**[証明書]** をクリックします。次に、詳細ウィンドウで証明書が一覧にあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d5074-219">After using this procedure to assign the edge certificate, open the Certificate snap-in on each server, expand **Certificates (Local computer)**, expand **Personal**, click **Certificates**, and then verify in the details pane that the certificate is listed.</span></span>

9.  <span data-ttu-id="d5074-220">展開に複数のエッジ サーバーが含まれる場合は、各エッジ サーバーでこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="d5074-220">If your deployment includes multiple Edge Servers, repeat this procedure for each Edge Server.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

