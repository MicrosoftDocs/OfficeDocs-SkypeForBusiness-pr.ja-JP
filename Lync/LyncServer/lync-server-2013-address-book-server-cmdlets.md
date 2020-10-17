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
# <a name="address-book-server-cmdlets-in-lync-server-2013"></a>Lync Server 2013 のアドレス帳サーバーのコマンドレット

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-06-26_

アドレス帳サーバーは、Active Directory ドメインサービスと Microsoft Lync Server 2013 の間で中継されます。 アドレス帳サーバーによって、Lync Server 2013 に格納されているユーザー情報が Active Directory に格納されているユーザー情報と同期していることが保証されます。 この処理は、アドレス帳ファイルとユーザー データベース保存されている情報との同期を定期的に取ることで実行されます。 さらに、Lync Server には、アドレス帳サーバーを管理するためのコマンドレットが多数含まれています。

<div>

## <a name="address-book-server-cmdlets"></a>アドレス帳サーバーのコマンドレット

Lync Server コントロールパネルでアドレス帳サーバーの設定を構成することはできません。 Windows PowerShell は、これらの設定を管理するための主要なツールです。 以下は、アドレス帳サーバーの管理に直接関連するコマンドレットの一覧です。

**アドレス帳サーバー**

  - <span></span>  
    [-CsAddressBookConfiguration の取得](https://technet.microsoft.com/library/Gg398132(v=OCS.15))

  - <span></span>  
    [新しい-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398395(v=OCS.15))

  - <span></span>  
    [-CsAddressBookConfiguration の削除](https://technet.microsoft.com/library/Gg398934(v=OCS.15))

  - <span></span>  
    [設定-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg412784(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Update-csaddressbook](https://technet.microsoft.com/library/Gg398194(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [デバッグ-CsAddressBookReplication](https://technet.microsoft.com/library/JJ205232(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsAddressBookService](https://technet.microsoft.com/library/Gg398661(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsAddressBookWebQuery](https://technet.microsoft.com/library/Gg398773(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server PowerShell ブログ](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

