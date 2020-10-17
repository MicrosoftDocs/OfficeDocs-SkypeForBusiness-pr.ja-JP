---
title: 'Lync Server 2013: アドレス帳サーバーのコマンドレット'
description: 'Lync Server 2013: アドレス帳サーバーのコマンドレット。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Address Book Server cmdlets
ms:assetid: 33da45da-3c57-4d04-9679-f0e5a0cfd37e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415643(v=OCS.15)
ms:contentKeyID: 48183793
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4fef903d25f0d2707410e017f4eb280282bbdab
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553033"
---
# <a name="address-book-server-cmdlets-in-lync-server-2013"></a><span data-ttu-id="01f14-103">Lync Server 2013 のアドレス帳サーバーのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="01f14-103">Address Book Server cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01f14-104">_**トピックの最終更新日:** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="01f14-104">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="01f14-105">アドレス帳サーバーは、Active Directory ドメインサービスと Microsoft Lync Server 2013 の間で中継されます。</span><span class="sxs-lookup"><span data-stu-id="01f14-105">Address Book servers are intermediaries between Active Directory Domain Services and Microsoft Lync Server 2013.</span></span> <span data-ttu-id="01f14-106">アドレス帳サーバーによって、Lync Server 2013 に格納されているユーザー情報が Active Directory に格納されているユーザー情報と同期していることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="01f14-106">The Address Book server ensures that the user information stored in Lync Server 2013 is in synch with the user information stored in Active Directory.</span></span> <span data-ttu-id="01f14-107">この処理は、アドレス帳ファイルとユーザー データベース保存されている情報との同期を定期的に取ることで実行されます。</span><span class="sxs-lookup"><span data-stu-id="01f14-107">This is done by periodically synching Address Book files with information stored in the User database.</span></span> <span data-ttu-id="01f14-108">さらに、Lync Server には、アドレス帳サーバーを管理するためのコマンドレットが多数含まれています。</span><span class="sxs-lookup"><span data-stu-id="01f14-108">In turn, Lync Server includes a number of cmdlets for managing Address Book servers.</span></span>

<div>

## <a name="address-book-server-cmdlets"></a><span data-ttu-id="01f14-109">アドレス帳サーバーのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="01f14-109">Address Book Server Cmdlets</span></span>

<span data-ttu-id="01f14-110">Lync Server コントロールパネルでアドレス帳サーバーの設定を構成することはできません。</span><span class="sxs-lookup"><span data-stu-id="01f14-110">You cannot configure the Address Book Server settings in Lync Server Control Panel.</span></span> <span data-ttu-id="01f14-111">Windows PowerShell は、これらの設定を管理するための主要なツールです。</span><span class="sxs-lookup"><span data-stu-id="01f14-111">Windows PowerShell is the primary tool for managing these settings.</span></span> <span data-ttu-id="01f14-112">以下は、アドレス帳サーバーの管理に直接関連するコマンドレットの一覧です。</span><span class="sxs-lookup"><span data-stu-id="01f14-112">The following is a list of cmdlets that relate directly to managing the Address Book Server:</span></span>

<span data-ttu-id="01f14-113">**アドレス帳サーバー**</span><span class="sxs-lookup"><span data-stu-id="01f14-113">**Address Book Server**</span></span>

  - <span></span>  
    <span data-ttu-id="01f14-114">[-CsAddressBookConfiguration の取得](https://technet.microsoft.com/library/Gg398132(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="01f14-114">[Get-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398132(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="01f14-115">[新しい-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398395(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="01f14-115">[New-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398395(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="01f14-116">[-CsAddressBookConfiguration の削除](https://technet.microsoft.com/library/Gg398934(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="01f14-116">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398934(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="01f14-117">[設定-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg412784(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="01f14-117">[Set-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg412784(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="01f14-118">[Update-csaddressbook](https://technet.microsoft.com/library/Gg398194(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="01f14-118">[Update-CsAddressBook](https://technet.microsoft.com/library/Gg398194(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="01f14-119">[デバッグ-CsAddressBookReplication](https://technet.microsoft.com/library/JJ205232(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="01f14-119">[Debug-CsAddressBookReplication](https://technet.microsoft.com/library/JJ205232(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="01f14-120">[Test-CsAddressBookService](https://technet.microsoft.com/library/Gg398661(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="01f14-120">[Test-CsAddressBookService](https://technet.microsoft.com/library/Gg398661(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="01f14-121">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/library/Gg398773(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="01f14-121">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/library/Gg398773(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="01f14-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="01f14-122">See Also</span></span>


[<span data-ttu-id="01f14-123">Lync Server PowerShell ブログ</span><span class="sxs-lookup"><span data-stu-id="01f14-123">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

