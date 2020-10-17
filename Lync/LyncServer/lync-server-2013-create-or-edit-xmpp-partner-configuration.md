---
title: 'Lync Server 2013: XMPP パートナー構成の作成または編集'
description: 'Lync Server 2013: XMPP パートナー構成を作成または編集します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit XMPP partner configuration
ms:assetid: 362dbe5e-8ee9-4aba-8c26-5907312b4a60
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552447(v=OCS.15)
ms:contentKeyID: 48679558
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19289df1920287984f104bb1bdfa214d6f83f5cf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553873"
---
# <a name="create-or-edit-xmpp-partner-configuration-in-lync-server-2013"></a><span data-ttu-id="8eca3-103">Lync Server 2013 での XMPP パートナー構成の作成または編集</span><span class="sxs-lookup"><span data-stu-id="8eca3-103">Create or edit XMPP partner configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8eca3-104">_**トピックの最終更新日:** 2014-09-03_</span><span class="sxs-lookup"><span data-stu-id="8eca3-104">_**Topic Last Modified:** 2014-09-03_</span></span>

<span data-ttu-id="8eca3-105">Microsoft Lync Server 2013 では、フロントエンドサーバーまたはフロントエンドプールのエッジサーバーと XMPP ゲートウェイに、拡張可能なメッセージングとプレゼンスプロトコル (XMPP) プロキシが統合されています。</span><span class="sxs-lookup"><span data-stu-id="8eca3-105">Microsoft Lync Server 2013 integrates an Extensible Messaging and Presence Protocol (XMPP) proxy on the Edge Server and an XMPP Gateway on the Front End Server or Front End pool.</span></span> <span data-ttu-id="8eca3-106">他の XMPP 展開からの接続を許可するには、Lync Server コントロールパネルで XMPP を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8eca3-106">To allow connections from other XMPP deployments, you must configure XMPP in the Lync Server Control Panel.</span></span> <span data-ttu-id="8eca3-107">XMPP ドメインベースで設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="8eca3-107">You configure settings on an XMPP domain basis.</span></span> <span data-ttu-id="8eca3-108">新しいパートナー関連付けを作成するには、以下の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="8eca3-108">To create a new partner association, you do the following:</span></span>

<div>

## <a name="to-create-a-new-federated-partner-or-edit-an-existing-configuration"></a><span data-ttu-id="8eca3-109">新しいフェデレーションパートナーを作成する、または既存の構成を編集するには</span><span class="sxs-lookup"><span data-stu-id="8eca3-109">To create a new federated partner or edit an existing configuration</span></span>

1.  <span data-ttu-id="8eca3-110">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="8eca3-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8eca3-111">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="8eca3-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8eca3-112">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8eca3-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8eca3-113">左側のナビゲーション バーで [**フェデレーションと外部アクセス**] をクリックし、[**XMPP フェデレーション パートナー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8eca3-113">In the left navigation bar, click **Federation and External Access**, and then click **XMPP Federated Partners**.</span></span>

