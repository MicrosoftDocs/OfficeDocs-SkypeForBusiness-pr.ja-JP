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
ms.openlocfilehash: 198df79f63415affa4fb9b41d55265b58ae00a8a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756261"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exchange-and-sharepoint-integration-support-in-lync-server-2013"></a><span data-ttu-id="3f034-102">Lync Server 2013 での Exchange と SharePoint の統合のサポート</span><span class="sxs-lookup"><span data-stu-id="3f034-102">Exchange and SharePoint integration support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f034-103">_**最終更新日:** 2017-01-18_</span><span class="sxs-lookup"><span data-stu-id="3f034-103">_**Topic Last Modified:** 2017-01-18_</span></span>

<span data-ttu-id="3f034-104">Lync Server 2013 および Lync 2013 では、これらの製品を統合すると、Office 2013、Exchange Server 2013、Exchange Server 2016、SharePoint などの他のアプリケーションやサーバー製品との安全かつシームレスな通信を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="3f034-104">Lync Server 2013 and Lync 2013 can securely and seamlessly communicate with other applications and server products, including Office 2013, Exchange Server 2013, Exchange Server 2016, and SharePoint, if you integrate these products.</span></span> <span data-ttu-id="3f034-105">Lync Server 2013 と Office を統合すると、ユーザーは、Lync のインスタントメッセージング (IM)、拡張プレゼンス、電話、電話会議などの機能にコンテキストでアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="3f034-105">Integrating Lync Server 2013 and Office provides users with in-context access to the instant messaging (IM), enhanced presence, telephony, and conferencing capabilities of Lync.</span></span> <span data-ttu-id="3f034-106">Office ユーザーは、Outlook 2013 メッセージングおよび共同作業クライアント、および他の Office プログラムまたは SharePoint ページから Lync 機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3f034-106">Office users can access Lync features from within the Outlook 2013 messaging and collaboration client and other Office programs or from a SharePoint page.</span></span> <span data-ttu-id="3f034-107">ユーザーは、Outlook の [会話履歴] フォルダーで Lync の会話のレコードを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="3f034-107">Users can also view a record of Lync conversations in the Outlook Conversation History folder.</span></span> <span data-ttu-id="3f034-108">Lync Server 2013 は、Exchange 2013、Exchange 2016、または Exchange Online と統合されている場合に、次の機能もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="3f034-108">When integrated with Exchange 2013, Exchange 2016, or Exchange Online, Lync Server 2013 also supports the following:</span></span>

  - <span data-ttu-id="3f034-109">統合連絡先ストア: Lync 2013、Exchange、Outlook、Outlook Web App で情報をグローバルに使用できるように、ユーザーは Exchange または Exchange Online のすべての連絡先情報を保存できます。</span><span class="sxs-lookup"><span data-stu-id="3f034-109">Unified contact store, which enables users to store all contact information in Exchange or Exchange Online so that the information is available globally across Lync 2013, Exchange, Outlook, and Outlook Web App.</span></span>

  - <span data-ttu-id="3f034-110">Exchange ユーザーフォルダーに保存された会話履歴と Web 会議履歴。</span><span class="sxs-lookup"><span data-stu-id="3f034-110">Conversation history and Web conferencing history, which is stored in Exchange user folders.</span></span>

  - <span data-ttu-id="3f034-111">IM や会議の内容など、Lync からアーカイブされたコンテンツは、Exchange ストレージに保存することができます。</span><span class="sxs-lookup"><span data-stu-id="3f034-111">Archived content from Lync, such as IM and meeting content, can be stored in Exchange storage.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3f034-112">Lync Server 2013 は、以前のバージョンの Microsoft Exchange Server と SharePoint Server との統合をサポートしていますが、Microsoft Exchange とのアーカイブストレージの統合など、以前のバージョンではすべての機能がサポートされているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="3f034-112">Lync Server 2013 supports integration with previous versions of Microsoft Exchange Server and SharePoint Server, but not all functionality is supported with these previous versions, such as integration of Archiving storage with Microsoft Exchange.</span></span><BR><span data-ttu-id="3f034-113">Exchange 2013 または Exchange 2016 にユーザーを移行する場合は、移行の完了時に Exchange ストレージと Lync Server ストレージの両方を暫定的な方法で使うことができます。</span><span class="sxs-lookup"><span data-stu-id="3f034-113">If you are migrating your users to Exchange 2013 or Exchange 2016, you can use both Exchange storage and Lync Server storage on an interim basis, while you complete the migration.</span></span> <span data-ttu-id="3f034-114">Exchange と Lync の両方のサーバーストレージを永続的に使用することはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3f034-114">Permanent use of both Exchange and Lync Server storage is not supported.</span></span>



