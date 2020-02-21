---
title: 'Lync Server 2013: コールパークで使用されるコンポーネント'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Call Park
ms:assetid: c7ffbee3-0ce1-48c0-bb56-af098b41d6d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398824(v=OCS.15)
ms:contentKeyID: 48185374
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a6585663ac6dedcd83e00ca4abc4f57047fcb7f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204653"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-used-by-call-park-in-lync-server-2013"></a><span data-ttu-id="c5bc1-102">Lync Server 2013 のコールパークで使用されるコンポーネント</span><span class="sxs-lookup"><span data-stu-id="c5bc1-102">Components used by Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5bc1-103">_**トピックの最終更新日:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="c5bc1-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="c5bc1-104">コールパークアプリケーションは、エンタープライズ Voip を展開するときに自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="c5bc1-104">The Call Park application is automatically installed when you deploy Enterprise Voice.</span></span> <span data-ttu-id="c5bc1-105">通話パークを有効にするには、音声ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="c5bc1-105">You enable Call Park by configuring voice policy.</span></span> <span data-ttu-id="c5bc1-106">次の Lync Server 2013 コンポーネントは、コールパークアプリケーションをサポートします。</span><span class="sxs-lookup"><span data-stu-id="c5bc1-106">The following Lync Server 2013 components support the Call Park application:</span></span>

  - <span data-ttu-id="c5bc1-107">**Application service**   アプリケーションサービスは、コールパークアプリケーションなどの統合コミュニケーションアプリケーションを展開、ホスト、および管理するためのプラットフォームを提供します。</span><span class="sxs-lookup"><span data-stu-id="c5bc1-107">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications, such as the Call Park application.</span></span> <span data-ttu-id="c5bc1-108">アプリケーションサービスは、フロントエンドプール内のすべてのフロントエンドサーバーとすべての Standard Edition サーバーに自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="c5bc1-108">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="c5bc1-109">**コールパークアプリケーション**   コールパークアプリケーションは、アプリケーションサービスによってホストされている統合コミュニケーションアプリケーションの1つです。</span><span class="sxs-lookup"><span data-stu-id="c5bc1-109">**Call Park application**   The Call Park application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="c5bc1-110">エンタープライズ VoIP を展開するときに自動的に組み込まれます。</span><span class="sxs-lookup"><span data-stu-id="c5bc1-110">It is included automatically when you deploy Enterprise Voice.</span></span> <span data-ttu-id="c5bc1-111">コールパークパーク、通話を取得し、コールパークオービットを管理します。</span><span class="sxs-lookup"><span data-stu-id="c5bc1-111">Call Park parks and retrieves calls and manages call park orbits.</span></span>

  - <span data-ttu-id="c5bc1-112">**音楽-on ホールド-ファイル**   音楽が有効になっている場合は、通話の保留中に音楽ファイルが再生されます。</span><span class="sxs-lookup"><span data-stu-id="c5bc1-112">**Music-on hold-file**   If music in enabled, the music file is played while a call is parked.</span></span> <span data-ttu-id="c5bc1-113">コールパークアプリケーションがインストールされている場合は、既定の音楽ファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c5bc1-113">A default music file is included when the Call Park application is installed.</span></span>

  - <span data-ttu-id="c5bc1-114">**ファイルストア**   コールパークアプリケーションは、カスタムオーディオファイルを保持するためにファイルストアを使用します。</span><span class="sxs-lookup"><span data-stu-id="c5bc1-114">**File Store**   The Call Park application uses File Store to hold custom audio files.</span></span>

  - <span data-ttu-id="c5bc1-115">**Lync server コントロールパネル**   lync server コントロールパネルを使用して、コールパークオービットテーブルを構成し、ユーザーのコールパークを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c5bc1-115">**Lync Server Control Panel**   You can use Lync Server Control Panel to configure the call park orbit table and to enable Call Park for users.</span></span>

  - <span data-ttu-id="c5bc1-116">**Lync server 管理シェル**   すべてのコールパークアプリケーションの構成は、Lync Server 管理シェルコマンドレットを使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="c5bc1-116">**Lync Server Management Shell**   All Call Park application configuration can be performed by using Lync Server Management Shell cmdlets.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

