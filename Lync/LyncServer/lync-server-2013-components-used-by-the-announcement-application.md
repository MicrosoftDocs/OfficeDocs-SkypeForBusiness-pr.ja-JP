---
title: 'Lync Server 2013: アナウンスメントアプリケーションで使用されるコンポーネント'
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
ms.openlocfilehash: a16690a1dee49c3b28b1f951894c216666d1eec9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151609"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-used-by-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="4ff3e-102">Lync Server 2013 のアナウンスアプリケーションで使用されるコンポーネント</span><span class="sxs-lookup"><span data-stu-id="4ff3e-102">Components used by the Announcement application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ff3e-103">_**トピックの最終更新日:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="4ff3e-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="4ff3e-104">Lync Server 2013 では、アナウンスメントアプリケーションは応答グループアプリケーションのコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="4ff3e-104">In Lync Server 2013, the Announcement application is a component of the Response Group application.</span></span> <span data-ttu-id="4ff3e-105">エンタープライズ Voip を展開すると、アナウンスアプリケーションが自動的にインストールされ、応答グループアプリケーションと共にアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="4ff3e-105">When you deploy Enterprise Voice, the Announcement application is automatically installed and activated along with the Response Group application.</span></span> <span data-ttu-id="4ff3e-106">このセクションでは、アナウンスメントアプリケーションをサポートするコンポーネントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="4ff3e-106">This section describes the components that support the Announcement application.</span></span>

<div>

## <a name="announcement-application-components"></a><span data-ttu-id="4ff3e-107">アナウンス アプリケーションのコンポーネント</span><span class="sxs-lookup"><span data-stu-id="4ff3e-107">Announcement Application Components</span></span>

<span data-ttu-id="4ff3e-108">アナウンスメントアプリケーションは、次の Lync Server コンポーネントでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4ff3e-108">The following Lync Server components support the Announcement application:</span></span>

  - <span data-ttu-id="4ff3e-109">**Application service**   アプリケーションサービスは、統合コミュニケーションアプリケーションを展開、ホスト、および管理するためのプラットフォームを提供します。</span><span class="sxs-lookup"><span data-stu-id="4ff3e-109">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications.</span></span> <span data-ttu-id="4ff3e-110">アプリケーションサービスは、フロントエンドプール内のすべてのフロントエンドサーバーとすべての Standard Edition サーバーに自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="4ff3e-110">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="4ff3e-111">**応答グループアプリケーション**   応答グループアプリケーションは、アプリケーションサービスによってホストされている統合コミュニケーションアプリケーションの1つです。</span><span class="sxs-lookup"><span data-stu-id="4ff3e-111">**Response Group application**   The Response Group application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="4ff3e-112">割り当てられていない電話番号の範囲をアナウンスにルーティングするように構成すると、その電話番号に発信された通話をルーティングするために、応答グループアプリケーションが必要になります。</span><span class="sxs-lookup"><span data-stu-id="4ff3e-112">When an unassigned phone number range is configured to route to an announcement, the Response Group application is required to route the calls made to the phone number.</span></span> <span data-ttu-id="4ff3e-113">(Exchange ユニファイドメッセージング (UM) にルーティングするようにすべての範囲が構成されている場合、応答グループアプリケーションは必要ありません)。</span><span class="sxs-lookup"><span data-stu-id="4ff3e-113">(Response Group application is not required if all the ranges are configured to route to Exchange Unified Messaging (UM).)</span></span>

  - <span data-ttu-id="4ff3e-114">**音声ファイル**   オーディオファイルはアナウンスに使用されます。</span><span class="sxs-lookup"><span data-stu-id="4ff3e-114">**Audio files**   Audio files are used for the announcements.</span></span>

  - <span data-ttu-id="4ff3e-115">**ファイルストア**   アナウンスアプリケーションは、ファイルストアを使用してオーディオファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="4ff3e-115">**File Store**   The Announcement application uses File Store to store its audio files.</span></span>

  - <span data-ttu-id="4ff3e-116">**Lync server コントロールパネル**   lync server コントロールパネルを使用して、割り当てられていない番号の表を構成できます。</span><span class="sxs-lookup"><span data-stu-id="4ff3e-116">**Lync Server Control Panel**   You can use Lync Server Control Panel to configure the unassigned number table.</span></span>

  - <span data-ttu-id="4ff3e-117">**Lync server 管理**   シェル lync server 管理シェルコマンドレットを使用して、アナウンスの設定と割り当てられていない番号の表を構成できます。</span><span class="sxs-lookup"><span data-stu-id="4ff3e-117">**Lync Server Management Shell**   You can use Lync Server Management Shell cmdlets to configure Announcement settings and the unassigned number table.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

