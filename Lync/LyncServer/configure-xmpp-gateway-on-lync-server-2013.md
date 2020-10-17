---
title: Lync Server 2013 で XMPP ゲートウェイを構成する
description: Lync Server 2013 で XMPP ゲートウェイを構成します。
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
ms.openlocfilehash: 78765237e737dea29d77230d6b0eecdb0348cb41
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542953"
---
# <a name="configure-xmpp-gateway-on-lync-server-2013"></a><span data-ttu-id="68c3a-103">Lync Server 2013 で XMPP ゲートウェイを構成する</span><span class="sxs-lookup"><span data-stu-id="68c3a-103">Configure XMPP gateway on Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68c3a-104">_**トピックの最終更新日:** 2013-10-28_</span><span class="sxs-lookup"><span data-stu-id="68c3a-104">_**Topic Last Modified:** 2013-10-28_</span></span>

<span data-ttu-id="68c3a-105">XMPP ゲートウェイを移行するための最後の手順は、Lync server 2013 エッジサーバー用の証明書を構成し、Lync Server 2013 XMPP ゲートウェイを展開し、XMPP ゲートウェイの DNS レコードを更新することです。</span><span class="sxs-lookup"><span data-stu-id="68c3a-105">The final steps for migrating your XMPP Gateway are to configure certificates for the Lync Server 2013 Edge Server, deploy the Lync Server 2013 XMPP Gateway, and update the DNS records for the XMPP Gateway.</span></span> <span data-ttu-id="68c3a-106">これらの手順は、XMPP ゲートウェイのダウン タイムを最小限に抑えるために、並行して実行します。</span><span class="sxs-lookup"><span data-stu-id="68c3a-106">These steps should be performed in parallel to minimize the down time of your XMPP Gateway.</span></span> <span data-ttu-id="68c3a-107">これらの手順を実行する前に、すべてのユーザーを Microsoft Lync Server 2013 展開に移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68c3a-107">All users must be moved to your Microsoft Lync Server 2013 deployment before performing these steps.</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="68c3a-108">XMPP フェデレーションは、存続可能 branch アプライアンスに所属しているユーザーに対してはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="68c3a-108">XMPP federation is not supported for users who are homed on survivable branch appliances.</span></span> <span data-ttu-id="68c3a-109">これは、プレゼンス情報の表示と IM メッセージの交換の両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="68c3a-109">This applies to both seeing presence information and exchanging IM messages.</span></span>



</div>

<div>

## <a name="configure-xmpp-gateway-certificates-on-the-lync-server-2013-edge-server"></a><span data-ttu-id="68c3a-110">Lync Server 2013 エッジ サーバーで XMPP ゲートウェイの証明書を構成する</span><span class="sxs-lookup"><span data-stu-id="68c3a-110">Configure XMPP Gateway Certificates on the Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="68c3a-111">エッジ サーバーで、展開ウィザードの [**手順 3: 証明書の要求、インストール、または割り当て**] の横にある [**再実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="68c3a-111">On the Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="68c3a-112">初めてエッジ サーバーを展開する場合は、[再実行] ではなく [実行] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="68c3a-112">If you are deploying the Edge Server for the first time, you will see Run instead of Run Again.</span></span>

    
    </div>

