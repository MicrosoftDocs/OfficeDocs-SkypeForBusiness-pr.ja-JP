---
title: リバース HTTP プロキシ用の証明書の要求と構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Request and configure a certificate for your reverse HTTP proxy
ms:assetid: 4b70991e-5f10-40a3-b069-0b227c3a3a0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429704(v=OCS.15)
ms:contentKeyID: 48184085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ffe1ce6a4b206b927b2fcdec4c02b905e01d5bd1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823309"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-and-configure-a-certificate-for-your-reverse-http-proxy-in-lync-server-2013"></a><span data-ttu-id="e2b17-102">Lync Server 2013 でのリバース HTTP プロキシ用の証明書の要求と構成</span><span class="sxs-lookup"><span data-stu-id="e2b17-102">Request and configure a certificate for your reverse HTTP proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2b17-103">_**最終更新日:** 2014-02-14_</span><span class="sxs-lookup"><span data-stu-id="e2b17-103">_**Topic Last Modified:** 2014-02-14_</span></span>

<span data-ttu-id="e2b17-104">Microsoft Lync を実行している内部サーバーにサーバー証明書を発行した CA インフラストラクチャの、Microsoft Forefront Threat Management ゲートウェイ2010または IIS ARR を実行しているサーバーに、ルート証明機関 (CA) 証明書をインストールする必要があります。サーバー2013。</span><span class="sxs-lookup"><span data-stu-id="e2b17-104">You need to install the root certification authority (CA) certificate on the server running Microsoft Forefront Threat Management Gateway 2010 or IIS ARR for the CA infrastructure that issued the server certificates to the internal servers running Microsoft Lync Server 2013.</span></span>

<span data-ttu-id="e2b17-105">また、リバースプロキシサーバーに公開 web サーバー証明書をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2b17-105">You also must install a public web server certificate on your reverse proxy server.</span></span> <span data-ttu-id="e2b17-106">この証明書のサブジェクトの名前には、リモートアクセスが有効になっている各プールの公開された外部完全修飾ドメイン名 (Fqdn) と、その中で使用されるすべてのディレクターまたはディレクタープールの外部 Fqdn が含まれている必要があります。このエッジインフラストラクチャ。</span><span class="sxs-lookup"><span data-stu-id="e2b17-106">This certificate’s subject alternative names should contain the published external fully qualified domain names (FQDNs) of each pool that is home to users enabled for remote access, and the external FQDNs of all Directors or Director pools that will be used within that Edge infrastructure.</span></span> <span data-ttu-id="e2b17-107">[件名の代替名] には、会議の単純な URL、ダイヤルインの単純な URL、および次の表に示すように、自動検出サービスの URL が含まれている場合もあります。</span><span class="sxs-lookup"><span data-stu-id="e2b17-107">The subject alternative name must also contain the meeting simple URL, the dial-in simple URL, and, if you are deploying mobile applications and plan to use automatic discovery, the external Autodiscover Service URL as shown in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="e2b17-108">値</span><span class="sxs-lookup"><span data-stu-id="e2b17-108">Value</span></span></th>
<th><span data-ttu-id="e2b17-109">例</span><span class="sxs-lookup"><span data-stu-id="e2b17-109">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e2b17-110">サブジェクト名</span><span class="sxs-lookup"><span data-stu-id="e2b17-110">Subject name</span></span></p></td>
<td><p><span data-ttu-id="e2b17-111">プールの FQDN</span><span class="sxs-lookup"><span data-stu-id="e2b17-111">Pool FQDN</span></span></p></td>
<td><p><span data-ttu-id="e2b17-112">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e2b17-112">webext.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2b17-113">サブジェクトの別名</span><span class="sxs-lookup"><span data-stu-id="e2b17-113">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="e2b17-114">プールの FQDN</span><span class="sxs-lookup"><span data-stu-id="e2b17-114">Pool FQDN</span></span></p></td>
<td><p><span data-ttu-id="e2b17-115">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e2b17-115">webext.contoso.com</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="e2b17-116">サブジェクト名は、サブジェクトの代替名にも含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2b17-116">The subject name must also be present in the subject alternative name.</span></span>

