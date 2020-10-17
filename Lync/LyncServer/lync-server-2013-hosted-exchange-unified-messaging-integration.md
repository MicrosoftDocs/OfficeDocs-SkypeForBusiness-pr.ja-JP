---
title: 'Lync Server 2013: Hosted Exchange ユニファイドメッセージング統合'
description: 'Lync Server 2013: Hosted Exchange ユニファイドメッセージング統合。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange Unified Messaging integration
ms:assetid: f4de0165-da3b-499e-98fc-28ddd0db02d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413027(v=OCS.15)
ms:contentKeyID: 48185829
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 980c0bc47258e9fae94ff623559342ca36eea145
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550123"
---
# <a name="hosted-exchange-unified-messaging-integration-in-lync-server-2013"></a><span data-ttu-id="0a9b8-103">Lync Server 2013 でのホスト型 Exchange ユニファイドメッセージングの統合</span><span class="sxs-lookup"><span data-stu-id="0a9b8-103">Hosted Exchange Unified Messaging integration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a9b8-104">_**トピックの最終更新日:** 2012-09-20_</span><span class="sxs-lookup"><span data-stu-id="0a9b8-104">_**Topic Last Modified:** 2012-09-20_</span></span>

<span data-ttu-id="0a9b8-105">以前の Lync Server 2013 リリースは2013、Exchange ユニファイドメッセージング (UM) の *社内* 展開との統合のために提供されたサポートに加えて、 *hosted* Exchange UM との統合のサポートが導入されました。</span><span class="sxs-lookup"><span data-stu-id="0a9b8-105">In addition to the support that previous Lync Server 2013 releases have provided for integration with *on-premises* deployments of Exchange Unified Messaging (UM), Lync Server 2013 introduces support for integration with *hosted* Exchange UM.</span></span> <span data-ttu-id="0a9b8-106">Hosted Exchange UM を使用すると、Microsoft Exchange Online などのホストされた Exchange サービスプロバイダーに一部またはすべてを転送する場合に、Lync Server 2013 がユーザーにボイスメッセージングを提供することができます。</span><span class="sxs-lookup"><span data-stu-id="0a9b8-106">Hosted Exchange UM enables Lync Server 2013 to provide voice messaging to your users if you transfer some or all of them to a hosted Exchange service provider such as Microsoft Exchange Online.</span></span>

<span data-ttu-id="0a9b8-107">Lync Server 2013 Enterprise Voice は、Exchange UM インフラストラクチャを使用して、通話応答、通話通知、音声アクセス (ボイスメールを含む)、および自動応答サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="0a9b8-107">Lync Server 2013 Enterprise Voice uses the Exchange UM infrastructure to provide call answering, call notification, voice access (including voice mail), and auto attendant services.</span></span> <span data-ttu-id="0a9b8-108">詳細については、「 [統合ユニファイドメッセージングと Lync Server 2013 の機能](lync-server-2013-features-of-integrated-unified-messaging.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a9b8-108">For details, see [Features of integrated Unified Messaging and Lync Server 2013](lync-server-2013-features-of-integrated-unified-messaging.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0a9b8-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="0a9b8-109">In This Section</span></span>

  - [<span data-ttu-id="0a9b8-110">Lync Server 2013 での Hosted Exchange UM アーキテクチャとルーティング</span><span class="sxs-lookup"><span data-stu-id="0a9b8-110">Hosted Exchange UM architecture and routing in Lync Server 2013</span></span>](lync-server-2013-hosted-exchange-um-architecture-and-routing.md)

  - [<span data-ttu-id="0a9b8-111">Lync Server 2013 のホストボイスメールポリシー</span><span class="sxs-lookup"><span data-stu-id="0a9b8-111">Hosted voice mail policies in Lync Server 2013</span></span>](lync-server-2013-hosted-voice-mail-policies.md)

  - [<span data-ttu-id="0a9b8-112">Lync Server 2013 での Hosted Exchange ユーザー管理</span><span class="sxs-lookup"><span data-stu-id="0a9b8-112">Hosted Exchange user management in Lync Server 2013</span></span>](lync-server-2013-hosted-exchange-user-management.md)

  - [<span data-ttu-id="0a9b8-113">Lync Server 2013 での Hosted Exchange の連絡先オブジェクト管理</span><span class="sxs-lookup"><span data-stu-id="0a9b8-113">Hosted Exchange Contact object management in Lync Server 2013</span></span>](lync-server-2013-hosted-exchange-contact-object-management.md)

  - [<span data-ttu-id="0a9b8-114">ホストされた Exchange UM と Lync Server 2013 を統合するための展開プロセス</span><span class="sxs-lookup"><span data-stu-id="0a9b8-114">Deployment process for integrating hosted Exchange UM with Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-integrating-hosted-exchange-um.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

