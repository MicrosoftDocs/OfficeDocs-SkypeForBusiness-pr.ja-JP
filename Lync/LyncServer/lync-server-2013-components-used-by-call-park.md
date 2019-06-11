---
title: 'Lync Server 2013: コール パークで使用されるコンポーネント'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components used by Call Park
ms:assetid: c7ffbee3-0ce1-48c0-bb56-af098b41d6d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398824(v=OCS.15)
ms:contentKeyID: 48185374
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64f74161230504ee3f24ed19780e0a62ad4e7d08
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840507"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-call-park-in-lync-server-2013"></a><span data-ttu-id="20f82-102">Lync Server 2013 のコール パークで使用されるコンポーネント</span><span class="sxs-lookup"><span data-stu-id="20f82-102">Components used by Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20f82-103">_**最終更新日:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="20f82-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="20f82-104">エンタープライズ Voip を展開すると、コールパークアプリケーションが自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="20f82-104">The Call Park application is automatically installed when you deploy Enterprise Voice.</span></span> <span data-ttu-id="20f82-105">音声ポリシーを構成して、コールパークを有効にします。</span><span class="sxs-lookup"><span data-stu-id="20f82-105">You enable Call Park by configuring voice policy.</span></span> <span data-ttu-id="20f82-106">次の Lync Server 2013 コンポーネントは、コールパークアプリケーションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="20f82-106">The following Lync Server 2013 components support the Call Park application:</span></span>

  - <span data-ttu-id="20f82-107">**アプリケーションサービス**   アプリケーションサービスは、コールパークアプリケーションなどのユニファイドコミュニケーションアプリケーションを展開、ホスティング、および管理するためのプラットフォームを提供します。</span><span class="sxs-lookup"><span data-stu-id="20f82-107">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications, such as the Call Park application.</span></span> <span data-ttu-id="20f82-108">アプリケーションサービスは、フロントエンドプールのすべてのフロントエンドサーバーと、すべての Standard Edition サーバーに自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="20f82-108">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="20f82-109">**コールパーク**   アプリケーションは、アプリケーションサービスによってホストされるユニファイドコミュニケーションアプリケーションの1つです。</span><span class="sxs-lookup"><span data-stu-id="20f82-109">**Call Park application**   The Call Park application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="20f82-110">エンタープライズボイスの展開時に自動的に含まれます。</span><span class="sxs-lookup"><span data-stu-id="20f82-110">It is included automatically when you deploy Enterprise Voice.</span></span> <span data-ttu-id="20f82-111">[パークパーク] を選び、通話を取得して、通話パークの orbits を管理します。</span><span class="sxs-lookup"><span data-stu-id="20f82-111">Call Park parks and retrieves calls and manages call park orbits.</span></span>

  - <span data-ttu-id="20f82-112">**音楽-保留-ファイル**   音楽が有効になっている場合は、通話の保留中に音楽ファイルが再生されます。</span><span class="sxs-lookup"><span data-stu-id="20f82-112">**Music-on hold-file**   If music in enabled, the music file is played while a call is parked.</span></span> <span data-ttu-id="20f82-113">既定の音楽ファイルは、コールパークアプリケーションがインストールされているときに含まれます。</span><span class="sxs-lookup"><span data-stu-id="20f82-113">A default music file is included when the Call Park application is installed.</span></span>

  - <span data-ttu-id="20f82-114">**ファイルストア**   コールパークアプリケーションは、カスタムオーディオファイルを保持するためにファイルストアを使用します。</span><span class="sxs-lookup"><span data-stu-id="20f82-114">**File Store**   The Call Park application uses File Store to hold custom audio files.</span></span>

  - <span data-ttu-id="20f82-115">**Lync server コントロールパネル**   lync server コントロールパネルを使用すると、通話パークの軌道の表を構成し、ユーザーに対してコールパークを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="20f82-115">**Lync Server Control Panel**   You can use Lync Server Control Panel to configure the call park orbit table and to enable Call Park for users.</span></span>

  - <span data-ttu-id="20f82-116">**Lync server 管理シェル**   すべてのコールパークアプリケーション構成は、lync Server 管理シェルコマンドレットを使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="20f82-116">**Lync Server Management Shell**   All Call Park application configuration can be performed by using Lync Server Management Shell cmdlets.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

