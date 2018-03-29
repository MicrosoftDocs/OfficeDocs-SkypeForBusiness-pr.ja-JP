---
title: Skype for Business での Exchange ユニファイド メッセージング統合の計画
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7b22002b-7e6a-4d3f-b600-a733a7e3778a
description: '概要: は、Exchange 2013 でのビジネス サーバー 2015 の Skype を統合するために計画するときにこのトピックを参照します。'
ms.openlocfilehash: 1a1ea968f9feb14c0a7b0d69c13ad273a18a53f5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-exchange-unified-messaging-integration-in-skype-for-business"></a><span data-ttu-id="d11ff-103">Skype for Business での Exchange ユニファイド メッセージング統合の計画</span><span class="sxs-lookup"><span data-stu-id="d11ff-103">Plan for Exchange Unified Messaging integration in Skype for Business</span></span>
 
<span data-ttu-id="d11ff-104">**の概要:**Exchange 2013 でのビジネス サーバー 2015 の Skype を統合するために計画するときに、このトピックを確認します。</span><span class="sxs-lookup"><span data-stu-id="d11ff-104">**Summary:** Review this topic while planning to integrate Skype for Business Server 2015 with Exchange 2013.</span></span>
  
<span data-ttu-id="d11ff-105">ビジネス サーバー 2015 の Skype では、ボイス メッセージングと電子メールのメッセージを単一のメッセージング インフラストラクチャを組み合わせる場合の Exchange ユニファイド メッセージング (UM) との統合をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d11ff-105">Skype for Business Server 2015 supports integration with Exchange Unified Messaging (UM) for combining voice messaging and email messaging into a single messaging infrastructure.</span></span> <span data-ttu-id="d11ff-106">Exchange では、Exchange ユニファイド メッセージング (UM) をインストールして構成することができますいくつかの Exchange サーバーの役割の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="d11ff-106">In Exchange, Exchange Unified Messaging (UM) is one of several Exchange server roles that you can install and configure.</span></span> 
  
<span data-ttu-id="d11ff-107">Microsoft Exchange Server 2013 で Exchange UM サービスとして実行 Exchange メールボックス サーバーにします。</span><span class="sxs-lookup"><span data-stu-id="d11ff-107">In Microsoft Exchange Server 2013, Exchange UM runs as a service on an Exchange Mailbox server.</span></span> <span data-ttu-id="d11ff-108">ビジネス サーバー 2015 のエンタープライズ VoIP 展開の Skype では、ユニファイド メッセージング、ボイス メッセージングと電子メール メッセージングをユーザーが電話 (Outlook Voice Access) またはコンピューターからアクセスできる 1 つのストアが組み合わせたものです。</span><span class="sxs-lookup"><span data-stu-id="d11ff-108">For Skype for Business Server 2015 Enterprise Voice deployments, Unified Messaging combines voice messaging and email messaging into a single store that users can access from a telephone (Outlook Voice Access) or a computer.</span></span> <span data-ttu-id="d11ff-109">ユニファイド メッセージングおよびビジネス サーバー 2015 の Skype は連携して、エンタープライズ VoIP のユーザーが通話応答、Outlook Voice Access、および自動応答サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="d11ff-109">Unified Messaging and Skype for Business Server 2015 work together to provide call answering, Outlook Voice Access, and auto-attendant services to users of Enterprise Voice.</span></span>
  
