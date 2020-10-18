---
title: 'Lync Server 2013: アナウンスメントアプリケーションで使用されるコンポーネント'
description: 'Lync Server 2013: アナウンスメントアプリケーションで使用されるコンポーネント。'
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
ms.openlocfilehash: e5338ad097c814d5c6435bd89dbf7cfa8680feb8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577693"
---
# <a name="components-used-by-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="498e8-103">Lync Server 2013 のアナウンスアプリケーションで使用されるコンポーネント</span><span class="sxs-lookup"><span data-stu-id="498e8-103">Components used by the Announcement application in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="498e8-104">_**トピックの最終更新日:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="498e8-104">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="498e8-105">Lync Server 2013 では、アナウンスメントアプリケーションは応答グループアプリケーションのコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="498e8-105">In Lync Server 2013, the Announcement application is a component of the Response Group application.</span></span> <span data-ttu-id="498e8-106">エンタープライズ Voip を展開すると、アナウンスアプリケーションが自動的にインストールされ、応答グループアプリケーションと共にアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="498e8-106">When you deploy Enterprise Voice, the Announcement application is automatically installed and activated along with the Response Group application.</span></span> <span data-ttu-id="498e8-107">このセクションでは、アナウンスメントアプリケーションをサポートするコンポーネントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="498e8-107">This section describes the components that support the Announcement application.</span></span>

<div>

## <a name="announcement-application-components"></a><span data-ttu-id="498e8-108">アナウンス アプリケーションのコンポーネント</span><span class="sxs-lookup"><span data-stu-id="498e8-108">Announcement Application Components</span></span>

<span data-ttu-id="498e8-109">アナウンスメントアプリケーションは、次の Lync Server コンポーネントでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="498e8-109">The following Lync Server components support the Announcement application:</span></span>

  - <span data-ttu-id="498e8-110">**アプリケーションサービス**    アプリケーションサービスは、統合コミュニケーションアプリケーションを展開、ホスト、および管理するためのプラットフォームを提供します。</span><span class="sxs-lookup"><span data-stu-id="498e8-110">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications.</span></span> <span data-ttu-id="498e8-111">アプリケーションサービスは、フロントエンドプール内のすべてのフロントエンドサーバーとすべての Standard Edition サーバーに自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="498e8-111">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="498e8-112">**応答グループアプリケーション**    応答グループアプリケーションは、アプリケーションサービスによってホストされている統合コミュニケーションアプリケーションの1つです。</span><span class="sxs-lookup"><span data-stu-id="498e8-112">**Response Group application**   The Response Group application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="498e8-113">割り当てられていない電話番号の範囲をアナウンスにルーティングするように構成すると、その電話番号に発信された通話をルーティングするために、応答グループアプリケーションが必要になります。</span><span class="sxs-lookup"><span data-stu-id="498e8-113">When an unassigned phone number range is configured to route to an announcement, the Response Group application is required to route the calls made to the phone number.</span></span> <span data-ttu-id="498e8-114">(Exchange ユニファイドメッセージング (UM) にルーティングするようにすべての範囲が構成されている場合、応答グループアプリケーションは必要ありません)。</span><span class="sxs-lookup"><span data-stu-id="498e8-114">(Response Group application is not required if all the ranges are configured to route to Exchange Unified Messaging (UM).)</span></span>

  - <span data-ttu-id="498e8-115">**オーディオファイル**    音声ファイルはアナウンスに使用されます。</span><span class="sxs-lookup"><span data-stu-id="498e8-115">**Audio files**   Audio files are used for the announcements.</span></span>

  - <span data-ttu-id="498e8-116">**ファイルストア**    アナウンスメントアプリケーションは、ファイルストアを使用してオーディオファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="498e8-116">**File Store**   The Announcement application uses File Store to store its audio files.</span></span>

  - <span data-ttu-id="498e8-117">**Lync Server コントロールパネル**    Lync Server コントロールパネルを使用して、割り当てられていない番号の表を構成できます。</span><span class="sxs-lookup"><span data-stu-id="498e8-117">**Lync Server Control Panel**   You can use Lync Server Control Panel to configure the unassigned number table.</span></span>

  - <span data-ttu-id="498e8-118">**Lync Server 管理シェル**    Lync Server 管理シェルコマンドレットを使用すると、アナウンスの設定と割り当てられていない番号の表を構成できます。</span><span class="sxs-lookup"><span data-stu-id="498e8-118">**Lync Server Management Shell**   You can use Lync Server Management Shell cmdlets to configure Announcement settings and the unassigned number table.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