</td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2b17-117">サブジェクトの別名</span><span class="sxs-lookup"><span data-stu-id="e2b17-117">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="e2b17-118">オプションのディレクター Web サービス (ディレクターが展開されている場合)</span><span class="sxs-lookup"><span data-stu-id="e2b17-118">Optional Director Web Services (if Director is deployed)</span></span></p></td>
<td><p><span data-ttu-id="e2b17-119">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e2b17-119">webdirext.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2b17-120">サブジェクトの別名</span><span class="sxs-lookup"><span data-stu-id="e2b17-120">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="e2b17-121">会議の単純な URL</span><span class="sxs-lookup"><span data-stu-id="e2b17-121">Meeting simple URL</span></span></p>



> [!NOTE]
> <span data-ttu-id="e2b17-122">すべての会議の単純な Url は、件名の代替名に含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2b17-122">All meeting simple URLs must be in the subject alternative name.</span></span> <span data-ttu-id="e2b17-123">各 SIP ドメインには、少なくとも1つのアクティブな会議の単純な URL が必要です。</span><span class="sxs-lookup"><span data-stu-id="e2b17-123">Each SIP domain must have at least one active meeting simple URL.</span></span>

</td>
<td><p><span data-ttu-id="e2b17-124">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e2b17-124">meet.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2b17-125">サブジェクトの別名</span><span class="sxs-lookup"><span data-stu-id="e2b17-125">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="e2b17-126">ダイヤルインの簡易 URL</span><span class="sxs-lookup"><span data-stu-id="e2b17-126">Dial-in simple URL</span></span></p></td>
<td><p><span data-ttu-id="e2b17-127">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e2b17-127">dialin.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2b17-128">サブジェクトの別名</span><span class="sxs-lookup"><span data-stu-id="e2b17-128">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="e2b17-129">Office Web Apps サーバー</span><span class="sxs-lookup"><span data-stu-id="e2b17-129">Office Web Apps Server</span></span></p></td>
<td><p><span data-ttu-id="e2b17-130">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e2b17-130">officewebapps01.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2b17-131">サブジェクトの別名</span><span class="sxs-lookup"><span data-stu-id="e2b17-131">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="e2b17-132">外部自動検出サービスの URL</span><span class="sxs-lookup"><span data-stu-id="e2b17-132">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="e2b17-133">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e2b17-133">lyncdiscover.contoso.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="e2b17-134">Microsoft Exchange Server も使用している場合は、Exchange の自動検出と web サービスの Url に対してリバースプロキシルールを構成する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="e2b17-134">If you are also using Microsoft Exchange Server you will also need to configure reverse proxy rules for the Exchange autodiscover and web services URLs.</span></span>

</td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> <span data-ttu-id="e2b17-135">内部展開が複数の Standard Edition サーバーまたはフロントエンドプールで構成されている場合は、外部 web ファームの各 FQDN に対して web 公開ルールを構成する必要があります。また、それぞれに対して証明書と web リスナーが必要です。または、証明書を取得する必要があります。サブジェクトの別名には、すべてのプールで使用される名前が含まれているため、web リスナーに割り当て、複数の web 公開ルールで共有することができます。</span><span class="sxs-lookup"><span data-stu-id="e2b17-135">If your internal deployment consists of more than one Standard Edition server or Front End pool, you must configure web publishing rules for each external web farm FQDN and you will either need a certificate and web listener for each, or you must obtain a certificate whose subject alternative name contains the names used by all of the pools, assign it to a web listener, and share it among multiple web publishing rules.</span></span>



</div>

<div>

## <a name="create-a-certificate-request"></a><span data-ttu-id="e2b17-136">証明書の要求を作成する</span><span class="sxs-lookup"><span data-stu-id="e2b17-136">Create a Certificate Request</span></span>

