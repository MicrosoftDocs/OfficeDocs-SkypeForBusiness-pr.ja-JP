---
title: 'Lync Server 2013: パーキング呼び出しの電話番号内線を構成する'
description: 'Lync Server 2013: パーキング呼び出しの電話番号拡張機能を構成します。'
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
ms.openlocfilehash: 6219e04243d0c19bc37251f7d113f7ebdd09fb72
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548833"
---
# <a name="configure-phone-number-extensions-for-parking-calls-in-lync-server-2013"></a><span data-ttu-id="8231d-103">Lync Server 2013 でのパーキング呼び出しの内線電話番号の構成</span><span class="sxs-lookup"><span data-stu-id="8231d-103">Configure phone number extensions for parking calls in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8231d-104">_**トピックの最終更新日:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="8231d-104">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="8231d-105">コールパークアプリケーションは、コールパークオービットテーブルの内線番号を使用して通話をパークします。</span><span class="sxs-lookup"><span data-stu-id="8231d-105">The Call Park application uses extension numbers in the Call Park orbit table to park calls.</span></span> <span data-ttu-id="8231d-106">保留呼び出しに対して組織で予約されている内線番号の範囲を使用して、コールパークオービットテーブルを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8231d-106">You need to configure the Call Park orbit table with the ranges of extension numbers that your organization reserves for parked calls.</span></span> <span data-ttu-id="8231d-107">これらの内線番号は仮想の内線番号 (つまり、ユーザーや電話が割り当てられていない内線番号) にする必要あがります。</span><span class="sxs-lookup"><span data-stu-id="8231d-107">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="8231d-108">コールパークアプリケーションが展開および構成されている各 Lync Server プールは、1つ以上のオービット範囲を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="8231d-108">Each Lync Server pool where a Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="8231d-109">オービット範囲は、Lync Server の展開間でグローバルに一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8231d-109">Orbit ranges must be globally unique across the Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8231d-110">コールパークを使用する前に、音声ポリシーの [ <STRONG>コールパークを有効</STRONG> にする] チェックボックスをオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8231d-110">You must select the <STRONG>Enable call park</STRONG> check box in your voice policy before you can use Call Park.</span></span> <span data-ttu-id="8231d-111">既定では、このオプションはオフになっています。</span><span class="sxs-lookup"><span data-stu-id="8231d-111">By default, this option is not selected.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8231d-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8231d-112">In This Section</span></span>

  - [<span data-ttu-id="8231d-113">Lync Server 2013 でのコールパークオービット範囲の作成または変更</span><span class="sxs-lookup"><span data-stu-id="8231d-113">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

  - [<span data-ttu-id="8231d-114">Lync Server 2013 でのコールパークオービット範囲の削除</span><span class="sxs-lookup"><span data-stu-id="8231d-114">Delete a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-delete-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

