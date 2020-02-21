---
title: Lync Server 2013 で XMPP ゲートウェイを構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway on Lync Server 2013
ms:assetid: c70282e0-b502-47e2-a0be-a32eb1faf99d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721881(v=OCS.15)
ms:contentKeyID: 49733816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b087b04a4f6bbf4b5740dcc28172d3f5312e793e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180720"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-on-lync-server-2013"></a><span data-ttu-id="6f214-102">Lync Server 2013 で XMPP ゲートウェイを構成する</span><span class="sxs-lookup"><span data-stu-id="6f214-102">Configure XMPP gateway on Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f214-103">_**トピックの最終更新日:** 2013-10-28_</span><span class="sxs-lookup"><span data-stu-id="6f214-103">_**Topic Last Modified:** 2013-10-28_</span></span>

<span data-ttu-id="6f214-104">XMPP ゲートウェイを移行するための最後の手順は、Lync server 2013 エッジサーバー用の証明書を構成し、Lync Server 2013 XMPP ゲートウェイを展開し、XMPP ゲートウェイの DNS レコードを更新することです。</span><span class="sxs-lookup"><span data-stu-id="6f214-104">The final steps for migrating your XMPP Gateway are to configure certificates for the Lync Server 2013 Edge Server, deploy the Lync Server 2013 XMPP Gateway, and update the DNS records for the XMPP Gateway.</span></span> <span data-ttu-id="6f214-105">これらの手順は、XMPP ゲートウェイのダウン タイムを最小限に抑えるために、並行して実行します。</span><span class="sxs-lookup"><span data-stu-id="6f214-105">These steps should be performed in parallel to minimize the down time of your XMPP Gateway.</span></span> <span data-ttu-id="6f214-106">これらの手順を実行する前に、すべてのユーザーを Microsoft Lync Server 2013 展開に移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f214-106">All users must be moved to your Microsoft Lync Server 2013 deployment before performing these steps.</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="6f214-107">XMPP フェデレーションは、存続可能 branch アプライアンスに所属しているユーザーに対してはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6f214-107">XMPP federation is not supported for users who are homed on survivable branch appliances.</span></span> <span data-ttu-id="6f214-108">これは、プレゼンス情報の表示と IM メッセージの交換の両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="6f214-108">This applies to both seeing presence information and exchanging IM messages.</span></span>



</div>

<div>

## <a name="configure-xmpp-gateway-certificates-on-the-lync-server-2013-edge-server"></a><span data-ttu-id="6f214-109">Lync Server 2013 エッジ サーバーで XMPP ゲートウェイの証明書を構成する</span><span class="sxs-lookup"><span data-stu-id="6f214-109">Configure XMPP Gateway Certificates on the Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="6f214-110">エッジ サーバーで、展開ウィザードの [**手順 3: 証明書の要求、インストール、または割り当て**] の横にある [**再実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f214-110">On the Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="6f214-111">初めてエッジ サーバーを展開する場合は、[再実行] ではなく [実行] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6f214-111">If you are deploying the Edge Server for the first time, you will see Run instead of Run Again.</span></span>

    
    </div>

