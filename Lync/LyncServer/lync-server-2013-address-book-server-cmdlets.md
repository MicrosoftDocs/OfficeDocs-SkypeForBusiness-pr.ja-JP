---
title: 'Lync Server 2013: アドレス帳サーバーのコマンドレット'
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
ms.openlocfilehash: 91a4953edf97d45cb29038ed8803917fe62a076c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521184"
---
# <a name="address-book-server-cmdlets-in-lync-server-2013"></a><span data-ttu-id="33c53-102">Lync Server 2013 のアドレス帳サーバーのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="33c53-102">Address Book Server cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33c53-103">_**トピックの最終更新日:** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="33c53-103">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="33c53-104">アドレス帳サーバーは、Active Directory ドメインサービスと Microsoft Lync Server 2013 の間で中継されます。</span><span class="sxs-lookup"><span data-stu-id="33c53-104">Address Book servers are intermediaries between Active Directory Domain Services and Microsoft Lync Server 2013.</span></span> <span data-ttu-id="33c53-105">アドレス帳サーバーによって、Lync Server 2013 に格納されているユーザー情報が Active Directory に格納されているユーザー情報と同期していることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="33c53-105">The Address Book server ensures that the user information stored in Lync Server 2013 is in synch with the user information stored in Active Directory.</span></span> <span data-ttu-id="33c53-106">この処理は、アドレス帳ファイルとユーザー データベース保存されている情報との同期を定期的に取ることで実行されます。</span><span class="sxs-lookup"><span data-stu-id="33c53-106">This is done by periodically synching Address Book files with information stored in the User database.</span></span> <span data-ttu-id="33c53-107">さらに、Lync Server には、アドレス帳サーバーを管理するためのコマンドレットが多数含まれています。</span><span class="sxs-lookup"><span data-stu-id="33c53-107">In turn, Lync Server includes a number of cmdlets for managing Address Book servers.</span></span>

<div>

## <a name="address-book-server-cmdlets"></a><span data-ttu-id="33c53-108">アドレス帳サーバーのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="33c53-108">Address Book Server Cmdlets</span></span>

<span data-ttu-id="33c53-109">Lync Server コントロールパネルでアドレス帳サーバーの設定を構成することはできません。</span><span class="sxs-lookup"><span data-stu-id="33c53-109">You cannot configure the Address Book Server settings in Lync Server Control Panel.</span></span> <span data-ttu-id="33c53-110">Windows PowerShell は、これらの設定を管理するための主要なツールです。</span><span class="sxs-lookup"><span data-stu-id="33c53-110">Windows PowerShell is the primary tool for managing these settings.</span></span> <span data-ttu-id="33c53-111">以下は、アドレス帳サーバーの管理に直接関連するコマンドレットの一覧です。</span><span class="sxs-lookup"><span data-stu-id="33c53-111">The following is a list of cmdlets that relate directly to managing the Address Book Server:</span></span>

<span data-ttu-id="33c53-112">**アドレス帳サーバー**</span><span class="sxs-lookup"><span data-stu-id="33c53-112">**Address Book Server**</span></span>

  - <span></span>  
    <span data-ttu-id="33c53-113">[-CsAddressBookConfiguration の取得](https://technet.microsoft.com/library/Gg398132(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="33c53-113">[Get-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398132(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="33c53-114">[新しい-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398395(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="33c53-114">[New-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398395(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="33c53-115">[-CsAddressBookConfiguration の削除](https://technet.microsoft.com/library/Gg398934(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="33c53-115">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398934(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="33c53-116">[設定-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg412784(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="33c53-116">[Set-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg412784(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="33c53-117">[Update-csaddressbook](https://technet.microsoft.com/library/Gg398194(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="33c53-117">[Update-CsAddressBook](https://technet.microsoft.com/library/Gg398194(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="33c53-118">[デバッグ-CsAddressBookReplication](https://technet.microsoft.com/library/JJ205232(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="33c53-118">[Debug-CsAddressBookReplication](https://technet.microsoft.com/library/JJ205232(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="33c53-119">[Test-CsAddressBookService](https://technet.microsoft.com/library/Gg398661(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="33c53-119">[Test-CsAddressBookService](https://technet.microsoft.com/library/Gg398661(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="33c53-120">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/library/Gg398773(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="33c53-120">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/library/Gg398773(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="33c53-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="33c53-121">See Also</span></span>


[<span data-ttu-id="33c53-122">Lync Server PowerShell ブログ</span><span class="sxs-lookup"><span data-stu-id="33c53-122">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