2.  <span data-ttu-id="68c3a-113">[**利用可能な証明書タスク**] ページで、[**新しい証明書要求を作成する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="68c3a-113">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="68c3a-114">[**証明書の要求**] ページで、[**外部エッジの証明書**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="68c3a-114">On the **Certificate Request** page, click **External Edge Certificate**.</span></span>

4.  <span data-ttu-id="68c3a-115">[**要求を後で送信または今すぐ送信**] ページで、[**要求を準備して後で送信する**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="68c3a-115">On the **Delayed or Immediate Request** page, select the **Prepare the request now, but send it later** check box.</span></span>

5.  <span data-ttu-id="68c3a-116">[ **証明書要求ファイル** ] ページで、要求を保存するファイルの完全なパスとファイル名を入力します (たとえば、c: \\ cert \_ 外部 \_ edge. .cer)。</span><span class="sxs-lookup"><span data-stu-id="68c3a-116">On the **Certificate Request File** page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

6.  <span data-ttu-id="68c3a-117">[**代替証明書テンプレートの指定**] ページで、既定の WebServer テンプレート以外のテンプレートを使用するには、[**選択した証明機関に別の証明書テンプレートを使用する**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="68c3a-117">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected certification authority** check box.</span></span>

7.  <span data-ttu-id="68c3a-118">[**名前およびセキュリティの設定**] ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="68c3a-118">On the **Name and Security Settings** page, do the following:</span></span>
    
    1.  <span data-ttu-id="68c3a-119">[**フレンドリ名**] に、証明書の表示名を入力します。</span><span class="sxs-lookup"><span data-stu-id="68c3a-119">In **Friendly name**, type a display name for the certificate.</span></span>
    
    2.  <span data-ttu-id="68c3a-120">[**ビット長**] で、ビット長を指定します (通常は既定値の 2048)。</span><span class="sxs-lookup"><span data-stu-id="68c3a-120">In **Bit length**, specify the bit length (typically, the default of 2048).</span></span>
    
    3.  <span data-ttu-id="68c3a-121">[**証明書の秘密キーをエクスポート可能としてマークする**] チェック ボックスがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="68c3a-121">Verify that the **Mark certificate private key as exportable** check box is selected.</span></span>

8.  <span data-ttu-id="68c3a-122">[**組織情報**] ページで、組織の名前と組織単位 (部や課など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="68c3a-122">On the **Organization Information** page, type the name for the organization and the organizational unit (for example, a division or department).</span></span>

9.  <span data-ttu-id="68c3a-123">[**地理情報**] ページで、場所情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="68c3a-123">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="68c3a-p103">[**サブジェクト名/サブジェクト代替名**] ページに、ウィザードによって自動的に設定される情報が表示されます。追加のサブジェクトの別名が必要な場合、次の 2 つの手順で指定します。</span><span class="sxs-lookup"><span data-stu-id="68c3a-p103">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed. If additional subject alternative names are needed, you specify them in the next two steps.</span></span>

11. <span data-ttu-id="68c3a-126">[ **サブジェクト代替名 (san) の Sip ドメイン設定** ] ページで、[ドメイン] チェックボックスをオンにして sip を追加します。\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="68c3a-126">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the domain check box to add a sip.\<sipdomain\></span></span> <span data-ttu-id="68c3a-127">サブジェクトの別名リストへのエントリ。</span><span class="sxs-lookup"><span data-stu-id="68c3a-127">entry to the subject alternative names list.</span></span>

12. <span data-ttu-id="68c3a-128">[**追加のサブジェクト代替名の構成**] ページで、必要な追加のサブジェクトの別名を指定します。</span><span class="sxs-lookup"><span data-stu-id="68c3a-128">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="68c3a-p105">XMPP プロキシがインストールされている場合は、既定でドメイン名 (contoso.com など) が SAN エントリに設定されています。別のエントリが必要な場合は、この手順で追加します。</span><span class="sxs-lookup"><span data-stu-id="68c3a-p105">If the XMPP proxy is installed, by default the domain name (such as contoso.com) is populated in the SAN entries. If you require more entries, add them in this step.</span></span>

    
    </div>

13. <span data-ttu-id="68c3a-131">[**要求の概要**] ページで、要求を生成するために使用する証明書情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="68c3a-131">On the **Request Summary** page, review the certificate information to be used to generate the request.</span></span>

14. <span data-ttu-id="68c3a-132">コマンドの実行が完了したら、ログを表示するか、または [**次へ**] をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="68c3a-132">After the commands finish running, you can **View Log**, or click Next to continue.</span></span>

15. <span data-ttu-id="68c3a-133">[**証明書要求ファイル**] ページで、[**表示**] をクリックして生成済みの証明書の署名要求 (CSR) ファイルを表示するか、または [**完了**] をクリックして証明書ウィザードを終了します。</span><span class="sxs-lookup"><span data-stu-id="68c3a-133">On the **Certificate Request File** page, you can view the generated certificate signing request (CSR) file by clicking **View** or exit the Certificate Wizard by clicking **Finish**.</span></span>

16. <span data-ttu-id="68c3a-134">要求ファイルをコピーして、公的証明機関に送信します。</span><span class="sxs-lookup"><span data-stu-id="68c3a-134">Copy the request file and submit to your public certification authority.</span></span>

17. <span data-ttu-id="68c3a-p106">パブリック証明書の受信、インポート、および割り当てを行った後、エッジ サーバー サービスを停止して再起動する必要があります。これは、Lync Server 管理コンソールで次のコマンドを入力して行います。</span><span class="sxs-lookup"><span data-stu-id="68c3a-p106">After receiving, importing and assigning the public certificate, you must stop and restart the Edge Server services. You do this by typing in the Lync Server Management console:</span></span>
    
        Stop-CsWindowsService

      &nbsp;
    
        Start-CsWindowsService

</div>

<div>

## <a name="configure-a-new-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="68c3a-137">新しい Lync Server 2013 XMPP ゲートウェイを構成する</span><span class="sxs-lookup"><span data-stu-id="68c3a-137">Configure a new Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="68c3a-138">[Lync Server コントロール パネル] を開きます。</span><span class="sxs-lookup"><span data-stu-id="68c3a-138">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="68c3a-139">左側のナビゲーション バーで [**フェデレーションと外部アクセス**]、[**XMPP フェデレーション パートナー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="68c3a-139">In the left navigation bar, click **Federation and External Access** and then click **XMPP Federated Partners**.</span></span>

3.  <span data-ttu-id="68c3a-140">新しい構成を作成するには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="68c3a-140">To create a new configuration, click **New**.</span></span>

4.  <span data-ttu-id="68c3a-141">以下の設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="68c3a-141">Define the following settings:</span></span>

5.  <span data-ttu-id="68c3a-142">**プライマリドメイン**    (必須)。</span><span class="sxs-lookup"><span data-stu-id="68c3a-142">**Primary domain**    (Required).</span></span> <span data-ttu-id="68c3a-143">プライマリ ドメインは、XMPP パートナーの基本ドメインです。</span><span class="sxs-lookup"><span data-stu-id="68c3a-143">The primary domain is the base domain of the XMPP partner.</span></span> <span data-ttu-id="68c3a-144">たとえば、XMPP パートナーのドメイン名として **fabrikam.com** と入力します。</span><span class="sxs-lookup"><span data-stu-id="68c3a-144">For example, you would enter **fabrikam.com** for the XMPP partner domain name.</span></span> <span data-ttu-id="68c3a-145">これは必須のエントリです。</span><span class="sxs-lookup"><span data-stu-id="68c3a-145">This is a required entry.</span></span>

6.  <span data-ttu-id="68c3a-146">**説明**    説明は、この特定の構成に関するメモまたはその他の識別情報を対象としています。</span><span class="sxs-lookup"><span data-stu-id="68c3a-146">**Description**   The description is for notes or other identifying information for this particular configuration.</span></span> <span data-ttu-id="68c3a-147">このエントリは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="68c3a-147">This entry is optional.</span></span>

7.  <span data-ttu-id="68c3a-148">**追加のドメイン**    追加のドメインは、許可された XMPP 通信の一部として含める必要がある、XMPP パートナーのドメインの一部であるドメインです。</span><span class="sxs-lookup"><span data-stu-id="68c3a-148">**Additional domains**   Additional domains are domains that are a part of your XMPP partner’s domain that should be included as part of the allowed XMPP communication.</span></span> <span data-ttu-id="68c3a-149">たとえば、プライマリドメインが **fabrikam.com**の場合は、xmpp を使用して通信する fabrikam.com の下にある他のすべてのドメインを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="68c3a-149">For example, if the primary domain is **fabrikam.com**, then you would list all other domains that are under fabrikam.com that you will communicate with by way of XMPP.</span></span>

8.  <span data-ttu-id="68c3a-150">**パートナーの種類**    **パートナーの種類**は必須の設定です。</span><span class="sxs-lookup"><span data-stu-id="68c3a-150">**Partner type**   The **Partner type** is a required setting.</span></span> <span data-ttu-id="68c3a-151">連絡先を追加できるようにするには、次のいずれかを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68c3a-151">You must choose one of the following to describe and enforce what contacts can be added.</span></span> <span data-ttu-id="68c3a-152">次の中から選択できます。</span><span class="sxs-lookup"><span data-stu-id="68c3a-152">You can select from:</span></span>
    
      - <span data-ttu-id="68c3a-153">**フェデレーション**    **フェデレーション**パートナーの種類は、Lync Server の展開と xmpp パートナーとの間の高レベルの信頼を表します。</span><span class="sxs-lookup"><span data-stu-id="68c3a-153">**Federated**   A **Federated** partner type represents a high level of trust between the Lync Server deployment and the XMPP partner.</span></span><span data-ttu-id="68c3a-154">このパートナーの種類は、同じエンタープライズ内で XMPP サーバーとのフェデレーションを行う場合や、ビジネス上の関係が確立されている場合にお勧めします。</span><span class="sxs-lookup"><span data-stu-id="68c3a-154">  This partner type is recommended for federating with XMPP servers within the same enterprise or where there is an established business relationship.</span></span><span data-ttu-id="68c3a-155">フェデレーションパートナーの XMPP 連絡先は次のことができます。</span><span class="sxs-lookup"><span data-stu-id="68c3a-155">  XMPP contacts in Federated partners can:</span></span>
        
        1.  <span data-ttu-id="68c3a-156">Lync ユーザーからの明示的な承認なしで Lync の連絡先を追加し、そのプレゼンスを表示する。</span><span class="sxs-lookup"><span data-stu-id="68c3a-156">Add Lync contacts and view their presence without express authorization from the Lync user.</span></span>
        
        2.  <span data-ttu-id="68c3a-157">Lync ユーザーが連絡先リストに追加しているかどうかに関係なく、Lync の連絡先にインスタント メッセージを送信する。</span><span class="sxs-lookup"><span data-stu-id="68c3a-157">Send instant messages to Lync contacts whether or not the Lync user has added them into their contact list.</span></span>
        
        3.  <span data-ttu-id="68c3a-158">Lync ユーザーの状態メモを表示する。</span><span class="sxs-lookup"><span data-stu-id="68c3a-158">See a Lync user’s status notes.</span></span>
    
      - <span data-ttu-id="68c3a-159">**公開の確認**    公開されている**確認済み**パートナーとは、そのユーザーの身元を確認するために信頼されているパブリック xmpp プロバイダーのことです。</span><span class="sxs-lookup"><span data-stu-id="68c3a-159">**Public verified**   A **Public verified** partner is a public XMPP provider that is trusted to verify the identity of its users.</span></span><span data-ttu-id="68c3a-160">パブリック検証されたネットワークの XMPP 連絡先は、Lync の連絡先を追加し、そのプレゼンスを表示して、Lync ユーザーからの明示的な承認なしにインスタントメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="68c3a-160">  XMPP contacts in Public Verified networks can add Lync contacts and view their presence and send instant messages to them without express authorization from the Lync users.</span></span><span data-ttu-id="68c3a-161">パブリックに確認されたネットワークの XMPP 連絡先には、Lync ユーザーの状態メモは表示されません。</span><span class="sxs-lookup"><span data-stu-id="68c3a-161">  XMPP contacts in public verified networks never see a Lync users’ status notes.</span></span><span data-ttu-id="68c3a-162">この設定は推奨されていません。</span><span class="sxs-lookup"><span data-stu-id="68c3a-162">  This setting is not recommended.</span></span>
    
      - <span data-ttu-id="68c3a-163">**パブリック未確認**    **公開**されていないパートナーとは、そのユーザーの id を検証するために信頼されていないパブリック xmpp プロバイダーのことです。</span><span class="sxs-lookup"><span data-stu-id="68c3a-163">**Public unverified**   A **Public unverified** partner is a public XMPP provider that is not trusted to verify the identity of its users.</span></span><span data-ttu-id="68c3a-164">一般に確認されていないネットワーク上の XMPP ユーザーは、lync ユーザーが連絡先リストに追加することによって明示的に承認されていない限り、Lync ユーザーと通信することはできません。</span><span class="sxs-lookup"><span data-stu-id="68c3a-164">  XMPP users on Public Unverified networks cannot communicate with Lync users unless the Lync user has expressly authorized them by adding them to the contact list.</span></span><span data-ttu-id="68c3a-165">未確認のパブリックネットワーク上の XMPP ユーザーには、Lync ユーザーの状態メモは表示されません。</span><span class="sxs-lookup"><span data-stu-id="68c3a-165">  XMPP users on public unverified networks never see Lync users’ status notes.</span></span><span data-ttu-id="68c3a-166">この設定は、Google Talk などのパブリック XMPP プロバイダーとのフェデレーションにお勧めします。</span><span class="sxs-lookup"><span data-stu-id="68c3a-166">  This setting is recommended for any federation with public XMPP providers such as Google Talk.</span></span>

9.  <span data-ttu-id="68c3a-167">[**接続の種類:**] さまざまなルールとダイヤルバック設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="68c3a-167">**Connection Type:** Defines the various rules and dialback settings.</span></span>
    
      - <span data-ttu-id="68c3a-168">**TLS ネゴシエーション**    TLS ネゴシエーションルールを定義します。</span><span class="sxs-lookup"><span data-stu-id="68c3a-168">**TLS Negotiation**   Defines the TLS negotiation rules.</span></span> <span data-ttu-id="68c3a-169">また、TLS がサポートされないように定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="68c3a-169">An XMPP service can require TLS, can make TLS optional, or you define that TLS is not supported.</span></span> <span data-ttu-id="68c3a-170">[任意] を選択すると、ネゴシエーションが必須であるかどうかの決定は XMPP サービスに委ねられます。</span><span class="sxs-lookup"><span data-stu-id="68c3a-170">Choosing Optional leaves the requirement up to the XMPP service for a mandatory-to-negotiate decision.</span></span> <span data-ttu-id="68c3a-171">使用可能なすべての設定と詳細を表示するには、有効でなく既知のエラーの構成を含む、SASL、TLS、およびダイヤルバックのネゴシエーションに関するすべての情報を表示します。「 [Lync Server 2013 の XMPP フェデレーションパートナーのネゴシエーション設定](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68c3a-171">To view all possible settings and details for SASL, TLS and Dialback negotiation –including not valid and known error configurations - see [Negotiation settings for XMPP federated partners in Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).</span></span>
        
          - <span></span>  
            <span data-ttu-id="68c3a-172">**必須**    XMPP サービスは TLS ネゴシエーションを必要とします。</span><span class="sxs-lookup"><span data-stu-id="68c3a-172">**Required**   The XMPP service requires TLS negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="68c3a-173">**省略可能**    XMPP サービスは、TLS のネゴシエーションが必須であることを示します。</span><span class="sxs-lookup"><span data-stu-id="68c3a-173">**Optional**   The XMPP service indicates that TLS is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="68c3a-174">サポートされ**ません**    XMPP サービスは TLS をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="68c3a-174">**Not Supported**   The XMPP service does not support TLS.</span></span>
    
      - <span data-ttu-id="68c3a-175">**SASL ネゴシエーション**    SASL ネゴシエーションルールを定義します。</span><span class="sxs-lookup"><span data-stu-id="68c3a-175">**SASL negotiation**   Defines the SASL negotiation rules.</span></span> <span data-ttu-id="68c3a-176">また、SASL がサポートされないように定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="68c3a-176">An XMPP service can require SASL, can make SASL optional, or you define that SASL is not supported.</span></span> <span data-ttu-id="68c3a-177">[任意] を選択すると、ネゴシエーションが必須であるかどうかの決定は XMPP サービスに委ねられます。</span><span class="sxs-lookup"><span data-stu-id="68c3a-177">Choosing Optional leaves the requirement up to the partner XMPP service for a mandatory-to-negotiate decision.</span></span>
        
          - <span></span>  
            <span data-ttu-id="68c3a-178">**必須**    XMPP サービスは、SASL ネゴシエーションを必要とします。</span><span class="sxs-lookup"><span data-stu-id="68c3a-178">**Required**   The XMPP service requires SASL negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="68c3a-179">**省略可能**    XMPP サービスは、SASL がネゴシエーションに必須であることを示します。</span><span class="sxs-lookup"><span data-stu-id="68c3a-179">**Optional**   The XMPP service indicates that SASL is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="68c3a-180">サポートされ**ません**    XMPP サービスは SASL をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="68c3a-180">**Not Supported**   The XMPP service does not support SASL.</span></span>
    
      - <span data-ttu-id="68c3a-181">**サーバーダイヤルバックネゴシエーションのサポート** サポートサーバーのダイヤルバックネゴシエーション処理では、ドメインネームシステム (DNS) と権限のあるサーバーを使用して、要求が有効な XMPP パートナーから来たものであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="68c3a-181">**Support server dialback negotiation** The support server dialback negotiation process uses the domain name system (DNS) and an authoritative server to verify that the request came from a valid XMPP partner.</span></span> <span data-ttu-id="68c3a-182">これを行うために、送信元サーバーは、生成されたダイヤルバックキーを使用して特定の種類のメッセージを作成し、DNS で受信側サーバーを検索します。</span><span class="sxs-lookup"><span data-stu-id="68c3a-182">To do this, the originating server creates a message of a specific type with a generated dialback key and looks up the receiving server in DNS.</span></span> <span data-ttu-id="68c3a-183">送信元サーバーは、生成された DNS 参照 (受信側サーバーなど) に、XML ストリームでキーを送信します。</span><span class="sxs-lookup"><span data-stu-id="68c3a-183">The originating server sends the key in an XML stream to the resulting DNS lookup, presumably the receiving server.</span></span> <span data-ttu-id="68c3a-184">XML ストリームの上でキーを受け取ると、受信側サーバーは送信元のサーバーに応答しませんが、既知の権限のあるサーバーにキーを送信します。</span><span class="sxs-lookup"><span data-stu-id="68c3a-184">On receipt of the key over the XML stream, the receiving server does not respond to the originating server, but sends the key to a known authoritative server.</span></span> <span data-ttu-id="68c3a-185">権限のあるサーバーは、キーが有効であるか無効であるかを確認します。</span><span class="sxs-lookup"><span data-stu-id="68c3a-185">The authoritative server verifies that the key is either valid or not valid.</span></span> <span data-ttu-id="68c3a-186">有効でない場合、受信側のサーバーは送信元のサーバーに応答しません。</span><span class="sxs-lookup"><span data-stu-id="68c3a-186">If not valid, the receiving server does not respond to the originating server.</span></span> <span data-ttu-id="68c3a-187">キーが有効である場合、受信側のサーバーは、送信元のサーバーに id とキーが有効であることを通知し、会話を開始できます。</span><span class="sxs-lookup"><span data-stu-id="68c3a-187">If the key is valid, the receiving server informs the originating server that the identity and key is valid and the conversation can commence.</span></span>
        
        <span data-ttu-id="68c3a-188">**ダイヤルバック ネゴシエーション**には、2 つの状態があります。</span><span class="sxs-lookup"><span data-stu-id="68c3a-188">There are two valid states for **Dialback negotiation**:</span></span>
        
          - <span></span>  
            <span data-ttu-id="68c3a-189">**True**    要求が発信元サーバーから受信された場合、XMPP サーバーはダイヤルバックネゴシエーションを使用するように構成されます。</span><span class="sxs-lookup"><span data-stu-id="68c3a-189">**True**   The XMPP server is configured to use Dialback negotiation if a request should be received from an originating server.</span></span>
        
          - <span></span>  
            <span data-ttu-id="68c3a-190">**False**    XMPP サーバーはダイヤルバックネゴシエーションを使用するように構成されておらず、発信元サーバーから要求を受信した場合は無視されます。</span><span class="sxs-lookup"><span data-stu-id="68c3a-190">**False**   The XMPP server is not configured to use Dialback negotiation and if a request should be received from an originating server, it will be ignored.</span></span>

10. <span data-ttu-id="68c3a-191">[**確定**] をクリックして、サイトまたはユーザー ポリシーへの変更を保存します。
</span><span class="sxs-lookup"><span data-stu-id="68c3a-191">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

<div>

## <a name="update-dns-records-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="68c3a-192">Lync Server 2013 XMPP ゲートウェイの DNS レコードを更新する</span><span class="sxs-lookup"><span data-stu-id="68c3a-192">Update DNS Records for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="68c3a-193">XMPP フェデレーションの DNS を構成するには、外部 DNS: \_ xmpp サーバー \_ に次の SRV レコードを追加します。プロトコル.\<domain name\></span><span class="sxs-lookup"><span data-stu-id="68c3a-193">To configure DNS for XMPP federation, you add the following SRV record to your external DNS:\_xmpp-server.\_tcp.\<domain name\></span></span> <span data-ttu-id="68c3a-194">SRV レコードは、エッジサーバーのアクセスエッジ FQDN に解決され、ポート値は5269になります。</span><span class="sxs-lookup"><span data-stu-id="68c3a-194">The SRV record will resolve to the Access Edge FQDN of the Edge server, with a port value of 5269.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

