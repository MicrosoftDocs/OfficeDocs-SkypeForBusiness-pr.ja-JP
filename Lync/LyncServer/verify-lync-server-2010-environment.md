---
title: Lync Server 2010 環境の確認
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify Lync Server 2010 environment
ms:assetid: bfc7c620-556a-43cd-b1ed-2c268ec2b5cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205231(v=OCS.15)
ms:contentKeyID: 48185301
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 248d779bc43b7c3e220728222aca030036f17e00
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847929"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-lync-server-2010-environment"></a>Lync Server 2010 環境の確認

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-19_

Lync server 2010 を使用した共存状態で lync server 2013 を展開する前に、lync Server 2010 サービスが構成され、開始されていることを確認する必要があります。 Lync Server 2013 パイロットプールを展開する前に、従来の環境に存在する主要なサービスと機能を特定することが重要です。 従来の XMPP 展開で Microsoft Lync Server 2013 XMPP を共存状態で展開する前に、以前の xmpp サービスが構成されて開始されていることを確認して、従来の XMPP 構成でサポートされているフェデレーションパートナーを特定する必要があります。 従来の Lync Server 2010 の展開を確認するには、次のものがあります。

  - Lync Server 2010 サービスが開始されていることを確認する

  - Lync Server 2010 でトポロジとユーザーを確認します。

  - フェデレーションとエッジサーバーの設定を確認します。

  - XMPP サービスおよびフェデレーションパートナーを確認します。

**Lync Server 2010 サービスが開始されていることを確認する**

1.  Lync Server 2010 フロントエンドサーバーから、管理ツール\\の [サービス] アプレットに移動します。

2.  フロントエンドサーバーで次のサービスが実行されていることを確認します。
    
    ![フロントエンドサーバーで実行されているサービスの一覧](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "フロントエンドサーバーで実行されているサービスの一覧")

**Lync server のコントロールパネルで Lync Server 2010 トポロジを確認する**

1.  RTCUniversalServerAdmins グループ、CsAdministrator 管理者ロール、または CsUserAdministrator 管理者ロールのメンバーであるアカウントを使用して、フロントエンド サーバーにログオンします。

2.  Lync Server コントロールパネルを開きます。

3.  [**トポロジ**] を選びます。 Lync Server 2010 の展開に含まれるさまざまなサーバーが一覧に表示されていることを確認します。
    
    ![Lync Server 2010 コントロールパネルのトポロジページ](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Lync Server 2010 コントロールパネルのトポロジページ")

**Lync server の [コントロールパネル] の Lync Server 2010 ユーザーを確認するには**

1.  Lync Server コントロールパネルを開きます。

2.  [**ユーザー** ] を選択し、[**検索**] をクリックします。

3.  **レジストラー pool**列が、表示されている各ユーザーの Lync Server 2010 プールをポイントしていることを確認します。
    
    ![Lync Server 2010 コントロールパネルのユーザーの一覧](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Lync Server 2010 コントロールパネルのユーザーの一覧")

**Lync Server 2010 Edge およびフェデレーション設定を確認するには**

1.  トポロジビルダーを起動します。

2.  [**既存の展開からトポロジをダウンロード**] を選択します。

3.  ファイル名を選択し、tbxml ファイルの種類が設定されたトポロジを保存します。

4.  [Lync Server 2010] ノードを展開して、展開内のさまざまなサーバーの役割を表示します。

5.  サイトノードを選択し、[**サイトフェデレーションルートの割り当て**] の値が設定されているかどうかを確認します。
    
    ![トポロジビルダー、サイトフェデレーションルート](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "トポロジビルダー、サイトフェデレーションルート")

6.  次に、Standard Edition Server または Enterprise Edition のフロントエンドプールを選択します。 エッジプールが**関連付け**の下にあるメディアに対して構成されているかどうかを確認します。
    
    ![サーバーとプールを表示するトポロジビルダー](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "サーバーとプールを表示するトポロジビルダー")

7.  最後に、エッジプールを選択して、次ホッププールが**次ホップの選択**の下に構成されているかどうかを確認します。
    
    ![トポロジビルダー、次ホップの選択](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "トポロジビルダー、次ホップの選択")

**従来の XMPP フェデレーションパートナーの構成を確認する**

1.  従来の XMPP サーバーから、管理ツール\\の [サービス] アプレットに移動します。

2.  Office Communications Server XMPP ゲートウェイサービスが開始されていることを確認します。
    
    ![Office Communications Server XMPP ゲートウェイサービス](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP ゲートウェイサービス")

</div>

<span> </span>

</div>

</div>

</div>

