---
title: ポリシーと設定をインポートする
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Import policies and settings
ms:assetid: b25decee-2ee5-4836-b370-454411d39252
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205178(v=OCS.15)
ms:contentKeyID: 48185147
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f4a4d86d687236934c319e3fb7bd5e6c8027a73
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840987"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-policies-and-settings"></a>ポリシーと設定をインポートする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-28_

Office Communications Server 2007 R2 のトポロジ情報を Lync Server 2013 パイロットプールに統合したら、Lync Server 2013 Management Shell コマンドレットを実行して、Office Communications Server 2007 R2 のポリシーと構成の設定を移行する必要があります。Lync Server 2013 パイロットプール。

**CsLegacyConfiguration**コマンドレットは、ポリシー、音声ルート、ダイヤルプラン、Communicator Web Access url、ダイヤルインアクセス番号を Lync Server 2013 にインポートします。

<div>

## <a name="to-migrate-policies-and-settings"></a>ポリシーと設定を移行するには

1.  Lync Server 2013 フロントエンドサーバーで、Lync Server 管理シェルを起動します。

2.  コマンドラインで、次のように入力します。
    
        Import-CsLegacyConfiguration
    
    ポリシーがインポートされたら、次の手順を実行して、Lync Server コントロールパネルにインポートされたポリシーを表示します。

</div>

<div>

## <a name="to-view-imported-policies"></a>インポートしたポリシーを表示するには

1.  Lync Server 2013 コントロールパネルを開きます。

2.  [**音声ルーティング**] をクリックして、インポートしたポリシーを表示します。

3.  [**会議**] をクリックして、インポートしたポリシーを表示します。

4.  [**フェデレーションと外部アクセス**] をクリックし、インポートされたポリシーを表示します。

5.  [**監視およびアーカイブ**] をクリックして、インポートしたポリシーを表示します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

