---
title: 'Lync Server 2013: パーキング呼び出しの電話番号内線を構成する'
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
ms.openlocfilehash: 97a8871454ed95b955558c441d567f68dd0974bd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520434"
---
# <a name="configure-phone-number-extensions-for-parking-calls-in-lync-server-2013"></a><span data-ttu-id="01074-102">Lync Server 2013 でのパーキング呼び出しの内線電話番号の構成</span><span class="sxs-lookup"><span data-stu-id="01074-102">Configure phone number extensions for parking calls in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01074-103">_**トピックの最終更新日:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="01074-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="01074-104">コールパークアプリケーションは、コールパークオービットテーブルの内線番号を使用して通話をパークします。</span><span class="sxs-lookup"><span data-stu-id="01074-104">The Call Park application uses extension numbers in the Call Park orbit table to park calls.</span></span> <span data-ttu-id="01074-105">保留呼び出しに対して組織で予約されている内線番号の範囲を使用して、コールパークオービットテーブルを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01074-105">You need to configure the Call Park orbit table with the ranges of extension numbers that your organization reserves for parked calls.</span></span> <span data-ttu-id="01074-106">これらの内線番号は仮想の内線番号 (つまり、ユーザーや電話が割り当てられていない内線番号) にする必要あがります。</span><span class="sxs-lookup"><span data-stu-id="01074-106">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="01074-107">コールパークアプリケーションが展開および構成されている各 Lync Server プールは、1つ以上のオービット範囲を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="01074-107">Each Lync Server pool where a Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="01074-108">オービット範囲は、Lync Server の展開間でグローバルに一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="01074-108">Orbit ranges must be globally unique across the Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="01074-109">コールパークを使用する前に、音声ポリシーの [ <STRONG>コールパークを有効</STRONG> にする] チェックボックスをオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="01074-109">You must select the <STRONG>Enable call park</STRONG> check box in your voice policy before you can use Call Park.</span></span> <span data-ttu-id="01074-110">既定では、このオプションはオフになっています。</span><span class="sxs-lookup"><span data-stu-id="01074-110">By default, this option is not selected.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="01074-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="01074-111">In This Section</span></span>

  - [<span data-ttu-id="01074-112">Lync Server 2013 でのコールパークオービット範囲の作成または変更</span><span class="sxs-lookup"><span data-stu-id="01074-112">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

  - [<span data-ttu-id="01074-113">Lync Server 2013 でのコールパークオービット範囲の削除</span><span class="sxs-lookup"><span data-stu-id="01074-113">Delete a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-delete-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

