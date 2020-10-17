---
title: ポリシーと設定をインポートする
description: ポリシーと設定をインポートします。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Import policies and settings
ms:assetid: b25decee-2ee5-4836-b370-454411d39252
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205178(v=OCS.15)
ms:contentKeyID: 48185147
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e014b7e8f0498742104118eec9eb313394ae6a94
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569033"
---
# <a name="import-policies-and-settings"></a>ポリシーと設定をインポートする

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-28_

Office Communications Server 2007 R2 のトポロジ情報を Lync Server 2013 パイロットプールに結合した後、lync Server 2013 Management Shell コマンドレットを実行して、Office Communications Server の 2007 R2 ポリシーと構成設定を Lync 2013 Server のパイロットプールに移行する必要があります。

**Import-cslegacyconfiguration**コマンドレットでは、ポリシー、音声ルート、ダイヤルプラン、Communicator Web access url、およびダイヤルインアクセス番号が Lync Server 2013 にインポートされます。

<div>

## <a name="to-migrate-policies-and-settings"></a>ポリシーと設定を移行するには

1.  Lync Server 2013 のフロントエンドサーバーで、Lync Server 管理シェルを起動します。

2.  コマンドラインで、次のように入力します。
    
        Import-CsLegacyConfiguration
    
    ポリシーがインポートされたら、次の手順を使用して、Lync Server コントロールパネルにインポートされたポリシーを表示します。

</div>

<div>

## <a name="to-view-imported-policies"></a>インポートされたポリシーを表示するには

1.  Lync Server 2013 コントロールパネルを開きます。

2.  [**音声のルーティング**] をクリックし、インポートされたポリシーを表示します。

3.  [**電話会議**] をクリックし、インポートされたポリシーを表示します。

4.  [ **フェデレーションと外部アクセス** ] をクリックし、インポートされたポリシーを表示します。

5.  [**監視およびアーカイブ**] をクリックし、インポートされたポリシーを表示します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

