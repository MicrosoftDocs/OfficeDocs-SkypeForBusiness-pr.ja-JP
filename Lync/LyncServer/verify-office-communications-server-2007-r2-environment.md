---
title: Office Communications Server 2007 R2 環境の確認
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify Office Communications Server 2007 R2 environment
ms:assetid: e051bdd5-e7ef-4754-8705-900b2c57f37c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721906(v=OCS.15)
ms:contentKeyID: 49733840
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fb67868c9f7eddfe2b11b4238c5fdd1bd14d8e6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730907"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-office-communications-server-2007-r2-environment"></a>Office Communications Server 2007 R2 環境の確認

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-16_

Office Communications Server 2007 R2 を使用して、共存状態で Lync Server 2013 を展開する前に、Office Communications Server 2007 R2 サービスが構成されて開始されていることを確認する必要があります。

**Office Communications Server 2007 R2 管理ツールを使用してプールが開始されていることを確認する**

1.  Office Communications Server 2007 R2 管理ツールを開きます。

2.  [**フォレスト**] ノードを展開し、 **Standard Edition サーバー**または [**エンタープライズプール**] ノードを展開して、プールまたはサーバー名を展開します。

3.  サービスが Standard Edition サーバーまたはエンタープライズプールで実行されていることを確認します。
    
    ![Office Communications Server 2007 R2 管理コンソール](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2 管理コンソール")

**Office Communications Server 2007 R2 用に構成されているユーザーを確認する**

1.  Office Communications Server 2007 R2 管理ツールを開きます。

2.  [**フォレスト**] ノードを展開し、 **Standard Edition サーバー**または [**エンタープライズプール**] ノードを展開して、プールまたはサーバー名を展開します。

3.  [**ユーザー**] をクリックします。

4.  Office Communications Server 2007 R2 ユーザーの一覧を確認します。
    
    ![OCS 管理ツールでユーザーを一覧表示する](images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "OCS 管理ツールでユーザーを一覧表示する")

**従来の XMPP フェデレーションパートナーの構成を確認する**

1.  従来の XMPP サーバーから、管理ツール\\の [サービス] アプレットに移動します。

2.  Office Communications Server XMPP ゲートウェイサービスが開始されていることを確認します。
    
    ![Office Communications Server XMPP ゲートウェイサービス](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP ゲートウェイサービス")

</div>

<span> </span>

</div>

</div>

</div>