</div>

<span data-ttu-id="3f034-115">Lync server 2013 と Exchange Server および SharePoint server との統合には、Lync Server 2013、Exchange Server、および SharePoint Server を実行しているサーバー間のサーバー間認証が必要です。</span><span class="sxs-lookup"><span data-stu-id="3f034-115">Integration of Lync Server 2013 with Exchange Server and SharePoint Server requires server-to-server authentication between servers running Lync Server 2013, Exchange Server, and SharePoint Server.</span></span> <span data-ttu-id="3f034-116">Lync Server 2013 は、サーバー間の認証と承認のための OAuth (Open Authorization) プロトコルをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="3f034-116">Lync Server 2013 supports OAuth (Open Authorization) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="3f034-117">2つの Microsoft サーバー間でのオンプレミスのサーバー間認証の場合、サードパーティのトークンサーバーを使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3f034-117">For on-premises server-to-server authentication between two Microsoft servers, there is no need to use a third-party token server.</span></span> <span data-ttu-id="3f034-118">Lync Server 2013、Exchange Server、および SharePoint Server には、相互に認証目的で使用できる組み込みのトークンサーバーがあります。</span><span class="sxs-lookup"><span data-stu-id="3f034-118">Lync Server 2013, Exchange Server, and SharePoint Server have a built-in token server that can be used for authentication purposes with each other.</span></span> <span data-ttu-id="3f034-119">たとえば、Lync Server 2013 は、セキュリティトークンを単独で発行して署名し、Exchange と通信するときにそのトークンを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="3f034-119">For example, Lync Server 2013 can issue and sign a security token by itself, and use that token when communicating with Exchange.</span></span> <span data-ttu-id="3f034-120">この場合、サードパーティのトークンサーバーを使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3f034-120">In this case, there is no need to use a third-party token server.</span></span>

<span data-ttu-id="3f034-121">Lync Server 2013 は、サーバー間認証の2つのシナリオをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="3f034-121">Lync Server 2013 supports the two server-to-server authentication scenarios.</span></span> <span data-ttu-id="3f034-122">これには、次のようなサーバー間認証の構成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3f034-122">These include configuration of server-to-server authentication between the following:</span></span>

  - <span data-ttu-id="3f034-123">オンプレミスでの Lync Server 2013 および exchange server 2013、Exchange Server 2016、または SharePoint Server のオンプレミスインストール。</span><span class="sxs-lookup"><span data-stu-id="3f034-123">An on-premise installation of Lync Server 2013 and an on-premises installation of Exchange Server 2013, Exchange Server 2016, and/or SharePoint Server.</span></span>

  - <span data-ttu-id="3f034-124">Office コンポーネントのペア (たとえば、Microsoft Exchange 365 と Microsoft Lync Server 365、または Microsoft Lync Server 365 と Microsoft SharePoint 365 の間)。</span><span class="sxs-lookup"><span data-stu-id="3f034-124">A pair of Office components (for example, between Microsoft Exchange 365 and Microsoft Lync Server 365, or between Microsoft Lync Server 365 and Microsoft SharePoint 365).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3f034-125">この Lync Server 2013 リリースでは、オンプレミスサーバーと Office 365 コンポーネント間のサーバー間認証はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3f034-125">Server-to-server authentication between an on-premises server and an Office 365 component is not supported in this Lync Server 2013 release.</span></span> <span data-ttu-id="3f034-126">特に、Lync Server 2013 と Microsoft Exchange 365 のオンプレミスインストールとの間でサーバー間認証をセットアップできないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="3f034-126">Among other things, this means that you cannot set up server-to-server authentication between an on-premises installation of Lync Server 2013 and Microsoft Exchange 365.</span></span>



</div>

<span data-ttu-id="3f034-127">サーバー間認証の詳細については、展開ドキュメントまたは操作のドキュメントの「 [Lync server 2013 でのサーバー間認証 (OAuth) とパートナーアプリケーションの管理](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f034-127">For details about server-to-server authentication, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or Operations documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

