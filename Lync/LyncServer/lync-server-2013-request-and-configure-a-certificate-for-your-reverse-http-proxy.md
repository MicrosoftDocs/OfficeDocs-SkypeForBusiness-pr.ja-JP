---
title: リバース HTTP プロキシの証明書を要求および構成する
description: リバース HTTP プロキシの証明書を要求して構成します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request and configure a certificate for your reverse HTTP proxy
ms:assetid: 4b70991e-5f10-40a3-b069-0b227c3a3a0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429704(v=OCS.15)
ms:contentKeyID: 48184085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bdeaa080e3ccb6a9895e18a6ac02084e99a1e33e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579043"
---
# <a name="request-and-configure-a-certificate-for-your-reverse-http-proxy-in-lync-server-2013"></a><span data-ttu-id="ac64a-103">Lync Server 2013 でのリバース HTTP プロキシの証明書の要求と構成</span><span class="sxs-lookup"><span data-stu-id="ac64a-103">Request and configure a certificate for your reverse HTTP proxy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac64a-104">_**トピックの最終更新日:** 2014-02-14_</span><span class="sxs-lookup"><span data-stu-id="ac64a-104">_**Topic Last Modified:** 2014-02-14_</span></span>

<span data-ttu-id="ac64a-105">Microsoft Lync Server 2013 を実行している内部サーバーにサーバー証明書を発行した CA インフラストラクチャの、Microsoft Forefront Threat Management Gateway 2010 または IIS ARR を実行しているサーバーに、ルート証明機関 (CA) 証明書をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac64a-105">You need to install the root certification authority (CA) certificate on the server running Microsoft Forefront Threat Management Gateway 2010 or IIS ARR for the CA infrastructure that issued the server certificates to the internal servers running Microsoft Lync Server 2013.</span></span>

<span data-ttu-id="ac64a-106">また、リバースプロキシサーバーには、パブリック web サーバー証明書をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac64a-106">You also must install a public web server certificate on your reverse proxy server.</span></span> <span data-ttu-id="ac64a-107">この証明書のサブジェクトの別名には、リモートアクセスが有効になっているユーザーの自宅にある各プールの公開外部完全修飾ドメイン名 (Fqdn) と、そのエッジインフラストラクチャ内で使用されるすべてのディレクターまたはディレクタープールの外部 Fqdn が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac64a-107">This certificate’s subject alternative names should contain the published external fully qualified domain names (FQDNs) of each pool that is home to users enabled for remote access, and the external FQDNs of all Directors or Director pools that will be used within that Edge infrastructure.</span></span> <span data-ttu-id="ac64a-108">サブジェクトの別名には、次の表に示すように、会議の簡易 URL、ダイヤルインの簡易 URL、および自動検出の使用を計画している場合は、外部自動検出サービスの URL も含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac64a-108">The subject alternative name must also contain the meeting simple URL, the dial-in simple URL, and, if you are deploying mobile applications and plan to use automatic discovery, the external Autodiscover Service URL as shown in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="ac64a-109">値</span><span class="sxs-lookup"><span data-stu-id="ac64a-109">Value</span></span></th>
<th><span data-ttu-id="ac64a-110">例</span><span class="sxs-lookup"><span data-stu-id="ac64a-110">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ac64a-111">サブジェクト名</span><span class="sxs-lookup"><span data-stu-id="ac64a-111">Subject name</span></span></p></td>
<td><p><span data-ttu-id="ac64a-112">プールの FQDN</span><span class="sxs-lookup"><span data-stu-id="ac64a-112">Pool FQDN</span></span></p></td>
<td><p><span data-ttu-id="ac64a-113">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ac64a-113">webext.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac64a-114">サブジェクト名の別名</span><span class="sxs-lookup"><span data-stu-id="ac64a-114">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="ac64a-115">プールの FQDN</span><span class="sxs-lookup"><span data-stu-id="ac64a-115">Pool FQDN</span></span></p></td>
<td><p><span data-ttu-id="ac64a-116">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ac64a-116">webext.contoso.com</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="ac64a-117">サブジェクト名は、サブジェクトの別名にも存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac64a-117">The subject name must also be present in the subject alternative name.</span></span>