4.  <span data-ttu-id="8eca3-114">新しい較正を作成するには、[**新規作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8eca3-114">To create a new configuration, click **New**</span></span>

5.  <span data-ttu-id="8eca3-115">既存の構成を編集するには、構成を選択して [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8eca3-115">To edit an existing configuration, select the configuration and click **Edit**</span></span>

6.  <span data-ttu-id="8eca3-116">[**XMPP フェデレーション パートナー**] の構成を作成、または編集するには、以下の設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="8eca3-116">To create or edit configurations for **XMPP Federated Partners**, you define the following settings:</span></span>

7.  <span data-ttu-id="8eca3-117">**プライマリドメイン** (必須)。</span><span class="sxs-lookup"><span data-stu-id="8eca3-117">**Primary domain** (Required).</span></span> <span data-ttu-id="8eca3-118">プライマリ ドメインは、XMPP パートナーの基本ドメインです。</span><span class="sxs-lookup"><span data-stu-id="8eca3-118">The primary domain is the base domain of the XMPP partner.</span></span> <span data-ttu-id="8eca3-119">たとえば、XMPP パートナーのドメイン名として **fabrikam.com** と入力します。</span><span class="sxs-lookup"><span data-stu-id="8eca3-119">For example, you would enter **fabrikam.com** for the XMPP partner domain name.</span></span> <span data-ttu-id="8eca3-120">これは必須のエントリです。</span><span class="sxs-lookup"><span data-stu-id="8eca3-120">This is a required entry.</span></span>

8.  <span data-ttu-id="8eca3-121">**説明**。</span><span class="sxs-lookup"><span data-stu-id="8eca3-121">**Description**.</span></span> <span data-ttu-id="8eca3-122">説明は、この特定の構成に関するメモまたはその他の識別情報を対象としています。</span><span class="sxs-lookup"><span data-stu-id="8eca3-122">The description is for notes or other identifying information for this particular configuration.</span></span> <span data-ttu-id="8eca3-123">このエントリは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="8eca3-123">This entry is optional.</span></span>

9.  <span data-ttu-id="8eca3-124">**追加のドメイン**。</span><span class="sxs-lookup"><span data-stu-id="8eca3-124">**Additional domains**.</span></span> <span data-ttu-id="8eca3-125">追加のドメインは、許可された XMPP 通信の一部として含める必要がある、XMPP パートナーのドメインの一部であるドメインです。</span><span class="sxs-lookup"><span data-stu-id="8eca3-125">Additional domains are domains that are a part of your XMPP partner’s domain that should be included as part of the allowed XMPP communication.</span></span> <span data-ttu-id="8eca3-126">たとえば、プライマリドメインが **fabrikam.com**の場合は、xmpp を使用して通信する fabrikam.com の下にある他のすべてのドメインを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="8eca3-126">For example, if the primary domain is **fabrikam.com**, then you would list all other domains that are under fabrikam.com that you will communicate with by way of XMPP.</span></span> <span data-ttu-id="8eca3-127">たとえば、fabrikam のメイン XMPP ドメインの下に、企業の XMPP ドメインと Information Technologies XMPP ドメインの **corp.fabrikam.com** と **it.fabrikam.com** を入力することができます。</span><span class="sxs-lookup"><span data-stu-id="8eca3-127">For example, you might enter **corp.fabrikam.com** and **it.fabrikam.com** for the Corporate XMPP domain and the Information Technologies XMPP domain under fabrikam.com’s main XMPP domain.</span></span>

10. <span data-ttu-id="8eca3-128">**パートナーの種類**。</span><span class="sxs-lookup"><span data-stu-id="8eca3-128">**Partner type**.</span></span> <span data-ttu-id="8eca3-129">**パートナーの種類**は必須の設定であり、ドロップダウンメニューから選択できる選択肢は3つあります。</span><span class="sxs-lookup"><span data-stu-id="8eca3-129">The **Partner type** is a required setting and gives you a selection of three choices in a drop-down menu.</span></span> <span data-ttu-id="8eca3-130">連絡先を追加できるようにするには、次のいずれかを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8eca3-130">You must choose one of the following to describe and enforce what contacts can be added.</span></span> <span data-ttu-id="8eca3-131">次の中から選択できます。</span><span class="sxs-lookup"><span data-stu-id="8eca3-131">You can select from:</span></span>
    
      - <span data-ttu-id="8eca3-132">**フェデレーション**。</span><span class="sxs-lookup"><span data-stu-id="8eca3-132">**Federated**.</span></span> <span data-ttu-id="8eca3-133">**フェデレーション**パートナーの種類は、Lync server または Office Communications Server 2007 R2 パートナー展開との間の信頼された接続です。</span><span class="sxs-lookup"><span data-stu-id="8eca3-133">A **Federated** partner type is a trusted connection between a Lync Server or Office Communications Server 2007 R2 partner deployment.</span></span>
    
      - <span data-ttu-id="8eca3-134">**パブリック確認済み**。</span><span class="sxs-lookup"><span data-stu-id="8eca3-134">**Public verified**.</span></span> <span data-ttu-id="8eca3-135">**一般に確認**されたパートナーとは、プロバイダーによって確認された展開の一部である連絡先をユーザーの連絡先リストに追加できることです。</span><span class="sxs-lookup"><span data-stu-id="8eca3-135">A **Public verified** partner is when contacts that are part of a deployment that are verified by the provider can be added to your user’s list of contacts.</span></span> <span data-ttu-id="8eca3-136">招待は、Lync ユーザーから送信できます。または Lync ユーザーは、パートナー連絡先からの招待を受け入れることができます。</span><span class="sxs-lookup"><span data-stu-id="8eca3-136">Invites can be sent from the Lync user or the Lync user can accept invites from the partner contact.</span></span>
    
      - <span data-ttu-id="8eca3-137">**パブリック未確認**。</span><span class="sxs-lookup"><span data-stu-id="8eca3-137">**Public unverified**.</span></span> <span data-ttu-id="8eca3-138">**公開**されていない関係とは、2つの展開間で確立および検証可能な状態がないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="8eca3-138">A **Public unverified** relationship implies that there is no established and verifiable status between the two deployments.</span></span> <span data-ttu-id="8eca3-139">Lync ユーザーは、その連絡先に対して未確認の連絡先を招待して、Lync ユーザーを連絡先リストに追加できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8eca3-139">A Lync user must invite the unverified contact for that contact to be able to add the Lync user to his contact list.</span></span> <span data-ttu-id="8eca3-140">たとえば、Google GTalk は、Lync Server に関連付けられているパブリックに検証された XMPP サービスではありません。</span><span class="sxs-lookup"><span data-stu-id="8eca3-140">For example, Google GTalk is not a public verified XMPP service as it relates to Lync Server.</span></span> <span data-ttu-id="8eca3-141">Lync ユーザーから明示的な招待が送信されていない限り、GTalk ユーザーは Lync ユーザーを連絡先として追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="8eca3-141">A GTalk user will not be able to add the Lync user as a contact unless there is an explicit invite sent from the Lync user.</span></span>

11. <span data-ttu-id="8eca3-142">ストリーム ネゴシエーションとセキュリティ方式についてのメモ - トランスポート層セキュリティ (TLS) と簡易認証およびセキュリティ層 (SASL):</span><span class="sxs-lookup"><span data-stu-id="8eca3-142">Notes on stream negotiation and the security methods Transport Layer Security (TLS) and Software Authentication and Security Layer (SASL):</span></span>
    
    <span data-ttu-id="8eca3-p110">**XMPP Standards Foundation** (XSF) と**インターネット技術標準化委員会** (IETF) は、TLS クライアント証明書、TLS サーバー証明書、および SASL メカニズムの使用と管理についての一連の規則と標準規格を定義しています。TLS と SASL の使用は、XMPP ストリームをセキュリティ保護するうえで必要な過程です。XMPP 標準規格ドキュメント **XEP-0178** では、以下のように記されています。「特に XMPP サービスが TLS でネゴシエーションが必須であると示されているとき、PKIX 証明書と SASL 外部メカニズムの使用での推奨プロトコル フローを指定します。」この XSF ドキュメントでの PKIX とは、公開キー基盤 (PKI) のことです。</span><span class="sxs-lookup"><span data-stu-id="8eca3-p110">The **XMPP Standards Foundation** (XSF) and the **Internet Engineering Task Force** (IETF) define a set of rules and standards for using and managing TLS client certificates, TLS server certificates, and the SASL mechanism. Using TLS and SASL is the required process for securing the XMPP stream. From the XMPP Standards document **XEP-0178**, “specifies a recommended protocol flow for use of the SASL EXTERNAL mechanism with PKIX certificates, especially when an XMPP service indicates that TLS is mandatory-to-negotiate.” PKIX, as stated in the XSF documentation, refers to public key infrastructure, also known as PKI.</span></span>
    
    <span data-ttu-id="8eca3-147">XMPP 要件についての詳細は、XSF ドキュメント XEP-0178 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8eca3-147">Refer to the XSF document XEP-0178 for more details on the XMPP requirements.</span></span> <span data-ttu-id="8eca3-148">詳細は、「XEP-0178: Best Practices for Use of SASL EXTERNAL with Certificates」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8eca3-148">For details, refer to “XEP-0178: Best Practices for Use of SASL EXTERNAL with Certificates”.</span></span> <http://xmpp.org/extensions/xep-0178.html>
    
    <span data-ttu-id="8eca3-149">IETF ドキュメント「拡張可能なメッセージングおよびプレゼンスプロトコル (XMPP): Core」、Section 5.0、STARTTLS ネゴシエーション」を参照してください <https://tools.ietf.org/html/rfc6120> 。</span><span class="sxs-lookup"><span data-stu-id="8eca3-149">Refer to the IETF document “Extensible Messaging and Presence Protocol (XMPP): Core“, Section 5.0, STARTTLS Negotiation <https://tools.ietf.org/html/rfc6120>.</span></span>
    
      - <span data-ttu-id="8eca3-150">**TLS ネゴシエーション**。</span><span class="sxs-lookup"><span data-stu-id="8eca3-150">**TLS Negotiation**.</span></span> <span data-ttu-id="8eca3-151">XMPP サービスでは、TLS を必須にすることも任意にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="8eca3-151">Defines the TLS negotiation rules.</span></span> <span data-ttu-id="8eca3-152">また、TLS がサポートされないように定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="8eca3-152">An XMPP service can require TLS, can make TLS optional, or you define that TLS is not supported.</span></span> <span data-ttu-id="8eca3-153">[任意] を選択すると、ネゴシエーションが必須であるかどうかの決定は XMPP サービスに委ねられます。</span><span class="sxs-lookup"><span data-stu-id="8eca3-153">Choosing Optional leaves the requirement up to the XMPP service for a mandatory-to-negotiate decision.</span></span> <span data-ttu-id="8eca3-154">使用可能なすべての設定と詳細を表示するには、有効でなく既知のエラーの構成を含む、SASL、TLS、およびダイヤルバックのネゴシエーションに関するすべての情報を表示します。「 [Lync Server 2013 の XMPP フェデレーションパートナーのネゴシエーション設定](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8eca3-154">To view all possible settings and details for SASL, TLS and Dialback negotiation –including not valid and known error configurations - see [Negotiation settings for XMPP federated partners in Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).</span></span>
        
          - <span></span>  
            <span data-ttu-id="8eca3-155">**必須**。</span><span class="sxs-lookup"><span data-stu-id="8eca3-155">**Required**.</span></span> <span data-ttu-id="8eca3-156">XMPP サービスは TLS ネゴシエーションを必要とします。</span><span class="sxs-lookup"><span data-stu-id="8eca3-156">The XMPP service requires TLS negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="8eca3-157">**省略可能**です。</span><span class="sxs-lookup"><span data-stu-id="8eca3-157">**Optional**.</span></span> <span data-ttu-id="8eca3-158">XMPP サービスは、TLS がネゴシエーション必須であることを示します。</span><span class="sxs-lookup"><span data-stu-id="8eca3-158">The XMPP service indicates that TLS is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="8eca3-159">**サポートされません**。</span><span class="sxs-lookup"><span data-stu-id="8eca3-159">**Not Supported**.</span></span> <span data-ttu-id="8eca3-160">XMPP サービスは TLS をサポートしません。</span><span class="sxs-lookup"><span data-stu-id="8eca3-160">The XMPP service does not support TLS.</span></span>
    
      - <span data-ttu-id="8eca3-161">**SASL ネゴシエーション**。</span><span class="sxs-lookup"><span data-stu-id="8eca3-161">**SASL negotiation**.</span></span> <span data-ttu-id="8eca3-162">XMPP サービスでは、SASL を必須にすることも任意にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="8eca3-162">Defines the SASL negotiation rules.</span></span> <span data-ttu-id="8eca3-163">また、SASL がサポートされないように定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="8eca3-163">An XMPP service can require SASL, can make SASL optional, or you define that SASL is not supported.</span></span> <span data-ttu-id="8eca3-164">[任意] を選択すると、ネゴシエーションが必須であるかどうかの決定は XMPP サービスに委ねられます。</span><span class="sxs-lookup"><span data-stu-id="8eca3-164">Choosing Optional leaves the requirement up to the partner XMPP service for a mandatory-to-negotiate decision.</span></span>
        
        <div>
        

        > [!WARNING]  
        > <span data-ttu-id="8eca3-p117">SASL は TLS を必要とします。SASL を使用するには、TLS を必須とするかオプションにする必要があります。SASL を必須またはオプションと定義するすべての構成は、TLS サポートを持っている必要があります。変更を保存する目的で [<STRONG>コミット</STRONG>] をクリックしたとき、TLS を必須またはオプションに設定していなかった場合は、SASL には TLS サポートが必要という警告が表示され、変更は保存されません。エラーを解決するには、TLS を [<STRONG>必須</STRONG>] または [<STRONG>オプション</STRONG>] に設定します。SASL の使用がオプションで、TLS ネゴシエーションのサポートができない場合は、SASL ネゴシエーションを [<STRONG>サポートなし</STRONG>] に設定する必要があります。サービスが中断しないように、TLS と SASL で適切なネゴシエーション ストリームがなにか、XMPP サービスに確認してください。</span><span class="sxs-lookup"><span data-stu-id="8eca3-p117">SASL requires TLS. To use SASL, TLS must either be required or optional. Any configuration that defines SASL as either required or optional must have TLS support. When clicking <STRONG>Commit</STRONG> to save your changes, if you have not set TLS to required or optional, you will be warned that SASL must have TLS support and your changes are not saved. To resolve the error, set TLS to <STRONG>Required</STRONG> or <STRONG>Optional</STRONG>. If use of SASL is optional and TLS negotiation support is not possible, you must set SASL negotiation to <STRONG>Not Supported</STRONG>. Confirm with the XMPP service what the proper negotiation streams must be for TLS and SASL or service interruption will occur.</span></span>

        
        </div>
        
          - <span></span>  
            <span data-ttu-id="8eca3-172">**必須**。</span><span class="sxs-lookup"><span data-stu-id="8eca3-172">**Required**.</span></span> <span data-ttu-id="8eca3-173">XMPP サービスは SASL ネゴシエーションを必要とします。</span><span class="sxs-lookup"><span data-stu-id="8eca3-173">The XMPP service requires SASL negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="8eca3-174">**省略可能**です。</span><span class="sxs-lookup"><span data-stu-id="8eca3-174">**Optional**.</span></span> <span data-ttu-id="8eca3-175">XMPP サービスは、SASL がネゴシエーション必須であることを示します。</span><span class="sxs-lookup"><span data-stu-id="8eca3-175">The XMPP service indicates that SASL is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="8eca3-176">**サポートされません**。</span><span class="sxs-lookup"><span data-stu-id="8eca3-176">**Not Supported**.</span></span> <span data-ttu-id="8eca3-177">XMPP サービスは SASL をサポートしません。</span><span class="sxs-lookup"><span data-stu-id="8eca3-177">The XMPP service does not support SASL.</span></span>
    
      - <span data-ttu-id="8eca3-178">**ダイヤルバックネゴシエーション**。</span><span class="sxs-lookup"><span data-stu-id="8eca3-178">**Dialback negotiation**.</span></span> <span data-ttu-id="8eca3-179">ダイヤルバックネゴシエーションは、ドキュメント **Xep-220: サーバーダイヤル**インの XSF によって定義され <http://xmpp.org/extensions/xep-0220.html> ます。</span><span class="sxs-lookup"><span data-stu-id="8eca3-179">Dialback negotiation is defined by the XSF in document **XEP-220 : Server Dialback** <http://xmpp.org/extensions/xep-0220.html>.</span></span> <span data-ttu-id="8eca3-180">サーバーダイヤルアウトプロセスは、ドメインネームシステム (DNS) と権限のあるサーバーを使用して、要求が有効な XMPP パートナーから来たものであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8eca3-180">The server dialback process uses the domain name system (DNS) and an authoritative server to verify that the request came from a valid XMPP partner.</span></span> <span data-ttu-id="8eca3-181">これを行うために、送信元サーバーは、生成されたダイヤルバックキーを使用して特定の種類のメッセージを作成し、DNS で受信側サーバーを検索します。</span><span class="sxs-lookup"><span data-stu-id="8eca3-181">To do this, the originating server creates a message of a specific type with a generated dialback key and looks up the receiving server in DNS.</span></span> <span data-ttu-id="8eca3-182">送信元サーバーは、生成された DNS 参照 (受信側サーバーなど) に、XML ストリームでキーを送信します。</span><span class="sxs-lookup"><span data-stu-id="8eca3-182">The originating server sends the key in an XML stream to the resulting DNS lookup, presumably the receiving server.</span></span> <span data-ttu-id="8eca3-183">XML ストリームの上でキーを受け取ると、受信側サーバーは送信元のサーバーに応答しませんが、既知の権限のあるサーバーにキーを送信します。</span><span class="sxs-lookup"><span data-stu-id="8eca3-183">On receipt of the key over the XML stream, the receiving server does not respond to the originating server, but sends the key to a known authoritative server.</span></span> <span data-ttu-id="8eca3-184">権限のあるサーバーは、キーが有効であるか無効であるかを確認します。</span><span class="sxs-lookup"><span data-stu-id="8eca3-184">The authoritative server verifies that the key is either valid or not valid.</span></span> <span data-ttu-id="8eca3-185">有効でない場合、受信側のサーバーは送信元のサーバーに応答しません。</span><span class="sxs-lookup"><span data-stu-id="8eca3-185">If not valid, the receiving server does not respond to the originating server.</span></span> <span data-ttu-id="8eca3-186">キーが有効である場合、受信側のサーバーは、送信元のサーバーに id とキーが有効であることを通知し、会話を開始できます。</span><span class="sxs-lookup"><span data-stu-id="8eca3-186">If the key is valid, the receiving server informs the originating server that the identity and key is valid and the conversation can commence.</span></span>
        
        <span data-ttu-id="8eca3-187">**ダイヤルバック ネゴシエーション**には、2 つの状態があります。</span><span class="sxs-lookup"><span data-stu-id="8eca3-187">There are two valid states for **Dialback negotiation**:</span></span>
        
          - <span></span>  
            <span data-ttu-id="8eca3-188">**True**。</span><span class="sxs-lookup"><span data-stu-id="8eca3-188">**True**.</span></span> <span data-ttu-id="8eca3-189">発信元サーバーから要求を受信した場合、XMPP サーバーはダイヤルバックネゴシエーションを使用するように構成されます。</span><span class="sxs-lookup"><span data-stu-id="8eca3-189">The XMPP server is configured to use Dialback negotiation if a request should be received from an originating server</span></span>
        
          - <span></span>  
            <span data-ttu-id="8eca3-190">**False を返し**ます。</span><span class="sxs-lookup"><span data-stu-id="8eca3-190">**False**.</span></span> <span data-ttu-id="8eca3-191">XMPP サーバーはダイヤルバックネゴシエーションを使用するように構成されておらず、発信元サーバーから要求を受信した場合は無視されます。</span><span class="sxs-lookup"><span data-stu-id="8eca3-191">The XMPP server is not configured to use Dialback negotiation and if a request should be received from an originating server, it will be ignored</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

