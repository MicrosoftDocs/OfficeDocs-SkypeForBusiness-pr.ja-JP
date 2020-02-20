---
title: Lync Server 2010 環境の確認
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify Lync Server 2010 environment
ms:assetid: bfc7c620-556a-43cd-b1ed-2c268ec2b5cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205231(v=OCS.15)
ms:contentKeyID: 48185301
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a162c51dabf88231edc7fb5a5f5372a9f29d8687
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147880"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-lync-server-2010-environment"></a>Lync Server 2010 環境の確認

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-19_

Lync server 2010 を使用して Lync Server 2013 を共存状態に展開する前に、lync Server 2010 サービスが構成され、起動していることを確認する必要があります。 Lync Server 2013 パイロットプールを展開する前に、従来の環境に存在する主要なサービスと機能を特定することが重要です。 レガシ XMPP 展開を使用して、Microsoft Lync Server 2013 XMPP を共存状態に展開する前に、従来の XMPP サービスが構成されて起動していることを確認し、従来の XMPP 構成がサポートしているフェデレーションパートナーを特定する必要があります。 従来の Lync Server 2010 の展開を確認するには、次のことが伴います。

  - Lync Server 2010 サービスが開始されていることを確認する

  - Lync Server 2010 のトポロジとユーザーを確認します。

  - フェデレーションとエッジ サーバーの設定を確認する。

  - XMPP サービスとフェデレーション パートナーを確認する。

**Lync Server 2010 サービスが開始されていることを確認する**

1.  Lync Server 2010 フロントエンドサーバーから、[管理ツール\\] [サービス] アプレットに移動します。

2.  次のサービスがフロントエンド サーバーで実行されていることを確認します。
    
    ![フロントエンドサーバーで実行されているサービスの一覧](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "フロントエンドサーバーで実行されているサービスの一覧")

**Lync Server コントロールパネルで Lync Server 2010 トポロジを確認する**

1.  RTCUniversalServerAdmins グループのメンバーであるか、CsAdministrator または CsUserAdministrator 管理者ロールのメンバーであるアカウントを使用して、フロントエンド サーバーにログオンします。

2.  Lync Server コントロール パネルを開きます。

3.  [**トポロジ**] クリックします。 Lync Server 2010 の展開に含まれるさまざまなサーバーが表示されていることを確認します。
    
    ![Lync Server 2010 コントロールパネルのトポロジページ](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Lync Server 2010 コントロールパネルのトポロジページ")

**Lync server コントロールパネルで Lync Server 2010 ユーザーを確認するには**

1.  Lync Server コントロール パネルを開きます。

2.  [**ユーザー**]、[**検索**] の順にクリックします。

3.  [**レジストラープール**] 列が、表示されている各ユーザーの Lync Server 2010 プールを指していることを確認します。
    
    ![Lync Server 2010 コントロールパネルのユーザー一覧](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Lync Server 2010 コントロールパネルのユーザー一覧")

**Lync Server 2010 のエッジとフェデレーションの設定を確認するには**

1.  トポロジ ビルダーを開始します。

2.  [**既存の展開からトポロジをダウンロードする**] をクリックします。

3.  ファイル名を選択して、既定のファイルの種類である .tbxml でトポロジを保存します。

4.  [Lync Server 2010] ノードを展開して、展開に含まれるさまざまなサーバーの役割を確認します。

5.  サイト ノードを選択して、[**サイトのフェデレーション ルートの割り当て**] に値が設定されているかどうかを確認します。
    
    ![トポロジビルダー、サイトのフェデレーションルート](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "トポロジビルダー、サイトのフェデレーションルート")

6.  次に、Standard Edition Server または Enterprise Edition のフロントエンド プールを選択します。[**関連付け**] の下のメディアに対してエッジ プールが構成されているかどうかを確認します。
    
    ![トポロジビルダー、サーバーとプールが表示されている](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "トポロジビルダー、サーバーとプールが表示されている")

7.  最後に、エッジ プールを選択して、[**次ホップの選択**] の下に次ホップ プールが構成されているかどうかを確認します。
    
    ![トポロジビルダー、次ホップの選択](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "トポロジビルダー、次ホップの選択")

**レガシ XMPP フェデレーション パートナーの構成を確認する**

1.  従来の XMPP サーバーから、[管理ツール\\] [サービス] アプレットに移動します。

2.  Office Communications Server XMPP Gateway サービスが開始されていることを確認します。
    
    ![Office Communications Server XMPP ゲートウェイサービス](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP ゲートウェイサービス")

</div>

<span> </span>

</div>

</div>

</div>