</td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac64a-118">サブジェクト名の別名</span><span class="sxs-lookup"><span data-stu-id="ac64a-118">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="ac64a-119">オプションのディレクター Web サービス (ディレクターが展開されている場合)</span><span class="sxs-lookup"><span data-stu-id="ac64a-119">Optional Director Web Services (if Director is deployed)</span></span></p></td>
<td><p><span data-ttu-id="ac64a-120">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ac64a-120">webdirext.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac64a-121">サブジェクト名の別名</span><span class="sxs-lookup"><span data-stu-id="ac64a-121">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="ac64a-122">会議の簡易 URL</span><span class="sxs-lookup"><span data-stu-id="ac64a-122">Meeting simple URL</span></span></p>



> [!NOTE]
> <span data-ttu-id="ac64a-123">すべての会議の簡易 Url は、サブジェクトの別名にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac64a-123">All meeting simple URLs must be in the subject alternative name.</span></span> <span data-ttu-id="ac64a-124">各 SIP ドメインには、少なくとも1つのアクティブな会議の簡易 URL が必要です。</span><span class="sxs-lookup"><span data-stu-id="ac64a-124">Each SIP domain must have at least one active meeting simple URL.</span></span>

</td>
<td><p><span data-ttu-id="ac64a-125">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ac64a-125">meet.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac64a-126">サブジェクト名の別名</span><span class="sxs-lookup"><span data-stu-id="ac64a-126">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="ac64a-127">簡単なダイヤルイン URL</span><span class="sxs-lookup"><span data-stu-id="ac64a-127">Dial-in simple URL</span></span></p></td>
<td><p><span data-ttu-id="ac64a-128">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ac64a-128">dialin.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac64a-129">サブジェクト名の別名</span><span class="sxs-lookup"><span data-stu-id="ac64a-129">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="ac64a-130">Office Web Apps サーバー</span><span class="sxs-lookup"><span data-stu-id="ac64a-130">Office Web Apps Server</span></span></p></td>
<td><p><span data-ttu-id="ac64a-131">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ac64a-131">officewebapps01.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac64a-132">サブジェクト名の別名</span><span class="sxs-lookup"><span data-stu-id="ac64a-132">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="ac64a-133">外部自動検出サービス URL</span><span class="sxs-lookup"><span data-stu-id="ac64a-133">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="ac64a-134">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ac64a-134">lyncdiscover.contoso.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="ac64a-135">Microsoft Exchange Server も使用している場合は、Exchange の自動検出と web サービスの Url に対してリバースプロキシルールを構成する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="ac64a-135">If you are also using Microsoft Exchange Server you will also need to configure reverse proxy rules for the Exchange autodiscover and web services URLs.</span></span>

</td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> <span data-ttu-id="ac64a-136">内部展開が複数の Standard Edition サーバーまたはフロントエンドプールで構成されている場合は、各外部 web ファームの FQDN に対して web 公開ルールを構成する必要があり、それぞれに対して証明書と web リスナーが必要です。または、サブジェクトの別名にすべてのプールで使用される名前が含まれる証明書を取得する複数の web 公開ルール間で共有します。</span><span class="sxs-lookup"><span data-stu-id="ac64a-136">If your internal deployment consists of more than one Standard Edition server or Front End pool, you must configure web publishing rules for each external web farm FQDN and you will either need a certificate and web listener for each, or you must obtain a certificate whose subject alternative name contains the names used by all of the pools, assign it to a web listener, and share it among multiple web publishing rules.</span></span>



</div>

<div>

## <a name="create-a-certificate-request"></a><span data-ttu-id="ac64a-137">証明書要求を作成する</span><span class="sxs-lookup"><span data-stu-id="ac64a-137">Create a Certificate Request</span></span>

