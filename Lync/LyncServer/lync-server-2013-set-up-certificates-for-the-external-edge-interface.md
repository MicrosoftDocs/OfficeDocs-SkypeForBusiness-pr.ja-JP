---
title: 'Lync Server 2013: 外部エッジ インターフェイスの証明書の設定'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set up certificates for the external edge interface
ms:assetid: 5d78182c-88d8-4483-95ad-74b17f2d5fac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398409(v=OCS.15)
ms:contentKeyID: 48184287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2cb33a91d6609f9109e6416f5688d1b2ddfb9ed
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822119"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-external-edge-interface-for-lync-server-2013"></a><span data-ttu-id="8ecd7-102">Lync Server 2013 外部エッジ インターフェイスの証明書の設定</span><span class="sxs-lookup"><span data-stu-id="8ecd7-102">Set up certificates for the external edge interface for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ecd7-103">_**最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="8ecd7-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8ecd7-104">証明書ウィザードを実行するときは、使用する証明書テンプレートの種類に対して適切な権限が割り当てられているグループのメンバーであるアカウントを使用してログインしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-104">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="8ecd7-105">既定では、Lync Server の証明書の要求では、Web サーバー証明書テンプレートが使用されます。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-105">By default, a Lync Server certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="8ecd7-106">RTCUniversalServerAdmins グループのメンバーであるアカウントを使用して、このテンプレートを使用して証明書を要求する場合は、そのテンプレートを使用するために必要な登録権限がグループに割り当てられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-106">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="8ecd7-107">各エッジサーバーでは、境界ネットワークとインターネット間のインターフェイスに対して公開証明書が必要です。また、証明書のサブジェクトの代替名には、アクセスエッジサービスと Web 会議エッジサービスの外部名が含まれている必要があります。修飾ドメイン名 (Fqdn)。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-107">Each Edge Server requires a public certificate on the interface between the perimeter network and the Internet, and the certificate’s subject alternative name must contain the external names of the Access Edge service and Web Conferencing Edge service fully qualified domain names (FQDNs).</span></span>

