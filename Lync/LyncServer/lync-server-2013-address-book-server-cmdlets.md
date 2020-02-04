---
title: 'Lync Server 2013: アドレス帳サーバーコマンドレット'
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
ms.openlocfilehash: 5117b7a17d607ec995df371fd0cd80fd7c05aeab
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737997"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="address-book-server-cmdlets-in-lync-server-2013"></a><span data-ttu-id="2ffac-102">Lync Server 2013 のアドレス帳サーバーコマンドレット</span><span class="sxs-lookup"><span data-stu-id="2ffac-102">Address Book Server cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ffac-103">_**トピックの最終更新日:** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="2ffac-103">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="2ffac-104">アドレス帳サーバーは、Active Directory ドメインサービスと Microsoft Lync Server 2013 との間で中継されています。</span><span class="sxs-lookup"><span data-stu-id="2ffac-104">Address Book servers are intermediaries between Active Directory Domain Services and Microsoft Lync Server 2013.</span></span> <span data-ttu-id="2ffac-105">アドレス帳サーバーによって、Lync Server 2013 に保存されているユーザー情報が Active Directory に保存されているユーザー情報と同期していることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="2ffac-105">The Address Book server ensures that the user information stored in Lync Server 2013 is in synch with the user information stored in Active Directory.</span></span> <span data-ttu-id="2ffac-106">これは、ユーザーデータベースに保存されている情報を使用して、定期的にアドレス帳ファイルを同期することによって行われます。</span><span class="sxs-lookup"><span data-stu-id="2ffac-106">This is done by periodically synching Address Book files with information stored in the User database.</span></span> <span data-ttu-id="2ffac-107">さらに、Lync Server には、アドレス帳サーバーを管理するための多数のコマンドレットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="2ffac-107">In turn, Lync Server includes a number of cmdlets for managing Address Book servers.</span></span>

<div>

## <a name="address-book-server-cmdlets"></a><span data-ttu-id="2ffac-108">アドレス帳サーバーのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="2ffac-108">Address Book Server Cmdlets</span></span>

<span data-ttu-id="2ffac-109">Lync Server コントロールパネルで、アドレス帳のサーバー設定を構成することはできません。</span><span class="sxs-lookup"><span data-stu-id="2ffac-109">You cannot configure the Address Book Server settings in Lync Server Control Panel.</span></span> <span data-ttu-id="2ffac-110">Windows PowerShell は、これらの設定を管理するための主要なツールです。</span><span class="sxs-lookup"><span data-stu-id="2ffac-110">Windows PowerShell is the primary tool for managing these settings.</span></span> <span data-ttu-id="2ffac-111">アドレス帳サーバーの管理に直接関連するコマンドレットの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2ffac-111">The following is a list of cmdlets that relate directly to managing the Address Book Server:</span></span>

<span data-ttu-id="2ffac-112">**アドレス帳サーバー**</span><span class="sxs-lookup"><span data-stu-id="2ffac-112">**Address Book Server**</span></span>

  - <span></span>  
    <span data-ttu-id="2ffac-113">[CsAddressBookConfiguration の入手](https://technet.microsoft.com/en-us/library/Gg398132(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2ffac-113">[Get-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398132(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2ffac-114">[New-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398395(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2ffac-114">[New-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398395(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2ffac-115">[CsAddressBookConfiguration の削除](https://technet.microsoft.com/en-us/library/Gg398934(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2ffac-115">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398934(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2ffac-116">[Set-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg412784(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2ffac-116">[Set-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg412784(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2ffac-117">[更新-CsAddressBook](https://technet.microsoft.com/en-us/library/Gg398194(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2ffac-117">[Update-CsAddressBook](https://technet.microsoft.com/en-us/library/Gg398194(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2ffac-118">[Debug-CsAddressBookReplication](https://technet.microsoft.com/en-us/library/JJ205232(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2ffac-118">[Debug-CsAddressBookReplication](https://technet.microsoft.com/en-us/library/JJ205232(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2ffac-119">[Test-CsAddressBookService](https://technet.microsoft.com/en-us/library/Gg398661(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2ffac-119">[Test-CsAddressBookService](https://technet.microsoft.com/en-us/library/Gg398661(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2ffac-120">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/en-us/library/Gg398773(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2ffac-120">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/en-us/library/Gg398773(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2ffac-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="2ffac-121">See Also</span></span>


[<span data-ttu-id="2ffac-122">Lync Server PowerShell ブログ</span><span class="sxs-lookup"><span data-stu-id="2ffac-122">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

