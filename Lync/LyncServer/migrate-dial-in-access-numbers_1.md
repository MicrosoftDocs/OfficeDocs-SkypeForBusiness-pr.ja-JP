---
title: ダイヤルイン アクセス番号を移行する
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate dial-in access numbers
ms:assetid: 568a94b7-a697-4ab2-9008-dc9ecc1c87c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204898(v=OCS.15)
ms:contentKeyID: 48184171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc96ef027d63c5d2020bd52d55f378fcf7dacf51
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503524"
---
# <a name="migrate-dial-in-access-numbers"></a>ダイヤルイン アクセス番号を移行する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-26_

ダイヤルインアクセス番号を移行するには、次の 2[つの手順](import-policies-and-settings.md)を実行する必要があります。 **import-cslegacyconfiguration**コマンドレットを実行して、ダイヤルプランおよびその他のダイヤルインアクセス番号の設定を移行し、**移動-csapplicationendpoint**コマンドレットを実行して連絡先オブジェクトを移行します。

<div>

## <a name="to-migrate-dial-in-access-numbers"></a>ダイヤルイン アクセス番号を移行するには

1.  Office Communications Server 2007 R2 管理ツールを開きます。

2.  コンソール ツリーでフォレスト ノードを右クリックし、[**プロパティ**]、[**会議アテンダントのプロパティ**] の順にクリックします。

3.  [**アクセスの電話番号**] タブで、[**プールによるサービス提供**] をクリックして、関連するプールでアクセスの電話番号を並べ替え、移行元のプールのすべてのアクセス番号を識別します。

4.  各アクセス番号の SIP URI を識別するには、アクセス番号をダブルクリックして [**会議アテンダント番号の編集**] ダイアログ ボックスを開き、[**SIP URI**] を探します。

5.  Lync Server 管理シェルを開きます。

6.  Lync Server 2013 でホストされているプールに各ダイヤルインアクセス番号を移動するには、次を実行します。
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

7.  Office Communications Server 2007 R2 管理ツールの [ **アクセスの電話番号** ] タブで、移行元の Office communications Server 2007 R2 プールのダイヤルインアクセス番号が残っていないことを確認します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

