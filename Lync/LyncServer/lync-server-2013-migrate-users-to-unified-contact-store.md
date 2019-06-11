---
title: 'Lync Server 2013: 統合連絡先ストアへのユーザーの移行'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Migrate users to unified contact store
ms:assetid: 215a8ec1-d63e-4fdf-b73d-75aeb9dddb43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204737(v=OCS.15)
ms:contentKeyID: 48183600
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd0ec64192f1aa83eb9c076976c20a9e87ab9115
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827215"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-users-to-unified-contact-store-in-lync-server-2013"></a>Lync Server 2013 での統合連絡先ストアへのユーザーの移行

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-15_

ユーザーの連絡先は、ユーザーが次のように Exchange 2013 サーバーに自動的に移行されます。

  - UcsAllowed が True に設定されたユーザー サービス ポリシーがユーザーに割り当てられている場合。

  - は Exchange 2013 メールボックスでプロビジョニングされ、少なくとも1回はメールボックスにサインインしています。

  - Lync 2013 リッチクライアントを使用してログインします。

ユーザーが Lync 2010 以前のクライアントでログインしている場合、またはユーザーが Exchange 2013 サーバーに接続されていない場合、ユーザーサービスポリシーは無視され、ユーザーの連絡先は Lync Server に残ります。

ユーザーの連絡先が移行されているかどうかは、次のいずれかの方法で確認できます。

  - クライアント コンピューターで次のレジストリ キーを調べます。
    
    HKEY\_現在\_の\\ユーザー\\ソフトウェア\\Microsoft\\Office\\15.0\\\<Lync SIP\>\\URL UCS
    
    ユーザーの連絡先が Exchange 2013 に保存されている場合、このキーには2165の値を持つ InUCSMode の値が格納されます。

  - **Test-CsUnifiedContactStore** コマンドレットを実行します。 Lync Server 管理シェルコマンドラインで、次のように入力します。
    
        Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
    
    **Test-CsUnifiedContactStore** が成功した場合は、ユーザーの連絡先が統合連絡先ストアに移行されています。

</div>

<span> </span>

</div>

</div>

</div>

