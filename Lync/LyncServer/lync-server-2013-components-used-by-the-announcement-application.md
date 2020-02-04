---
title: 'Lync Server 2013: アナウンス アプリケーションで使用されるコンポーネント'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by the Announcement application
ms:assetid: 7b1a0281-cf31-459d-a734-5f10a129089c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398608(v=OCS.15)
ms:contentKeyID: 48184595
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52ef0b1da665f8797f29582e9ce9e1d311287d61
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757051"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="ed2ea-102">Lync Server 2013 のアナウンス アプリケーションで使用されるコンポーネント</span><span class="sxs-lookup"><span data-stu-id="ed2ea-102">Components used by the Announcement application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed2ea-103">_**最終更新日:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="ed2ea-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="ed2ea-104">Lync Server 2013 では、アナウンスメントアプリケーションは応答グループアプリケーションのコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="ed2ea-104">In Lync Server 2013, the Announcement application is a component of the Response Group application.</span></span> <span data-ttu-id="ed2ea-105">エンタープライズ Voip を展開すると、応答グループアプリケーションと共に、アナウンスメントアプリケーションが自動的にインストールされ、アクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="ed2ea-105">When you deploy Enterprise Voice, the Announcement application is automatically installed and activated along with the Response Group application.</span></span> <span data-ttu-id="ed2ea-106">このセクションでは、アナウンスメントアプリケーションをサポートするコンポーネントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ed2ea-106">This section describes the components that support the Announcement application.</span></span>

<div>

## <a name="announcement-application-components"></a><span data-ttu-id="ed2ea-107">アナウンスメントアプリケーションのコンポーネント</span><span class="sxs-lookup"><span data-stu-id="ed2ea-107">Announcement Application Components</span></span>

<span data-ttu-id="ed2ea-108">以下の Lync Server コンポーネントは、アナウンスメントアプリケーションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="ed2ea-108">The following Lync Server components support the Announcement application:</span></span>

  - <span data-ttu-id="ed2ea-109">**アプリケーションサービス**   アプリケーションサービスは、ユニファイドコミュニケーションアプリケーションを展開、ホスティング、および管理するためのプラットフォームを提供します。</span><span class="sxs-lookup"><span data-stu-id="ed2ea-109">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications.</span></span> <span data-ttu-id="ed2ea-110">アプリケーションサービスは、フロントエンドプールのすべてのフロントエンドサーバーと、すべての Standard Edition サーバーに自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="ed2ea-110">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="ed2ea-111">**応答グループ**   アプリケーション応答グループアプリケーションは、アプリケーションサービスによってホストされるユニファイドコミュニケーションアプリケーションの1つです。</span><span class="sxs-lookup"><span data-stu-id="ed2ea-111">**Response Group application**   The Response Group application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="ed2ea-112">[割り当てられていない電話番号] の範囲がお知らせにルーティングするように構成されている場合は、電話番号への通話をルーティングするために応答グループアプリケーションが必要です。</span><span class="sxs-lookup"><span data-stu-id="ed2ea-112">When an unassigned phone number range is configured to route to an announcement, the Response Group application is required to route the calls made to the phone number.</span></span> <span data-ttu-id="ed2ea-113">(応答グループアプリケーションは、すべての範囲が Exchange ユニファイドメッセージング (UM) にルーティングするように構成されている場合は必須ではありません)。</span><span class="sxs-lookup"><span data-stu-id="ed2ea-113">(Response Group application is not required if all the ranges are configured to route to Exchange Unified Messaging (UM).)</span></span>

  - <span data-ttu-id="ed2ea-114">\*\*\*\*   アナウンスメントにはオーディオファイルのオーディオファイルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="ed2ea-114">**Audio files**   Audio files are used for the announcements.</span></span>

  - <span data-ttu-id="ed2ea-115">**ファイルストア**   アナウンスメントアプリケーションは、ファイルストアを使ってオーディオファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="ed2ea-115">**File Store**   The Announcement application uses File Store to store its audio files.</span></span>

  - <span data-ttu-id="ed2ea-116">**Lync server コントロールパネル**   lync server コントロールパネルを使用して、割り当てられていない番号テーブルを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="ed2ea-116">**Lync Server Control Panel**   You can use Lync Server Control Panel to configure the unassigned number table.</span></span>

  - <span data-ttu-id="ed2ea-117">**Lync server 管理**   シェルコマンドレットを使用して、アナウンスメントの設定および未使用の番号テーブルを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="ed2ea-117">**Lync Server Management Shell**   You can use Lync Server Management Shell cmdlets to configure Announcement settings and the unassigned number table.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

