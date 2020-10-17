---
title: パイロット エッジ サーバーを展開する
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Deploy pilot Edge Server
ms:assetid: dab345c0-8577-4c11-ac73-fe8b2a75f4cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205306(v=OCS.15)
ms:contentKeyID: 48185559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37f2d51480567d1f775e9fb4b2161c9e54f8dfe7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502961"
---
# <a name="deploy-pilot-edge-server"></a>パイロット エッジ サーバーを展開する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-19_

このトピックでは、Lync Server 2013 エッジサーバーを展開する前に認識しておく必要がある構成設定について説明します。 Lync Server 2013 の展開および構成プロセスは、Lync Server 2010 によく似ています。 このセクションで説明するのは、パイロット プールの展開の際に考慮が必要となる主なポイントのみです。 詳細な手順については、「展開」のドキュメントの「Deployment [external user access In Lync Server 2013](lync-server-2013-deploying-external-user-access.md) 」 (展開プロセスについて説明し、外部ユーザーアクセスの構成情報も提供します) を参照してください。

**新しいエッジ プールの定義**ウィザードでは、以下の手順に示すキー構成の設定を確認してください。ただし、**新しいエッジ プールの定義**ウィザードのごく一部のページのみが示されています。

**エッジ プールを定義する**

1.  トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。

2.  [Lync Server 2013 ノードに移動します。 [**エッジ プール**] を右クリックし、[**新しいエッジ プール**] をクリックします。
    
    ![[新しいエッジプールの定義] ダイアログボックス](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "[新しいエッジプールの定義] ダイアログボックス")

3.  エッジ プールは、[**複数のコンピューター プール**] または [**単一コンピューター プール**] のどちらかになります。
    
    ![[エッジプールの FQDN の定義] ダイアログボックス](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "[エッジプールの FQDN の定義] ダイアログボックス")

4.  [**機能の選択**] ページでは、フェデレーションまたは XMPP フェデレーションを有効にしないでください。 フェデレーションと XMPP フェデレーションは、現在、従来の Lync Server 2010 エッジサーバーを経由してルーティングされています。 この機能は、後ほど移行のフェーズで構成されます。
    
    ![[機能の選択] ダイアログボックス](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "[機能の選択] ダイアログボックス")

5.  次に、次のウィザードページに進みます。 **外部 fqdn**、 **内部 IP アドレスの定義**、および **外部 ip アドレスの定義**を行います。

6.  [ **次ホップの定義** ] ページで、Lync Server 2010 エッジプールの次ホップのディレクターを選択します。
    
    ![[次ホップの定義] ダイアログボックス](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "[次ホップの定義] ダイアログボックス")

7.  [ **フロントエンドまたは仲介プールの関連付け** ] ページで、現時点ではプールをこのエッジプールに関連付けないでください。 外部メディアトラフィックは、現在、従来の Lync Server 2010 エッジサーバーを経由してルーティングされています。 この設定は、後ほど移行のフェーズで構成されます。
    
    ![[フロントエンドプールの関連付け] ダイアログボックス](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "[フロントエンドプールの関連付け] ダイアログボックス")

8.  [**完了**] をクリックし、[**公開**] をクリックしてトポロジを公開します。

9.  「展開」のドキュメントの「 [Install Edge Servers For Lync server 2013](lync-server-2013-install-edge-servers.md) 」の手順に従って、新しいエッジサーバーにファイルをインストールし、証明書を構成して、サービスを開始します。

「展開」のドキュメントの「 [Lync Server 2013 での外部ユーザーアクセスの展開](lync-server-2013-deploying-external-user-access.md) 」のトピックのガイドラインに従うことが非常に重要です。 このセクションでは、これらのサーバーの役割をインストールする際の構成設定に関するガイドラインの一部を提供したにすぎません。

これで、Lync server 2013 エッジサーバー展開と並行して、従来の Lync Server 2010 エッジサーバーが展開されるようになります。 次のフェーズに進む前に、双方の展開が適切に動作していること、サービスが開始されていること、および各展開を管理できることを確認してください。

</div>

<span> </span>

</div>

</div>

</div>

