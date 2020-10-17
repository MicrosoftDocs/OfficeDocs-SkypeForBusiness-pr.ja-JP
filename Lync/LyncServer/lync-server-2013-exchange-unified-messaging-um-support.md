---
title: 'Lync Server 2013: Exchange ユニファイドメッセージング (UM) のサポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exchange Unified Messaging (UM) support
ms:assetid: 0da62b8d-7416-4fb8-a405-381ca805c53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398179(v=OCS.15)
ms:contentKeyID: 48183405
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac42e46bf92e7fa170ee3dff059edc1b5871aafd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533124"
---
# <a name="exchange-unified-messaging-um-support-in-lync-server-2013"></a><span data-ttu-id="86c0b-102">Lync Server 2013 での Exchange ユニファイドメッセージング (UM) のサポート</span><span class="sxs-lookup"><span data-stu-id="86c0b-102">Exchange Unified Messaging (UM) support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86c0b-103">_**トピックの最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="86c0b-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="86c0b-104">Lync Server 2013 は、ボイスメッセージングと電子メールメッセージングを単一のメッセージングインフラストラクチャに結合するための Exchange ユニファイドメッセージング (UM) との統合をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="86c0b-104">Lync Server 2013 supports integration with Exchange Unified Messaging (UM) for combining voice messaging and email messaging into a single messaging infrastructure.</span></span> <span data-ttu-id="86c0b-105">Exchange 2013 では、exchange UM はメールボックスサーバー上にインストールされて実行される Exchange UM サービスで構成され、UM 呼び出しルーターはクライアントアクセスサーバー上にインストールされて実行されます。</span><span class="sxs-lookup"><span data-stu-id="86c0b-105">In Exchange 2013, Exchange UM consists of the Exchange UM service, which is installed and runs on the Mailbox server, and the UM Call Router, which is installed and runs on the Client Access server.</span></span> <span data-ttu-id="86c0b-106">Lync Server 2013 エンタープライズ Voip 展開の場合、Exchange UM はボイスメッセージングと電子メールメッセージングを、電話 (つまり、Outlook Voice Access) またはコンピューターからアクセスできる単一のストアに結合します。</span><span class="sxs-lookup"><span data-stu-id="86c0b-106">For Lync Server 2013 Enterprise Voice deployments, Exchange UM combines voice messaging and email messaging into a single store that is accessible from a telephone (that is, Outlook Voice Access) or a computer.</span></span> <span data-ttu-id="86c0b-107">Exchange UM と Lync Server 2013 は連携して、エンタープライズ Voip のユーザーに通話応答、Outlook Voice Access、および自動応答サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="86c0b-107">Exchange UM and Lync Server 2013 work together to provide call answering, Outlook Voice Access, and auto attendant services to users of Enterprise Voice.</span></span>

<span data-ttu-id="86c0b-108">Exchange UM の社内展開との統合のサポートに加えて、Lync Server 2013 では、hosted Exchange UM との統合がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="86c0b-108">In addition to the support for integration with on-premises deployments of Exchange UM, Lync Server 2013 supports integration with hosted Exchange UM.</span></span> <span data-ttu-id="86c0b-109">これにより、Microsoft Exchange Online などの Hosted Exchange サービス プロバイダーにユーザーの一部または全部を移行すると、音声メッセージングをユーザーに提供できるようになります。</span><span class="sxs-lookup"><span data-stu-id="86c0b-109">This enables you to provide voice messaging to your users if you migrate some or all of them to a hosted Exchange service provider such as Microsoft Exchange Online.</span></span>

<span data-ttu-id="86c0b-110">Lync Server 2013 では、次のバージョンがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="86c0b-110">Lync Server 2013 supports the following versions:</span></span>

  - <span data-ttu-id="86c0b-111">Microsoft Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="86c0b-111">Microsoft Exchange 2013</span></span>

  - <span data-ttu-id="86c0b-112">Microsoft Exchange Server 2010 (必須) または最新の service pack (推奨)</span><span class="sxs-lookup"><span data-stu-id="86c0b-112">Microsoft Exchange Server 2010 (required) or with latest service pack (recommended)</span></span>

  - <span data-ttu-id="86c0b-113">Microsoft Exchange Server 2007 Service Pack 1 (SP1) (必須) または最新のサービスパック (推奨)</span><span class="sxs-lookup"><span data-stu-id="86c0b-113">Microsoft Exchange Server 2007 with Service Pack 1 (SP1) (required) or latest service pack (recommended)</span></span>

<span data-ttu-id="86c0b-114">Exchange UM を Lync Server 2013 または Lync Server 2013 データベースと併置することはできません。</span><span class="sxs-lookup"><span data-stu-id="86c0b-114">You cannot collocate Exchange UM with Lync Server 2013 or a Lync Server 2013 database.</span></span> <span data-ttu-id="86c0b-115">Exchange UM と Lync Server 2013 は、別のフォレストにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="86c0b-115">You can install Exchange UM and Lync Server 2013 in separate forests.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="86c0b-116">Pbx は、すべてのユーザーにボイスメールと関連サービスを継続的に提供できるため、PBX が展開されているエンタープライズ Voip 展開では Exchange UM を必要としない場合があります。</span><span class="sxs-lookup"><span data-stu-id="86c0b-116">Exchange UM may not be required for Enterprise Voice deployments that have a PBX deployed, because the PBX can continue to provide voice mail and related services to all users.</span></span> <span data-ttu-id="86c0b-117">最終的に PBX の使用を中止した場合 (たとえば、公衆交換電話網 (PSTN) 接続用に SIP トランキングを展開する場合)、Exchange UM を再構成して、以前 PBX ボイスメールシステムを使用していたユーザーにボイスメールを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="86c0b-117">If you eventually retire the PBX (for example, if you deploy SIP trunking for public switched telephone network (PSTN) connectivity), you must reconfigure Exchange UM to provide voice mail to users who previously used the PBX voice mail system.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="86c0b-118">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="86c0b-118">In This Section</span></span>

  - [<span data-ttu-id="86c0b-119">Lync Server 2013 でのオンプレミスのユニファイドメッセージングのコンポーネントとトポロジ</span><span class="sxs-lookup"><span data-stu-id="86c0b-119">Components and topologies for on-premises Unified Messaging in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [<span data-ttu-id="86c0b-120">Lync Server 2013 での hosted Exchange UM 統合のサポート</span><span class="sxs-lookup"><span data-stu-id="86c0b-120">Support for hosted Exchange UM integration in Lync Server 2013</span></span>](lync-server-2013-support-for-hosted-exchange-um-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

