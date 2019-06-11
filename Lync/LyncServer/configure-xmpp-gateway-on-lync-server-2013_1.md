---
title: Lync Server 2013 での XMPP ゲートウェイの構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure XMPP gateway on Lync Server 2013
ms:assetid: 00777a34-cc36-4992-9459-08c14543ef6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687953(v=OCS.15)
ms:contentKeyID: 49733538
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5874495bb7a398ab8b5b5cde6376faaa6c193a85
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840842"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-on-lync-server-2013"></a><span data-ttu-id="e6052-102">Lync Server 2013 での XMPP ゲートウェイの構成</span><span class="sxs-lookup"><span data-stu-id="e6052-102">Configure XMPP gateway on Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6052-103">_**最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="e6052-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="e6052-104">拡張メッセージングとプレゼンスプロトコル (XMPP) フェデレーションパートナーをサポートするためにポリシーを構成すると、そのポリシーは XMPP フェデレーションドメインのユーザーに適用されますが、セッション開始プロトコル (SIP) のインスタントメッセージング (IM) サービスプロバイダーのユーザーには適用されません。(たとえば、Windows Live など)、または SIP フェデレーションドメイン。</span><span class="sxs-lookup"><span data-stu-id="e6052-104">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains.</span></span> <span data-ttu-id="e6052-105">ユーザーが連絡先を追加して通信できるようにする、各 XMPP フェデレーションドメインに対して XMPP フェデレーションパートナーを構成します。</span><span class="sxs-lookup"><span data-stu-id="e6052-105">You configure an XMPP Federated Partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="e6052-106">ポリシーが設定されると、追加のタスクとして、XMPP ゲートウェイ証明書の構成、Lync Server 2013 XMPP ゲートウェイの展開、および最終的に XMPP ゲートウェイの DNS レコードの更新が行われます。</span><span class="sxs-lookup"><span data-stu-id="e6052-106">Once the policies are in place, additional tasks include configuring the XMPP Gateway certificates, deploying the Lync Server 2013 XMPP Gateway, and finally updating the DNS records for the XMPP Gateway.</span></span>

<div>

## <a name="configure-xmpp-gateway-certificates-on-the-lync-server-2013-edge-server"></a><span data-ttu-id="e6052-107">Lync Server 2013 Edge サーバーで XMPP ゲートウェイ証明書を構成する</span><span class="sxs-lookup"><span data-stu-id="e6052-107">Configure XMPP Gateway Certificates on the Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="e6052-108">エッジサーバーの展開ウィザードで、[**手順 3: 証明書の要求、インストール、または割り当て**] の横にある [実行] を**もう一度**クリックします。</span><span class="sxs-lookup"><span data-stu-id="e6052-108">On the Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="e6052-109">初めてエッジサーバーを展開する場合は、[実行] ではなく、[実行] と表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6052-109">If you are deploying the Edge Server for the first time, you will see Run instead of Run Again.</span></span>

    
    </div>

