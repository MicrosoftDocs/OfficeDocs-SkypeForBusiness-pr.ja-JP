---
title: ポリシーと設定をインポートする
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Import policies and settings
ms:assetid: b25decee-2ee5-4836-b370-454411d39252
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205178(v=OCS.15)
ms:contentKeyID: 48185147
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7dde4cfdc2f027c095cd6ad95582a130d047d3c7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198930"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="import-policies-and-settings"></a>ポリシーと設定をインポートする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-28_

Office Communications Server 2007 R2 のトポロジ情報を Lync Server 2013 パイロットプールと統合した後、Office Communications Server の 2007 R2 ポリシーと構成設定を移行するには、Lync Server 2013 Management Shell コマンドレットを実行する必要があります。Lync Server 2013 パイロットプールに展開します。

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

4.  [**フェデレーションと外部アクセス**] をクリックし、インポートされたポリシーを表示します。

5.  [**監視およびアーカイブ**] をクリックし、インポートされたポリシーを表示します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