2.  <span data-ttu-id="6f214-112">[**利用可能な証明書タスク**] ページで、[**新しい証明書要求を作成する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f214-112">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="6f214-113">[**証明書の要求**] ページで、[**外部エッジの証明書**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f214-113">On the **Certificate Request** page, click **External Edge Certificate**.</span></span>

4.  <span data-ttu-id="6f214-114">[**要求を後で送信または今すぐ送信**] ページで、[**要求を準備して後で送信する**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="6f214-114">On the **Delayed or Immediate Request** page, select the **Prepare the request now, but send it later** check box.</span></span>

5.  <span data-ttu-id="6f214-115">[**証明書要求ファイル**] ページで、要求を保存するファイルの完全なパスとファイル名を入力します (たとえば、c:\\cert\_外部\_edge. .cer)。</span><span class="sxs-lookup"><span data-stu-id="6f214-115">On the **Certificate Request File** page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

6.  <span data-ttu-id="6f214-116">[**代替証明書テンプレートの指定**] ページで、既定の WebServer テンプレート以外のテンプレートを使用するには、[**選択した証明機関に別の証明書テンプレートを使用する**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="6f214-116">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected certification authority** check box.</span></span>

7.  <span data-ttu-id="6f214-117">[**名前およびセキュリティの設定**] ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6f214-117">On the **Name and Security Settings** page, do the following:</span></span>
    
    1.  <span data-ttu-id="6f214-118">[**フレンドリ名**] に、証明書の表示名を入力します。</span><span class="sxs-lookup"><span data-stu-id="6f214-118">In **Friendly name**, type a display name for the certificate.</span></span>
    
    2.  <span data-ttu-id="6f214-119">[**ビット長**] で、ビット長を指定します (通常は既定値の 2048)。</span><span class="sxs-lookup"><span data-stu-id="6f214-119">In **Bit length**, specify the bit length (typically, the default of 2048).</span></span>
    
    3.  <span data-ttu-id="6f214-120">[**証明書の秘密キーをエクスポート可能としてマークする**] チェック ボックスがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6f214-120">Verify that the **Mark certificate private key as exportable** check box is selected.</span></span>

8.  <span data-ttu-id="6f214-121">[**組織情報**] ページで、組織の名前と組織単位 (部や課など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="6f214-121">On the **Organization Information** page, type the name for the organization and the organizational unit (for example, a division or department).</span></span>

9.  <span data-ttu-id="6f214-122">[**地理情報**] ページで、場所情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="6f214-122">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="6f214-p103">[**サブジェクト名/サブジェクト代替名**] ページに、ウィザードによって自動的に設定される情報が表示されます。追加のサブジェクトの別名が必要な場合、次の 2 つの手順で指定します。</span><span class="sxs-lookup"><span data-stu-id="6f214-p103">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed. If additional subject alternative names are needed, you specify them in the next two steps.</span></span>

11. <span data-ttu-id="6f214-125">[**サブジェクト代替名 (san) の Sip ドメイン設定**] ページで、[ドメイン] チェックボックスをオンにして sip を追加します。\<microsoft.rtc.management.xds.sipdomain\>エントリをサブジェクトの別名一覧に入力します。</span><span class="sxs-lookup"><span data-stu-id="6f214-125">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the domain check box to add a sip.\<sipdomain\> entry to the subject alternative names list.</span></span>

12. <span data-ttu-id="6f214-126">[**追加のサブジェクト代替名の構成**] ページで、必要な追加のサブジェクトの別名を指定します。</span><span class="sxs-lookup"><span data-stu-id="6f214-126">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="6f214-p104">XMPP プロキシがインストールされている場合は、既定でドメイン名 (contoso.com など) が SAN エントリに設定されています。別のエントリが必要な場合は、この手順で追加します。</span><span class="sxs-lookup"><span data-stu-id="6f214-p104">If the XMPP proxy is installed, by default the domain name (such as contoso.com) is populated in the SAN entries. If you require more entries, add them in this step.</span></span>

    
    </div>

13. <span data-ttu-id="6f214-129">[**要求の概要**] ページで、要求を生成するために使用する証明書情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="6f214-129">On the **Request Summary** page, review the certificate information to be used to generate the request.</span></span>

14. <span data-ttu-id="6f214-130">コマンドの実行が完了したら、ログを表示するか、または [**次へ**] をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="6f214-130">After the commands finish running, you can **View Log**, or click Next to continue.</span></span>

15. <span data-ttu-id="6f214-131">[**証明書要求ファイル**] ページで、[**表示**] をクリックして生成済みの証明書の署名要求 (CSR) ファイルを表示するか、または [**完了**] をクリックして証明書ウィザードを終了します。</span><span class="sxs-lookup"><span data-stu-id="6f214-131">On the **Certificate Request File** page, you can view the generated certificate signing request (CSR) file by clicking **View** or exit the Certificate Wizard by clicking **Finish**.</span></span>

16. <span data-ttu-id="6f214-132">要求ファイルをコピーして、公的証明機関に送信します。</span><span class="sxs-lookup"><span data-stu-id="6f214-132">Copy the request file and submit to your public certification authority.</span></span>

17. <span data-ttu-id="6f214-p105">パブリック証明書の受信、インポート、および割り当てを行った後、エッジ サーバー サービスを停止して再起動する必要があります。これは、Lync Server 管理コンソールで次のコマンドを入力して行います。</span><span class="sxs-lookup"><span data-stu-id="6f214-p105">After receiving, importing and assigning the public certificate, you must stop and restart the Edge Server services. You do this by typing in the Lync Server Management console:</span></span>
    
        Stop-CsWindowsService

      &nbsp;
    
        Start-CsWindowsService

</div>

<div>

## <a name="configure-a-new-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="6f214-135">新しい Lync Server 2013 XMPP ゲートウェイを構成する</span><span class="sxs-lookup"><span data-stu-id="6f214-135">Configure a new Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="6f214-136">[Lync Server コントロール パネル] を開きます。</span><span class="sxs-lookup"><span data-stu-id="6f214-136">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="6f214-137">左側のナビゲーション バーで [**フェデレーションと外部アクセス**]、[**XMPP フェデレーション パートナー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f214-137">In the left navigation bar, click **Federation and External Access** and then click **XMPP Federated Partners**.</span></span>

3.  <span data-ttu-id="6f214-138">新しい構成を作成するには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f214-138">To create a new configuration, click **New**.</span></span>

4.  <span data-ttu-id="6f214-139">以下の設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="6f214-139">Define the following settings:</span></span>

5.  <span data-ttu-id="6f214-140">**プライマリドメイン**    (必須)。</span><span class="sxs-lookup"><span data-stu-id="6f214-140">**Primary domain**    (Required).</span></span> <span data-ttu-id="6f214-141">プライマリ ドメインは、XMPP パートナーの基本ドメインです。</span><span class="sxs-lookup"><span data-stu-id="6f214-141">The primary domain is the base domain of the XMPP partner.</span></span> <span data-ttu-id="6f214-142">たとえば、XMPP パートナーのドメイン名として **fabrikam.com** と入力します。</span><span class="sxs-lookup"><span data-stu-id="6f214-142">For example, you would enter **fabrikam.com** for the XMPP partner domain name.</span></span> <span data-ttu-id="6f214-143">これは必須のエントリです。</span><span class="sxs-lookup"><span data-stu-id="6f214-143">This is a required entry.</span></span>

6.  <span data-ttu-id="6f214-144">**説明**   この特定の構成についての説明は、メモまたはその他の識別情報を対象としています。</span><span class="sxs-lookup"><span data-stu-id="6f214-144">**Description**   The description is for notes or other identifying information for this particular configuration.</span></span> <span data-ttu-id="6f214-145">このエントリは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="6f214-145">This entry is optional.</span></span>

7.  <span data-ttu-id="6f214-146">**その他のドメイン**   追加のドメインは、許可された xmpp 通信の一部として含める必要がある、xmpp パートナーのドメインの一部であるドメインです。</span><span class="sxs-lookup"><span data-stu-id="6f214-146">**Additional domains**   Additional domains are domains that are a part of your XMPP partner’s domain that should be included as part of the allowed XMPP communication.</span></span> <span data-ttu-id="6f214-147">たとえば、プライマリドメインが**fabrikam.com**の場合は、xmpp を使用して通信する fabrikam.com の下にある他のすべてのドメインを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="6f214-147">For example, if the primary domain is **fabrikam.com**, then you would list all other domains that are under fabrikam.com that you will communicate with by way of XMPP.</span></span>

8.  <span data-ttu-id="6f214-148">**パートナー**   の種類**パートナーの種類**は必要な設定です。</span><span class="sxs-lookup"><span data-stu-id="6f214-148">**Partner type**   The **Partner type** is a required setting.</span></span> <span data-ttu-id="6f214-149">連絡先を追加できるようにするには、次のいずれかを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f214-149">You must choose one of the following to describe and enforce what contacts can be added.</span></span> <span data-ttu-id="6f214-150">次の中から選択できます。</span><span class="sxs-lookup"><span data-stu-id="6f214-150">You can select from:</span></span>
    
      - <span data-ttu-id="6f214-151">**フェデレーション**   パートナー**の種類は、Lync** Server の展開と xmpp パートナーとの間の高レベルの信頼を表します。</span><span class="sxs-lookup"><span data-stu-id="6f214-151">**Federated**   A **Federated** partner type represents a high level of trust between the Lync Server deployment and the XMPP partner.</span></span><span data-ttu-id="6f214-152">このパートナーの種類は、同じエンタープライズ内で XMPP サーバーとのフェデレーションを行う場合や、ビジネス上の関係が確立されている場合にお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6f214-152">  This partner type is recommended for federating with XMPP servers within the same enterprise or where there is an established business relationship.</span></span><span data-ttu-id="6f214-153">フェデレーションパートナーの XMPP 連絡先は次のことができます。</span><span class="sxs-lookup"><span data-stu-id="6f214-153">  XMPP contacts in Federated partners can:</span></span>
        
        1.  <span data-ttu-id="6f214-154">Lync ユーザーからの明示的な承認なしで Lync の連絡先を追加し、そのプレゼンスを表示する。</span><span class="sxs-lookup"><span data-stu-id="6f214-154">Add Lync contacts and view their presence without express authorization from the Lync user.</span></span>
        
        2.  <span data-ttu-id="6f214-155">Lync ユーザーが連絡先リストに追加しているかどうかに関係なく、Lync の連絡先にインスタント メッセージを送信する。</span><span class="sxs-lookup"><span data-stu-id="6f214-155">Send instant messages to Lync contacts whether or not the Lync user has added them into their contact list.</span></span>
        
        3.  <span data-ttu-id="6f214-156">Lync ユーザーの状態メモを表示する。</span><span class="sxs-lookup"><span data-stu-id="6f214-156">See a Lync user’s status notes.</span></span>
    
      - <span data-ttu-id="6f214-157">**公開**されていることが確認済みの公開パートナーは、ユーザーの id を確認するために信頼されているパブリック xmpp プロバイダーです。 \*\*\*\*    </span><span class="sxs-lookup"><span data-stu-id="6f214-157">**Public verified**   A **Public verified** partner is a public XMPP provider that is trusted to verify the identity of its users.</span></span><span data-ttu-id="6f214-158">パブリック検証されたネットワークの XMPP 連絡先は、Lync の連絡先を追加し、そのプレゼンスを表示して、Lync ユーザーからの明示的な承認なしにインスタントメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="6f214-158">  XMPP contacts in Public Verified networks can add Lync contacts and view their presence and send instant messages to them without express authorization from the Lync users.</span></span><span data-ttu-id="6f214-159">パブリックに確認されたネットワークの XMPP 連絡先には、Lync ユーザーの状態メモは表示されません。</span><span class="sxs-lookup"><span data-stu-id="6f214-159">  XMPP contacts in public verified networks never see a Lync users’ status notes.</span></span><span data-ttu-id="6f214-160">この設定は推奨されていません。</span><span class="sxs-lookup"><span data-stu-id="6f214-160">  This setting is not recommended.</span></span>
    
      - <span data-ttu-id="6f214-161">**パブリック未確認**   **公開**されていないパートナーは、ユーザーの身元を確認するために信頼されていないパブリック xmpp プロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="6f214-161">**Public unverified**   A **Public unverified** partner is a public XMPP provider that is not trusted to verify the identity of its users.</span></span><span data-ttu-id="6f214-162">一般に確認されていないネットワーク上の XMPP ユーザーは、lync ユーザーが連絡先リストに追加することによって明示的に承認されていない限り、Lync ユーザーと通信することはできません。</span><span class="sxs-lookup"><span data-stu-id="6f214-162">  XMPP users on Public Unverified networks cannot communicate with Lync users unless the Lync user has expressly authorized them by adding them to the contact list.</span></span><span data-ttu-id="6f214-163">未確認のパブリックネットワーク上の XMPP ユーザーには、Lync ユーザーの状態メモは表示されません。</span><span class="sxs-lookup"><span data-stu-id="6f214-163">  XMPP users on public unverified networks never see Lync users’ status notes.</span></span><span data-ttu-id="6f214-164">この設定は、Google Talk などのパブリック XMPP プロバイダーとのフェデレーションにお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6f214-164">  This setting is recommended for any federation with public XMPP providers such as Google Talk.</span></span>

9.  <span data-ttu-id="6f214-165">[**接続の種類:**] さまざまなルールとダイヤルバック設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="6f214-165">**Connection Type:** Defines the various rules and dialback settings.</span></span>
    
      - <span data-ttu-id="6f214-166">**Tls ネゴシエーション**   は tls ネゴシエーションルールを定義します。</span><span class="sxs-lookup"><span data-stu-id="6f214-166">**TLS Negotiation**   Defines the TLS negotiation rules.</span></span> <span data-ttu-id="6f214-167">また、TLS がサポートされないように定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="6f214-167">An XMPP service can require TLS, can make TLS optional, or you define that TLS is not supported.</span></span> <span data-ttu-id="6f214-168">[任意] を選択すると、ネゴシエーションが必須であるかどうかの決定は XMPP サービスに委ねられます。</span><span class="sxs-lookup"><span data-stu-id="6f214-168">Choosing Optional leaves the requirement up to the XMPP service for a mandatory-to-negotiate decision.</span></span> <span data-ttu-id="6f214-169">使用可能なすべての設定と詳細を表示するには、有効でなく既知のエラーの構成を含む、SASL、TLS、およびダイヤルバックのネゴシエーションに関するすべての情報を表示します。「 [Lync Server 2013 の XMPP フェデレーションパートナーのネゴシエーション設定](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f214-169">To view all possible settings and details for SASL, TLS and Dialback negotiation –including not valid and known error configurations - see [Negotiation settings for XMPP federated partners in Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).</span></span>
        
          - <span></span>  
            <span data-ttu-id="6f214-170">**必須**   xmpp サービスは TLS ネゴシエーションを必要とします。</span><span class="sxs-lookup"><span data-stu-id="6f214-170">**Required**   The XMPP service requires TLS negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="6f214-171">**オプション**   xmpp サービスは、TLS がネゴシエーションに必須であることを示します。</span><span class="sxs-lookup"><span data-stu-id="6f214-171">**Optional**   The XMPP service indicates that TLS is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="6f214-172">**[サポート**   なし xmpp サービスは TLS をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="6f214-172">**Not Supported**   The XMPP service does not support TLS.</span></span>
    
      - <span data-ttu-id="6f214-173">**Sasl ネゴシエーション**   は、sasl ネゴシエーションルールを定義します。</span><span class="sxs-lookup"><span data-stu-id="6f214-173">**SASL negotiation**   Defines the SASL negotiation rules.</span></span> <span data-ttu-id="6f214-174">また、SASL がサポートされないように定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="6f214-174">An XMPP service can require SASL, can make SASL optional, or you define that SASL is not supported.</span></span> <span data-ttu-id="6f214-175">[任意] を選択すると、ネゴシエーションが必須であるかどうかの決定は XMPP サービスに委ねられます。</span><span class="sxs-lookup"><span data-stu-id="6f214-175">Choosing Optional leaves the requirement up to the partner XMPP service for a mandatory-to-negotiate decision.</span></span>
        
          - <span></span>  
            <span data-ttu-id="6f214-176">**必須**   xmpp サービスは SASL ネゴシエーションを必要とします。</span><span class="sxs-lookup"><span data-stu-id="6f214-176">**Required**   The XMPP service requires SASL negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="6f214-177">**省略可能**   xmpp サービスは、SASL がネゴシエーションに必須であることを示します。</span><span class="sxs-lookup"><span data-stu-id="6f214-177">**Optional**   The XMPP service indicates that SASL is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="6f214-178">**[サポート**   なし xmpp サービスは SASL をサポートしません。</span><span class="sxs-lookup"><span data-stu-id="6f214-178">**Not Supported**   The XMPP service does not support SASL.</span></span>
    
      - <span data-ttu-id="6f214-179">**サーバーダイヤルバックネゴシエーションのサポート**サポートサーバーのダイヤルバックネゴシエーション処理では、ドメインネームシステム (DNS) と権限のあるサーバーを使用して、要求が有効な XMPP パートナーから来たものであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6f214-179">**Support server dialback negotiation** The support server dialback negotiation process uses the domain name system (DNS) and an authoritative server to verify that the request came from a valid XMPP partner.</span></span> <span data-ttu-id="6f214-180">これを行うために、送信元サーバーは、生成されたダイヤルバックキーを使用して特定の種類のメッセージを作成し、DNS で受信側サーバーを検索します。</span><span class="sxs-lookup"><span data-stu-id="6f214-180">To do this, the originating server creates a message of a specific type with a generated dialback key and looks up the receiving server in DNS.</span></span> <span data-ttu-id="6f214-181">送信元サーバーは、生成された DNS 参照 (受信側サーバーなど) に、XML ストリームでキーを送信します。</span><span class="sxs-lookup"><span data-stu-id="6f214-181">The originating server sends the key in an XML stream to the resulting DNS lookup, presumably the receiving server.</span></span> <span data-ttu-id="6f214-182">XML ストリームの上でキーを受け取ると、受信側サーバーは送信元のサーバーに応答しませんが、既知の権限のあるサーバーにキーを送信します。</span><span class="sxs-lookup"><span data-stu-id="6f214-182">On receipt of the key over the XML stream, the receiving server does not respond to the originating server, but sends the key to a known authoritative server.</span></span> <span data-ttu-id="6f214-183">権限のあるサーバーは、キーが有効であるか無効であるかを確認します。</span><span class="sxs-lookup"><span data-stu-id="6f214-183">The authoritative server verifies that the key is either valid or not valid.</span></span> <span data-ttu-id="6f214-184">有効でない場合、受信側のサーバーは送信元のサーバーに応答しません。</span><span class="sxs-lookup"><span data-stu-id="6f214-184">If not valid, the receiving server does not respond to the originating server.</span></span> <span data-ttu-id="6f214-185">キーが有効である場合、受信側のサーバーは、送信元のサーバーに id とキーが有効であることを通知し、会話を開始できます。</span><span class="sxs-lookup"><span data-stu-id="6f214-185">If the key is valid, the receiving server informs the originating server that the identity and key is valid and the conversation can commence.</span></span>
        
        <span data-ttu-id="6f214-186">**ダイヤルバック ネゴシエーション**には、2 つの状態があります。</span><span class="sxs-lookup"><span data-stu-id="6f214-186">There are two valid states for **Dialback negotiation**:</span></span>
        
          - <span></span>  
            <span data-ttu-id="6f214-187">**True**   は、発信元サーバーから要求を受信した場合に、ダイヤルバックネゴシエーションを使用するように xmpp サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="6f214-187">**True**   The XMPP server is configured to use Dialback negotiation if a request should be received from an originating server.</span></span>
        
          - <span></span>  
            <span data-ttu-id="6f214-188">**False**   xmpp サーバーはダイヤルバックネゴシエーションを使用するように構成されておらず、発信元サーバーから要求を受信した場合は無視されます。</span><span class="sxs-lookup"><span data-stu-id="6f214-188">**False**   The XMPP server is not configured to use Dialback negotiation and if a request should be received from an originating server, it will be ignored.</span></span>

10. <span data-ttu-id="6f214-189">[**確定**] をクリックして、サイトまたはユーザー ポリシーへの変更を保存します。
</span><span class="sxs-lookup"><span data-stu-id="6f214-189">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

<div>

## <a name="update-dns-records-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="6f214-190">Lync Server 2013 XMPP ゲートウェイの DNS レコードを更新する</span><span class="sxs-lookup"><span data-stu-id="6f214-190">Update DNS Records for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="6f214-191">XMPP フェデレーションの DNS を構成するには、外部 DNS:\_xmpp サーバーに次の SRV レコードを追加します。\_tcp。\<ドメイン名\> SRV レコードは、エッジサーバーのアクセスエッジ FQDN に解決され、ポート値は5269になります。</span><span class="sxs-lookup"><span data-stu-id="6f214-191">To configure DNS for XMPP federation, you add the following SRV record to your external DNS:\_xmpp-server.\_tcp.\<domain name\> The SRV record will resolve to the Access Edge FQDN of the Edge server, with a port value of 5269.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