<span data-ttu-id="ac64a-138">リバースプロキシで証明書要求を作成します。</span><span class="sxs-lookup"><span data-stu-id="ac64a-138">You create a certificate request on the reverse proxy.</span></span> <span data-ttu-id="ac64a-139">別のコンピューターに対して要求を作成したが、公開証明機関から証明書を受信したら、署名された証明書を秘密キーを使用してエクスポートして、リバースプロキシにインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac64a-139">You create a request on another computer, but you must export the signed certificate with the private key and import it onto the reverse proxy once you have received it from the public certification authority.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="ac64a-140">証明書の要求または証明書の署名要求 (CSR) は、信頼できるパブリック証明機関 (CA) に対する要求であり、要求元のコンピューターの公開キーを検証して署名します。</span><span class="sxs-lookup"><span data-stu-id="ac64a-140">A certificate request or a certificate signing request (CSR) is a request to a trusted public certification authority (CA) to validate and sign the requesting computer’s public key.</span></span> <span data-ttu-id="ac64a-141">証明書が生成されると、公開キーと秘密キーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="ac64a-141">When a certificate is generated, a public key and a private key are created.</span></span> <span data-ttu-id="ac64a-142">公開キーのみが共有および署名されています。</span><span class="sxs-lookup"><span data-stu-id="ac64a-142">Only the public key is shared and signed.</span></span> <span data-ttu-id="ac64a-143">その名前が示すとおり、公開キーは任意のパブリック要求に対して使用可能になります。</span><span class="sxs-lookup"><span data-stu-id="ac64a-143">As the name implies, the public key is made available to any public request.</span></span> <span data-ttu-id="ac64a-144">公開キーは、クライアント、サーバー、および情報を安全に交換し、コンピューターの id を検証する必要があるその他の要求者によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="ac64a-144">The public key is for use by clients, servers and other requesters that need to exchange information securely and validate a computer’s identity.</span></span> <span data-ttu-id="ac64a-145">秘密キーはセキュリティ保護されたままで、キーペアを作成したコンピューターによってのみ使用され、公開キーで暗号化されたメッセージを解読します。</span><span class="sxs-lookup"><span data-stu-id="ac64a-145">The private key is kept secured and is used only by the computer that created the key pair to decrypt messages encrypted with its public key.</span></span> <span data-ttu-id="ac64a-146">秘密キーは他の目的に使用できます。</span><span class="sxs-lookup"><span data-stu-id="ac64a-146">The private key can be used for other purposes.</span></span> <span data-ttu-id="ac64a-147">リバースプロキシを使用する場合、データ暗号化が主な用途となります。</span><span class="sxs-lookup"><span data-stu-id="ac64a-147">For reverse proxy purposes, data encipherment is the primary use.</span></span> <span data-ttu-id="ac64a-148">Secondarily は、証明書キーレベルでの証明書認証は別の使用方法であり、要求者がコンピューターの公開キーを持っているか、または公開キーを持っているコンピューターが実際に要求するコンピューターであることを示す検証にのみ制限されます。</span><span class="sxs-lookup"><span data-stu-id="ac64a-148">Secondarily, the certificate authentication at the certificate key level is another use, and is limited only to validation that a requester has the computer’s public key, or that the computer that you have a public key for is actually the computer that it claims to be.</span></span>



</div>

<div>


