---
title: パイロット エッジ サーバーの展開
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Deploy pilot Edge Server
ms:assetid: 11a59c48-0a53-4de1-83ed-875f850febd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204682(v=OCS.15)
ms:contentKeyID: 48183446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9cfe98069d3c90f4e021b34f6a7d31c583e7565
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840834"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a>パイロット エッジ サーバーの展開

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-19_

このトピックでは、Lync Server 2013 Edge サーバーを展開する前に知っておく必要がある構成設定について説明します。 このセクションでは、パイロットエッジプールの展開の一部として考慮する必要がある重要なポイントについて説明します。 詳細な手順については、「展開プロセスについて説明し、外部ユーザーアクセスの構成情報も提供する展開ドキュメントの「 [Lync Server 2013 での外部ユーザーアクセスの展開](lync-server-2013-deploying-external-user-access.md)」を参照してください。

[**新しいエッジプールの定義**] ウィザードを実行するときに、次の手順に示されているキー構成の設定を確認します。 [**新しいエッジプールの定義**] ウィザードの一部のページのみが表示されることに注意してください。

**エッジプールを定義する**

1.  トポロジビルダーを使用して、パイロットプールトポロジを開きます。

2.  Lync Server 2013 ノードに移動します。 [**エッジプール**] を右クリックし、[**新しいエッジプール**] をクリックします。
    
    ![[新しいエッジプールの定義] ダイアログボックス](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "[新しいエッジプールの定義] ダイアログボックス")

3.  エッジプールには、**複数のコンピュータプール**または**単一のコンピュータプール**を使用できます。
    
    ![エッジプールの FQDN ダイアログボックスの定義](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "エッジプールの FQDN ダイアログボックスの定義")

4.  **[機能の選択**] ページで、フェデレーションまたは xmpp フェデレーションを有効にしないようにします。 フェデレーションと XMPP フェデレーションは現在、従来の Office Communications Server 2007 R2 Edge サーバーを経由してルーティングされます。 これらの機能は、移行の後のフェーズで構成されます。
    
    ![[機能の選択] ダイアログボックス](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "[機能の選択] ダイアログボックス")

5.  次に、次のウィザードページに進みます。 **[IP オプション**]、[**外部 Fqdn**] の選択、**内部 ip アドレスの定義**、**外部 ip アドレスの定義**を行います。

6.  [**次ホップの定義**] ページで、Lync Server 2013 Edge プールの次ホップのディレクターを選択します。
    
    [![新しいエッジプールの定義] ダイアログ、[次ホッププール] の一覧][(images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "新しいエッジプールの定義] ダイアログ、[次ホッププール] の一覧")

7.  [**フロントエンドプールの関連付け**] ページで、この時点ではプールをこのエッジプールに関連付けないでください。 外部メディアトラフィックは、現在、従来の Office Communications Server 2007 R2 Edge サーバーを経由してルーティングされています。 この設定は、移行の後のフェーズで構成されます。
    
    [![新しいエッジプールの定義] ダイアログ][(images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "新しいエッジプールの定義] ダイアログ")

8.  [**完了**] をクリックして、トポロジを**公開**します。

9.  展開ドキュメントの「 [Lync server 2013 用エッジサーバー](lync-server-2013-install-edge-servers.md)をインストールする」の手順に従って、新しいエッジサーバーにファイルをインストールし、証明書を構成して、サービスを開始します。

展開ドキュメントの「 [Lync Server 2013 での外部ユーザーアクセスの展開に](lync-server-2013-deploying-external-user-access.md)関するトピック」のガイドラインに従うことが非常に重要です。 このセクションでは、これらのサーバーの役割をインストールするときの構成設定について、いくつかのガイダンスを示しました。

これで、Lync Server 2013 Edge server の展開と並行して、BackCompatSite が存在することを示す、従来の Office Communications Server 2007 R2 Edge サーバーの展開ができます。 フェデレーションは、Office Communications Server 2007 R2 Director を使用するように構成されています。 両方の展開が適切に実行されていることを確認し、サービスが開始されていることを確認します。次のフェーズに移行する前に、各展開を管理することができます。

![OCS Edge サーバーが表示]されているトポロジビルダー(images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "OCS Edge サーバーが表示")されているトポロジビルダー

</div>

<span> </span>

</div>

</div>

</div>

