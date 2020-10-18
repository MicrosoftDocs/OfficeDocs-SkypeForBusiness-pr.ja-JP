---
title: 共通領域電話の移行
description: 共通領域電話を移行します。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Common Area Phones
ms:assetid: 31bd26fc-861b-45c6-8221-18df16e575de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688015(v=OCS.15)
ms:contentKeyID: 49733604
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b8df4d94a3db3274df7e4e82ed2185c3626de12
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579353"
---
# <a name="migrate-common-area-phones"></a><span data-ttu-id="8b64a-103">共通領域電話の移行</span><span class="sxs-lookup"><span data-stu-id="8b64a-103">Migrate Common Area Phones</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b64a-104">_**トピックの最終更新日:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="8b64a-104">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="8b64a-105">共通領域電話は、ロビー、調理場、または工場の作業場のような、共有ワークスペースまたは共用エリアによく設置されている IP 電話です。</span><span class="sxs-lookup"><span data-stu-id="8b64a-105">Common Area Phones are IP phones that most often reside in a shared workspace or common area, like a lobby, kitchen, or factory floor.</span></span> <span data-ttu-id="8b64a-106">一般的なエリア電話は、Lync Server の UC 機能を提供するためにコンピューターに接続する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8b64a-106">Common Area Phones do not need to be connected to a computer to provide Lync Server UC functionality.</span></span> <span data-ttu-id="8b64a-107">Lync server 2010 の展開を Lync Server 2013 に移行した後、従来の共通領域電話に関連付けられている連絡先オブジェクトも移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b64a-107">After migrating an Lync Server 2010 deployment to Lync Server 2013, you must also migrate the contact objects associated with the legacy Common Area Phone.</span></span> <span data-ttu-id="8b64a-108">Lync Server 管理シェルを使用して、まず、Lync Server 2010 共通領域電話に関連付けられているすべての連絡先オブジェクトを取得し、そのオブジェクトを Lync Server 2013 プールに移動します。</span><span class="sxs-lookup"><span data-stu-id="8b64a-108">Using Lync Server Management Shell you will first retrieve all contact objects associated with the Lync Server 2010 Common Area Phones, and then move those objects to the Lync Server 2013 pool.</span></span>

<span data-ttu-id="8b64a-109">**共通領域電話の移行**</span><span class="sxs-lookup"><span data-stu-id="8b64a-109">**Migrate Common Area Phones**</span></span>

1.  <span data-ttu-id="8b64a-110">Lync Server 2013 フロントエンドサーバーから、Lync Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="8b64a-110">From the Lync Server 2013 Front End server, open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="8b64a-111">コマンド ラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="8b64a-111">From the command line, type the following:</span></span>
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net

3.  <span data-ttu-id="8b64a-112">すべての連絡先オブジェクトが Lync Server 2013 プールに移動されたことを確認するには、Lync Server 管理シェルから次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="8b64a-112">To verify all contact objects have been moved to the Lync Server 2013 pool, from the Lync Server Management Shell type the following:</span></span>
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
    
    <span data-ttu-id="8b64a-113">すべての連絡先オブジェクトが Lync Server 2013 プールに関連付けられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8b64a-113">Verify all contact objects are now associated with the Lync Server 2013 pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

