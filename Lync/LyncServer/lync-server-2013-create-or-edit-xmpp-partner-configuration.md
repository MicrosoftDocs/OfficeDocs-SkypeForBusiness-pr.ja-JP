---
title: 'Lync Server 2013: XMPP パートナー構成の作成または編集'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or edit XMPP partner configuration
ms:assetid: 362dbe5e-8ee9-4aba-8c26-5907312b4a60
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552447(v=OCS.15)
ms:contentKeyID: 48679558
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 488fa84a3f24133c6ebcde4467cacdbdcffe7ff8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833836"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-edit-xmpp-partner-configuration-in-lync-server-2013"></a><span data-ttu-id="69a91-102">Lync Server 2013 での XMPP パートナー構成の作成または編集</span><span class="sxs-lookup"><span data-stu-id="69a91-102">Create or edit XMPP partner configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69a91-103">_**最終更新日:** 2014-09-03_</span><span class="sxs-lookup"><span data-stu-id="69a91-103">_**Topic Last Modified:** 2014-09-03_</span></span>

<span data-ttu-id="69a91-104">Microsoft Lync Server 2013 は、エッジサーバー上の拡張メッセージングおよびプレゼンスプロトコル (XMPP) プロキシと、フロントエンドサーバーまたはフロントエンドプール上の XMPP ゲートウェイを統合します。</span><span class="sxs-lookup"><span data-stu-id="69a91-104">Microsoft Lync Server 2013 integrates an Extensible Messaging and Presence Protocol (XMPP) proxy on the Edge Server and an XMPP Gateway on the Front End Server or Front End pool.</span></span> <span data-ttu-id="69a91-105">他の XMPP の展開からの接続を許可するには、Lync Server コントロールパネルで XMPP を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69a91-105">To allow connections from other XMPP deployments, you must configure XMPP in the Lync Server Control Panel.</span></span> <span data-ttu-id="69a91-106">設定は XMPP ドメイン単位で構成します。</span><span class="sxs-lookup"><span data-stu-id="69a91-106">You configure settings on an XMPP domain basis.</span></span> <span data-ttu-id="69a91-107">新しいパートナーの関連付けを作成するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="69a91-107">To create a new partner association, you do the following:</span></span>

<div>

## <a name="to-create-a-new-federated-partner-or-edit-an-existing-configuration"></a><span data-ttu-id="69a91-108">新しいフェデレーションパートナーを作成する、または既存の構成を編集するには</span><span class="sxs-lookup"><span data-stu-id="69a91-108">To create a new federated partner or edit an existing configuration</span></span>

1.  <span data-ttu-id="69a91-109">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="69a91-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="69a91-110">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="69a91-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="69a91-111">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="69a91-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="69a91-112">左側のナビゲーションバーで、[**フェデレーションと外部アクセス**] をクリックし、[ **Xmpp フェデレーションパートナー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69a91-112">In the left navigation bar, click **Federation and External Access**, and then click **XMPP Federated Partners**.</span></span>

4.  <span data-ttu-id="69a91-113">新しい構成を作成するには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69a91-113">To create a new configuration, click **New**</span></span>