> [!TIP]
> <span data-ttu-id="ac64a-149">エッジサーバー証明書とリバースプロキシ証明書を同時に計画する場合は、2つの証明書要件の間に大きな類似性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ac64a-149">If you plan your Edge Server certificates and your reverse proxy certificates at the same time, you should notice that there is a great deal of similarity between the two certificate requirements.</span></span> <span data-ttu-id="ac64a-150">エッジサーバーの証明書を構成して要求するときに、エッジサーバーとリバースプロキシのサブジェクトの別名を結合します。</span><span class="sxs-lookup"><span data-stu-id="ac64a-150">When you configure and request your Edge Server certificate, combine the Edge Server and the reverse proxy subject alternative names.</span></span> <span data-ttu-id="ac64a-151">証明書と秘密キーをエクスポートし、エクスポートしたファイルをリバースプロキシにコピーしてから、証明書とキーの組をインポートして、それを今後の手順で必要に応じて割り当てる場合は、リバースプロキシに対して同じ証明書を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ac64a-151">You can use the same certificate for your reverse proxy if you export the certificate and the private key and copy the exported file to the reverse proxy and then import the certificate/key pair and assign it as needed in the upcoming procedures.</span></span> <span data-ttu-id="ac64a-152">「Lync server &nbsp; <A href="lync-server-2013-plan-for-edge-server-certificates.md">2013 でエッジサーバー証明書を計画</A>する」および「リバースプロキシ<A href="lync-server-2013-certificate-summary-reverse-proxy.md">証明書の概要-Lync server 2013 のリバースプロキシ</A>」の「エッジサーバーの証明書の要件」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac64a-152">Refer to the certificate requirements for the Edge Server&nbsp;<A href="lync-server-2013-plan-for-edge-server-certificates.md">Plan for Edge Server certificates in Lync Server 2013</A> and the reverse proxy <A href="lync-server-2013-certificate-summary-reverse-proxy.md">Certificate summary - Reverse proxy in Lync Server 2013</A>.</span></span> <span data-ttu-id="ac64a-153">必ず、エクスポート可能な秘密キーを使用して証明書を作成してください。</span><span class="sxs-lookup"><span data-stu-id="ac64a-153">Make sure that you create the certificate with an exportable private key.</span></span> <span data-ttu-id="ac64a-154">プールされたエッジサーバーには、エクスポート可能な秘密キーを使用して証明書と証明書の要求を作成する必要があるため、これは通常の方法であり、エッジサーバーの Lync Server 展開ウィザードの証明書ウィザードを使用して、 <STRONG>秘密キーをエクスポート</STRONG> 可能なフラグを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="ac64a-154">Creating the certificate and certificate request with an exportable private key is required for pooled Edge Servers, so this is a normal practice and the Certificate Wizard in the Lync Server Deployment Wizard for the Edge Server will allow you to set the <STRONG>Make private key exportable</STRONG> flag.</span></span> <span data-ttu-id="ac64a-155">公開証明機関から証明書の要求を受信すると、証明書と秘密キーがエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="ac64a-155">Once you receive the certificate request back from the public certification authority, you will export the certificate and the private key.</span></span> <span data-ttu-id="ac64a-156">秘密キーを使用して証明書を作成およびエクスポートする方法については、トピック「 <A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">Lync Server 2013 の外部エッジインターフェイス</A> の証明書のセットアップ」の「プール内のエッジサーバーの秘密キーを使用して証明書をエクスポートするには」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac64a-156">See the section “To export the certificate with the private key for Edge Servers in a pool” in the topic <A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">Set up certificates for the external edge interface for Lync Server 2013</A> for details on how to create and export your certificate with a private key.</span></span> <span data-ttu-id="ac64a-157">証明書の拡張子の種類は <STRONG>.pfx</STRONG>である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac64a-157">The extension of the certificate should be of type <STRONG>.pfx</STRONG>.</span></span>



</div>

<span data-ttu-id="ac64a-158">証明書と秘密キーが割り当てられるコンピューターで証明書の署名要求を生成するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ac64a-158">To generate a certificate signing request on the computer where the certificate and private key will be assigned, you do the following:</span></span>

<span data-ttu-id="ac64a-159">**証明書署名要求の作成**</span><span class="sxs-lookup"><span data-stu-id="ac64a-159">**Creating a certificate signing request**</span></span>

