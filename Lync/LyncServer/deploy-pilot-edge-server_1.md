---
title: パイロット エッジ サーバーを展開する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Deploy pilot Edge Server
ms:assetid: 11a59c48-0a53-4de1-83ed-875f850febd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204682(v=OCS.15)
ms:contentKeyID: 48183446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7cabf1b5f16d5be179ce2bca16edc861bf6c3a7e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137968"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a>パイロット エッジ サーバーを展開する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-19_

このトピックでは、Lync Server 2013 エッジサーバーを展開する前に認識しておく必要がある構成設定について説明します。 このセクションでは、パイロットエッジプールの展開の一部として考慮する必要がある重要事項について説明します。 詳細な手順については、「展開」のドキュメントの「Deployment [external user access In Lync Server 2013](lync-server-2013-deploying-external-user-access.md) 」 (展開プロセスについて説明し、外部ユーザーアクセスの構成情報も提供します) を参照してください。

**新しいエッジ プールの定義**ウィザードでは、以下の手順に示すキー構成の設定を確認してください。ただし、**新しいエッジ プールの定義**ウィザードのごく一部のページのみが示されています。

**エッジ プールを定義する**

1.  トポロジ ビルダーを使用してパイロット プールを開きます。

2.  [Lync Server 2013 ノードに移動します。 [**エッジ プール**] を右クリックし、[**新しいエッジ プール**] をクリックします。
    
    ![[新しいエッジプールの定義] ダイアログボックス](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "[新しいエッジプールの定義] ダイアログボックス")

3.  エッジ プールは、[**複数のコンピューター プール**] または [**単一コンピューター プール**] のどちらかになります。
    
    ![[エッジプールの FQDN の定義] ダイアログボックス](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "[エッジプールの FQDN の定義] ダイアログボックス")

4.  [**機能の選択**] ページでは、フェデレーションまたは XMPP フェデレーションを有効にしないでください。 現在、フェデレーションと XMPP フェデレーションは、従来の Office Communications Server 2007 R2 エッジサーバーを経由してルーティングされています。 この機能は、後ほど移行のフェーズで構成されます。
    
    ![[機能の選択] ダイアログボックス](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "[機能の選択] ダイアログボックス")

5.  次に、引き続きウィザードの [**IP オプションの選択**]、[**外部 FQDN**]、[**内部 IP アドレスの定義**]、および [**外部 IP アドレスの定義**] の各ページの設定を完了します。

6.  [**次ホップの定義**] ページで、Lync Server 2013 エッジプールの次ホップのディレクターを選択します。
    
    ![[新しいエッジプールの定義] ダイアログ、次ホッププール一覧](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "[新しいエッジプールの定義] ダイアログ、次ホッププール一覧")

7.  [**フロントエンドプールの関連付け**] ページで、現時点ではプールをこのエッジプールに関連付けないでください。 外部メディアトラフィックは、現在、従来の Office Communications Server 2007 R2 エッジサーバーを経由してルーティングされます。 この設定は、後ほど移行のフェーズで構成されます。
    
    ![[新しいエッジプールの定義] ダイアログ](images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "[新しいエッジプールの定義] ダイアログ")

8.  [**完了**] をクリックし、[**公開**] をクリックしてトポロジを公開します。

9.  「展開」のドキュメントの「 [Install Edge Servers For Lync server 2013](lync-server-2013-install-edge-servers.md) 」の手順に従って、新しいエッジサーバーにファイルをインストールし、証明書を構成して、サービスを開始します。

「展開」のドキュメントの「 [Lync Server 2013 での外部ユーザーアクセスの展開](lync-server-2013-deploying-external-user-access.md)」のトピックのガイドラインに従うことが非常に重要です。 このセクションでは、これらのサーバーの役割をインストールする際の構成設定に関するガイドラインの一部を提供したにすぎません。

これで、BackCompatSite の存在が Lync Server 2013 エッジサーバー展開と並行して、従来の Office Communications Server 2007 R2 エッジサーバー展開を使用できるようになります。 フェデレーションは、Office Communications Server 2007 R2 Director を使用するように構成されています。 次のフェーズに進む前に、双方の展開が適切に動作していること、サービスが開始されていること、および各展開を管理できることを確認してください。

![OCS エッジサーバーが表示されているトポロジビルダー](images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "OCS エッジサーバーが表示されているトポロジビルダー")

</div>

<span> </span>

</div>

</div>

</div>

