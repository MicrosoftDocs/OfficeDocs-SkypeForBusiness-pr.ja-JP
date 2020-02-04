---
title: Office Communications Server 2007 R2 Edge サーバーへの接続を承認する
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
ms.openlocfilehash: 8dbce32a12f05dff768d23a2bdccfe1b84a567cb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724217"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="authorize-connection-to-office-communications-server-2007-r2-edge-server"></a>Office Communications Server 2007 R2 Edge サーバーへの接続を承認する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-28_

パイロットプールの各 Lync Server 2013 フロントエンドサーバーまたは Standard Edition サーバーの場合、Office Communications Server 2007 R2 Edge Server への接続が許可されている内部サーバーの一覧を更新する必要があります。 これらの更新プログラムがないと、従来のエッジサーバーを使用して参加しているユーザーの外部オーディオ/ビジュアル (A/V) 会議が機能しなくなります。

<div>

## <a name="to-authorize-connection-to-office-communications-server-2007-r2-edge-server"></a>Office Communications Server 2007 R2 Edge サーバーへの接続を承認するには

1.  Office Communications Server 2007 R2 Edge サーバーから、[**管理ツール**] グループから [コンピューターの**管理**] スナップインを開きます。

2.  コンソールツリーで、[**サービスとアプリケーション**] を展開します。

3.  **Office Communications Server 2007 R2**を右クリックし、[**プロパティ**] をクリックします。

4.  [**内部**] タブをクリックします。

5.  [**サーバーの追加**] の [**追加**] をクリックします。

6.  [ **Office Communications Server の追加**] ダイアログボックスで、必要な情報を入力します。
    
      - 各 Lync Server 2013 フロントエンドサーバーまたは標準エディションサーバー、および Lync Server 2013 プールの完全修飾ドメイン名 (FQDN) を指定します。
    
      - 次ホップのコンピューターを FQDN で指定するプールで静的ルートを構成している場合は、Lync Server 2013 ディレクターの FQDN を指定します。

7.  各 Lync Server 2013、フロントエンドサーバー、Standard Edition server、プール、およびディレクターのエントリを追加したら、[**適用**] をクリックし、[ **OK** ] をクリックしてプロパティページを閉じます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