1.  <span data-ttu-id="ac64a-160">Microsoft 管理コンソール (MMC) を開き、証明書スナップインを追加して、[ **コンピューター**]、[ **個人**] の順に展開します。</span><span class="sxs-lookup"><span data-stu-id="ac64a-160">Open the Microsoft Management Console (MMC) and add the Certificates snap-in and select **Computers**, then expand **Personal**.</span></span> <span data-ttu-id="ac64a-161">Microsoft 管理コンソール (MMC) で証明書コンソールを作成する方法の詳細については、「」を参照してください [https://go.microsoft.com/fwlink/?LinkId=282616](https://go.microsoft.com/fwlink/?linkid=282616) 。</span><span class="sxs-lookup"><span data-stu-id="ac64a-161">For details on how to create a certificates console in the Microsoft Management Console (MMC), see [https://go.microsoft.com/fwlink/?LinkId=282616](https://go.microsoft.com/fwlink/?linkid=282616).</span></span>

2.  <span data-ttu-id="ac64a-162">[ **証明書**] を右クリックし、[ **すべてのタスク**]、[ **詳細な操作**]、[ **カスタム要求の作成**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac64a-162">Right-click **Certificates**, click **All Tasks**, click **Advanced Operations**, click **Create Custom Request**.</span></span>

3.  <span data-ttu-id="ac64a-163">[ **証明書の登録** ] ページで、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac64a-163">On the **Certificate Enrollment** page, click **Next**.</span></span>

4.  <span data-ttu-id="ac64a-164">[**カスタム要求**] の [**証明書登録ポリシーの選択**] ページで、[**登録ポリシーなしで続行**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ac64a-164">On the **Select Certificate Enrollment Policy** page under **Custom Request**, select **Proceed without enrollment policy**.</span></span> <span data-ttu-id="ac64a-165">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac64a-165">Click **Next**.</span></span>

5.  <span data-ttu-id="ac64a-166">[ **カスタム要求** ] ページの [ **テンプレート** ] の [ **(テンプレートなし)] レガシキー**。</span><span class="sxs-lookup"><span data-stu-id="ac64a-166">On the **Custom Request** page, for **Template** select **(No template) Legacy key**.</span></span> <span data-ttu-id="ac64a-167">証明書プロバイダーから特に指定されていない限り、 **PKCS \# 10**で [**既定の拡張子**を表示しない] チェックをオフにし、**要求形式**を選択したままにします。</span><span class="sxs-lookup"><span data-stu-id="ac64a-167">Unless otherwise directed by your certificate provider, leave **Suppress default extensions** unchecked and the **Request format** selection on **PKCS \#10**.</span></span> <span data-ttu-id="ac64a-168">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac64a-168">Click **Next**.</span></span>

6.  <span data-ttu-id="ac64a-169">[ **証明書情報** ] ページで、[ **詳細**]、[ **プロパティ**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac64a-169">On the **Certificate Information** page, click **Details**, then click **Properties**.</span></span>

7.  <span data-ttu-id="ac64a-170">[**証明書のプロパティ**] ページの [**フレンドリ名**] フィールドにある [**全般**] タブで、この証明書の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="ac64a-170">On the **Certificate Properties** page on the **General** tab in the **Friendly Name** field, type a name for this certificate.</span></span> <span data-ttu-id="ac64a-171">必要に応じて、[ **説明** ] フィールドに説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="ac64a-171">Optionally, type a description in the **Description** field.</span></span> <span data-ttu-id="ac64a-172">フレンドリ名と説明は、通常、管理者が、証明書の目的を識別するために使用します ( **たとえば、Lync Server のリバースプロキシリスナー**など)。</span><span class="sxs-lookup"><span data-stu-id="ac64a-172">The Friendly Name and description are typically used by the Administrator to identify what the certificate purpose is, such as **Reverse Proxy Listener for Lync Server**.</span></span>

8.  <span data-ttu-id="ac64a-173">[**件名**] タブを選択します。[**種類**] の [**サブジェクト名**] で、サブジェクト名の種類として [**共通名**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ac64a-173">Select the **Subject** tab. Under **Subject name** for the **Type**, select **Common name** for the Subject name type.</span></span> <span data-ttu-id="ac64a-174">**値**には、リバースプロキシに使用するサブジェクト名を入力し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac64a-174">For the **Value**, type the subject name that you will use for the reverse proxy, and then click **Add**.</span></span> <span data-ttu-id="ac64a-175">このトピックの表に示されている例では、サブジェクト名は webext.contoso.com で、サブジェクト名の値フィールドに入力されます。</span><span class="sxs-lookup"><span data-stu-id="ac64a-175">In the example provided in the table in this topic, the subject name is webext.contoso.com and would be typed into the Value field for the Subject name.</span></span>

9.  <span data-ttu-id="ac64a-176">[**代替名**] の [**件名**] タブで、[**種類**] ドロップダウンから [ **DNS** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ac64a-176">On the **Subject** tab under **Alternative name**, select **DNS** from the drop down for **Type**.</span></span> <span data-ttu-id="ac64a-177">証明書に必要な定義済みサブジェクトの別名ごとに、完全修飾ドメイン名を入力し、[ **追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac64a-177">For each defined subject alternative name that you require on the certificate, type the fully qualified domain name, then click **Add**.</span></span> <span data-ttu-id="ac64a-178">たとえば、表には、3つのサブジェクトの別名、meet.contoso.com、dialin.contoso.com、および lyncdiscover.contoso.com があります。</span><span class="sxs-lookup"><span data-stu-id="ac64a-178">For example, in the table there are three subject alternative names, meet.contoso.com, dialin.contoso.com, and lyncdiscover.contoso.com.</span></span> <span data-ttu-id="ac64a-179">[ **値** ] フィールドに「meet.contoso.com」と入力し、[ **追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac64a-179">In the **Value** field, type meet.contoso.com, then click **Add**.</span></span> <span data-ttu-id="ac64a-180">定義する必要があるサブジェクトの別名ごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="ac64a-180">Repeat for each subject alternative names that you need to define.</span></span>

10. <span data-ttu-id="ac64a-181">[ **証明書のプロパティ** ] ページで、[ **拡張機能** ] タブをクリックします。このページでは、キー **使用** 法と拡張キー使用法 **(アプリケーションポリシー)** での暗号化キーの目的を定義します。</span><span class="sxs-lookup"><span data-stu-id="ac64a-181">On the **Certificate Properties** page, click the **Extensions** tab. On this page, you will define the cryptographic key purposes in **Key usage** and the extended key usage in **Extended Key Usage (application policies)**.</span></span>

11. <span data-ttu-id="ac64a-182">[ **キー使用法** ] 矢印をクリックして、 **使用可能なオプション**を表示します。</span><span class="sxs-lookup"><span data-stu-id="ac64a-182">Click the **Key usage** arrow to show the **Available options**.</span></span> <span data-ttu-id="ac64a-183">[選択可能なオプション] で、[ **デジタル署名**] をクリックし、[ **追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac64a-183">Under Available options, click **Digital signature**, then click **Add**.</span></span> <span data-ttu-id="ac64a-184">[ **キーの暗号化**] をクリックし、[ **追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac64a-184">Click **Key encipherment**, then click **Add**.</span></span> <span data-ttu-id="ac64a-185">[ **次のキー使用法を重要** にする] チェックボックスがオフになっている場合は、チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="ac64a-185">If the checkbox for **Make these key usages critical** is unchecked, select the checkbox.</span></span>

12. <span data-ttu-id="ac64a-186">[ **拡張キー使用法 (アプリケーションポリシー)** ] 矢印をクリックして、 **使用可能なオプション**を表示します。</span><span class="sxs-lookup"><span data-stu-id="ac64a-186">Click the **Extended Key Usage (application policies)** arrow to show the **Available options**.</span></span> <span data-ttu-id="ac64a-187">[利用可能なオプション] で、[ **サーバー認証**] をクリックし、[ **追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac64a-187">Under Available options, click **Server Authentication**, then click **Add**.</span></span> <span data-ttu-id="ac64a-188">[ **クライアント認証**] をクリックし、[ **追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac64a-188">Click **Client Authentication**, then click **Add**.</span></span> <span data-ttu-id="ac64a-189">[ **拡張キー使用法を重要** にする] チェックボックスがオンになっている場合は、このチェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="ac64a-189">If the check box for **Make the Extended Key Usages critical** is checked, unselect the checkbox.</span></span> <span data-ttu-id="ac64a-190">[キー使用法] チェックボックス (オンにする必要があります) に反して、[拡張キー使用法] チェックボックスがオフになっていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac64a-190">Contrary to the Key usage checkbox (which must be checked) you must be sure that the Extended Key Usage checkbox is not checked.</span></span>

13. <span data-ttu-id="ac64a-191">**証明書のプロパティ**ページで、[**秘密キー** ] タブをクリックします。[**キーオプション**] 矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac64a-191">On the **Certificate Properties** page, click the **Private Key** tab. Click the **Key options** arrow.</span></span> <span data-ttu-id="ac64a-192">[ **キーサイズ**] で、ドロップダウンから [ **2048** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ac64a-192">For **Key size**, select **2048** from the drop down.</span></span> <span data-ttu-id="ac64a-193">この証明書の対象となるリバースプロキシ以外のコンピューターでこのキーペアと CSR を生成する場合は、[ **秘密キーをエクスポート**可能にする] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ac64a-193">If you are generating this key pair and CSR on a computer other than the reverse proxy that this certificate is intended for, select **Make private key exportable**.</span></span>
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="security" alt="security" /><span data-ttu-id="ac64a-195">セキュリティに関する注意事項:</span><span class="sxs-lookup"><span data-stu-id="ac64a-195">Security Note:</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="ac64a-196">ファーム内の各コンピューターに証明書と秘密キーをコピーするため、ファーム内に複数のリバースプロキシがある場合は、通常、[ <strong>エクスポート可能な秘密キーを作成</strong> する] を選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ac64a-196">Selecting <strong>Make a private key exportable</strong> is generally advised when you have more than one reverse proxy in a farm because you will copy the certificate and the private key to each machine in the farm.</span></span> <span data-ttu-id="ac64a-197">エクスポート可能な秘密キーを許可する場合は、証明書とそれが生成されるコンピューターに特に注意を払う必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac64a-197">If you do allow for an exportable private key, you must take extra care with the certificate and the computer that it is generated on.</span></span> <span data-ttu-id="ac64a-198">秘密キーが侵害された場合、その証明書は無意味なだけでなく、コンピューターが外部アクセスやその他のセキュリティ上の脆弱性にさらされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ac64a-198">The private key, if compromised, will render the certificate useless as well as potentially expose the computer or computers to external access and other security vulnerabilities.</span></span></td>
    </tr>
    </tbody>
    </table>
    
    </div>

14. <span data-ttu-id="ac64a-199">[ **秘密キー** ] タブで、[ **キーの種類** ] 矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac64a-199">On the **Private Key** tab, click the **Key type** arrow.</span></span> <span data-ttu-id="ac64a-200">[ **Exchange** ] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="ac64a-200">Select the **Exchange** option.</span></span>

15. <span data-ttu-id="ac64a-201">[ **OK]** をクリックして、設定した **証明書のプロパティ** を保存します。</span><span class="sxs-lookup"><span data-stu-id="ac64a-201">Click **OK** to save the **Certificate Properties** that you have set.</span></span>

16. <span data-ttu-id="ac64a-202">[ **証明書の登録** ] ページで、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac64a-202">On the **Certificate Enrollment** page, click **Next**.</span></span>

17. <span data-ttu-id="ac64a-203">[ **オフライン要求を保存する場所** ] ページで、証明書の署名要求を保存するための **ファイル名** と **ファイル形式** の入力を求められます。</span><span class="sxs-lookup"><span data-stu-id="ac64a-203">On the **Where do you want to save the offline request?** page, you are prompted for a **File Name** and a **File Format** for saving the certificate signing request.</span></span>

18. <span data-ttu-id="ac64a-204">[ **ファイル名** のエントリ] フィールドに、要求のパスとファイル名を入力するか、[ **参照** ] をクリックしてファイルの場所を選択し、要求のファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="ac64a-204">In the **File Name** entry field, type a path and filename for the request, or click **Browse** to select a location for the file and type the filename for the request.</span></span>

19. <span data-ttu-id="ac64a-205">[ **ファイル形式**] で、[ **基本 64** または **バイナリ**] のどちらかをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac64a-205">For **File format**, click either **Base 64** or **Binary**.</span></span> <span data-ttu-id="ac64a-206">証明書のベンダーによる指示がない限り、[ **ベース 64** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ac64a-206">Select **Base 64** unless you are instructed otherwise by the vendor for your certificates.</span></span>

20. <span data-ttu-id="ac64a-207">前の手順で保存した要求ファイルを見つけます。</span><span class="sxs-lookup"><span data-stu-id="ac64a-207">Locate the request file that you saved in the previous step.</span></span> <span data-ttu-id="ac64a-208">公開証明機関に提出します。</span><span class="sxs-lookup"><span data-stu-id="ac64a-208">Submit to your public certification authority.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="ac64a-209">Microsoft は、ユニファイドコミュニケーションの目的の要件を満たすパブリック Ca を識別しています。</span><span class="sxs-lookup"><span data-stu-id="ac64a-209">Microsoft has identified Public CAs that meets the requirements for Unified Communications purposes.</span></span> <span data-ttu-id="ac64a-210">リストは、次のサポート技術情報の記事で管理されています。</span><span class="sxs-lookup"><span data-stu-id="ac64a-210">A list is maintained in the following knowledge base article.</span></span> <A href="https://go.microsoft.com/fwlink/?linkid=282625">https://go.microsoft.com/fwlink/?LinkId=282625</A>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

