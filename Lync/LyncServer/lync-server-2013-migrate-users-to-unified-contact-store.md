---
title: 'Lync Server 2013: ユーザーを統合連絡先ストアに移行する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migrate users to unified contact store
ms:assetid: 215a8ec1-d63e-4fdf-b73d-75aeb9dddb43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204737(v=OCS.15)
ms:contentKeyID: 48183600
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09897effe252f49eda73fea567d9b54bdc8ad52a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149677"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-users-to-unified-contact-store-in-lync-server-2013"></a>Lync Server 2013 でユーザーを統合連絡先ストアに移行する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-15_

次の場合、ユーザーの連絡先は Exchange 2013 サーバーに自動的に移行されます。

  - UcsAllowed が True に設定されたユーザー サービス ポリシーがユーザーに割り当てられている場合。

  - Exchange 2013 メールボックスでプロビジョニングされ、少なくとも1回はメールボックスにサインインしています。

  - Lync 2013 リッチクライアントを使用してログインします。

ユーザーが Lync 2010 またはそれ以前のクライアントを使用してログインしている場合、またはユーザーが Exchange 2013 サーバーに接続されていない場合、ユーザーサービスポリシーは無視され、ユーザーの連絡先は Lync Server に残ります。

ユーザーの連絡先が移行されているかどうかは、次のどちらかの方法で確認できます。

  - クライアント コンピューターで次のレジストリ キーを調べます。
    
    HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\\<SIP URL\>\\UCS
    
    ユーザーの連絡先が Exchange 2013 に格納されている場合、このキーには2165という値を持つ InUCSMode の値が含まれます。

  - **Test-CsUnifiedContactStore** コマンドレットを実行します。 Lync Server 管理シェルコマンドラインで、次のように入力します。
    
        Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
    
    **Test-CsUnifiedContactStore** が成功した場合は、ユーザーの連絡先が統合連絡先ストアに移行されています。

</div>

<span> </span>

</div>

</div>

</div>

