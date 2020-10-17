---
title: 'Lync Server 2013: モビリティの展開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying mobility
ms:assetid: f41e6b25-d2cd-43fd-a17b-22cfda8bcd4f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690055(v=OCS.15)
ms:contentKeyID: 48185805
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 118e0d1384f3ef74c3b42341e659694a228c3675
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507344"
---
# <a name="deploying-mobility-in-lync-server-2013"></a><span data-ttu-id="191d7-102">Lync Server 2013 でのモビリティの展開</span><span class="sxs-lookup"><span data-stu-id="191d7-102">Deploying mobility in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="191d7-103">_**トピックの最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="191d7-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="191d7-104">Lync Server 2013 モビリティ機能を展開すると、モバイルユーザーは、インスタントメッセージング (IM)、プレゼンス、連絡先などの Lync 機能に対してサポートされているモバイルデバイスを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="191d7-104">When you deploy the Lync Server 2013 mobility feature, mobile users can use supported mobile devices for Lync functionality such as instant messaging (IM), presence, and contacts.</span></span>

<span data-ttu-id="191d7-105">モビリティ機能を展開するための要件の詳細については、「 [Lync Server 2013 でのモビリティの計画](lync-server-2013-planning-for-mobility.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="191d7-105">For details about requirements for deploying the mobility feature, see [Planning for mobility in Lync Server 2013](lync-server-2013-planning-for-mobility.md).</span></span>

<span data-ttu-id="191d7-106">このセクションでは、モビリティ機能と自動検出機能を展開および確認する方法を順を追って説明します。</span><span class="sxs-lookup"><span data-stu-id="191d7-106">This section guides you through the steps for deploying and verifying the mobility and automatic discovery features.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="191d7-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="191d7-107">In This Section</span></span>

  - [<span data-ttu-id="191d7-108">Lync Server 2013 での自動検出サービスの DNS レコードの作成</span><span class="sxs-lookup"><span data-stu-id="191d7-108">Creating DNS records for the Autodiscover Service in Lync Server 2013</span></span>](lync-server-2013-creating-dns-records-for-the-autodiscover-service.md)

  - [<span data-ttu-id="191d7-109">Lync Server 2013 でのモビリティの証明書の変更</span><span class="sxs-lookup"><span data-stu-id="191d7-109">Modifying certificates for mobility in Lync Server 2013</span></span>](lync-server-2013-modifying-certificates-for-mobility.md)

  - [<span data-ttu-id="191d7-110">Lync Server 2013 でのモビリティのリバースプロキシの構成</span><span class="sxs-lookup"><span data-stu-id="191d7-110">Configuring the reverse proxy for mobility in Lync Server 2013</span></span>](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)

  - [<span data-ttu-id="191d7-111">Lync Server 2013 での自動検出の構成 (ハイブリッド展開を使用したモビリティ)</span><span class="sxs-lookup"><span data-stu-id="191d7-111">Configuring Autodiscover in Lync Server 2013 for mobility with hybrid deployments</span></span>](lync-server-2013-configuring-autodiscover-for-mobility-with-hybrid-deployments.md)

  - [<span data-ttu-id="191d7-112">Lync Server 2013 でのモビリティの展開の確認</span><span class="sxs-lookup"><span data-stu-id="191d7-112">Verifying your mobility deployment in Lync Server 2013</span></span>](lync-server-2013-verifying-your-mobility-deployment.md)

  - [<span data-ttu-id="191d7-113">Lync Server 2013 でのプッシュ通知の構成</span><span class="sxs-lookup"><span data-stu-id="191d7-113">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)

  - [<span data-ttu-id="191d7-114">Lync Server 2013 でのモビリティポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="191d7-114">Configuring mobility policy in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-policy.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

