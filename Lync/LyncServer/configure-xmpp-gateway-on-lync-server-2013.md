---
title: Lync Server 2013 での XMPP ゲートウェイの構成
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
ms.openlocfilehash: 2910766dbb2147fa5d1c51235f10ab2e80826bda
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723217"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-on-lync-server-2013"></a><span data-ttu-id="73979-102">Lync Server 2013 での XMPP ゲートウェイの構成</span><span class="sxs-lookup"><span data-stu-id="73979-102">Configure XMPP gateway on Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73979-103">_**最終更新日:** 2013-10-28_</span><span class="sxs-lookup"><span data-stu-id="73979-103">_**Topic Last Modified:** 2013-10-28_</span></span>

<span data-ttu-id="73979-104">XMPP ゲートウェイを移行するための最終的な手順は、Lync Server 2013 Edge サーバー用の証明書を構成し、Lync Server 2013 XMPP ゲートウェイを展開して、XMPP ゲートウェイの DNS レコードを更新することです。</span><span class="sxs-lookup"><span data-stu-id="73979-104">The final steps for migrating your XMPP Gateway are to configure certificates for the Lync Server 2013 Edge Server, deploy the Lync Server 2013 XMPP Gateway, and update the DNS records for the XMPP Gateway.</span></span> <span data-ttu-id="73979-105">XMPP ゲートウェイのダウンタイムを最小限に抑えるために、これらの手順は並列で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="73979-105">These steps should be performed in parallel to minimize the down time of your XMPP Gateway.</span></span> <span data-ttu-id="73979-106">これらの手順を実行する前に、すべてのユーザーを Microsoft Lync Server 2013 の展開に移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="73979-106">All users must be moved to your Microsoft Lync Server 2013 deployment before performing these steps.</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="73979-107">XMPP フェデレーションは、survivable branch アプライアンスをホームにしているユーザーに対してはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="73979-107">XMPP federation is not supported for users who are homed on survivable branch appliances.</span></span> <span data-ttu-id="73979-108">これは、プレゼンス情報の表示と IM メッセージの交換の両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="73979-108">This applies to both seeing presence information and exchanging IM messages.</span></span>



</div>

<div>

## <a name="configure-xmpp-gateway-certificates-on-the-lync-server-2013-edge-server"></a><span data-ttu-id="73979-109">Lync Server 2013 Edge サーバーで XMPP ゲートウェイ証明書を構成する</span><span class="sxs-lookup"><span data-stu-id="73979-109">Configure XMPP Gateway Certificates on the Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="73979-110">エッジサーバーの展開ウィザードで、[**手順 3: 証明書の要求、インストール、または割り当て**] の横にある [実行] を**もう一度**クリックします。</span><span class="sxs-lookup"><span data-stu-id="73979-110">On the Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="73979-111">初めてエッジサーバーを展開する場合は、[実行] ではなく、[実行] と表示されます。</span><span class="sxs-lookup"><span data-stu-id="73979-111">If you are deploying the Edge Server for the first time, you will see Run instead of Run Again.</span></span>

    
    </div>

