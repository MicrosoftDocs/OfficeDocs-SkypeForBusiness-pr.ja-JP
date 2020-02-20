---
title: 'Lync Server 2013: Exchange と SharePoint の統合のサポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exchange and SharePoint integration support
ms:assetid: 72bf8aa5-55b1-4851-8a59-c96bf85d215a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205005(v=OCS.15)
ms:contentKeyID: 48184504
ms.date: 01/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1fdfaffa12d84b57f0ae0203ebc14491bb6d8d4f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146820"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="exchange-and-sharepoint-integration-support-in-lync-server-2013"></a><span data-ttu-id="46819-102">Lync Server 2013 での Exchange と SharePoint の統合のサポート</span><span class="sxs-lookup"><span data-stu-id="46819-102">Exchange and SharePoint integration support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46819-103">_**トピックの最終更新日:** 2017-01-18_</span><span class="sxs-lookup"><span data-stu-id="46819-103">_**Topic Last Modified:** 2017-01-18_</span></span>

<span data-ttu-id="46819-104">Lync Server 2013 および Lync 2013 は、これらの製品を統合すると、Office 2013、Exchange Server 2013、Exchange Server 2016、および SharePoint を含む他のアプリケーションやサーバー製品と安全かつシームレスに通信することができます。</span><span class="sxs-lookup"><span data-stu-id="46819-104">Lync Server 2013 and Lync 2013 can securely and seamlessly communicate with other applications and server products, including Office 2013, Exchange Server 2013, Exchange Server 2016, and SharePoint, if you integrate these products.</span></span> <span data-ttu-id="46819-105">Lync Server 2013 と Office を統合することにより、ユーザーは、インスタントメッセージング (IM)、拡張プレゼンス、テレフォニー、および Lync の会議機能に対して、コンテキストに依存したアクセスが可能になります。</span><span class="sxs-lookup"><span data-stu-id="46819-105">Integrating Lync Server 2013 and Office provides users with in-context access to the instant messaging (IM), enhanced presence, telephony, and conferencing capabilities of Lync.</span></span> <span data-ttu-id="46819-106">Office ユーザーは、Outlook 2013 メッセージングおよびコラボレーションクライアントおよびその他の Office プログラム内から、または SharePoint ページから Lync 機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="46819-106">Office users can access Lync features from within the Outlook 2013 messaging and collaboration client and other Office programs or from a SharePoint page.</span></span> <span data-ttu-id="46819-107">ユーザーは、Outlook の [会話履歴] フォルダーで Lync 会話のレコードを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="46819-107">Users can also view a record of Lync conversations in the Outlook Conversation History folder.</span></span> <span data-ttu-id="46819-108">Exchange 2013、Exchange 2016、または Exchange Online と統合されている場合、Lync Server 2013 は次の機能もサポートします。</span><span class="sxs-lookup"><span data-stu-id="46819-108">When integrated with Exchange 2013, Exchange 2016, or Exchange Online, Lync Server 2013 also supports the following:</span></span>

  - <span data-ttu-id="46819-109">統合連絡先ストア。これにより、ユーザーはすべての連絡先情報を Exchange または Exchange Online に保存できるようになり、Lync 2013、Exchange、Outlook、および Outlook Web App 間で情報をグローバルに利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="46819-109">Unified contact store, which enables users to store all contact information in Exchange or Exchange Online so that the information is available globally across Lync 2013, Exchange, Outlook, and Outlook Web App.</span></span>

  - <span data-ttu-id="46819-110">Exchange ユーザーフォルダーに格納されている会話履歴と Web 会議履歴。</span><span class="sxs-lookup"><span data-stu-id="46819-110">Conversation history and Web conferencing history, which is stored in Exchange user folders.</span></span>

  - <span data-ttu-id="46819-111">Lync からのアーカイブされたコンテンツ (IM、会議コンテンツなど) は、Exchange ストレージに保存できます。</span><span class="sxs-lookup"><span data-stu-id="46819-111">Archived content from Lync, such as IM and meeting content, can be stored in Exchange storage.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="46819-112">Lync Server 2013 は、以前のバージョンの Microsoft Exchange Server および SharePoint Server との統合をサポートしていますが、Microsoft Exchange とのアーカイブストレージの統合など、以前のバージョンではサポートされない機能もあります。</span><span class="sxs-lookup"><span data-stu-id="46819-112">Lync Server 2013 supports integration with previous versions of Microsoft Exchange Server and SharePoint Server, but not all functionality is supported with these previous versions, such as integration of Archiving storage with Microsoft Exchange.</span></span><BR><span data-ttu-id="46819-113">ユーザーを Exchange 2013 または Exchange 2016 に移行している場合は、移行を完了する間、Exchange ストレージと Lync Server ストレージの両方を中間に使用することができます。</span><span class="sxs-lookup"><span data-stu-id="46819-113">If you are migrating your users to Exchange 2013 or Exchange 2016, you can use both Exchange storage and Lync Server storage on an interim basis, while you complete the migration.</span></span> <span data-ttu-id="46819-114">Exchange と Lync Server の両方のストレージを恒久的に使用することはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="46819-114">Permanent use of both Exchange and Lync Server storage is not supported.</span></span>