<span data-ttu-id="8ecd7-108">このような証明書の要件の詳細については、「 [Lync Server 2013 の外部ユーザーアクセスの証明書の要件](lync-server-2013-certificate-requirements-for-external-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-108">For details about this and other certificate requirements, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<span data-ttu-id="8ecd7-109">ユニファイドコミュニケーション証明書の特定の要件に準拠し、Microsoft と提携して Lync Server 2013 証明書ウィザードで動作する証明書を提供する公開証明機関 (Ca) の一覧については、「」を参照してください。Microsoft サポート技術情報の記事929395、「Exchange Server および通信サーバーのユニファイドコミュニケーション証明書パートナー [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834)」の「」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-109">For a list of public certification authorities (CAs) that provide certificates that comply with specific requirements for unified communications certificates and have partnered with Microsoft to ensure they work with the Lync Server 2013 Certificate Wizard, see Microsoft Knowledge Base article 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

<div>

## <a name="configuring-certificates-on-the-external-interfaces"></a><span data-ttu-id="8ecd7-110">外部インターフェイスで証明書を構成する</span><span class="sxs-lookup"><span data-stu-id="8ecd7-110">Configuring Certificates on the External Interfaces</span></span>

<span data-ttu-id="8ecd7-111">サイトの外部エッジインターフェイスで証明書を設定するには、このセクションの手順を使用して、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-111">To set up a certificate on the external edge interface at a site, use the procedures in this section to do the following:</span></span>

  - <span data-ttu-id="8ecd7-112">エッジサーバーの外部インターフェイスの証明書要求を作成します。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-112">Create the certificate request for the external interface of the Edge Server.</span></span>

  - <span data-ttu-id="8ecd7-113">公開 CA に要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-113">Submit the request to your public CA.</span></span>

  - <span data-ttu-id="8ecd7-114">各エッジサーバーの外部インターフェイスの証明書をインポートします。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-114">Import the certificate for the external interface of each Edge Server.</span></span>

  - <span data-ttu-id="8ecd7-115">各エッジサーバーの外部インターフェイスの証明書を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-115">Assign the certificate for the external interface of each Edge Server.</span></span>

  - <span data-ttu-id="8ecd7-116">展開に複数のエッジサーバーが含まれている場合は、証明書と秘密キーをエクスポートして、他のエッジサーバーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-116">If your deployment includes multiple Edge Servers, export the certificate along with its private key, and then copy it to the other Edge Servers.</span></span> <span data-ttu-id="8ecd7-117">次に、各エッジサーバーについてインポートし、前に説明したように割り当てます。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-117">Then, for each Edge Server, import it and assign it as previously described.</span></span> <span data-ttu-id="8ecd7-118">各エッジサーバーについて、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-118">Repeat this procedure for each Edge Server.</span></span>

<span data-ttu-id="8ecd7-119">パブリック証明機関 (CA) からパブリック証明書を直接要求することができます (パブリック CA の web サイトなど)。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-119">You can request public certificates directly from a public certification authority (CA) (such as from the website of a public CA).</span></span> <span data-ttu-id="8ecd7-120">このセクションの手順では、ほとんどの証明書タスクに対して証明書ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-120">The procedures in this section use the Certificate Wizard for most certificate tasks.</span></span> <span data-ttu-id="8ecd7-121">パブリック CA から直接証明書を要求するように選択した場合、証明書の要求、トランスポート、インポート、および証明書チェーンのインポートに必要な各手順を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-121">If you chose to request a certificate directly from a public CA, then you will need to modify each procedure as appropriate to request, transport, and import the certificate and also to import the certificate chain.</span></span>

<span data-ttu-id="8ecd7-122">外部 CA から証明書を要求する場合は、提供された資格情報にその CA から証明書を要求する権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-122">When you request a certificate from an External CA, the credentials provided must have rights to request a certificate from that CA.</span></span> <span data-ttu-id="8ecd7-123">各 CA には、証明書の要求、発行、管理、または読み取りを許可する資格情報 (具体的なユーザー名とグループ名) を定義するセキュリティポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-123">Each CA has a security policy that defines which credentials (that is, specific user and group names) are allowed to request, issue, manage, or read certificates.</span></span>

<span data-ttu-id="8ecd7-124">Microsoft 管理コンソール (MMC) を使って証明書チェーンと証明書をインポートする場合は、そのコンピューターの証明書ストアに証明書をインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-124">If you decide to use the Certificates Microsoft Management Console (MMC) to import the certificate chain and certificate, you must import them to the certificate store for the computer.</span></span> <span data-ttu-id="8ecd7-125">ユーザーまたはサービスの証明書ストアにインポートした場合、Lync Server 2013 の証明書ウィザードでは、この証明書を割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-125">If you import them to the user or service certificate store, the certificate will not be available for assignment in the Lync Server 2013 Certificate Wizard.</span></span>

<div>

## <a name="to-create-the-certificate-request-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="8ecd7-126">エッジサーバーの外部インターフェイスの証明書の要求を作成するには</span><span class="sxs-lookup"><span data-stu-id="8ecd7-126">To create the certificate request for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="8ecd7-127">エッジサーバーの展開ウィザードで、[**手順 3: 証明書の要求、インストール、または割り当て**] の横にある [実行] を**もう一度**クリックします。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-127">On the Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8ecd7-128">組織で AOL とのパブリックインスタントメッセージング (IM) 接続をサポートしたい場合は、Lync Server Deployment ウィザードを使って証明書を要求することはできません。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-128">If your organization wants to support public instant messaging (IM) connectivity with AOL, you cannot use the Lync Server Deployment Wizard to request the certificate.</span></span> <span data-ttu-id="8ecd7-129">代わりに、このトピックで後述する「AOL でのパブリック IM 接続をサポートするための外部インターフェイスの証明書要求を作成するには」の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-129">Instead, perform the steps in the “To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL” procedure later in this topic.</span></span><BR><span data-ttu-id="8ecd7-130">プール内の1つの場所に複数のエッジサーバーがある場合は、いずれかのエッジサーバーで Lync Server 2013 証明書ウィザードを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-130">If you have multiple Edge Servers in one location in a pool, you can run the Lync Server 2013 Certificate Wizard on any one of the Edge Servers.</span></span>

    
    </div>

2.  <span data-ttu-id="8ecd7-131">[**利用可能な証明書タスク**] ページで、[**新しい証明書要求を作成する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-131">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="8ecd7-132">[**証明書の要求**] ページで、[**外部境界の証明書**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-132">On the **Certificate Request** page, click **External Edge Certificate**.</span></span>

4.  <span data-ttu-id="8ecd7-133">[**遅延または即時要求**] ページで、[**今すぐ要求を準備するが、後で送信**する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-133">On the **Delayed or Immediate Request** page, select the **Prepare the request now, but send it later** check box.</span></span>

5.  <span data-ttu-id="8ecd7-134">[**証明書要求ファイル**] ページで、要求を保存するファイルの完全パスとファイル名を入力します (たとえば、c:\\cert\_外部\_edge)。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-134">On the **Certificate Request File** page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

6.  <span data-ttu-id="8ecd7-135">[**代替証明書テンプレートの指定**] ページで、既定の web サーバテンプレート以外のテンプレートを使用するには、[**選択された証明機関に別の証明書テンプレートを使用**する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-135">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected certification authority** check box.</span></span>

7.  <span data-ttu-id="8ecd7-136">[**名前とセキュリティの設定**] ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-136">On the **Name and Security Settings** page, do the following:</span></span>
    
      - <span data-ttu-id="8ecd7-137">[**フレンドリ名**] に、証明書の表示名を入力します。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-137">In **Friendly name**, type a display name for the certificate.</span></span>
    
      - <span data-ttu-id="8ecd7-138">**ビット長**では、ビット長 (通常は**2048**の既定値) を指定します。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-138">In **Bit length**, specify the bit length (typically, the default of **2048**).</span></span>
    
      - <span data-ttu-id="8ecd7-139">[**証明書の秘密キーをエクスポート可能としてマーク**する] チェックボックスがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-139">Verify that the **Mark certificate private key as exportable** check box is selected.</span></span>

8.  <span data-ttu-id="8ecd7-140">[**組織の情報**] ページで、組織の名前と組織単位 (たとえば、部門や部署) を入力します。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-140">On the **Organization Information** page, type the name for the organization and the organizational unit (for example, a division or department).</span></span>

9.  <span data-ttu-id="8ecd7-141">[**地理情報**] ページで、場所情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-141">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="8ecd7-142">[ **Subject Name/Subject name** ] ページには、ウィザードによって自動的に入力される情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-142">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed.</span></span> <span data-ttu-id="8ecd7-143">追加の件名の代替名が必要な場合は、次の2つの手順で指定します。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-143">If additional subject alternative names are needed, you specify them in the next two steps.</span></span>

11. <span data-ttu-id="8ecd7-144">[**サブジェクト代替名 (san)] ページの Sip ドメイン設定**で、[Domain] チェックボックスをオンにして sip を追加します。\<[\>件名の代替名] ボックスの一覧に sipdomain エントリを入力します。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-144">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the domain check box to add a sip.\<sipdomain\> entry to the subject alternative names list.</span></span>

12. <span data-ttu-id="8ecd7-145">[**追加のサブジェクト代替名の構成**] ページで、必要なその他のサブジェクトの代替名を指定します。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-145">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>

13. <span data-ttu-id="8ecd7-146">[**要求の概要**] ページで、要求の生成に使用する証明書情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-146">On the **Request Summary** page, review the certificate information to be used to generate the request.</span></span>

14. <span data-ttu-id="8ecd7-147">コマンドの実行が完了したら、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-147">After the commands finish running, do the following:</span></span>
    
      - <span data-ttu-id="8ecd7-148">証明書要求のログを表示するには、[**ログの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-148">To view the log for the certificate request, click **View Log**.</span></span>
    
      - <span data-ttu-id="8ecd7-149">証明書の要求を完了するには、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-149">To complete the certificate request, click **Next**.</span></span>

15. <span data-ttu-id="8ecd7-150">[**証明書要求ファイル**] ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-150">On the **Certificate Request File** page, do the following:</span></span>
    
      - <span data-ttu-id="8ecd7-151">生成された証明書署名要求 (CSR) ファイルを表示するには、[**表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-151">To view the generated certificate signing request (CSR) file, click **View**.</span></span>
    
      - <span data-ttu-id="8ecd7-152">ウィザードを閉じるには、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-152">To close the wizard, click **Finish**.</span></span>

16. <span data-ttu-id="8ecd7-153">公開 CA に送信できる場所に出力ファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-153">Copy the output file to a location where you can submit it to the public CA.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a><span data-ttu-id="8ecd7-154">AOL とのパブリック IM 接続をサポートするために、エッジサーバーの外部インターフェイスの証明書要求を作成するには</span><span class="sxs-lookup"><span data-stu-id="8ecd7-154">To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL</span></span>

1.  <span data-ttu-id="8ecd7-155">必要なテンプレートが CA で利用できるようになったら、エッジサーバーから次の Windows PowerShell コマンドレットを使用して証明書を要求します。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-155">When the required template is available to the CA, use the following Windows PowerShell cmdlet from at the Edge Server to request the certificate:</span></span>
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    <span data-ttu-id="8ecd7-156">Lync Server 2013 で提供されるテンプレートの既定の証明書名は、Web サーバーです。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-156">The default certificate name of the template provided in Lync Server 2013 is Web Server.</span></span> <span data-ttu-id="8ecd7-157">既定のテンプレート\<とは\>異なるテンプレートを使用する必要がある場合は、テンプレート名のみを指定します。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-157">Only specify the \<template name\> if you need to use a template that is different from the default template.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8ecd7-158">組織で AOL とのパブリック IM 接続をサポートしたい場合は、証明書ウィザードの代わりに Windows PowerShell を使用して、アクセスエッジサービスの外部境界に証明書を割り当てるように要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-158">If your organization wants to support public IM connectivity with AOL, you must use Windows PowerShell instead of the Certificate Wizard to request the certificate to be assigned to the external edge for the Access Edge service.</span></span> <span data-ttu-id="8ecd7-159">これは、証明書ウィザードで証明書を要求するために使用される Lync Server 2013 Web サーバーテンプレートがクライアント EKU 構成をサポートしていないためです。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-159">This is because the Lync Server 2013 Web Server template that the Certificate Wizard uses to request a certificate does not support client EKU configuration.</span></span> <span data-ttu-id="8ecd7-160">Windows PowerShell を使用して証明書を作成する前に、CA 管理者がクライアント EKU をサポートする新しいテンプレートを作成して展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-160">Before using Windows PowerShell to create the certificate, the CA administrator must create and deploy a new template that supports client EKU.</span></span>

    
    </div>

</div>

<div>

## <a name="to-submit-a-request-to-a-public-certification-authority"></a><span data-ttu-id="8ecd7-161">公開証明機関に要求を送信するには</span><span class="sxs-lookup"><span data-stu-id="8ecd7-161">To submit a request to a public certification authority</span></span>

1.  <span data-ttu-id="8ecd7-162">出力ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-162">Open the output file.</span></span>

2.  <span data-ttu-id="8ecd7-163">証明書署名リクエスト (CSR) の内容をコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-163">Copy and paste the contents of the Certificate Signing Request (CSR).</span></span>

3.  <span data-ttu-id="8ecd7-164">メッセージが表示されたら、次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-164">If prompted, specify the following:</span></span>
    
      - <span data-ttu-id="8ecd7-165">**Microsoft**をサーバープラットフォームとしてお選びください。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-165">**Microsoft** as the server platform.</span></span>
    
      - <span data-ttu-id="8ecd7-166">バージョンとしての**IIS** 。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-166">**IIS** as the version.</span></span>
    
      - <span data-ttu-id="8ecd7-167">使用の種類としての**Web サーバー** 。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-167">**Web Server** as the usage type.</span></span>
    
      - <span data-ttu-id="8ecd7-168">返信形式としての**PKCS7** 。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-168">**PKCS7** as the response format.</span></span>

4.  <span data-ttu-id="8ecd7-169">公開 CA が自分の情報を確認したら、証明書に必要なテキストを含むメールメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-169">When the public CA has verified your information, you will receive an email message containing text required for your certificate.</span></span>

5.  <span data-ttu-id="8ecd7-170">メールメッセージからテキストをコピーし、ローカルコンピューターのテキストファイル (.txt) にコンテンツを保存します。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-170">Copy the text from the email message and save the contents in a text file (.txt) on your local computer.</span></span>

</div>

<div>

## <a name="to-import-the-certificate-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="8ecd7-171">エッジサーバーの外部インターフェイスの証明書をインポートするには</span><span class="sxs-lookup"><span data-stu-id="8ecd7-171">To import the certificate for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="8ecd7-172">証明書要求を作成したのと同じエッジサーバーに、管理者グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-172">Log on as a member of the Administrators group to the same Edge Server on which you created the certificate request.</span></span>

2.  <span data-ttu-id="8ecd7-173">展開ウィザードの [**エッジサーバーの展開**] ページで、[**手順 3: 証明書の要求、インストール、または割り当て**] の横にある [実行] を**もう一度**クリックします。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-173">In the Deployment Wizard, on the **Deploy Edge Server** page, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

3.  <span data-ttu-id="8ecd7-174">[**利用可能な証明書タスク**] ページで、[ **. p7b、.pfx、または .cer ファイルから証明書をインポートする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-174">On the **Available Certificate Tasks** page, click **Import a certificate from a .p7b, pfx or .cer file**.</span></span>

4.  <span data-ttu-id="8ecd7-175">[**証明書のインポート**] ページで、[**参照**] をクリックして、エッジサーバーの外部インターフェイスに対して要求した証明書を見つけて選択します (または、完全なパスとファイル名を入力します)。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-175">On the **Import Certificate** page, click **Browse** to locate and select the certificate that you requested for the external interface of the Edge Server (or, you can type the full path and file name).</span></span> <span data-ttu-id="8ecd7-176">証明書に秘密キーが含まれている場合は、[**証明書ファイルに証明書の秘密キーが含まれ**ています] を選び、秘密キーのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-176">If the certificate contains a private key, select **Certificate file contains certificate’s private key** and type the password for the private key.</span></span> <span data-ttu-id="8ecd7-177">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-177">Click **Next**.</span></span>

5.  <span data-ttu-id="8ecd7-178">[**証明書の概要のインポート**] ページで、概要を確認し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-178">On **Import Certificate Summary** page, review the summary and then click **Next**.</span></span>

6.  <span data-ttu-id="8ecd7-179">**コマンドの実行**時に、インポートの結果を確認し、必要に応じて [**ログの表示**] をクリックし、[**完了**] をクリックして証明書のインポートを完了します。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-179">On **Executing Commands**, review the results of the import, click **View Log** for more information as needed, and then click **Finish** to complete the certificate import.</span></span>

7.  <span data-ttu-id="8ecd7-180">エッジサーバープールを構成している場合は、このトピックで後述する「プール内のエッジサーバーの秘密キーで証明書をエクスポートする」の手順に従って、秘密キーを持つ証明書をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-180">If you are configuring an Edge Server pool, export the certificate with its private key as outlined in the “To export the certificate with the private key for Edge Servers in a pool” procedure later in this topic.</span></span> <span data-ttu-id="8ecd7-181">エクスポートされた証明書ファイルを他のエッジサーバーにコピーし、各エッジサーバー上のコンピューターストアにインポートします。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-181">Copy the exported certificate file to the other Edge Servers, and import it into the computer store on each Edge Server.</span></span>

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a><span data-ttu-id="8ecd7-182">プール内のエッジサーバーの秘密キーを使って証明書をエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="8ecd7-182">To export the certificate with the private key for Edge Servers in a pool</span></span>

1.  <span data-ttu-id="8ecd7-183">証明書をインポートしたのと同じエッジサーバーに、管理者グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-183">Log on as a member of the Administrators group to the same Edge Server on which you imported the certificate.</span></span>

2.  <span data-ttu-id="8ecd7-184">[**スタート**] をクリックし、[**実行**] をクリックして、「 **MMC**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-184">Click **Start**, click **Run**, and type **MMC**.</span></span>

3.  <span data-ttu-id="8ecd7-185">Microsoft 管理コンソール (MMC) コンソールで、[**ファイル**] をクリックし、[スナップインの**追加と削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-185">In the Microsoft Management Console (MMC) console, click **File**, and then click **Add/Remove Snap-in**.</span></span>

4.  <span data-ttu-id="8ecd7-186">[**スナップインの追加と削除**] で [**証明書**] をクリックし、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-186">In **Add or Remove Snap-ins**, click **Certificates**, and then click **Add**.</span></span>

5.  <span data-ttu-id="8ecd7-187">[**証明書**] ダイアログボックスで、[**コンピューターアカウント**]、[**次へ**] の順にクリックし、[**ローカルコンピューター] (このコンソールが実行されているコンピューター)** を選択し、[**完了**] をクリックし、[ **OK** ] をクリックします。 \*\*\*\* MMC コンソールの構成を完了します。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-187">In the **Certificates** dialog box, select **Computer account**, click **Next**, select **Local computer: (the computer this console is running on)** in **Select Computer**, click **Finish** and then click **OK** to complete configuration of the MMC console.</span></span>

6.  <span data-ttu-id="8ecd7-188">[**証明書 (ローカルコンピューター)** ] をダブルクリックして、証明書ストアを展開し、[**個人用**] をダブルクリックして、[**証明書**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-188">Double-click **Certificates (Local Computer)** to expand the certificate stores, double-click **Personal**, and then double-click **Certificates**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="8ecd7-189">ローカルコンピューターの証明書の個人用ストアに証明書がない場合は、インポートされた証明書に関連付けられた秘密キーがありません。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-189">If there are no certificates in the Certificates Personal store for the local computer, there is no private key associated with the certificate that was imported.</span></span> <span data-ttu-id="8ecd7-190">要求とインポートの手順を確認します。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-190">Review the request and import steps.</span></span> <span data-ttu-id="8ecd7-191">問題が解決しない場合は、証明機関の管理者またはプロバイダーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-191">If the problem persists, contact your certification authority administrator or provider.</span></span>

    
    </div>

7.  <span data-ttu-id="8ecd7-192">**ローカルコンピューターの証明書の個人用ストア**で、エクスポートする証明書を右クリックし、[**すべてのタスク**] をクリックして、[**エクスポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-192">In the **Certificates Personal store for the local computer**, right-click the certificate that you are exporting, click **All Tasks**, and then click **Export**.</span></span>

8.  <span data-ttu-id="8ecd7-193">証明書のエクスポートウィザードで、[**次へ**] をクリックし、[**はい、秘密キーをエクスポート**します] をクリックして、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-193">In the Certificate Export Wizard, click **Next**, select **Yes, export the private key**, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8ecd7-194"><STRONG>[はい、秘密キーをエクスポート</STRONG>します] を選択できない場合は、この証明書に関連付けられている秘密キーがエクスポート対象としてマークされていません。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-194">If the selection <STRONG>Yes, export the private key</STRONG> is not available, the private key associated with this certificate was not marked for export.</span></span> <span data-ttu-id="8ecd7-195">エクスポートを続行する前に、証明書が秘密キーのエクスポートを許可するようにマークされていることを確認して、証明書をもう一度要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-195">You will need to request the certificate again, ensuring that the certificate is marked to allow for the export of the private key before you can continue with the export.</span></span> <span data-ttu-id="8ecd7-196">証明機関の管理者またはプロバイダーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-196">Contact your certification authority administrator or provider.</span></span>

    
    </div>

9.  <span data-ttu-id="8ecd7-197">[エクスポートファイルの形式] ダイアログボックスで、[ **Personal Information\#Exchange – PKCS 12 ()] を選びます。PFX)** を選び、次のように選択します。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-197">On the Export File Formats dialog, select **Personal Information Exchange – PKCS\#12 (.PFX)** and then select the following:</span></span>
    
      - <span data-ttu-id="8ecd7-198">可能であれば証明のパスにすべての証明書を含める</span><span class="sxs-lookup"><span data-stu-id="8ecd7-198">Include all certificates in the certification path if possible</span></span>
    
      - <span data-ttu-id="8ecd7-199">すべての拡張プロパティをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="8ecd7-199">Export all extended properties</span></span>
        
        <div>
        

        > [!WARNING]  
        > <span data-ttu-id="8ecd7-200">エッジサーバーから証明書をエクスポートするときに、<STRONG>エクスポートが正常に完了した場合は、[秘密キーの削除</STRONG>] を選択しないでください。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-200">When exporting the certificate from an Edge server, do not select <STRONG>Delete the private key if the export is successful</STRONG>.</span></span> <span data-ttu-id="8ecd7-201">このオプションを選択すると、証明書と秘密キーをこのエッジサーバーにインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-201">Selecting this option will require that you import the certificate and the private key to this Edge server.</span></span>

        
        </div>

10. <span data-ttu-id="8ecd7-202">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-202">Click **Next**.</span></span>

11. <span data-ttu-id="8ecd7-203">秘密キーのパスワードを入力し、確認のためにもう一度パスワードを入力して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-203">Type a password for the private key, type the password again to confirm, and then click **Next**.</span></span>

12. <span data-ttu-id="8ecd7-204">エクスポートする証明書のパスとファイル名を入力し、ファイル拡張子に .pfx を指定します。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-204">Type a path and file name for the exported certificate, using a file extension of .pfx.</span></span> <span data-ttu-id="8ecd7-205">パスは、プール内の他のすべてのエッジサーバーからアクセス可能であるか、またはリムーバブルメディア (USB フラッシュドライブなど) を使用して転送できるものである必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-205">The path must either be accessible to all other Edge servers in the pool or available to transport by means of removable media - for example, a USB flash drive.</span></span> <span data-ttu-id="8ecd7-206">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-206">Click **Next**.</span></span>

13. <span data-ttu-id="8ecd7-207">「**証明書のエクスポートウィザードの完了**」の概要を確認し、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-207">Review the summary in **Completing the Certificate Export Wizard**, and then click **Finish**.</span></span>

14. <span data-ttu-id="8ecd7-208">[エクスポートの成功] ダイアログボックスで、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-208">In the successful export dialog box, click **OK**.</span></span>

15. <span data-ttu-id="8ecd7-209">このトピックの前半にある「エッジサーバーの外部インターフェイス用の証明書をインポートする」の手順に従って、エクスポートされた証明書ファイルを他のエッジサーバーにインポートします。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-209">Import the exported certificate file to the other Edge servers following the steps outlined in the “To import the certificate for the external interface of the Edge Server” procedure earlier in this topic.</span></span>

</div>

<div>

## <a name="to-assign-the-certificate-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="8ecd7-210">エッジサーバーの外部インターフェイスの証明書を割り当てるには</span><span class="sxs-lookup"><span data-stu-id="8ecd7-210">To assign the certificate for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="8ecd7-211">各エッジサーバーの展開ウィザードで、[**手順 3: 証明書の要求、インストール、または割り当て**] の横にある [実行] を**もう一度**クリックします。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-211">On each Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

2.  <span data-ttu-id="8ecd7-212">[**利用可能な証明書タスク**] ページで、[**既存の証明書を割り当てる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-212">On the **Available Certificate Tasks** page, click **Assign an existing certificate**.</span></span>

3.  <span data-ttu-id="8ecd7-213">[**証明書の割り当て**] ページで、[**外部境界の証明書**] をクリックし、[**高度な証明書の使用法**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-213">On the **Certificate Assignment** page, click **External Edge Certificate** and select the **Advanced Certificate Usages** check box.</span></span>

4.  <span data-ttu-id="8ecd7-214">[**証明書の使用状況の詳細設定**] ページで、すべての使用状況に対して証明書を割り当てるためのすべてのチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-214">On the **Advanced Certificate Usages** page, select all check boxes to assign the certificate for all usages.</span></span>

5.  <span data-ttu-id="8ecd7-215">[**証明書ストア**] ページで、エッジサーバーの外部インターフェイスに対して要求およびインポートされた公開証明書を選びます。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-215">On the **Certificate Store** page, select the public certificate that you requested and imported for the external interface of the Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8ecd7-216">要求およびインポートされた証明書が一覧にない場合は、トラブルシューティングの方法の1つとして、証明書のサブジェクト名とサブジェクトの代替名が証明書のすべての要件を満たしていることを確認します。証明書と証明書チェーン上記の手順を使用する代わりに、証明書が適切な証明書ストア (ユーザーまたはサービス証明書ストアではなく、コンピューターの証明書ストア) に含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-216">If the certificate you requested and imported is not in the list, one of the trouble shooting methods is to verify that subject name and subject alternative names of the certificate meet all requirements for the certificate and, if you manually imported the certificate and certificate chain instead of using the preceding procedures, that the certificate is in the correct certificate store (the computer certificate store, not the user or service certificate store).</span></span>

    
    </div>

6.  <span data-ttu-id="8ecd7-217">[**証明書の割り当ての概要**] ページで、設定を確認し、[**次へ**] をクリックして証明書を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-217">On the **Certificate Assignment Summary** page, review your settings, and then click **Next** to assign the certificates.</span></span>

7.  <span data-ttu-id="8ecd7-218">ウィザードの完了ページで [**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-218">On the wizard completion page, click **Finish**.</span></span>

8.  <span data-ttu-id="8ecd7-219">この手順を実行してエッジ証明書を割り当てると、各サーバーで証明書スナップインを開き、[**証明書 (ローカルコンピューター)**]、[**個人**]、[**証明書**] の順に展開して、[詳細] ウィンドウで、証明書が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-219">After using this procedure to assign the edge certificate, open the Certificate snap-in on each server, expand **Certificates (Local computer)**, expand **Personal**, click **Certificates**, and then verify in the details pane that the certificate is listed.</span></span>

9.  <span data-ttu-id="8ecd7-220">展開に複数のエッジサーバーが含まれている場合は、各エッジサーバーに対してこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="8ecd7-220">If your deployment includes multiple Edge Servers, repeat this procedure for each Edge Server.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