<span data-ttu-id="e2b17-137">リバースプロキシで証明書要求を作成します。</span><span class="sxs-lookup"><span data-stu-id="e2b17-137">You create a certificate request on the reverse proxy.</span></span> <span data-ttu-id="e2b17-138">別のコンピューターで要求を作成した場合、公開された証明機関から署名された証明書を取得したら、秘密キーを使って署名された証明書をエクスポートして、リバースプロキシにインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2b17-138">You create a request on another computer, but you must export the signed certificate with the private key and import it onto the reverse proxy once you have received it from the public certification authority.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="e2b17-139">証明書の要求または証明書署名要求 (CSR) は、要求するコンピューターの公開キーを確認して署名するための、信頼できる公開証明機関 (CA) への要求です。</span><span class="sxs-lookup"><span data-stu-id="e2b17-139">A certificate request or a certificate signing request (CSR) is a request to a trusted public certification authority (CA) to validate and sign the requesting computer’s public key.</span></span> <span data-ttu-id="e2b17-140">証明書が生成されると、公開キーと秘密キーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="e2b17-140">When a certificate is generated, a public key and a private key are created.</span></span> <span data-ttu-id="e2b17-141">公開キーのみが共有され、署名されます。</span><span class="sxs-lookup"><span data-stu-id="e2b17-141">Only the public key is shared and signed.</span></span> <span data-ttu-id="e2b17-142">名前が示すように、公開キーはどのパブリック要求でも利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="e2b17-142">As the name implies, the public key is made available to any public request.</span></span> <span data-ttu-id="e2b17-143">公開キーは、クライアント、サーバー、および情報を安全に交換し、コンピューターの id を検証する必要があるその他の要求者によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="e2b17-143">The public key is for use by clients, servers and other requesters that need to exchange information securely and validate a computer’s identity.</span></span> <span data-ttu-id="e2b17-144">秘密キーはセキュリティで保護された状態であり、公開キーで暗号化されたメッセージの暗号化を解除するキーペアを作成したコンピューターによってのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="e2b17-144">The private key is kept secured and is used only by the computer that created the key pair to decrypt messages encrypted with its public key.</span></span> <span data-ttu-id="e2b17-145">秘密キーを他の目的で使うことができます。</span><span class="sxs-lookup"><span data-stu-id="e2b17-145">The private key can be used for other purposes.</span></span> <span data-ttu-id="e2b17-146">リバースプロキシを目的として、データの暗号化は主要な用途です。</span><span class="sxs-lookup"><span data-stu-id="e2b17-146">For reverse proxy purposes, data encipherment is the primary use.</span></span> <span data-ttu-id="e2b17-147">Secondarily は、証明書のキーレベルでの証明書の認証は別の用途であり、要求者にコンピューターの公開キーが設定されていること、または公開キーを持っているコンピューターが実際に要求するコンピューターとして使用されることが制限されます。</span><span class="sxs-lookup"><span data-stu-id="e2b17-147">Secondarily, the certificate authentication at the certificate key level is another use, and is limited only to validation that a requester has the computer’s public key, or that the computer that you have a public key for is actually the computer that it claims to be.</span></span>



</div>

<div>