5.  <span data-ttu-id="69a91-114">既存の構成を編集するには、構成を選択して [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69a91-114">To edit an existing configuration, select the configuration and click **Edit**</span></span>

6.  <span data-ttu-id="69a91-115">**Xmpp フェデレーションパートナー**の構成を作成または編集するには、次の設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="69a91-115">To create or edit configurations for **XMPP Federated Partners**, you define the following settings:</span></span>

7.  <span data-ttu-id="69a91-116">**プライマリドメイン**(必須)。</span><span class="sxs-lookup"><span data-stu-id="69a91-116">**Primary domain** (Required).</span></span> <span data-ttu-id="69a91-117">プライマリドメインは、XMPP パートナーのベースドメインです。</span><span class="sxs-lookup"><span data-stu-id="69a91-117">The primary domain is the base domain of the XMPP partner.</span></span> <span data-ttu-id="69a91-118">たとえば、XMPP パートナードメイン名の**fabrikam.com**を入力します。</span><span class="sxs-lookup"><span data-stu-id="69a91-118">For example, you would enter **fabrikam.com** for the XMPP partner domain name.</span></span> <span data-ttu-id="69a91-119">このエントリは必須です。</span><span class="sxs-lookup"><span data-stu-id="69a91-119">This is a required entry.</span></span>

8.  <span data-ttu-id="69a91-120">**説明**。</span><span class="sxs-lookup"><span data-stu-id="69a91-120">**Description**.</span></span> <span data-ttu-id="69a91-121">説明は、この特定の構成のメモまたはその他の識別情報に使用されます。</span><span class="sxs-lookup"><span data-stu-id="69a91-121">The description is for notes or other identifying information for this particular configuration.</span></span> <span data-ttu-id="69a91-122">このエントリは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="69a91-122">This entry is optional.</span></span>

9.  <span data-ttu-id="69a91-123">**追加ドメイン**。</span><span class="sxs-lookup"><span data-stu-id="69a91-123">**Additional domains**.</span></span> <span data-ttu-id="69a91-124">さらに多くのドメインは、XMPP パートナーのドメインの一部であり、許可されている XMPP 通信の一部として含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="69a91-124">Additional domains are domains that are a part of your XMPP partner’s domain that should be included as part of the allowed XMPP communication.</span></span> <span data-ttu-id="69a91-125">たとえば、プライマリドメインが**fabrikam.com**の場合は、fabrikam.com の下にある他のすべてのドメインを一覧表示します。これにより、xmpp で通信することができます。</span><span class="sxs-lookup"><span data-stu-id="69a91-125">For example, if the primary domain is **fabrikam.com**, then you would list all other domains that are under fabrikam.com that you will communicate with by way of XMPP.</span></span> <span data-ttu-id="69a91-126">たとえば、企業の XMPP ドメインと、corp.fabrikam.com のメイン XMPP ドメインの下にある Information Technologies XMPP ドメインの場合は、「 \*\*\*\* 」と「 **it.fabrikam.com** 」と入力できます。</span><span class="sxs-lookup"><span data-stu-id="69a91-126">For example, you might enter **corp.fabrikam.com** and **it.fabrikam.com** for the Corporate XMPP domain and the Information Technologies XMPP domain under fabrikam.com’s main XMPP domain.</span></span>

10. <span data-ttu-id="69a91-127">**パートナーの種類**。</span><span class="sxs-lookup"><span data-stu-id="69a91-127">**Partner type**.</span></span> <span data-ttu-id="69a91-128">**パートナーの種類**は必須の設定であり、ドロップダウンメニューで3つの選択肢を選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="69a91-128">The **Partner type** is a required setting and gives you a selection of three choices in a drop-down menu.</span></span> <span data-ttu-id="69a91-129">追加できる連絡先を説明して適用するには、次のいずれかを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69a91-129">You must choose one of the following to describe and enforce what contacts can be added.</span></span> <span data-ttu-id="69a91-130">次のいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="69a91-130">You can select from:</span></span>
    
      - <span data-ttu-id="69a91-131">**フェデレーション**。</span><span class="sxs-lookup"><span data-stu-id="69a91-131">**Federated**.</span></span> <span data-ttu-id="69a91-132">**フェデレーション**パートナーの種類は、Lync Server または Office Communications Server 2007 R2 パートナー展開との間の信頼できる接続です。</span><span class="sxs-lookup"><span data-stu-id="69a91-132">A **Federated** partner type is a trusted connection between a Lync Server or Office Communications Server 2007 R2 partner deployment.</span></span>
    
      - <span data-ttu-id="69a91-133">**公開確認済み**。</span><span class="sxs-lookup"><span data-stu-id="69a91-133">**Public verified**.</span></span> <span data-ttu-id="69a91-134">**公開確認**パートナーとは、プロバイダーによって確認された展開の一部である連絡先をユーザーの連絡先リストに追加できることです。</span><span class="sxs-lookup"><span data-stu-id="69a91-134">A **Public verified** partner is when contacts that are part of a deployment that are verified by the provider can be added to your user’s list of contacts.</span></span> <span data-ttu-id="69a91-135">招待は Lync ユーザーから送信できます。また、Lync ユーザーはパートナーの連絡先から招待を受け入れることができます。</span><span class="sxs-lookup"><span data-stu-id="69a91-135">Invites can be sent from the Lync user or the Lync user can accept invites from the partner contact.</span></span>
    
      - <span data-ttu-id="69a91-136">**公開未検証**。</span><span class="sxs-lookup"><span data-stu-id="69a91-136">**Public unverified**.</span></span> <span data-ttu-id="69a91-137">**公開**されていないリレーションシップは、2つの展開間で確立され、検証可能な状態ではないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="69a91-137">A **Public unverified** relationship implies that there is no established and verifiable status between the two deployments.</span></span> <span data-ttu-id="69a91-138">Lync ユーザーは、連絡先リストに Lync ユーザーを追加できるように、その連絡先の未確認の連絡先を招待する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69a91-138">A Lync user must invite the unverified contact for that contact to be able to add the Lync user to his contact list.</span></span> <span data-ttu-id="69a91-139">たとえば、Google GTalk は、Lync Server に関連しているのと同じように、公開確認済みの XMPP サービスではありません。</span><span class="sxs-lookup"><span data-stu-id="69a91-139">For example, Google GTalk is not a public verified XMPP service as it relates to Lync Server.</span></span> <span data-ttu-id="69a91-140">ユーザーは、Lync ユーザーからの明示的な招待が送信されていない場合、Lync ユーザーを連絡先として追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="69a91-140">A GTalk user will not be able to add the Lync user as a contact unless there is an explicit invite sent from the Lync user.</span></span>

11. <span data-ttu-id="69a91-141">ストリームのネゴシエーションとセキュリティメソッドトランスポート層セキュリティ (TLS) とソフトウェア認証とセキュリティレイヤー (SASL) についての注意事項:</span><span class="sxs-lookup"><span data-stu-id="69a91-141">Notes on stream negotiation and the security methods Transport Layer Security (TLS) and Software Authentication and Security Layer (SASL):</span></span>
    
    <span data-ttu-id="69a91-142">**Xmpp 規格ファンデーション**(XSF) と**Internet Engineering Task Force** (IETF) は、tls クライアント証明書、tls サーバー証明書、および SASL メカニズムを使用および管理するためのルールと標準のセットを定義しています。</span><span class="sxs-lookup"><span data-stu-id="69a91-142">The **XMPP Standards Foundation** (XSF) and the **Internet Engineering Task Force** (IETF) define a set of rules and standards for using and managing TLS client certificates, TLS server certificates, and the SASL mechanism.</span></span> <span data-ttu-id="69a91-143">TLS と SASL の使用は、XMPP ストリームをセキュリティで保護するために必要なプロセスです。</span><span class="sxs-lookup"><span data-stu-id="69a91-143">Using TLS and SASL is the required process for securing the XMPP stream.</span></span> <span data-ttu-id="69a91-144">XMPP 標準ドキュメント**Xmpp-0178**では、PKIX 証明書を使った SASL 外部機構の使用に推奨されるプロトコルフローを指定します。特に、xmpp サービスで TLS が必須であることを示すのは、TLS が必須であることを示しています。</span><span class="sxs-lookup"><span data-stu-id="69a91-144">From the XMPP Standards document **XEP-0178**, “specifies a recommended protocol flow for use of the SASL EXTERNAL mechanism with PKIX certificates, especially when an XMPP service indicates that TLS is mandatory-to-negotiate.”</span></span> <span data-ttu-id="69a91-145">PKIX は、XSF ドキュメントで説明されているように、公開キー基盤 (PKI とも呼ばれます) を指します。</span><span class="sxs-lookup"><span data-stu-id="69a91-145">PKIX, as stated in the XSF documentation, refers to public key infrastructure, also known as PKI.</span></span>
    
    <span data-ttu-id="69a91-146">XEP の要件の詳細については、「XSF ドキュメント XEP-0178」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69a91-146">Refer to the XSF document XEP-0178 for more details on the XMPP requirements.</span></span> <span data-ttu-id="69a91-147">詳細については、「XEP-0178: 証明書付きの SASL 外部を使用するためのベストプラクティス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69a91-147">For details, refer to “XEP-0178: Best Practices for Use of SASL EXTERNAL with Certificates”.</span></span> <http://xmpp.org/extensions/xep-0178.html>
    
    <span data-ttu-id="69a91-148">IETF ドキュメント「拡張可能なメッセージングとプレゼンスプロトコル (XMPP): Core "、Section 5.0、STARTTLS のネゴシエーション<http://tools.ietf.org/html/rfc6120>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69a91-148">Refer to the IETF document “Extensible Messaging and Presence Protocol (XMPP): Core“, Section 5.0, STARTTLS Negotiation <http://tools.ietf.org/html/rfc6120>.</span></span>
    
      - <span data-ttu-id="69a91-149">**TLS ネゴシエーション**。</span><span class="sxs-lookup"><span data-stu-id="69a91-149">**TLS Negotiation**.</span></span> <span data-ttu-id="69a91-150">TLS ネゴシエーションルールを定義します。</span><span class="sxs-lookup"><span data-stu-id="69a91-150">Defines the TLS negotiation rules.</span></span> <span data-ttu-id="69a91-151">XMPP サービスでは TLS が必要になる場合があります。 TLS をオプションにすることも、TLS がサポートされないことを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="69a91-151">An XMPP service can require TLS, can make TLS optional, or you define that TLS is not supported.</span></span> <span data-ttu-id="69a91-152">[オプションを選択すると、必須のネゴシエーションの意思決定を行うための XMPP サービスの要件が残ります。</span><span class="sxs-lookup"><span data-stu-id="69a91-152">Choosing Optional leaves the requirement up to the XMPP service for a mandatory-to-negotiate decision.</span></span> <span data-ttu-id="69a91-153">使用可能な SASL、TLS、およびダイヤルバックのネゴシエーションに関するすべての設定と詳細を表示するには、「有効なエラーと既知のエラー構成」を参照してください。詳しくは、「 [Lync Server 2013 での XMPP フェデレーションパートナーのネゴシエーション設定](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="69a91-153">To view all possible settings and details for SASL, TLS and Dialback negotiation –including not valid and known error configurations - see [Negotiation settings for XMPP federated partners in Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).</span></span>
        
          - <span></span>  
            <span data-ttu-id="69a91-154">**必須**。</span><span class="sxs-lookup"><span data-stu-id="69a91-154">**Required**.</span></span> <span data-ttu-id="69a91-155">XMPP サービスには TLS ネゴシエーションが必要です。</span><span class="sxs-lookup"><span data-stu-id="69a91-155">The XMPP service requires TLS negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="69a91-156">**省略可能**。</span><span class="sxs-lookup"><span data-stu-id="69a91-156">**Optional**.</span></span> <span data-ttu-id="69a91-157">XMPP サービスは、TLS が必須からネゴシエートされていることを示します。</span><span class="sxs-lookup"><span data-stu-id="69a91-157">The XMPP service indicates that TLS is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="69a91-158">**サポートされません**。</span><span class="sxs-lookup"><span data-stu-id="69a91-158">**Not Supported**.</span></span> <span data-ttu-id="69a91-159">XMPP サービスでは、TLS はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="69a91-159">The XMPP service does not support TLS.</span></span>
    
      - <span data-ttu-id="69a91-160">**SASL ネゴシエーション**。</span><span class="sxs-lookup"><span data-stu-id="69a91-160">**SASL negotiation**.</span></span> <span data-ttu-id="69a91-161">SASL ネゴシエーション規則を定義します。</span><span class="sxs-lookup"><span data-stu-id="69a91-161">Defines the SASL negotiation rules.</span></span> <span data-ttu-id="69a91-162">XMPP サービスでは、SASL を要求できるほか、SASL をオプションとして使うこともできます。また、SASL がサポートされていないことを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="69a91-162">An XMPP service can require SASL, can make SASL optional, or you define that SASL is not supported.</span></span> <span data-ttu-id="69a91-163">[オプションを選択すると、必須のネゴシエーションの意思決定を行うために、パートナーの XMPP サービスまでの要件が残ります。</span><span class="sxs-lookup"><span data-stu-id="69a91-163">Choosing Optional leaves the requirement up to the partner XMPP service for a mandatory-to-negotiate decision.</span></span>
        
        <div>
        

        > [!WARNING]  
        > <span data-ttu-id="69a91-164">SASL には TLS が必要です。</span><span class="sxs-lookup"><span data-stu-id="69a91-164">SASL requires TLS.</span></span> <span data-ttu-id="69a91-165">SASL を使うには、TLS が必要かオプションである必要があります。</span><span class="sxs-lookup"><span data-stu-id="69a91-165">To use SASL, TLS must either be required or optional.</span></span> <span data-ttu-id="69a91-166">SASL を required または optional として定義する構成では、TLS サポートを利用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69a91-166">Any configuration that defines SASL as either required or optional must have TLS support.</span></span> <span data-ttu-id="69a91-167">[<STRONG>コミット</STRONG>] をクリックして変更を保存するときに、tls を required に設定していない場合は、SASL に tls サポートが必要であり、変更が保存されていないことを示す警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="69a91-167">When clicking <STRONG>Commit</STRONG> to save your changes, if you have not set TLS to required or optional, you will be warned that SASL must have TLS support and your changes are not saved.</span></span> <span data-ttu-id="69a91-168">エラーを解決するには、TLS を<STRONG>Required</STRONG>または<STRONG>Optional</STRONG>に設定します。</span><span class="sxs-lookup"><span data-stu-id="69a91-168">To resolve the error, set TLS to <STRONG>Required</STRONG> or <STRONG>Optional</STRONG>.</span></span> <span data-ttu-id="69a91-169">SASL がオプションであり、TLS ネゴシエーションがサポートされていない場合は、SASL ネゴシエーションを<STRONG>サポートしない</STRONG>ように設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69a91-169">If use of SASL is optional and TLS negotiation support is not possible, you must set SASL negotiation to <STRONG>Not Supported</STRONG>.</span></span> <span data-ttu-id="69a91-170">XMPP サービスで、TLS および SASL に対応する適切なネゴシエーションストリームが必要であることを確認します。また、サービスの中断が発生します。</span><span class="sxs-lookup"><span data-stu-id="69a91-170">Confirm with the XMPP service what the proper negotiation streams must be for TLS and SASL or service interruption will occur.</span></span>

        
        </div>
        
          - <span></span>  
            <span data-ttu-id="69a91-171">**必須**。</span><span class="sxs-lookup"><span data-stu-id="69a91-171">**Required**.</span></span> <span data-ttu-id="69a91-172">XMPP サービスでは、SASL ネゴシエーションが必要です。</span><span class="sxs-lookup"><span data-stu-id="69a91-172">The XMPP service requires SASL negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="69a91-173">**省略可能**。</span><span class="sxs-lookup"><span data-stu-id="69a91-173">**Optional**.</span></span> <span data-ttu-id="69a91-174">XMPP サービスは、SASL のネゴシエーションが必須であることを示します。</span><span class="sxs-lookup"><span data-stu-id="69a91-174">The XMPP service indicates that SASL is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="69a91-175">**サポートされません**。</span><span class="sxs-lookup"><span data-stu-id="69a91-175">**Not Supported**.</span></span> <span data-ttu-id="69a91-176">XMPP サービスでは、SASL はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="69a91-176">The XMPP service does not support SASL.</span></span>
    
      - <span data-ttu-id="69a91-177">**ダイヤルバックのネゴシエーション**。</span><span class="sxs-lookup"><span data-stu-id="69a91-177">**Dialback negotiation**.</span></span> <span data-ttu-id="69a91-178">ダイヤルバックのネゴシエーションは、ドキュメント**Xep-220: サーバーのダイヤルバック** <http://xmpp.org/extensions/xep-0220.html>の XSF で定義されています。</span><span class="sxs-lookup"><span data-stu-id="69a91-178">Dialback negotiation is defined by the XSF in document **XEP-220 : Server Dialback** <http://xmpp.org/extensions/xep-0220.html>.</span></span> <span data-ttu-id="69a91-179">サーバーコールバックプロセスでは、ドメインネームシステム (DNS) と権限を持つサーバーを使用して、要求が有効な XMPP パートナーから送信されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="69a91-179">The server dialback process uses the domain name system (DNS) and an authoritative server to verify that the request came from a valid XMPP partner.</span></span> <span data-ttu-id="69a91-180">これを行うために、発信元のサーバーは、生成されたダイヤルバックキーを使用して、特定の種類のメッセージを作成し、DNS で受信側サーバーを検索します。</span><span class="sxs-lookup"><span data-stu-id="69a91-180">To do this, the originating server creates a message of a specific type with a generated dialback key and looks up the receiving server in DNS.</span></span> <span data-ttu-id="69a91-181">送信元のサーバーは、受信側サーバーであると思われるように、XML ストリームのキーを結果の DNS 参照に送信します。</span><span class="sxs-lookup"><span data-stu-id="69a91-181">The originating server sends the key in an XML stream to the resulting DNS lookup, presumably the receiving server.</span></span> <span data-ttu-id="69a91-182">XML ストリームを介してキーを受け取ると、受信側サーバーは元のサーバーには応答しませんが、既知の権限を持つサーバーにキーを送信します。</span><span class="sxs-lookup"><span data-stu-id="69a91-182">On receipt of the key over the XML stream, the receiving server does not respond to the originating server, but sends the key to a known authoritative server.</span></span> <span data-ttu-id="69a91-183">権限を持つサーバーは、キーが有効であるか無効であるかを確認します。</span><span class="sxs-lookup"><span data-stu-id="69a91-183">The authoritative server verifies that the key is either valid or not valid.</span></span> <span data-ttu-id="69a91-184">有効でない場合、受信側サーバーは元のサーバーには応答しません。</span><span class="sxs-lookup"><span data-stu-id="69a91-184">If not valid, the receiving server does not respond to the originating server.</span></span> <span data-ttu-id="69a91-185">キーが有効である場合、受信側のサーバーは、id とキーが有効であり、会話を開始できます。</span><span class="sxs-lookup"><span data-stu-id="69a91-185">If the key is valid, the receiving server informs the originating server that the identity and key is valid and the conversation can commence.</span></span>
        
        <span data-ttu-id="69a91-186">**ダイヤルバックのネゴシエーション**には、次の2つの有効な状態があります。</span><span class="sxs-lookup"><span data-stu-id="69a91-186">There are two valid states for **Dialback negotiation**:</span></span>
        
          - <span></span>  
            <span data-ttu-id="69a91-187">**True**。</span><span class="sxs-lookup"><span data-stu-id="69a91-187">**True**.</span></span> <span data-ttu-id="69a91-188">発信元のサーバーから要求を受信する必要がある場合に、ダイヤルバックのネゴシエーションを使用するように XMPP サーバーが構成されている</span><span class="sxs-lookup"><span data-stu-id="69a91-188">The XMPP server is configured to use Dialback negotiation if a request should be received from an originating server</span></span>
        
          - <span></span>  
            <span data-ttu-id="69a91-189">**False**。</span><span class="sxs-lookup"><span data-stu-id="69a91-189">**False**.</span></span> <span data-ttu-id="69a91-190">XMPP サーバーは、ダイヤルバックのネゴシエーションを使用するように構成されておらず、発信元のサーバーから要求を受信した場合、無視されます。</span><span class="sxs-lookup"><span data-stu-id="69a91-190">The XMPP server is not configured to use Dialback negotiation and if a request should be received from an originating server, it will be ignored</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

