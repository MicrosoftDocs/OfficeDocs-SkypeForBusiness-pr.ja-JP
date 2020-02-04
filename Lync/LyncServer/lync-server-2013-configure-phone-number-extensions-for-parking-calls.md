---
title: 'Lync Server 2013: パーキング通話用に電話番号の内線番号を構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure phone number extensions for parking calls
ms:assetid: fbf97624-9587-42a6-b276-1b69c574a74d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182611(v=OCS.15)
ms:contentKeyID: 48185980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba64f4f622a6f9ae9e134b2447abe21bc99ec62c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762825"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-phone-number-extensions-for-parking-calls-in-lync-server-2013"></a><span data-ttu-id="68c82-102">Lync Server 2013 でのパーキング通話用の電話番号の内線番号を構成する</span><span class="sxs-lookup"><span data-stu-id="68c82-102">Configure phone number extensions for parking calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68c82-103">_**最終更新日:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="68c82-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="68c82-104">コールパークアプリケーションでは、通話のパークをパークするために、コールパーク軌道の内線番号が使用されます。</span><span class="sxs-lookup"><span data-stu-id="68c82-104">The Call Park application uses extension numbers in the Call Park orbit table to park calls.</span></span> <span data-ttu-id="68c82-105">保留中の通話については、組織で予約されている内線番号の範囲を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68c82-105">You need to configure the Call Park orbit table with the ranges of extension numbers that your organization reserves for parked calls.</span></span> <span data-ttu-id="68c82-106">これらの内線番号は、仮想の内線番号 (つまり、ユーザーや電話が割り当てられていない内線番号) にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="68c82-106">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="68c82-107">コールパークアプリケーションが展開され構成されている各 Lync サーバープールは、1つ以上の軌道範囲を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="68c82-107">Each Lync Server pool where a Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="68c82-108">オービット範囲は、Lync Server 展開でグローバルに一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="68c82-108">Orbit ranges must be globally unique across the Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="68c82-109">通話パークを使用する前に、音声ポリシーの [<STRONG>通話パークを有効</STRONG>にする] チェックボックスをオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="68c82-109">You must select the <STRONG>Enable call park</STRONG> check box in your voice policy before you can use Call Park.</span></span> <span data-ttu-id="68c82-110">既定では、このオプションは選択されていません。</span><span class="sxs-lookup"><span data-stu-id="68c82-110">By default, this option is not selected.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="68c82-111">このセクション中</span><span class="sxs-lookup"><span data-stu-id="68c82-111">In This Section</span></span>

  - [<span data-ttu-id="68c82-112">通話パークの作成または変更 Lync Server 2013 の範囲の軌道</span><span class="sxs-lookup"><span data-stu-id="68c82-112">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

  - [<span data-ttu-id="68c82-113">Lync Server 2013 でのコールパークの範囲の削除</span><span class="sxs-lookup"><span data-stu-id="68c82-113">Delete a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-delete-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