> [!TIP]
> <span data-ttu-id="e2b17-148">エッジサーバー証明書とリバースプロキシ証明書を同時に計画している場合は、2つの証明書要件の間に大きな類似性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e2b17-148">If you plan your Edge Server certificates and your reverse proxy certificates at the same time, you should notice that there is a great deal of similarity between the two certificate requirements.</span></span> <span data-ttu-id="e2b17-149">エッジサーバーの証明書を構成して要求するときは、Edge サーバーと逆プロキシのサブジェクトの代替名を結合します。</span><span class="sxs-lookup"><span data-stu-id="e2b17-149">When you configure and request your Edge Server certificate, combine the Edge Server and the reverse proxy subject alternative names.</span></span> <span data-ttu-id="e2b17-150">証明書と秘密キーをエクスポートし、エクスポートされたファイルをリバースプロキシにコピーしてから、証明書とキーのペアをインポートして、今後の手順で必要に応じて割り当てることができる場合は、リバースプロキシに対して同じ証明書を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e2b17-150">You can use the same certificate for your reverse proxy if you export the certificate and the private key and copy the exported file to the reverse proxy and then import the certificate/key pair and assign it as needed in the upcoming procedures.</span></span> <span data-ttu-id="e2b17-151">「Lync server&nbsp;<A href="lync-server-2013-plan-for-edge-server-certificates.md">2013 のエッジサーバーの証明</A>書」および「リバースプロキシ<A href="lync-server-2013-certificate-summary-reverse-proxy.md">証明書の概要-lync server 2013 のリバースプロキシ</A>」の「エッジサーバーの証明書の要件」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2b17-151">Refer to the certificate requirements for the Edge Server&nbsp;<A href="lync-server-2013-plan-for-edge-server-certificates.md">Plan for Edge Server certificates in Lync Server 2013</A> and the reverse proxy <A href="lync-server-2013-certificate-summary-reverse-proxy.md">Certificate summary - Reverse proxy in Lync Server 2013</A>.</span></span> <span data-ttu-id="e2b17-152">エクスポート可能な秘密キーを使用して証明書を作成していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="e2b17-152">Make sure that you create the certificate with an exportable private key.</span></span> <span data-ttu-id="e2b17-153">プールされたエッジサーバーには、エクスポート可能な秘密キーを使用して証明書と証明書の要求を作成する必要があるため、これは通常の方法であり、エッジサーバーの Lync Server 展開ウィザードの証明書ウィザードでは、このように設定することができます。 <STRONG>エクスポート可能な秘密キー</STRONG>フラグ。</span><span class="sxs-lookup"><span data-stu-id="e2b17-153">Creating the certificate and certificate request with an exportable private key is required for pooled Edge Servers, so this is a normal practice and the Certificate Wizard in the Lync Server Deployment Wizard for the Edge Server will allow you to set the <STRONG>Make private key exportable</STRONG> flag.</span></span> <span data-ttu-id="e2b17-154">公開証明機関から証明書の要求を受信すると、証明書と秘密キーがエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="e2b17-154">Once you receive the certificate request back from the public certification authority, you will export the certificate and the private key.</span></span> <span data-ttu-id="e2b17-155">秘密キーを使って証明書を作成してエクスポートする方法について詳しくは、「 <A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">Lync Server 2013 の外部エッジインターフェイスの</A>証明書を設定する」の「プール内のエッジサーバーの秘密キーを使って証明書をエクスポートする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2b17-155">See the section “To export the certificate with the private key for Edge Servers in a pool” in the topic <A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">Set up certificates for the external edge interface for Lync Server 2013</A> for details on how to create and export your certificate with a private key.</span></span> <span data-ttu-id="e2b17-156">証明書の拡張子は<STRONG>.pfx</STRONG>である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2b17-156">The extension of the certificate should be of type <STRONG>.pfx</STRONG>.</span></span>



</div>

<span data-ttu-id="e2b17-157">証明書と秘密キーが割り当てられているコンピューター上で証明書署名要求を生成するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e2b17-157">To generate a certificate signing request on the computer where the certificate and private key will be assigned, you do the following:</span></span>

<span data-ttu-id="e2b17-158">**証明書署名要求の作成**</span><span class="sxs-lookup"><span data-stu-id="e2b17-158">**Creating a certificate signing request**</span></span>

