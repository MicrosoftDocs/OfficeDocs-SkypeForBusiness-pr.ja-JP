---
title: 'Lync Server 2013: コールパークの構成'
description: 'Lync Server 2013: コールパークの構成。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Call Park
ms:assetid: e4c5da53-7f6c-4535-bc9b-9da2026caec8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399014(v=OCS.15)
ms:contentKeyID: 48185732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d2708f26fae5706afc31aa195b9fdb82536247b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568753"
---
# <a name="configuring-call-park-in-lync-server-2013"></a><span data-ttu-id="ce3e2-103">Lync Server 2013 でのコールパークの構成</span><span class="sxs-lookup"><span data-stu-id="ce3e2-103">Configuring Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce3e2-104">_**トピックの最終更新日:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="ce3e2-104">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="ce3e2-105">コールパークを使用すると、エンタープライズ Voip ユーザーは1つの電話から通話を保留にした後、電話から電話をかけて (コールパーク *オービット*として知られている) 内部番号をダイヤルすることにより、後で通話を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="ce3e2-105">Call Park enables an Enterprise Voice user to put a call on hold from one telephone and then retrieve the call later by dialing an internal number (known as a Call Park *orbit*) from any telephone.</span></span>

<span data-ttu-id="ce3e2-106">エンタープライズ Voip を展開する場合、コールパークが使用するコンポーネントは、フロントエンドサーバーまたは Standard Edition サーバーに自動的にインストールされ、有効になります。</span><span class="sxs-lookup"><span data-stu-id="ce3e2-106">The components that Call Park uses are automatically installed and enabled on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="ce3e2-107">ただし、ユーザーが使用できるようにするには、コールパークを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce3e2-107">However, you must configure Call Park before it is available to users.</span></span>

<span data-ttu-id="ce3e2-108">このセクションでは、コールパークの構成について説明します。</span><span class="sxs-lookup"><span data-stu-id="ce3e2-108">This section guides you through the configuration of Call Park.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ce3e2-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ce3e2-109">In This Section</span></span>

  - [<span data-ttu-id="ce3e2-110">Lync Server 2013 のコールパーク構成の前提条件とユーザー権限</span><span class="sxs-lookup"><span data-stu-id="ce3e2-110">Call Park configuration prerequisites and user rights in Lync Server 2013</span></span>](lync-server-2013-call-park-configuration-prerequisites-and-user-rights.md)

  - [<span data-ttu-id="ce3e2-111">Lync Server 2013 でのコールパークの展開プロセス</span><span class="sxs-lookup"><span data-stu-id="ce3e2-111">Deployment process for Call Park in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-call-park.md)

  - [<span data-ttu-id="ce3e2-112">Lync Server 2013 でコールパークオービットテーブルを構成する</span><span class="sxs-lookup"><span data-stu-id="ce3e2-112">Configure the Call Park orbit table in Lync Server 2013</span></span>](lync-server-2013-configure-the-call-park-orbit-table.md)

  - [<span data-ttu-id="ce3e2-113">Lync Server 2013 でコールパーク設定を構成する</span><span class="sxs-lookup"><span data-stu-id="ce3e2-113">Configure Call Park settings in Lync Server 2013</span></span>](lync-server-2013-configure-call-park-settings.md)

  - [<span data-ttu-id="ce3e2-114">Lync Server 2013 でコールパーク保留音をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="ce3e2-114">Customize Call Park music on hold in Lync Server 2013</span></span>](lync-server-2013-customize-call-park-music-on-hold.md)

  - [<span data-ttu-id="ce3e2-115">Lync Server 2013 でユーザーのコールパークを有効にする</span><span class="sxs-lookup"><span data-stu-id="ce3e2-115">Enable Call Park for users in Lync Server 2013</span></span>](lync-server-2013-enable-call-park-for-users.md)

  - [<span data-ttu-id="ce3e2-116">Lync Server 2013 でのコールパークの正規化ルールの確認</span><span class="sxs-lookup"><span data-stu-id="ce3e2-116">Verify normalization rules for Call Park in Lync Server 2013</span></span>](lync-server-2013-verify-normalization-rules-for-call-park.md)

  - [<span data-ttu-id="ce3e2-117">オプションLync Server 2013 でのコールパーク展開の確認</span><span class="sxs-lookup"><span data-stu-id="ce3e2-117">(Optional) Verify Call Park deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-call-park-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

