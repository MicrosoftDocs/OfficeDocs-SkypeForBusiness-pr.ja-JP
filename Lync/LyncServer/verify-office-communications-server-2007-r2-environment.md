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
ms.openlocfilehash: 885b1b08ef2d02c6a3cb3a77b83ca832e70281a5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188940"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-office-communications-server-2007-r2-environment"></a>Office Communications Server 2007 R2 環境の確認

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-16_

Office Communications Server 2007 R2 と共存状態で Lync Server 2013 を展開する前に、Office Communications Server 2007 R2 サービスが構成され、起動していることを確認する必要があります。

**Office Communications Server 2007 R2 管理ツールを使用してプールが開始されていることを確認する**

1.  Office Communications Server 2007 R2 管理ツールを開きます。

2.  [**フォレスト**] ノード、[**Standard Edition サーバー**] ノードまたは [**エンタープライズ プール**] ノード、プールまたはサーバー名の順に展開します。

3.  サービスが Standard Edition サーバーまたはエンタープライズプールで実行されていることを確認します。
    
    ![Office Communications Server 2007 R2 管理コンソール](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2 管理コンソール")

**Office Communications Server 2007 R2 用に構成されているユーザーを確認する**

1.  Office Communications Server 2007 R2 管理ツールを開きます。

2.  [**フォレスト**] ノード、[**Standard Edition サーバー**] ノードまたは [**エンタープライズ プール**] ノード、プールまたはサーバー名の順に展開します。

3.  [**ユーザー**] をクリックします。

4.  Office Communications Server 2007 R2 ユーザーのリストを確認します。
    
    ![OCS 管理ツールでの fo ユーザーのリスト](images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "OCS 管理ツールでの fo ユーザーのリスト")

**レガシ XMPP フェデレーション パートナーの構成を確認する**

1.  従来の XMPP サーバーから、[管理ツール\\] [サービス] アプレットに移動します。

2.  Office Communications Server XMPP Gateway サービスが開始されていることを確認します。
    
    ![Office Communications Server XMPP ゲートウェイサービス](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP ゲートウェイサービス")

</div>

<span> </span>

</div>

</div>

</div>