<span data-ttu-id="d11ff-110">Microsoft Exchange Server 2013 のアーキテクチャの変更の詳細については、Microsoft Exchange Server 2013 のドキュメントでの[ボイスのアーキテクチャの変更](https://go.microsoft.com/fwlink/p/?LinkId=266730)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d11ff-110">For more information about the architecture changes in Microsoft Exchange Server 2013, see [Voice Architecture Changes](https://go.microsoft.com/fwlink/p/?LinkId=266730) in the Microsoft Exchange Server 2013 documentation.</span></span>
  
<span data-ttu-id="d11ff-111">設置型 Exchange UM の展開でサポートされているこれらの機能では、する必要があります実行されている次のいずれか。</span><span class="sxs-lookup"><span data-stu-id="d11ff-111">For these features to be supported in an on-premises Exchange UM deployment, you must be running one of the following:</span></span>
  
- <span data-ttu-id="d11ff-112">Microsoft Exchange Server 2010 または最新の service pack</span><span class="sxs-lookup"><span data-stu-id="d11ff-112">Microsoft Exchange Server 2010 or latest service pack</span></span>
    
- <span data-ttu-id="d11ff-113">Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="d11ff-113">Microsoft Exchange Server 2013</span></span>
    
-  <span data-ttu-id="d11ff-114">Microsoft Exchange Server 2016</span><span class="sxs-lookup"><span data-stu-id="d11ff-114">Microsoft Exchange Server 2016</span></span>
    
## <a name="features-of-integrated-unified-messaging-and-skype-for-business-server-2015"></a><span data-ttu-id="d11ff-115">統合ユニファイド メッセージングと Skype for Business Server 2015 の機能</span><span class="sxs-lookup"><span data-stu-id="d11ff-115">Features of integrated Unified Messaging and Skype for Business Server 2015</span></span>

<span data-ttu-id="d11ff-116">ビジネス サーバー 2015、エンタープライズ VoIP の Skype では、通話応答、通話の通知、音声アクセス (ボイス ・ メールを含む)、および自動応答サービスを提供するのに Exchange ユニファイド メッセージング (UM) インフラストラクチャを使用します。</span><span class="sxs-lookup"><span data-stu-id="d11ff-116">Skype for Business Server 2015, Enterprise Voice uses the Exchange Unified Messaging (UM) infrastructure to provide call answering, call notification, voice access (including voice mail), and auto-attendant services.</span></span>
  
- <span data-ttu-id="d11ff-p103">**通話応答** 通話応答は、ユーザーが電話に出られないときや通話が取り込み中のときに、ユーザーに代わって音声メッセージを受け取る機能です。個人用の応答メッセージの再生と、メッセージの録音ができます。メッセージはキューに登録され、ユーザーのメールボックスに配信されます。ユーザーのメールボックスは、Exchange メールボックス サーバーに格納されています。</span><span class="sxs-lookup"><span data-stu-id="d11ff-p103">**Call Answering** Call answering is the receiving of voice messages on behalf of users whose calls are not answered or are busy. It includes playing a personal greeting, recording a message, and submitting the message to be queued for delivery to the user's mailbox, which is stored on the Exchange mailbox server.</span></span>
    
    <span data-ttu-id="d11ff-p104">発信者がメッセージを残すと、ユーザーの受信トレイにメッセージがルーティングされます。発信者がメッセージを残さなかった場合は、不在着信通知がユーザーのメールボックスに格納されます。 ユーザーが自分の受信トレイにアクセスするには、Microsoft Outlook のメッセージングおよびコラボレーション クライアント、Outlook Web Access、Exchange ActiveSync テクノロジ、または Outlook Voice Access を使用します。 電子メールと同様の方法で、着信の件名と優先度を表示できます。</span><span class="sxs-lookup"><span data-stu-id="d11ff-p104">If a caller leaves a message, the message is routed to the user's Inbox. If a caller chooses not to leave a message, a missed call notification is stored in the user's mailbox. Users can then access their Inbox by using the Microsoft Outlook messaging and collaboration client, Outlook Web Access, the Exchange ActiveSync technology, or Outlook Voice Access. The subject and priority of calls can be displayed in a way similar to that of email.</span></span>
    
- <span data-ttu-id="d11ff-123">**Outlook Voice Access**Outlook Voice Access には、ボイス ・ メールだけでなく、できるだけでなく、電子メール、予定表、およびテレフォニー インターフェイスから連絡先を含む、Exchange 受信トレイにアクセスするのには、エンタープライズ VoIP ユーザーが有効にします。</span><span class="sxs-lookup"><span data-stu-id="d11ff-123">**Outlook Voice Access** Outlook Voice Access enables an Enterprise Voice user to access not just voice mail, but also the Exchange inbox, including email, calendar, and contacts from a telephony interface.</span></span> <span data-ttu-id="d11ff-124">サブスクライバー アクセス番号は、Exchange UM 管理者によって割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="d11ff-124">The subscriber access number is assigned by an Exchange UM administrator.</span></span>
    
- <span data-ttu-id="d11ff-125">**自動アテンダント**自動アテンダントは、外部ユーザーの会社の代表者に到達するためにダイアルする電話番号を構成に使用できる Exchange UM 機能です。</span><span class="sxs-lookup"><span data-stu-id="d11ff-125">**Auto attendant** Auto attendant is an Exchange UM feature that can be used to configure a phone number that outside users can dial to reach company representatives.</span></span> <span data-ttu-id="d11ff-126">具体的には、一連のメニュー システム内を移動する、外部の呼び出し元を支援する音声案内が用意されています。</span><span class="sxs-lookup"><span data-stu-id="d11ff-126">In particular, it provides a series of voice prompts that assist an external caller in navigating a menu system.</span></span> <span data-ttu-id="d11ff-127">Exchange UM 管理者が Exchange UM サーバーで使用可能なオプションの一覧を構成するとします。</span><span class="sxs-lookup"><span data-stu-id="d11ff-127">The list of available options is configured on the Exchange UM server by the Exchange UM administrator.</span></span>
    
- <span data-ttu-id="d11ff-128">**Fax サービス**Exchange UM fax 機能には、Exchange のメールボックスで fax を受信するユーザーを有効にするが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d11ff-128">**Fax Services** Exchange UM includes fax features, which enable users to receive incoming faxes in their Exchange mailboxes.</span></span> <span data-ttu-id="d11ff-129">詳細については、Microsoft Exchange Server のマニュアルで[ユニファイド メッセージング](https://go.microsoft.com/fwlink/p/?linkId=135652)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d11ff-129">For details, see [Unified Messaging](https://go.microsoft.com/fwlink/p/?linkId=135652) in the Microsoft Exchange Server documentation.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d11ff-130">Exchange UM サーバーが提供する fax サービスは、ビジネスのサーバー展開では Microsoft Exchange Server 2010、最新サービス パックを使用する Exchange 2010 または Exchange 2013 に統合されている Skype でご利用いただけません。</span><span class="sxs-lookup"><span data-stu-id="d11ff-130">Fax services provided by the Exchange UM server are not available in Skype for Business Server deployments that are integrated with Microsoft Exchange Server 2010, Exchange 2010 with the latest service pack, or Exchange 2013.</span></span> 
  
## <a name="components-and-topologies-for-on-premises-unified-messaging-in-skype-for-business-server-2015"></a><span data-ttu-id="d11ff-131">Skype for Business Server 2015 のオンプレミスのユニファイド メッセージングのコンポーネントとトポロジ</span><span class="sxs-lookup"><span data-stu-id="d11ff-131">Components and topologies for on-premises Unified Messaging in Skype for Business Server 2015</span></span>

### <a name="exchange-server-components"></a><span data-ttu-id="d11ff-132">Exchange Server コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d11ff-132">Exchange Server Components</span></span>

<span data-ttu-id="d11ff-133">Exchange UM の機能と[機能の統合されたユニファイド メッセージングおよび Lync Server 2013](http://technet.microsoft.com/library/094f549d-fccc-43ab-9f39-6ddd18130915.aspx)の「組織のエンタープライズ VoIP ユーザーにサービスを提供する、Microsoft Exchange メールボックス サーバーとクライアント アクセス サーバーを配置する必要があります。ユーザーのメールボックスをホストし、メールやボイス ・ メールの 1 つのストレージの場所を提供します。</span><span class="sxs-lookup"><span data-stu-id="d11ff-133">To provide the Exchange UM features and services described in [Features of Integrated Unified Messaging and Lync Server 2013](http://technet.microsoft.com/library/094f549d-fccc-43ab-9f39-6ddd18130915.aspx) to Enterprise Voice users in your organization, you must deploy an Microsoft Exchange Mailbox server and Client Access server, which hosts user mailboxes and provides a single storage location for email and voice mail.</span></span> <span data-ttu-id="d11ff-134">Exchange UM Exchange のメールボックスおよびクライアント アクセス サーバーでサービスとして実行されます。</span><span class="sxs-lookup"><span data-stu-id="d11ff-134">Exchange UM runs as a service on Exchange Mailbox and Client Access servers.</span></span>
  
<span data-ttu-id="d11ff-135">Microsoft Exchange Server 2010 での Exchange UM コンポーネントに関する詳細については、展開に関するドキュメントに[配置する設置型 Exchange UM Lync Server 2013 プレビュー音声メールの提供を](http://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx)参照してください。</span><span class="sxs-lookup"><span data-stu-id="d11ff-135">For details about Exchange UM components in Microsoft Exchange Server 2010, see [Deploying On-Premises Exchange UM to Provide Lync Server 2013 Preview Voice Mail](http://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx) in the Deployment documentation.</span></span>
  
### <a name="supported-topologies"></a><span data-ttu-id="d11ff-136">サポートされるトポロジ</span><span class="sxs-lookup"><span data-stu-id="d11ff-136">Supported Topologies</span></span>

<span data-ttu-id="d11ff-137">ビジネス サーバー 2015 および Exchange ユニファイド メッセージング (UM) 同じフォレスト内または複数のフォレストでの Skype を展開できます。</span><span class="sxs-lookup"><span data-stu-id="d11ff-137">You can deploy Skype for Business Server 2015 and Exchange Unified Messaging (UM) in the same forest or multiple forests.</span></span> <span data-ttu-id="d11ff-138">展開では、複数のフォレストをまたがっている場合は、各 Exchange UM フォレストの Exchange 統合の手順を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="d11ff-138">If the deployment spans multiple forests, you must perform the Exchange integration steps for each Exchange UM forest.</span></span> <span data-ttu-id="d11ff-139">さらに、各 Exchange UM フォレストを信頼するフォレストのビジネス サーバー 2015 Skype とビジネス サーバー 2015 フォレストの Skype を信頼する場合は、各 Microsoft Exchange フォレストを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d11ff-139">Furthermore, you must configure each Microsoft Exchange forest to trust the Skype for Business Server 2015 forest and the Skype for Business Server 2015 forest to trust each Exchange UM forest.</span></span> <span data-ttu-id="d11ff-140">このフォレストの信頼だけでなく、Skype のビジネス サーバー 2015 フォレストでユーザー オブジェクトのすべてのユーザーの Exchange UM の設定を設定しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="d11ff-140">In addition to this forest trust, the Exchange UM settings for all users must be set on the user objects in the Skype for Business Server 2015 forest.</span></span> 
  
<span data-ttu-id="d11ff-141">ビジネス サーバー 2015 の Skype には、Exchange UM の統合のための次のトポロジがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d11ff-141">Skype for Business Server 2015 supports the following topologies for Exchange UM integration:</span></span>
  
- <span data-ttu-id="d11ff-142">単一のフォレスト</span><span class="sxs-lookup"><span data-stu-id="d11ff-142">Single forest</span></span>
    
- <span data-ttu-id="d11ff-143">単一ドメイン (すなわち、単一ドメインを含む単一フォレスト)。</span><span class="sxs-lookup"><span data-stu-id="d11ff-143">Single domain (that is, a single forest with a single domain).</span></span> <span data-ttu-id="d11ff-144">ビジネス サーバー 2015、Microsoft Exchange、およびユーザーの Skype は、同じドメインに存在します。</span><span class="sxs-lookup"><span data-stu-id="d11ff-144">Skype for Business Server 2015, Microsoft Exchange, and users all reside in the same domain.</span></span>
    
- <span data-ttu-id="d11ff-145">複数ドメイン (つまり、1 つまたは複数の子ドメインとルート ドメイン)。</span><span class="sxs-lookup"><span data-stu-id="d11ff-145">Multiple domain (that is, a root domain with one or more child domains).</span></span> <span data-ttu-id="d11ff-146">Skype ビジネス サーバー 2015 年と Microsoft Exchange サーバーは、ユーザーを作成するドメインから別のドメインに配置されます。</span><span class="sxs-lookup"><span data-stu-id="d11ff-146">Skype for Business Server 2015, and Microsoft Exchange servers are deployed in different domains from the domain where you create users.</span></span> <span data-ttu-id="d11ff-147">Exchange UM サーバーは、Skype をサポートしているビジネス サーバー 2015 プールから別のドメインに展開できます。</span><span class="sxs-lookup"><span data-stu-id="d11ff-147">Exchange UM servers can be deployed in different domains from the Skype for Business Server 2015 pool they support.</span></span>
    
- <span data-ttu-id="d11ff-148">複数のフォレスト (すなわち、リソース フォレスト)。</span><span class="sxs-lookup"><span data-stu-id="d11ff-148">Multiple forest (that is, resource forest).</span></span> <span data-ttu-id="d11ff-149">ビジネス サーバー 2015 の Skype は、単一のフォレストに展開し、複数のフォレストにユーザーが分散し、します。</span><span class="sxs-lookup"><span data-stu-id="d11ff-149">Skype for Business Server 2015 is deployed in a single forest, and then users are distributed across multiple forests.</span></span> <span data-ttu-id="d11ff-150">ユーザーの Exchange UM の属性は、ビジネス サーバー 2015 フォレストの Skype を経由でレプリケートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d11ff-150">The users' Exchange UM attributes must be replicated over to the Skype for Business Server 2015 forest.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d11ff-151">Exchange は複数のフォレストに展開できます。</span><span class="sxs-lookup"><span data-stu-id="d11ff-151">Exchange can be deployed in multiple forests.</span></span> <span data-ttu-id="d11ff-152">各 Exchange 組織が提供できる Exchange UM に、ユーザー、または Exchange UM ビジネス サーバー 2015 の Skype と同じフォレストに展開することができます。</span><span class="sxs-lookup"><span data-stu-id="d11ff-152">Each Exchange organization can provide Exchange UM to its users, or Exchange UM can be deployed in the same forest as Skype for Business Server 2015.</span></span> 
  
## <a name="guidelines-for-integrating-on-premises-unified-messaging-and-skype-for-business-server-2015"></a><span data-ttu-id="d11ff-153">オンプレミスのユニファイド メッセージングと Skype for Business Server 2015 を統合するためのガイドライン</span><span class="sxs-lookup"><span data-stu-id="d11ff-153">Guidelines for integrating on-premises Unified Messaging and Skype for Business Server 2015</span></span>

<span data-ttu-id="d11ff-154">次に示すのは、エンタープライズ VoIP の展開時に考慮すべきガイドラインおよびベスト プラクティスです。</span><span class="sxs-lookup"><span data-stu-id="d11ff-154">The following are guidelines and best practices to consider when you deploy Enterprise Voice:</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d11ff-155">Exchange ユニファイド メッセージング (UM) UCMA 4 を使用する場合にのみ、IPv6 をサポートします。</span><span class="sxs-lookup"><span data-stu-id="d11ff-155">Exchange Unified Messaging (UM) supports IPv6 only if you are also using UCMA 4.</span></span> 
  
- <span data-ttu-id="d11ff-156">Skype のビジネス サーバー 2015 の Standard Edition サーバーまたはフロント エンド プールを展開します。</span><span class="sxs-lookup"><span data-stu-id="d11ff-156">Deploy a Skype for Business Server 2015 Standard Edition server or a Front End pool.</span></span> <span data-ttu-id="d11ff-157">インストールに関する詳細については、展開に関するドキュメントで[ビジネス サーバー 2015 の Skype の導入](../../deploy/deploy.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d11ff-157">For details about installation, see [Deploy Skype for Business Server 2015](../../deploy/deploy.md) in the Deployment documentation.</span></span>
    
- <span data-ttu-id="d11ff-158">スムーズに問題なく統合できるように、Exchange 管理者と協力して、各自が実施する作業を確認します。</span><span class="sxs-lookup"><span data-stu-id="d11ff-158">Work with Exchange administrators to confirm which tasks each of you will perform to assure a smooth and successful integration.</span></span>
    
- <span data-ttu-id="d11ff-159">Exchange UM のユーザーを有効にする各 Exchange ユニファイド メッセージング (UM) フォレスト内の Exchange メールボックス サーバーの役割を展開します。</span><span class="sxs-lookup"><span data-stu-id="d11ff-159">Deploy the Exchange Mailbox server roles in each Exchange Unified Messaging (UM) forest where you want to enable users for Exchange UM.</span></span> <span data-ttu-id="d11ff-160">Exchange サーバーの役割のインストール方法の詳細については、Microsoft Exchange Server 2013 のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d11ff-160">For details about installing Exchange server roles, see the Microsoft Exchange Server 2013 documentation.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d11ff-161">Exchange ユニファイド メッセージング (UM) がインストールされている場合、自己署名証明書を使用するように構成されます。</span><span class="sxs-lookup"><span data-stu-id="d11ff-161">When Exchange Unified Messaging (UM) is installed, it is configured to use a self-signed certificate.</span></span> <span data-ttu-id="d11ff-162">自己署名入りの証明書は、Skype ビジネス サーバー 2015 と Exchange UM、互いに信頼されるため、両方のサーバーを信頼する証明機関から個別の証明書を要求する必要があるを有効にできません。</span><span class="sxs-lookup"><span data-stu-id="d11ff-162">The self-signed certificate does not enable Skype for Business Server 2015 and Exchange UM to trust each other, which is why it is necessary to request a separate certificate from a certification authority that both servers trust.</span></span> 
  
- <span data-ttu-id="d11ff-163">ビジネス サーバー 2015 と Exchange UM の Skype は別々 のフォレストにインストールする場合は、各 Exchange フォレストを信頼するフォレストのビジネス サーバー 2015 Skype およびビジネス サーバー 2015 フォレストの Skype を信頼するには、各 Exchange フォレストを構成します。</span><span class="sxs-lookup"><span data-stu-id="d11ff-163">If Skype for Business Server 2015 and Exchange UM are installed in different forests, configure each Exchange forest to trust the Skype for Business Server 2015 forest and the Skype for Business Server 2015 forest to trust each Exchange forest.</span></span> <span data-ttu-id="d11ff-164">また、セットは、ユーザーの Exchange UM の設定ビジネス サーバー 2015 フォレストの場合は、Skype では、ユーザー オブジェクトの通常スクリプトまたはフォレスト間のツールでは、アイデンティティのライフ サイクル マネージャー (ILM) などを使用しています。</span><span class="sxs-lookup"><span data-stu-id="d11ff-164">Also, set the users' Exchange UM settings on the user objects in the Skype for Business Server 2015 forest, typically by using a script or a cross-forest tool, such as Identity Lifecycle Manager (ILM).</span></span>
    
- <span data-ttu-id="d11ff-165">必要に応じて、ユニファイド メッセージング サーバーを管理するのに Exchange 管理コンソールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="d11ff-165">If necessary, install the Exchange Management Console to manage your Unified Messaging servers.</span></span>
    
- <span data-ttu-id="d11ff-166">Outlook Voice Access および自動応答の有効な電話番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="d11ff-166">Obtain valid phone numbers for Outlook Voice Access and auto attendant.</span></span>
    
- <span data-ttu-id="d11ff-167">Microsoft Exchange Server 2010 Service Pack 1 (SP1) より前のバージョンの Exchange UM を使用している場合、Exchange UM SIP の URI に対して座標の名前は、計画およびエンタープライズ VoIP のダイヤル プランをダイヤルします。</span><span class="sxs-lookup"><span data-stu-id="d11ff-167">If you are using a version of Exchange UM earlier than Microsoft Exchange Server 2010 Service Pack 1 (SP1), coordinate names for Exchange UM SIP URI dial plans and Enterprise Voice dial plans.</span></span> 
    
### <a name="deploying-redundant-exchange-um-servers"></a><span data-ttu-id="d11ff-168">冗長 Exchange UM サーバーの展開</span><span class="sxs-lookup"><span data-stu-id="d11ff-168">Deploying Redundant Exchange UM Servers</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d11ff-169">どの Exchange UM サービスが実行されて、組織用に構成する各 Exchange UM ・ SIP ・ URI ダイヤル プランの 2 つのサーバーの最小値を配置することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d11ff-169">We recommend that you deploy a minimum of two servers on which Exchange UM services is running for each Exchange UM SIP URI dial plan that you configure for your organization.</span></span> <span data-ttu-id="d11ff-170">拡張された処理能力を提供することに加えて、冗長サーバーを展開することは高可用性を提供します。</span><span class="sxs-lookup"><span data-stu-id="d11ff-170">In addition to providing expanded capacity, deploying redundant servers provides high availability.</span></span> <span data-ttu-id="d11ff-171">サーバーに障害が発生した場合は、別のサーバーにフェールオーバーするビジネス サーバー 2015 の Skype を構成できます。</span><span class="sxs-lookup"><span data-stu-id="d11ff-171">In the event of an server failure, Skype for Business Server 2015 can be configured to fail over to another server.</span></span> 
  
<span data-ttu-id="d11ff-172">次に示すのは、Exchange UM の復元性を提供する構成例です。</span><span class="sxs-lookup"><span data-stu-id="d11ff-172">The following example configurations provide Exchange UM resiliency.</span></span>
  
<span data-ttu-id="d11ff-173">**例 1: Exchange UM の弾力性**</span><span class="sxs-lookup"><span data-stu-id="d11ff-173">**Example 1: Exchange UM Resiliency**</span></span>

![Exchange UM の復元性の図](../../media/d8381ecc-0e4e-47ea-9bf7-e54fec9414e7.png)
  
<span data-ttu-id="d11ff-p119">例 1 では、Exchange UM サーバー 1 と 2 は Tukwila のデータ センターで有効化されています。Exchange UM サーバー 3 と 4 は Dublin のデータ センターで有効化されています。Tukwila で Exchange UM サーバーが停止した場合、サーバー 1 と 2 のドメイン ネーム システム (DNS) A レコードを、サーバー 3 と 4 それぞれに向くよう、構成します。Dublin で Exchange UM サーバーが停止した場合、サーバー 3 と 4 の DNS A レコードを、サーバー 1 と 2 それぞれに向くよう、構成します。</span><span class="sxs-lookup"><span data-stu-id="d11ff-p119">In Example 1, Exchange UM servers 1 and 2 are enabled in the Tukwila data center, and Exchange UM servers 3 and 4 are enabled in the Dublin data center. In the event of an Exchange UM outage in Tukwila, the Domain Name System (DNS) A records for servers 1 and 2 should be configured to point to servers 3 and 4, respectively. In the event of an Exchange UM outage in Dublin, the DNS A records for servers 3 and 4 should be configured to point to servers 1 and 2, respectively.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d11ff-178">例 1 を割り当てる必要がありますも各 UM サーバーに証明書を次のいずれか: 証明書をサブジェクト代替名 (SAN) でワイルドカードを使用するか、4 つ Exchange UM サーバー、SAN 内のそれぞれの完全修飾ドメイン名 (FQDN) を配置します。</span><span class="sxs-lookup"><span data-stu-id="d11ff-178">For Example 1, you should also assign one of following certificates on each Exchange UM server: either use a certificate with a wildcard in the Subject Alternative Name (SAN) or Put the fully qualified domain name (FQDN) of each of the four Exchange UM servers in the SAN.</span></span> 
  
<span data-ttu-id="d11ff-179">**例 2: Exchange UM の弾力性**</span><span class="sxs-lookup"><span data-stu-id="d11ff-179">**Example 2: Exchange UM Resiliency**</span></span>

![Exchange UM の復元性の図](../../media/4ad101c3-f318-4fc0-b4da-c05f2e92a943.png)
  
<span data-ttu-id="d11ff-p120">例 2 では、通常の操作条件の下、Exchange UM サーバー 1 と 2 は Tukwila のデータ センターで有効化されています。Exchange UM サーバー 3 と 4 は Dublin のデータ センターで有効化されています。4 台すべてのサーバーが Tukwila のユーザーの SIP URL ダイヤル プランに含まれていますが、サーバー 3 と 4 は有効化されていません。たとえば、Tukwila で Exchange UM サーバーが停止した場合、Exchange UM サーバー 1 と 2 は無効化され、Tukwila の Exchange UM トラフィックが Dublin のサーバーにルーティングされるよう、Exchange UM サーバー 3 と 4 は有効化されます。</span><span class="sxs-lookup"><span data-stu-id="d11ff-p120">In Example 2, under ordinary operating conditions Exchange UM servers 1 and 2 are enabled in the Tukwila data center, and Exchange UM servers 3 and 4 are enabled in the Dublin data center. All four servers are included in the Tukwila users' SIP URI dial plan; however, servers 3 and 4 are disabled. In the event of an Exchange UM outage in Tukwila, for example, Exchange UM servers 1 and 2 should be disabled and Exchange UM servers 3 and 4 should be enabled so the Tukwila Exchange UM traffic will be routed to the servers in Dublin.</span></span>
  
<span data-ttu-id="d11ff-184">有効にするか、Exchange 2013 のユニファイド メッセージングを無効にする方法の詳細については、[統合 Exchange 2013 UM Lync Server を](https://go.microsoft.com/fwlink/p/?LinkId=265372)参照してください。</span><span class="sxs-lookup"><span data-stu-id="d11ff-184">For details about how to enable or disable Unified Messaging on Exchange 2013, see [Integrate Exchange 2013 UM with Lync Server](https://go.microsoft.com/fwlink/p/?LinkId=265372).</span></span> <span data-ttu-id="d11ff-185">提供された情報に等しく適用されます Skype ビジネス サーバー 2015 のです。</span><span class="sxs-lookup"><span data-stu-id="d11ff-185">The information provided applies equally to Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="d11ff-186">有効にするか、Microsoft Exchange Server 2010 のユニファイド メッセージングを無効にする方法の詳細については、次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="d11ff-186">For details about how to enable or disable Unified Messaging on Microsoft Exchange Server 2010, see:</span></span>
  
- [<span data-ttu-id="d11ff-187">Exchange 2010 でユニファイド メッセージングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="d11ff-187">Enable Unified Messaging on Exchange 2010</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=204418)
    
- [<span data-ttu-id="d11ff-188">Exchange 2010 でユニファイド メッセージングを無効にします。</span><span class="sxs-lookup"><span data-stu-id="d11ff-188">Disable Unified Messaging on Exchange 2010</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=204416)
    
## <a name="see-also"></a><span data-ttu-id="d11ff-189">関連項目</span><span class="sxs-lookup"><span data-stu-id="d11ff-189">See also</span></span>

#### 

[<span data-ttu-id="d11ff-190">統合するための展開プロセスの概要、設置型ユニファイド メッセージングおよびビジネス用の Skype</span><span class="sxs-lookup"><span data-stu-id="d11ff-190">Deployment process overview for integrating on-premises Unified Messaging and Skype for Business</span></span>](deployment-overview.md)