1.  <span data-ttu-id="e2b17-159">Microsoft 管理コンソール (MMC) を開き、証明書スナップインを追加して、[**コンピューター**]、[**個人**] の順に展開します。</span><span class="sxs-lookup"><span data-stu-id="e2b17-159">Open the Microsoft Management Console (MMC) and add the Certificates snap-in and select **Computers**, then expand **Personal**.</span></span> <span data-ttu-id="e2b17-160">Microsoft 管理コンソール (MMC) で証明書コンソールを作成する方法について詳しくは[http://go.microsoft.com/fwlink/?LinkId=282616](http://go.microsoft.com/fwlink/?linkid=282616)、「」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e2b17-160">For details on how to create a certificates console in the Microsoft Management Console (MMC), see [http://go.microsoft.com/fwlink/?LinkId=282616](http://go.microsoft.com/fwlink/?linkid=282616).</span></span>

2.  <span data-ttu-id="e2b17-161">[**証明書**] を右クリックし、[**すべてのタスク**]、[**詳細操作**]、[**カスタム要求の作成**] の順序でクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2b17-161">Right-click **Certificates**, click **All Tasks**, click **Advanced Operations**, click **Create Custom Request**.</span></span>

3.  <span data-ttu-id="e2b17-162">[**証明書の登録**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2b17-162">On the **Certificate Enrollment** page, click **Next**.</span></span>

4.  <span data-ttu-id="e2b17-163">[**カスタム要求**] の [**証明書の登録ポリシーの選択**] ページで、[**登録ポリシーなしで続行**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2b17-163">On the **Select Certificate Enrollment Policy** page under **Custom Request**, select **Proceed without enrollment policy**.</span></span> <span data-ttu-id="e2b17-164">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2b17-164">Click **Next**.</span></span>

5.  <span data-ttu-id="e2b17-165">[**カスタム要求**] ページの [**テンプレート**] で、[**レガシキーの選択 (テンプレートなし)**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="e2b17-165">On the **Custom Request** page, for **Template** select **(No template) Legacy key**.</span></span> <span data-ttu-id="e2b17-166">証明書プロバイダーによって指示されていない限り、[**既定の拡張子**を表示しない] をオフのままにし、 **PKCS \#10**で**要求形式**を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2b17-166">Unless otherwise directed by your certificate provider, leave **Suppress default extensions** unchecked and the **Request format** selection on **PKCS \#10**.</span></span> <span data-ttu-id="e2b17-167">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2b17-167">Click **Next**.</span></span>

6.  <span data-ttu-id="e2b17-168">[**証明書情報**] ページで、[**詳細**] をクリックし、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2b17-168">On the **Certificate Information** page, click **Details**, then click **Properties**.</span></span>

7.  <span data-ttu-id="e2b17-169">[**証明書のプロパティ**] ページ\*\*\*\* の [**フレンドリ名**] フィールドに、この証明書の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="e2b17-169">On the **Certificate Properties** page on the **General** tab in the **Friendly Name** field, type a name for this certificate.</span></span> <span data-ttu-id="e2b17-170">必要に応じて、[**説明**] フィールドに説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="e2b17-170">Optionally, type a description in the **Description** field.</span></span> <span data-ttu-id="e2b17-171">フレンドリ名と説明は、通常、管理者が証明書の目的 ( **Lync Server のリバースプロキシリスナー**など) を識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e2b17-171">The Friendly Name and description are typically used by the Administrator to identify what the certificate purpose is, such as **Reverse Proxy Listener for Lync Server**.</span></span>

8.  <span data-ttu-id="e2b17-172">[**件名**] タブを選択します。[**種類**] の [**サブジェクト名**] で、[サブジェクト名] の [**共通名**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2b17-172">Select the **Subject** tab. Under **Subject name** for the **Type**, select **Common name** for the Subject name type.</span></span> <span data-ttu-id="e2b17-173">この**値**には、リバースプロキシに使用するサブジェクト名を入力し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2b17-173">For the **Value**, type the subject name that you will use for the reverse proxy, and then click **Add**.</span></span> <span data-ttu-id="e2b17-174">このトピックの表に示した例では、サブジェクト名は webext.contoso.com であり、サブジェクト名の値フィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="e2b17-174">In the example provided in the table in this topic, the subject name is webext.contoso.com and would be typed into the Value field for the Subject name.</span></span>

9.  <span data-ttu-id="e2b17-175">[**件名**] タブの [**代替名**] で、[**種類**] のドロップダウンから [ **DNS** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="e2b17-175">On the **Subject** tab under **Alternative name**, select **DNS** from the drop down for **Type**.</span></span> <span data-ttu-id="e2b17-176">証明書に必要な定義されたサブジェクトの代替名ごとに、完全修飾ドメイン名を入力し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2b17-176">For each defined subject alternative name that you require on the certificate, type the fully qualified domain name, then click **Add**.</span></span> <span data-ttu-id="e2b17-177">たとえば、表に、meet.contoso.com、dialin.contoso.com、lyncdiscover.contoso.com という3つのサブジェクトの代替名があります。</span><span class="sxs-lookup"><span data-stu-id="e2b17-177">For example, in the table there are three subject alternative names, meet.contoso.com, dialin.contoso.com, and lyncdiscover.contoso.com.</span></span> <span data-ttu-id="e2b17-178">[**値**] フィールドに「meet.contoso.com」と入力して、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2b17-178">In the **Value** field, type meet.contoso.com, then click **Add**.</span></span> <span data-ttu-id="e2b17-179">定義する必要があるサブジェクト別の名前ごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="e2b17-179">Repeat for each subject alternative names that you need to define.</span></span>

10. <span data-ttu-id="e2b17-180">[**証明書のプロパティ**] ページで、[**拡張機能**] タブをクリックします。このページでは、**キー使用**時に暗号化キーの目的を定義し、**拡張キー使用法 (アプリケーションポリシー)** で拡張キー使用法を使用します。</span><span class="sxs-lookup"><span data-stu-id="e2b17-180">On the **Certificate Properties** page, click the **Extensions** tab. On this page, you will define the cryptographic key purposes in **Key usage** and the extended key usage in **Extended Key Usage (application policies)**.</span></span>

11. <span data-ttu-id="e2b17-181">**使用可能なオプション**を表示するには、**キー使用**の矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2b17-181">Click the **Key usage** arrow to show the **Available options**.</span></span> <span data-ttu-id="e2b17-182">[使用できるオプション] で [**デジタル署名**] をクリックし、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2b17-182">Under Available options, click **Digital signature**, then click **Add**.</span></span> <span data-ttu-id="e2b17-183">[**キーの暗号化**] をクリックし、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2b17-183">Click **Key encipherment**, then click **Add**.</span></span> <span data-ttu-id="e2b17-184">[**次のキーの使用を必須**にする] チェックボックスがオフになっている場合は、チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="e2b17-184">If the checkbox for **Make these key usages critical** is unchecked, select the checkbox.</span></span>

12. <span data-ttu-id="e2b17-185">[**拡張キー使用法 (アプリケーションポリシー)** ] の矢印をクリックして、**利用可能なオプション**を表示します。</span><span class="sxs-lookup"><span data-stu-id="e2b17-185">Click the **Extended Key Usage (application policies)** arrow to show the **Available options**.</span></span> <span data-ttu-id="e2b17-186">[使用可能なオプション] で [**サーバー認証**] をクリックし、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2b17-186">Under Available options, click **Server Authentication**, then click **Add**.</span></span> <span data-ttu-id="e2b17-187">[**クライアント認証**] をクリックし、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2b17-187">Click **Client Authentication**, then click **Add**.</span></span> <span data-ttu-id="e2b17-188">[**拡張キーの使用を確認**する] チェックボックスがオンになっている場合は、チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="e2b17-188">If the check box for **Make the Extended Key Usages critical** is checked, unselect the checkbox.</span></span> <span data-ttu-id="e2b17-189">[キーの使用方法] チェックボックス (オンにする必要があります) とは異なり、[拡張キー使用] チェックボックスがオフになっていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2b17-189">Contrary to the Key usage checkbox (which must be checked) you must be sure that the Extended Key Usage checkbox is not checked.</span></span>

13. <span data-ttu-id="e2b17-190">[**証明書のプロパティ**] ページで、[**秘密キー** ] タブをクリックします。 [**キーオプション**] の矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2b17-190">On the **Certificate Properties** page, click the **Private Key** tab. Click the **Key options** arrow.</span></span> <span data-ttu-id="e2b17-191">[**キーサイズ**] で、ドロップダウンから [ **2048** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="e2b17-191">For **Key size**, select **2048** from the drop down.</span></span> <span data-ttu-id="e2b17-192">この証明書の目的であるリバースプロキシ以外のコンピューターでこのキーペアと CSR を作成する場合は、[**秘密キーをエクスポート**可能にする] を選びます。</span><span class="sxs-lookup"><span data-stu-id="e2b17-192">If you are generating this key pair and CSR on a computer other than the reverse proxy that this certificate is intended for, select **Make private key exportable**.</span></span>
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="証券" alt="security" /><span data-ttu-id="e2b17-194">セキュリティメモ:</span><span class="sxs-lookup"><span data-stu-id="e2b17-194">Security Note:</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="e2b17-195">ファーム内の各コンピューターに証明書と秘密キーをコピーするので、通常は、ファーム内に複数の逆プロキシがある場合に、[<strong>エクスポート可能な秘密キーを作成</strong>する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2b17-195">Selecting <strong>Make a private key exportable</strong> is generally advised when you have more than one reverse proxy in a farm because you will copy the certificate and the private key to each machine in the farm.</span></span> <span data-ttu-id="e2b17-196">エクスポート可能な秘密キーの使用を許可する場合は、証明書とそれが生成されるコンピューターについて特別な注意を払う必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2b17-196">If you do allow for an exportable private key, you must take extra care with the certificate and the computer that it is generated on.</span></span> <span data-ttu-id="e2b17-197">秘密キーが侵害されると、その証明書は無意味になり、コンピューターやコンピューターが外部アクセスやその他のセキュリティの脆弱性にさらされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e2b17-197">The private key, if compromised, will render the certificate useless as well as potentially expose the computer or computers to external access and other security vulnerabilities.</span></span></td>
    </tr>
    </tbody>
    </table>
    
    </div>

14. <span data-ttu-id="e2b17-198">[**秘密キー** ] タブで、[**キーの種類**] の矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2b17-198">On the **Private Key** tab, click the **Key type** arrow.</span></span> <span data-ttu-id="e2b17-199">[ **Exchange** ] オプションを選びます。</span><span class="sxs-lookup"><span data-stu-id="e2b17-199">Select the **Exchange** option.</span></span>

15. <span data-ttu-id="e2b17-200">[ **OK** ] をクリックして、設定した**証明書のプロパティ**を保存します。</span><span class="sxs-lookup"><span data-stu-id="e2b17-200">Click **OK** to save the **Certificate Properties** that you have set.</span></span>

16. <span data-ttu-id="e2b17-201">[**証明書の登録**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2b17-201">On the **Certificate Enrollment** page, click **Next**.</span></span>

17. <span data-ttu-id="e2b17-202">[**オフライン要求を保存しますか?** ] ページで、証明書署名要求を保存するための**ファイル名**と**ファイル形式を指定**するように求められます。</span><span class="sxs-lookup"><span data-stu-id="e2b17-202">On the **Where do you want to save the offline request?** page, you are prompted for a **File Name** and a **File Format** for saving the certificate signing request.</span></span>

18. <span data-ttu-id="e2b17-203">[**ファイル名**エントリ] フィールドに要求のパスとファイル名を入力するか、[**参照**] をクリックしてファイルの場所を選択し、要求のファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="e2b17-203">In the **File Name** entry field, type a path and filename for the request, or click **Browse** to select a location for the file and type the filename for the request.</span></span>

19. <span data-ttu-id="e2b17-204">**ファイル形式**については、**ベース 64**または**バイナリ**のいずれかをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2b17-204">For **File format**, click either **Base 64** or **Binary**.</span></span> <span data-ttu-id="e2b17-205">証明書のベンダーによって指示されている場合を除き、[**ベース 64** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="e2b17-205">Select **Base 64** unless you are instructed otherwise by the vendor for your certificates.</span></span>

20. <span data-ttu-id="e2b17-206">前の手順で保存した要求ファイルを見つけます。</span><span class="sxs-lookup"><span data-stu-id="e2b17-206">Locate the request file that you saved in the previous step.</span></span> <span data-ttu-id="e2b17-207">公開証明機関に提出します。</span><span class="sxs-lookup"><span data-stu-id="e2b17-207">Submit to your public certification authority.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="e2b17-208">Microsoft は、統合された通信目的の要件を満たすパブリック Ca を特定しました。</span><span class="sxs-lookup"><span data-stu-id="e2b17-208">Microsoft has identified Public CAs that meets the requirements for Unified Communications purposes.</span></span> <span data-ttu-id="e2b17-209">リストは、次のサポート技術情報の記事に記載されています。</span><span class="sxs-lookup"><span data-stu-id="e2b17-209">A list is maintained in the following knowledge base article.</span></span> <A href="http://go.microsoft.com/fwlink/?linkid=282625">http://go.microsoft.com/fwlink/?LinkId=282625</A>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

