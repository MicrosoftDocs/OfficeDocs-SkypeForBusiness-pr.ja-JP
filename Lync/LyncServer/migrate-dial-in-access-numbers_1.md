---
title: ダイヤルイン アクセス番号の移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate dial-in access numbers
ms:assetid: 568a94b7-a697-4ab2-9008-dc9ecc1c87c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204898(v=OCS.15)
ms:contentKeyID: 48184171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b86db6e669fd5f52827591c25e5bb237bd9ee012
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848073"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a>ダイヤルイン アクセス番号の移行

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-26_

ダイヤルインアクセス番号を移行するには、次の2つの手順を実行する必要があります。**インポート-CsLegacyConfiguration**コマンドレットを実行し ([ポリシーと設定のインポート](import-policies-and-settings.md)では既に完了しています)、ダイヤルプランとその他のダイヤルインアクセス番号の設定を移行して、 **** コンタクトオブジェクトを移行するには、CsApplicationEndpoint コマンドレットを移動します。

<div>

## <a name="to-migrate-dial-in-access-numbers"></a>ダイヤルインアクセス番号を移行するには

1.  Office Communications Server 2007 R2 管理ツールを開きます。

2.  コンソールツリーで、[フォレスト] ノードを右クリックし、[**プロパティ**] をクリックして、[**会議アテンダントのプロパティ**] をクリックします。

3.  [**アクセス電話番号**] タブで、[**プールごとのサービス**] をクリックして、アクセス電話番号を関連付けられたプールで並べ替え、移行元のプールのすべてのアクセス番号を特定します。

4.  各アクセス番号の SIP URI を確認するには、アクセス番号をダブルクリックして [**会議アテンダント番号の編集**] ダイアログボックスを開き、[ **sip uri**] を確認します。

5.  Lync Server 管理シェルを開きます。

6.  各ダイヤルインアクセス番号を Lync Server 2013 でホストされているプールに移動するには、次を実行します。
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

7.  Office Communications Server 2007 R2 管理ツールの [**アクセス電話番号**] タブで、移行元の Office Communications Server 2007 R2 プールのダイヤルインアクセス番号が残っていないことを確認します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