</div>

<span data-ttu-id="46819-115">Lync server 2013 と Exchange Server および SharePoint Server との統合では、Lync Server 2013、Exchange Server、および SharePoint Server を実行しているサーバー間でのサーバー間認証が必要です。</span><span class="sxs-lookup"><span data-stu-id="46819-115">Integration of Lync Server 2013 with Exchange Server and SharePoint Server requires server-to-server authentication between servers running Lync Server 2013, Exchange Server, and SharePoint Server.</span></span> <span data-ttu-id="46819-116">Lync Server 2013 は、サーバー間の認証と承認に OAuth (オープン認証) プロトコルをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="46819-116">Lync Server 2013 supports OAuth (Open Authorization) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="46819-117">2つの Microsoft サーバー間でのオンプレミスのサーバー間認証の場合は、サードパーティのトークンサーバーを使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="46819-117">For on-premises server-to-server authentication between two Microsoft servers, there is no need to use a third-party token server.</span></span> <span data-ttu-id="46819-118">Lync Server 2013、Exchange Server、および SharePoint Server には、互いに認証の目的で使用できる組み込みのトークンサーバーがあります。</span><span class="sxs-lookup"><span data-stu-id="46819-118">Lync Server 2013, Exchange Server, and SharePoint Server have a built-in token server that can be used for authentication purposes with each other.</span></span> <span data-ttu-id="46819-119">たとえば、Lync Server 2013 は、セキュリティトークンを単独で発行して署名し、Exchange と通信するときにそのトークンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="46819-119">For example, Lync Server 2013 can issue and sign a security token by itself, and use that token when communicating with Exchange.</span></span> <span data-ttu-id="46819-120">この場合、サードパーティのトークンサーバーを使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="46819-120">In this case, there is no need to use a third-party token server.</span></span>

<span data-ttu-id="46819-121">Lync Server 2013 は、2台のサーバー間認証シナリオをサポートします。</span><span class="sxs-lookup"><span data-stu-id="46819-121">Lync Server 2013 supports the two server-to-server authentication scenarios.</span></span> <span data-ttu-id="46819-122">これには、次のようなサーバー間認証の構成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="46819-122">These include configuration of server-to-server authentication between the following:</span></span>

  - <span data-ttu-id="46819-123">Lync Server 2013 の社内インストールと、Exchange Server 2013、Exchange Server 2016、または SharePoint Server のオンプレミスのインストール。</span><span class="sxs-lookup"><span data-stu-id="46819-123">An on-premise installation of Lync Server 2013 and an on-premises installation of Exchange Server 2013, Exchange Server 2016, and/or SharePoint Server.</span></span>

  - <span data-ttu-id="46819-124">Office コンポーネントのペア (たとえば、Microsoft Exchange 365 と Microsoft Lync Server 365 の間、または Microsoft Lync Server 365 と Microsoft SharePoint 365 の間)。</span><span class="sxs-lookup"><span data-stu-id="46819-124">A pair of Office components (for example, between Microsoft Exchange 365 and Microsoft Lync Server 365, or between Microsoft Lync Server 365 and Microsoft SharePoint 365).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="46819-125">この Lync Server 2013 リリースでは、オンプレミスのサーバーと Office 365 コンポーネント間のサーバー間認証はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="46819-125">Server-to-server authentication between an on-premises server and an Office 365 component is not supported in this Lync Server 2013 release.</span></span> <span data-ttu-id="46819-126">これは特に、Lync Server 2013 と Microsoft Exchange 365 の社内インストールとの間でサーバー間認証をセットアップできないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="46819-126">Among other things, this means that you cannot set up server-to-server authentication between an on-premises installation of Lync Server 2013 and Microsoft Exchange 365.</span></span>



</div>

<span data-ttu-id="46819-127">サーバー間認証の詳細については、「展開」のドキュメントまたは「操作」のドキュメントの「 [Lync server 2013 でのサーバー間認証 (OAuth) およびパートナーアプリケーションの管理](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46819-127">For details about server-to-server authentication, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or Operations documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