2.  <span data-ttu-id="73979-112">[**利用可能な証明書タスク**] ページで、[**新しい証明書要求を作成する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="73979-112">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="73979-113">[**証明書の要求**] ページで、[**外部境界の証明書**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="73979-113">On the **Certificate Request** page, click **External Edge Certificate**.</span></span>

4.  <span data-ttu-id="73979-114">[**遅延または即時要求**] ページで、[**今すぐ要求を準備するが、後で送信**する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="73979-114">On the **Delayed or Immediate Request** page, select the **Prepare the request now, but send it later** check box.</span></span>

5.  <span data-ttu-id="73979-115">[**証明書要求ファイル**] ページで、要求を保存するファイルの完全パスとファイル名を入力します (たとえば、c:\\cert\_外部\_edge)。</span><span class="sxs-lookup"><span data-stu-id="73979-115">On the **Certificate Request File** page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

6.  <span data-ttu-id="73979-116">[**代替証明書テンプレートの指定**] ページで、既定の web サーバテンプレート以外のテンプレートを使用するには、[**選択された証明機関に別の証明書テンプレートを使用**する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="73979-116">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected certification authority** check box.</span></span>

7.  <span data-ttu-id="73979-117">[**名前とセキュリティの設定**] ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="73979-117">On the **Name and Security Settings** page, do the following:</span></span>
    
    1.  <span data-ttu-id="73979-118">[**フレンドリ名**] に、証明書の表示名を入力します。</span><span class="sxs-lookup"><span data-stu-id="73979-118">In **Friendly name**, type a display name for the certificate.</span></span>
    
    2.  <span data-ttu-id="73979-119">**ビット長**では、ビット長 (通常は2048の既定値) を指定します。</span><span class="sxs-lookup"><span data-stu-id="73979-119">In **Bit length**, specify the bit length (typically, the default of 2048).</span></span>
    
    3.  <span data-ttu-id="73979-120">[**証明書の秘密キーをエクスポート可能としてマーク**する] チェックボックスがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="73979-120">Verify that the **Mark certificate private key as exportable** check box is selected.</span></span>

8.  <span data-ttu-id="73979-121">[**組織の情報**] ページで、組織の名前と組織単位 (たとえば、部門や部署) を入力します。</span><span class="sxs-lookup"><span data-stu-id="73979-121">On the **Organization Information** page, type the name for the organization and the organizational unit (for example, a division or department).</span></span>

9.  <span data-ttu-id="73979-122">[**地理情報**] ページで、場所情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="73979-122">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="73979-123">[ **Subject Name/Subject name** ] ページには、ウィザードによって自動的に入力される情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="73979-123">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed.</span></span> <span data-ttu-id="73979-124">追加の件名の代替名が必要な場合は、次の2つの手順で指定します。</span><span class="sxs-lookup"><span data-stu-id="73979-124">If additional subject alternative names are needed, you specify them in the next two steps.</span></span>

11. <span data-ttu-id="73979-125">[**サブジェクト代替名 (san)] ページの Sip ドメイン設定**で、[Domain] チェックボックスをオンにして sip を追加します。\<[\>件名の代替名] ボックスの一覧に sipdomain エントリを入力します。</span><span class="sxs-lookup"><span data-stu-id="73979-125">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the domain check box to add a sip.\<sipdomain\> entry to the subject alternative names list.</span></span>

12. <span data-ttu-id="73979-126">[**追加のサブジェクト代替名の構成**] ページで、必要なその他のサブジェクトの代替名を指定します。</span><span class="sxs-lookup"><span data-stu-id="73979-126">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="73979-127">XMPP プロキシがインストールされている場合、既定では、ドメイン名 (contoso.com など) が SAN エントリに設定されます。</span><span class="sxs-lookup"><span data-stu-id="73979-127">If the XMPP proxy is installed, by default the domain name (such as contoso.com) is populated in the SAN entries.</span></span> <span data-ttu-id="73979-128">他のエントリが必要な場合は、この手順で追加します。</span><span class="sxs-lookup"><span data-stu-id="73979-128">If you require more entries, add them in this step.</span></span>

    
    </div>

13. <span data-ttu-id="73979-129">[**要求の概要**] ページで、要求の生成に使用する証明書情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="73979-129">On the **Request Summary** page, review the certificate information to be used to generate the request.</span></span>

14. <span data-ttu-id="73979-130">コマンドの実行が完了したら、**ログを表示**するか、[次へ] をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="73979-130">After the commands finish running, you can **View Log**, or click Next to continue.</span></span>

15. <span data-ttu-id="73979-131">[**証明書要求ファイル**] ページで、[**完了**] をクリックして、証明書ウィザードの [**表示**] または [終了] をクリックし、生成された証明書署名要求 (CSR) ファイルを表示できます。</span><span class="sxs-lookup"><span data-stu-id="73979-131">On the **Certificate Request File** page, you can view the generated certificate signing request (CSR) file by clicking **View** or exit the Certificate Wizard by clicking **Finish**.</span></span>

16. <span data-ttu-id="73979-132">要求ファイルをコピーして、公開証明機関に提出します。</span><span class="sxs-lookup"><span data-stu-id="73979-132">Copy the request file and submit to your public certification authority.</span></span>

17. <span data-ttu-id="73979-133">公開証明書の受信、インポート、割り当てが完了したら、Edge Server サービスを停止して再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="73979-133">After receiving, importing and assigning the public certificate, you must stop and restart the Edge Server services.</span></span> <span data-ttu-id="73979-134">これを行うには、Lync Server 管理コンソールで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="73979-134">You do this by typing in the Lync Server Management console:</span></span>
    
        Stop-CsWindowsService

      &nbsp;
    
        Start-CsWindowsService

</div>

<div>

## <a name="configure-a-new-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="73979-135">新しい Lync Server 2013 XMPP ゲートウェイを構成する</span><span class="sxs-lookup"><span data-stu-id="73979-135">Configure a new Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="73979-136">[Lync Server コントロール パネル] を開きます。</span><span class="sxs-lookup"><span data-stu-id="73979-136">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="73979-137">左側のナビゲーションバーで、[**フェデレーションと外部アクセス**] をクリックし、[ **Xmpp フェデレーションパートナー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="73979-137">In the left navigation bar, click **Federation and External Access** and then click **XMPP Federated Partners**.</span></span>

3.  <span data-ttu-id="73979-138">新しい構成を作成するには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="73979-138">To create a new configuration, click **New**.</span></span>

4.  <span data-ttu-id="73979-139">次の設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="73979-139">Define the following settings:</span></span>

5.  <span data-ttu-id="73979-140">**プライマリドメイン**    (必須)。</span><span class="sxs-lookup"><span data-stu-id="73979-140">**Primary domain**    (Required).</span></span> <span data-ttu-id="73979-141">プライマリドメインは、XMPP パートナーのベースドメインです。</span><span class="sxs-lookup"><span data-stu-id="73979-141">The primary domain is the base domain of the XMPP partner.</span></span> <span data-ttu-id="73979-142">たとえば、XMPP パートナードメイン名の**fabrikam.com**を入力します。</span><span class="sxs-lookup"><span data-stu-id="73979-142">For example, you would enter **fabrikam.com** for the XMPP partner domain name.</span></span> <span data-ttu-id="73979-143">このエントリは必須です。</span><span class="sxs-lookup"><span data-stu-id="73979-143">This is a required entry.</span></span>

6.  <span data-ttu-id="73979-144">**説明**   説明は、この特定の構成のメモやその他の識別情報の説明です。</span><span class="sxs-lookup"><span data-stu-id="73979-144">**Description**   The description is for notes or other identifying information for this particular configuration.</span></span> <span data-ttu-id="73979-145">このエントリは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="73979-145">This entry is optional.</span></span>

7.  <span data-ttu-id="73979-146">**追加ドメイン**   追加ドメインは、xmpp パートナーのドメインの一部であり、許可されている xmpp 通信の一部として含めることができるドメインです。</span><span class="sxs-lookup"><span data-stu-id="73979-146">**Additional domains**   Additional domains are domains that are a part of your XMPP partner’s domain that should be included as part of the allowed XMPP communication.</span></span> <span data-ttu-id="73979-147">たとえば、プライマリドメインが**fabrikam.com**の場合は、fabrikam.com の下にある他のすべてのドメインを一覧表示します。これにより、xmpp で通信することができます。</span><span class="sxs-lookup"><span data-stu-id="73979-147">For example, if the primary domain is **fabrikam.com**, then you would list all other domains that are under fabrikam.com that you will communicate with by way of XMPP.</span></span>

8.  <span data-ttu-id="73979-148">**パートナー**   の種類**パートナーの種類**は必須の設定です。</span><span class="sxs-lookup"><span data-stu-id="73979-148">**Partner type**   The **Partner type** is a required setting.</span></span> <span data-ttu-id="73979-149">追加できる連絡先を説明して適用するには、次のいずれかを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="73979-149">You must choose one of the following to describe and enforce what contacts can be added.</span></span> <span data-ttu-id="73979-150">次のいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="73979-150">You can select from:</span></span>
    
      - <span data-ttu-id="73979-151">**フェデレーション**   パートナー**の**種類は、Lync Server の展開と xmpp パートナーとの間の高レベルの信頼を表します。</span><span class="sxs-lookup"><span data-stu-id="73979-151">**Federated**   A **Federated** partner type represents a high level of trust between the Lync Server deployment and the XMPP partner.</span></span><span data-ttu-id="73979-152">同じエンタープライズ内または確立されたビジネス関係がある場合は、このパートナーの種類を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="73979-152">  This partner type is recommended for federating with XMPP servers within the same enterprise or where there is an established business relationship.</span></span><span data-ttu-id="73979-153">フェデレーションパートナーの XMPP 連絡先は、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="73979-153">  XMPP contacts in Federated partners can:</span></span>
        
        1.  <span data-ttu-id="73979-154">Lync ユーザーからの明示的な承認なしに、Lync の連絡先を追加して、自分のプレゼンスを表示します。</span><span class="sxs-lookup"><span data-stu-id="73979-154">Add Lync contacts and view their presence without express authorization from the Lync user.</span></span>
        
        2.  <span data-ttu-id="73979-155">Lync ユーザーが連絡先リストに追加したかどうかにかかわらず、Lync の連絡先にインスタントメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="73979-155">Send instant messages to Lync contacts whether or not the Lync user has added them into their contact list.</span></span>
        
        3.  <span data-ttu-id="73979-156">Lync ユーザーの状態メモを表示します。</span><span class="sxs-lookup"><span data-stu-id="73979-156">See a Lync user’s status notes.</span></span>
    
      - <span data-ttu-id="73979-157">**公開**確認済み**パートナーと**は、ユーザーの身元を確認するために信頼されているパブリックの xmpp プロバイダーです。   </span><span class="sxs-lookup"><span data-stu-id="73979-157">**Public verified**   A **Public verified** partner is a public XMPP provider that is trusted to verify the identity of its users.</span></span><span data-ttu-id="73979-158">パブリック検証ネットワークの XMPP の連絡先は、lync ユーザーのエクスプレス認証を使わずに、Lync の連絡先を追加して、そのプレゼンスを表示し、インスタントメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="73979-158">  XMPP contacts in Public Verified networks can add Lync contacts and view their presence and send instant messages to them without express authorization from the Lync users.</span></span><span data-ttu-id="73979-159">パブリック確認ネットワークの XMPP の連絡先には、Lync ユーザーの状態メモが表示されません。</span><span class="sxs-lookup"><span data-stu-id="73979-159">  XMPP contacts in public verified networks never see a Lync users’ status notes.</span></span><span data-ttu-id="73979-160">この設定はお勧めできません。</span><span class="sxs-lookup"><span data-stu-id="73979-160">  This setting is not recommended.</span></span>
    
      - <span data-ttu-id="73979-161">**公開**されていない公開されてい**ないパートナーは**、そのユーザーの id を確認するために信頼されていないパブリックの xmpp プロバイダーです。   </span><span class="sxs-lookup"><span data-stu-id="73979-161">**Public unverified**   A **Public unverified** partner is a public XMPP provider that is not trusted to verify the identity of its users.</span></span><span data-ttu-id="73979-162">公開されていないパブリックネットワーク上の XMPP ユーザーは、連絡先リストに追加して、lync ユーザーに対して明示的に許可されていない限り、Lync ユーザーと通信することはできません。</span><span class="sxs-lookup"><span data-stu-id="73979-162">  XMPP users on Public Unverified networks cannot communicate with Lync users unless the Lync user has expressly authorized them by adding them to the contact list.</span></span><span data-ttu-id="73979-163">公開されていないパブリックネットワーク上の XMPP ユーザーは、Lync ユーザーの状態メモを見ることはできません。</span><span class="sxs-lookup"><span data-stu-id="73979-163">  XMPP users on public unverified networks never see Lync users’ status notes.</span></span><span data-ttu-id="73979-164">この設定は、Google Talk などのパブリック XMPP プロバイダーとのフェデレーションの場合にお勧めします。</span><span class="sxs-lookup"><span data-stu-id="73979-164">  This setting is recommended for any federation with public XMPP providers such as Google Talk.</span></span>

9.  <span data-ttu-id="73979-165">**接続の種類:** さまざまなルールとダイヤルバック設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="73979-165">**Connection Type:** Defines the various rules and dialback settings.</span></span>
    
      - <span data-ttu-id="73979-166">**Tls ネゴシエーション**   は、tls ネゴシエーションルールを定義します。</span><span class="sxs-lookup"><span data-stu-id="73979-166">**TLS Negotiation**   Defines the TLS negotiation rules.</span></span> <span data-ttu-id="73979-167">XMPP サービスでは TLS が必要になる場合があります。 TLS をオプションにすることも、TLS がサポートされないことを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="73979-167">An XMPP service can require TLS, can make TLS optional, or you define that TLS is not supported.</span></span> <span data-ttu-id="73979-168">[オプションを選択すると、必須のネゴシエーションの意思決定を行うための XMPP サービスの要件が残ります。</span><span class="sxs-lookup"><span data-stu-id="73979-168">Choosing Optional leaves the requirement up to the XMPP service for a mandatory-to-negotiate decision.</span></span> <span data-ttu-id="73979-169">使用可能な SASL、TLS、およびダイヤルバックのネゴシエーションに関するすべての設定と詳細を表示するには、「有効なエラーと既知のエラー構成」を参照してください。詳しくは、「 [Lync Server 2013 での XMPP フェデレーションパートナーのネゴシエーション設定](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="73979-169">To view all possible settings and details for SASL, TLS and Dialback negotiation –including not valid and known error configurations - see [Negotiation settings for XMPP federated partners in Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).</span></span>
        
          - <span></span>  
            <span data-ttu-id="73979-170">**必須**   : xmpp サービスには TLS ネゴシエーションが必要です。</span><span class="sxs-lookup"><span data-stu-id="73979-170">**Required**   The XMPP service requires TLS negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="73979-171">**オプション**   : xmpp サービスは、TLS が必須からネゴシエートされていることを示します。</span><span class="sxs-lookup"><span data-stu-id="73979-171">**Optional**   The XMPP service indicates that TLS is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="73979-172">**サポート**   されていない xmpp サービスは、TLS をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="73979-172">**Not Supported**   The XMPP service does not support TLS.</span></span>
    
      - <span data-ttu-id="73979-173">**Sasl ネゴシエーション**   は、sasl ネゴシエーション規則を定義しています。</span><span class="sxs-lookup"><span data-stu-id="73979-173">**SASL negotiation**   Defines the SASL negotiation rules.</span></span> <span data-ttu-id="73979-174">XMPP サービスでは、SASL を要求できるほか、SASL をオプションとして使うこともできます。また、SASL がサポートされていないことを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="73979-174">An XMPP service can require SASL, can make SASL optional, or you define that SASL is not supported.</span></span> <span data-ttu-id="73979-175">[オプションを選択すると、必須のネゴシエーションの意思決定を行うために、パートナーの XMPP サービスまでの要件が残ります。</span><span class="sxs-lookup"><span data-stu-id="73979-175">Choosing Optional leaves the requirement up to the partner XMPP service for a mandatory-to-negotiate decision.</span></span>
        
          - <span></span>  
            <span data-ttu-id="73979-176">**必須**   xmpp サービスには、SASL ネゴシエーションが必要です。</span><span class="sxs-lookup"><span data-stu-id="73979-176">**Required**   The XMPP service requires SASL negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="73979-177">**オプション**   : xmpp サービスは、SASL のネゴシエーションが必須であることを示します。</span><span class="sxs-lookup"><span data-stu-id="73979-177">**Optional**   The XMPP service indicates that SASL is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="73979-178">**サポート**   されていない xmpp サービスは SASL をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="73979-178">**Not Supported**   The XMPP service does not support SASL.</span></span>
    
      - <span data-ttu-id="73979-179">**サポートサーバーのダイヤルバックのネゴシエーション**サポートサーバーのダイヤルバックネゴシエーションプロセスでは、ドメインネームシステム (DNS) と権限を持つサーバーを使用して、要求が有効な XMPP パートナーから送信されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="73979-179">**Support server dialback negotiation** The support server dialback negotiation process uses the domain name system (DNS) and an authoritative server to verify that the request came from a valid XMPP partner.</span></span> <span data-ttu-id="73979-180">これを行うために、発信元のサーバーは、生成されたダイヤルバックキーを使用して、特定の種類のメッセージを作成し、DNS で受信側サーバーを検索します。</span><span class="sxs-lookup"><span data-stu-id="73979-180">To do this, the originating server creates a message of a specific type with a generated dialback key and looks up the receiving server in DNS.</span></span> <span data-ttu-id="73979-181">送信元のサーバーは、受信側サーバーであると思われるように、XML ストリームのキーを結果の DNS 参照に送信します。</span><span class="sxs-lookup"><span data-stu-id="73979-181">The originating server sends the key in an XML stream to the resulting DNS lookup, presumably the receiving server.</span></span> <span data-ttu-id="73979-182">XML ストリームを介してキーを受け取ると、受信側サーバーは元のサーバーには応答しませんが、既知の権限を持つサーバーにキーを送信します。</span><span class="sxs-lookup"><span data-stu-id="73979-182">On receipt of the key over the XML stream, the receiving server does not respond to the originating server, but sends the key to a known authoritative server.</span></span> <span data-ttu-id="73979-183">権限を持つサーバーは、キーが有効であるか無効であるかを確認します。</span><span class="sxs-lookup"><span data-stu-id="73979-183">The authoritative server verifies that the key is either valid or not valid.</span></span> <span data-ttu-id="73979-184">有効でない場合、受信側サーバーは元のサーバーには応答しません。</span><span class="sxs-lookup"><span data-stu-id="73979-184">If not valid, the receiving server does not respond to the originating server.</span></span> <span data-ttu-id="73979-185">キーが有効である場合、受信側のサーバーは、id とキーが有効であり、会話を開始できます。</span><span class="sxs-lookup"><span data-stu-id="73979-185">If the key is valid, the receiving server informs the originating server that the identity and key is valid and the conversation can commence.</span></span>
        
        <span data-ttu-id="73979-186">**ダイヤルバックのネゴシエーション**には、次の2つの有効な状態があります。</span><span class="sxs-lookup"><span data-stu-id="73979-186">There are two valid states for **Dialback negotiation**:</span></span>
        
          - <span></span>  
            <span data-ttu-id="73979-187">**True**   xmpp サーバーは、発信元のサーバーから要求を受信するときに、ダイヤルバックのネゴシエーションを使うように構成されています。</span><span class="sxs-lookup"><span data-stu-id="73979-187">**True**   The XMPP server is configured to use Dialback negotiation if a request should be received from an originating server.</span></span>
        
          - <span></span>  
            <span data-ttu-id="73979-188">**False**   xmpp サーバーは、ダイヤルバックのネゴシエーションを使用するように構成されていません。また、発信元のサーバーから要求を受信する場合は、無視されます。</span><span class="sxs-lookup"><span data-stu-id="73979-188">**False**   The XMPP server is not configured to use Dialback negotiation and if a request should be received from an originating server, it will be ignored.</span></span>

10. <span data-ttu-id="73979-189">[**コミット**] をクリックして、サイトまたはユーザーポリシーの変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="73979-189">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

<div>

## <a name="update-dns-records-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="73979-190">Lync Server 2013 XMPP ゲートウェイの DNS レコードを更新する</span><span class="sxs-lookup"><span data-stu-id="73979-190">Update DNS Records for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="73979-191">XMPP フェデレーション用の DNS を構成するには、次の SRV レコードを外部 DNS\_: xmpp サーバーに追加します。\_tcp。\<ドメイン名\> SRV レコードはエッジサーバーのアクセスエッジ FQDN に解決され、ポート値は5269になります。</span><span class="sxs-lookup"><span data-stu-id="73979-191">To configure DNS for XMPP federation, you add the following SRV record to your external DNS:\_xmpp-server.\_tcp.\<domain name\> The SRV record will resolve to the Access Edge FQDN of the Edge server, with a port value of 5269.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

