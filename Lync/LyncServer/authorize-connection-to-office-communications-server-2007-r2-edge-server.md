---
title: Office Communications Server 2007 R2 エッジサーバーへの接続を承認する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Authorize connection to Office Communications Server 2007 R2 Edge Server
ms:assetid: 14f6798a-28d6-4b3d-8734-942192e1bbf5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204702(v=OCS.15)
ms:contentKeyID: 48183493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a6adeaa07efea62697ecfbd38fede7d2f2191b8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181160"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="authorize-connection-to-office-communications-server-2007-r2-edge-server"></a>Office Communications Server 2007 R2 エッジサーバーへの接続を承認する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-28_

パイロットプール内の各 Lync Server 2013 フロントエンドサーバーまたは Standard Edition サーバーについては、Office Communications Server 2007 R2 エッジサーバーへの接続を承認されている内部サーバーの一覧を更新する必要があります。 更新しないと、従来のエッジ サーバーを使用して参加するユーザーに対する外部音声ビデオ (A/V) 会議が動作しません。

<div>

## <a name="to-authorize-connection-to-office-communications-server-2007-r2-edge-server"></a>Office Communications Server 2007 R2 エッジサーバーへの接続を承認するには

1.  Office Communications Server 2007 R2 エッジサーバーから、[**管理ツール**] グループから [コンピューターの**管理**] スナップインを開きます。

2.  コンソール ツリーで [**サービスとアプリケーション**] を展開します。

3.  [**Office Communications Server 2007 R2**] を右クリックし、[**プロパティ**] をクリックします。

4.  [**内部**] タブをクリックします。

5.  [**サーバーの追加**] で [**追加**] をクリックします。

6.  [**Office Communications Server の追加**] ダイアログ ボックスで、適切な情報を入力します。
    
      - 各 Lync Server 2013 フロントエンドサーバーまたは Standard Edition サーバー、および Lync Server 2013 プールの完全修飾ドメイン名 (FQDN) を指定します。
    
      - 次ホップコンピューターを FQDN で指定する静的ルートをプールに構成した場合は、Lync Server 2013 ディレクターの FQDN を指定します。

7.  各 Lync Server 2013、フロントエンドサーバー、Standard Edition サーバー、プール、およびディレクターのエントリを追加した後、[**適用**] をクリックし、[ **OK** ] をクリックして [プロパティ] ページを閉じます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