2.  <span data-ttu-id="e6052-110">[**利用可能な証明書タスク**] ページで、[**新しい証明書要求を作成する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6052-110">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="e6052-111">[**証明書の要求**] ページで、[**外部境界の証明書**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6052-111">On the **Certificate Request** page, click **External Edge Certificate**.</span></span>

4.  <span data-ttu-id="e6052-112">[**遅延または即時要求**] ページで、[**今すぐ要求を準備するが、後で送信**する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="e6052-112">On the **Delayed or Immediate Request** page, select the **Prepare the request now, but send it later** check box.</span></span>

5.  <span data-ttu-id="e6052-113">[**証明書要求ファイル**] ページで、要求を保存するファイルの完全パスとファイル名を入力します (たとえば、c:\\cert\_外部\_edge)。</span><span class="sxs-lookup"><span data-stu-id="e6052-113">On the **Certificate Request File** page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

6.  <span data-ttu-id="e6052-114">[**代替証明書テンプレートの指定**] ページで、既定の web サーバテンプレート以外のテンプレートを使用するには、[**選択された証明機関に別の証明書テンプレートを使用**する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="e6052-114">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected certification authority** check box.</span></span>

7.  <span data-ttu-id="e6052-115">[**名前とセキュリティの設定**] ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e6052-115">On the **Name and Security Settings** page, do the following:</span></span>
    
    1.  <span data-ttu-id="e6052-116">[**フレンドリ名**] に、証明書の表示名を入力します。</span><span class="sxs-lookup"><span data-stu-id="e6052-116">In **Friendly name**, type a display name for the certificate.</span></span>
    
    2.  <span data-ttu-id="e6052-117">**ビット長**では、ビット長 (通常は2048の既定値) を指定します。</span><span class="sxs-lookup"><span data-stu-id="e6052-117">In **Bit length**, specify the bit length (typically, the default of 2048).</span></span>
    
    3.  <span data-ttu-id="e6052-118">[**証明書の秘密キーをエクスポート可能としてマーク**する] チェックボックスがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e6052-118">Verify that the **Mark certificate private key as exportable** check box is selected.</span></span>

8.  <span data-ttu-id="e6052-119">[**組織の情報**] ページで、組織の名前と組織単位 (たとえば、部門や部署) を入力します。</span><span class="sxs-lookup"><span data-stu-id="e6052-119">On the **Organization Information** page, type the name for the organization and the organizational unit (for example, a division or department).</span></span>

9.  <span data-ttu-id="e6052-120">[**地理情報**] ページで、場所情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="e6052-120">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="e6052-121">[ **Subject Name/Subject name** ] ページには、ウィザードによって自動的に入力される情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6052-121">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed.</span></span> <span data-ttu-id="e6052-122">追加の件名の代替名が必要な場合は、次の2つの手順で指定します。</span><span class="sxs-lookup"><span data-stu-id="e6052-122">If additional subject alternative names are needed, you specify them in the next two steps.</span></span>

11. <span data-ttu-id="e6052-123">[**サブジェクト代替名 (san)] ページの Sip ドメイン設定**で、[Domain] チェックボックスをオンにして sip を追加します。\<[\>件名の代替名] ボックスの一覧に sipdomain エントリを入力します。</span><span class="sxs-lookup"><span data-stu-id="e6052-123">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the domain check box to add a sip.\<sipdomain\> entry to the subject alternative names list.</span></span>

12. <span data-ttu-id="e6052-124">[**追加のサブジェクト代替名の構成**] ページで、必要なその他のサブジェクトの代替名を指定します。</span><span class="sxs-lookup"><span data-stu-id="e6052-124">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="e6052-125">XMPP プロキシがインストールされている場合、既定では、ドメイン名 (contoso.com など) が SAN エントリに設定されます。</span><span class="sxs-lookup"><span data-stu-id="e6052-125">If the XMPP proxy is installed, by default the domain name (such as contoso.com) is populated in the SAN entries.</span></span> <span data-ttu-id="e6052-126">他のエントリが必要な場合は、この手順で追加します。</span><span class="sxs-lookup"><span data-stu-id="e6052-126">If you require more entries, add them in this step.</span></span>

    
    </div>

13. <span data-ttu-id="e6052-127">[**要求の概要**] ページで、要求の生成に使用する証明書情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="e6052-127">On the **Request Summary** page, review the certificate information to be used to generate the request.</span></span>

14. <span data-ttu-id="e6052-128">コマンドの実行が完了したら、**ログを表示**するか、[**次へ**] をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="e6052-128">After the commands finish running, you can **View Log**, or click **Next** to continue.</span></span>

15. <span data-ttu-id="e6052-129">[**証明書要求ファイル**] ページで、[**完了**] をクリックして、証明書ウィザードの [表示] または [終了] をクリックし、生成された証明書署名要求 (CSR) ファイルを表示できます。</span><span class="sxs-lookup"><span data-stu-id="e6052-129">On the **Certificate Request File** page, you can view the generated certificate signing request (CSR) file by clicking View or exit the Certificate Wizard by clicking **Finish**.</span></span>

16. <span data-ttu-id="e6052-130">要求ファイルをコピーして、公開証明機関に提出します。</span><span class="sxs-lookup"><span data-stu-id="e6052-130">Copy the request file and submit to your public certification authority.</span></span>

17. <span data-ttu-id="e6052-131">公開証明書の受信、インポート、割り当てが完了したら、Edge Server サービスを停止して再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6052-131">After receiving, importing and assigning the public certificate, you must stop and restart the Edge Server services.</span></span> <span data-ttu-id="e6052-132">これを行うには、Lync Server 管理コンソールで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="e6052-132">You do this by typing in the Lync Server Management console:</span></span>
    
       ```
        Stop-CsWindowsService
       ```
    
       ```
        Start-CsWindowsService
       ```

</div>

<div>

## <a name="configure-a-new-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="e6052-133">新しい Lync Server 2013 XMPP ゲートウェイを構成する</span><span class="sxs-lookup"><span data-stu-id="e6052-133">Configure a new Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="e6052-134">[Lync Server コントロール パネル] を開きます。</span><span class="sxs-lookup"><span data-stu-id="e6052-134">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="e6052-135">左側のナビゲーションバーで、[**フェデレーションと外部アクセス**] をクリックし、[ **Xmpp フェデレーションパートナー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6052-135">In the left navigation bar, click **Federation and External Access** and then click **XMPP Federated Partners**.</span></span>

3.  <span data-ttu-id="e6052-136">新しい構成を作成するには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6052-136">To create a new configuration, click **New**.</span></span>

4.  <span data-ttu-id="e6052-137">次の設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="e6052-137">Define the following settings:</span></span>

5.  <span data-ttu-id="e6052-138">**プライマリドメイン**    (必須)。</span><span class="sxs-lookup"><span data-stu-id="e6052-138">**Primary domain**    (Required).</span></span> <span data-ttu-id="e6052-139">プライマリドメインは、XMPP パートナーのベースドメインです。</span><span class="sxs-lookup"><span data-stu-id="e6052-139">The primary domain is the base domain of the XMPP partner.</span></span> <span data-ttu-id="e6052-140">たとえば、XMPP パートナードメイン名の**fabrikam.com**を入力します。</span><span class="sxs-lookup"><span data-stu-id="e6052-140">For example, you would enter **fabrikam.com** for the XMPP partner domain name.</span></span> <span data-ttu-id="e6052-141">このエントリは必須です。</span><span class="sxs-lookup"><span data-stu-id="e6052-141">This is a required entry.</span></span>

6.  <span data-ttu-id="e6052-142">**説明**   説明は、この特定の構成のメモやその他の識別情報の説明です。</span><span class="sxs-lookup"><span data-stu-id="e6052-142">**Description**   The description is for notes or other identifying information for this particular configuration.</span></span> <span data-ttu-id="e6052-143">このエントリは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e6052-143">This entry is optional.</span></span>

7.  <span data-ttu-id="e6052-144">**追加ドメイン**   追加ドメインは、xmpp パートナーのドメインの一部であり、許可されている xmpp 通信の一部として含めることができるドメインです。</span><span class="sxs-lookup"><span data-stu-id="e6052-144">**Additional domains**   Additional domains are domains that are a part of your XMPP partner’s domain that should be included as part of the allowed XMPP communication.</span></span> <span data-ttu-id="e6052-145">たとえば、プライマリドメインが**fabrikam.com**の場合は、fabrikam.com の下にある他のすべてのドメインを一覧表示します。これにより、xmpp で通信することができます。</span><span class="sxs-lookup"><span data-stu-id="e6052-145">For example, if the primary domain is **fabrikam.com**, then you would list all other domains that are under fabrikam.com that you will communicate with by way of XMPP.</span></span>

8.  <span data-ttu-id="e6052-146">**パートナー**   の種類**パートナーの種類**は必須の設定です。</span><span class="sxs-lookup"><span data-stu-id="e6052-146">**Partner type**   The **Partner type** is a required setting.</span></span> <span data-ttu-id="e6052-147">追加できる連絡先を説明して適用するには、次のいずれかを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6052-147">You must choose one of the following to describe and enforce what contacts can be added.</span></span> <span data-ttu-id="e6052-148">次のいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="e6052-148">You can select from:</span></span>
    
      - <span data-ttu-id="e6052-149">**フェデレーション\*\*\*\*フェデレーション**パートナーの種類は、Lync Server の展開と xmpp パートナーの間の高レベルの信頼を表します。</span><span class="sxs-lookup"><span data-stu-id="e6052-149">**Federated** A **Federated** partner type represents a high level of trust between the Lync Server deployment and the XMPP partner.</span></span><span data-ttu-id="e6052-150">同じエンタープライズ内または確立されたビジネス関係がある場合は、このパートナーの種類を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e6052-150">  This partner type is recommended for federating with XMPP servers within the same enterprise or where there is an established business relationship.</span></span><span data-ttu-id="e6052-151">フェデレーションパートナーの XMPP 連絡先は、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="e6052-151">  XMPP contacts in Federated partners can:</span></span>
        
        1.  <span data-ttu-id="e6052-152">Lync ユーザーからの明示的な承認なしに、Lync の連絡先を追加して、自分のプレゼンスを表示します。</span><span class="sxs-lookup"><span data-stu-id="e6052-152">Add Lync contacts and view their presence without express authorization from the Lync user.</span></span>
        
        2.  <span data-ttu-id="e6052-153">Lync ユーザーが連絡先リストに追加したかどうかにかかわらず、Lync の連絡先にインスタントメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="e6052-153">Send instant messages to Lync contacts whether or not the Lync user has added them into their contact list.</span></span>
        
        3.  <span data-ttu-id="e6052-154">Lync ユーザーの状態メモを表示します。</span><span class="sxs-lookup"><span data-stu-id="e6052-154">See a Lync user’s status notes.</span></span>
    
      - <span data-ttu-id="e6052-155">**公開**確認済みパートナーとは、ユーザーの身元を確認するために信頼されているパブリックの xmpp プロバイダーです。 \*\*\*\*  </span><span class="sxs-lookup"><span data-stu-id="e6052-155">**Public verified** A **Public verified** partner is a public XMPP provider that is trusted to verify the identity of its users.</span></span><span data-ttu-id="e6052-156">パブリック検証ネットワークの XMPP の連絡先は、lync ユーザーのエクスプレス認証を使わずに、Lync の連絡先を追加して、そのプレゼンスを表示し、インスタントメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="e6052-156">  XMPP contacts in Public Verified networks can add Lync contacts and view their presence and send instant messages to them without express authorization from the Lync users.</span></span><span data-ttu-id="e6052-157">パブリック確認ネットワークの XMPP の連絡先には、Lync ユーザーの状態メモが表示されません。</span><span class="sxs-lookup"><span data-stu-id="e6052-157">  XMPP contacts in public verified networks never see a Lync users’ status notes.</span></span><span data-ttu-id="e6052-158">この設定はお勧めできません。</span><span class="sxs-lookup"><span data-stu-id="e6052-158">  This setting is not recommended.</span></span>
    
      - <span data-ttu-id="e6052-159">**パブリック未確認\*\*\*\*公開**されていないパートナーは、そのユーザーの id を確認するために信頼されていないパブリックの xmpp プロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="e6052-159">**Public unverified** A **Public unverified** partner is a public XMPP provider that is not trusted to verify the identity of its users.</span></span><span data-ttu-id="e6052-160">公開されていないパブリックネットワーク上の XMPP ユーザーは、連絡先リストに追加して、lync ユーザーに対して明示的に許可されていない限り、Lync ユーザーと通信することはできません。</span><span class="sxs-lookup"><span data-stu-id="e6052-160">  XMPP users on Public Unverified networks cannot communicate with Lync users unless the Lync user has expressly authorized them by adding them to the contact list.</span></span><span data-ttu-id="e6052-161">公開されていないパブリックネットワーク上の XMPP ユーザーは、Lync ユーザーの状態メモを見ることはできません。</span><span class="sxs-lookup"><span data-stu-id="e6052-161">  XMPP users on public unverified networks never see Lync users’ status notes.</span></span><span data-ttu-id="e6052-162">この設定は、Google Talk などのパブリック XMPP プロバイダーとのフェデレーションの場合にお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e6052-162">  This setting is recommended for any federation with public XMPP providers such as Google Talk.</span></span>

9.  <span data-ttu-id="e6052-163">**接続の種類:** さまざまなルールとダイヤルバック設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="e6052-163">**Connection Type:** Defines the various rules and dialback settings.</span></span>
    
      - <span data-ttu-id="e6052-164">**Tls ネゴシエーション**   は、tls ネゴシエーションルールを定義します。</span><span class="sxs-lookup"><span data-stu-id="e6052-164">**TLS Negotiation**   Defines the TLS negotiation rules.</span></span> <span data-ttu-id="e6052-165">XMPP サービスでは TLS が必要になる場合があります。 TLS をオプションにすることも、TLS がサポートされないことを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="e6052-165">An XMPP service can require TLS, can make TLS optional, or you define that TLS is not supported.</span></span> <span data-ttu-id="e6052-166">[オプションを選択すると、必須のネゴシエーションの意思決定を行うための XMPP サービスの要件が残ります。</span><span class="sxs-lookup"><span data-stu-id="e6052-166">Choosing Optional leaves the requirement up to the XMPP service for a mandatory-to-negotiate decision.</span></span> <span data-ttu-id="e6052-167">使用可能な SASL、TLS、およびダイヤルバックのネゴシエーションに関するすべての設定と詳細を表示するには、「無効なエラーと既知のエラーの構成」を参照してください。「 [Lync Server 2013 の XMPP フェデレーションパートナーのネゴシエーション設定](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6052-167">To view all possible settings and details for SASL, TLS and Dialback negotiation – including not valid and known error configurations - see [Negotiation settings for XMPP federated partners in Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)</span></span>
        
           - <span data-ttu-id="e6052-168">**必須**   : xmpp サービスには TLS ネゴシエーションが必要です。</span><span class="sxs-lookup"><span data-stu-id="e6052-168">**Required**   The XMPP service requires TLS negotiation.</span></span>
        
           - <span data-ttu-id="e6052-169">**オプション**   : xmpp サービスは、TLS が必須からネゴシエートされていることを示します。</span><span class="sxs-lookup"><span data-stu-id="e6052-169">**Optional**   The XMPP service indicates that TLS is mandatory-to-negotiate.</span></span>
        
           - <span data-ttu-id="e6052-170">**サポート**   されていない xmpp サービスは、TLS をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="e6052-170">**Not Supported**   The XMPP service does not support TLS.</span></span>
    
      - <span data-ttu-id="e6052-171">**Sasl ネゴシエーション**   は、sasl ネゴシエーション規則を定義しています。</span><span class="sxs-lookup"><span data-stu-id="e6052-171">**SASL negotiation**   Defines the SASL negotiation rules.</span></span> <span data-ttu-id="e6052-172">XMPP サービスでは、SASL を要求できるほか、SASL をオプションとして使うこともできます。また、SASL がサポートされていないことを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="e6052-172">An XMPP service can require SASL, can make SASL optional, or you define that SASL is not supported.</span></span> <span data-ttu-id="e6052-173">[オプションを選択すると、必須のネゴシエーションの意思決定を行うために、パートナーの XMPP サービスまでの要件が残ります。</span><span class="sxs-lookup"><span data-stu-id="e6052-173">Choosing Optional leaves the requirement up to the partner XMPP service for a mandatory-to-negotiate decision.</span></span>
        
           - <span data-ttu-id="e6052-174">**必須**   xmpp サービスには、SASL ネゴシエーションが必要です。</span><span class="sxs-lookup"><span data-stu-id="e6052-174">**Required**   The XMPP service requires SASL negotiation.</span></span>
        
           - <span data-ttu-id="e6052-175">**オプション**   : xmpp サービスは、SASL のネゴシエーションが必須であることを示します。</span><span class="sxs-lookup"><span data-stu-id="e6052-175">**Optional**   The XMPP service indicates that SASL is mandatory-to-negotiate.</span></span>
        
           - <span data-ttu-id="e6052-176">**サポート**   されていない xmpp サービスは SASL をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="e6052-176">**Not Supported**   The XMPP service does not support SASL.</span></span>
    
      - <span data-ttu-id="e6052-177">**サポートサーバーのダイヤルバックのネゴシエーション**サポートサーバーのダイヤルバックネゴシエーションプロセスでは、ドメインネームシステム (DNS) と権限を持つサーバーを使用して、要求が有効な XMPP パートナーから送信されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="e6052-177">**Support server dialback negotiation** The support server dialback negotiation process uses the domain name system (DNS) and an authoritative server to verify that the request came from a valid XMPP partner.</span></span> <span data-ttu-id="e6052-178">これを行うために、発信元のサーバーは、生成されたダイヤルバックキーを使用して、特定の種類のメッセージを作成し、DNS で受信側サーバーを検索します。</span><span class="sxs-lookup"><span data-stu-id="e6052-178">To do this, the originating server creates a message of a specific type with a generated dialback key and looks up the receiving server in DNS.</span></span> <span data-ttu-id="e6052-179">送信元のサーバーは、受信側サーバーであると思われるように、XML ストリームのキーを結果の DNS 参照に送信します。</span><span class="sxs-lookup"><span data-stu-id="e6052-179">The originating server sends the key in an XML stream to the resulting DNS lookup, presumably the receiving server.</span></span> <span data-ttu-id="e6052-180">XML ストリームを介してキーを受け取ると、受信側サーバーは元のサーバーには応答しませんが、既知の権限を持つサーバーにキーを送信します。</span><span class="sxs-lookup"><span data-stu-id="e6052-180">On receipt of the key over the XML stream, the receiving server does not respond to the originating server, but sends the key to a known authoritative server.</span></span> <span data-ttu-id="e6052-181">権限を持つサーバーは、キーが有効であるか無効であるかを確認します。</span><span class="sxs-lookup"><span data-stu-id="e6052-181">The authoritative server verifies that the key is either valid or not valid.</span></span> <span data-ttu-id="e6052-182">有効でない場合、受信側サーバーは元のサーバーには応答しません。</span><span class="sxs-lookup"><span data-stu-id="e6052-182">If not valid, the receiving server does not respond to the originating server.</span></span> <span data-ttu-id="e6052-183">キーが有効である場合、受信側のサーバーは、id とキーが有効であり、会話を開始できます。</span><span class="sxs-lookup"><span data-stu-id="e6052-183">If the key is valid, the receiving server informs the originating server that the identity and key is valid and the conversation can commence.</span></span>
        
        <span data-ttu-id="e6052-184">**ダイヤルバックのネゴシエーション**には、次の2つの有効な状態があります。</span><span class="sxs-lookup"><span data-stu-id="e6052-184">There are two valid states for **Dialback negotiation**:</span></span>
        
           - <span data-ttu-id="e6052-185">**True**   xmpp サーバーは、発信元のサーバーから要求を受信するときに、ダイヤルバックのネゴシエーションを使うように構成されています。</span><span class="sxs-lookup"><span data-stu-id="e6052-185">**True**   The XMPP server is configured to use Dialback negotiation if a request should be received from an originating server.</span></span>
        
           - <span data-ttu-id="e6052-186">**False**   xmpp サーバーは、ダイヤルバックのネゴシエーションを使用するように構成されていません。また、発信元のサーバーから要求を受信する場合は、無視されます。</span><span class="sxs-lookup"><span data-stu-id="e6052-186">**False**   The XMPP server is not configured to use Dialback negotiation and if a request should be received from an originating server, it will be ignored.</span></span>

10. <span data-ttu-id="e6052-187">[**コミット**] をクリックして、サイトまたはユーザーポリシーの変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="e6052-187">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

<div>

## <a name="update-dns-records-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="e6052-188">Lync Server 2013 XMPP ゲートウェイの DNS レコードを更新する</span><span class="sxs-lookup"><span data-stu-id="e6052-188">Update DNS Records for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="e6052-189">XMPP フェデレーション用の DNS を構成するには、次の SRV レコードを外部 DNS\_: xmpp サーバーに追加します。\_tcp。\<ドメイン名\> SRV レコードはエッジサーバーのアクセスエッジ FQDN に解決され、ポート値は5269になります。</span><span class="sxs-lookup"><span data-stu-id="e6052-189">To configure DNS for XMPP federation, you add the following SRV record to your external DNS:\_xmpp-server.\_tcp.\<domain name\> The SRV record will resolve to the Access Edge FQDN of the Edge server, with a port value of 5269.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

