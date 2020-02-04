---
title: パイロット エッジ サーバーの展開
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Deploy pilot Edge Server
ms:assetid: dab345c0-8577-4c11-ac73-fe8b2a75f4cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205306(v=OCS.15)
ms:contentKeyID: 48185559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc9f88d731873a16535e80eb0726aec8335e447b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729947"
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

このトピックでは、Lync Server 2013 Edge サーバーを展開する前に知っておく必要がある構成設定について説明します。 Lync Server 2013 の展開と構成のプロセスは、Lync Server 2010 とよく似ています。 このセクションでは、パイロットプールの展開の一部として考慮する必要がある重要なポイントについて説明します。 詳細な手順については、「展開プロセスについて説明し、外部ユーザーアクセスの構成情報も提供する展開ドキュメントの「 [Lync Server 2013 での外部ユーザーアクセスの展開](lync-server-2013-deploying-external-user-access.md)」を参照してください。

[**新しいエッジプールの定義**] ウィザードを実行するときに、次の手順に示されているキー構成の設定を確認します。 [**新しいエッジプールの定義**] ウィザードの一部のページのみが表示されることに注意してください。

**エッジプールを定義する**

1.  トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。

2.  Lync Server 2013 ノードに移動します。 [**エッジプール**] を右クリックし、[**新しいエッジプール**] をクリックします。
    
    ![[新しいエッジプールの定義] ダイアログボックス](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "[新しいエッジプールの定義] ダイアログボックス")

3.  エッジプールには、**複数のコンピュータプール**または**単一のコンピュータプール**を使用できます。
    
    ![エッジプールの FQDN ダイアログボックスの定義](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "エッジプールの FQDN ダイアログボックスの定義")

4.  **[機能の選択**] ページで、フェデレーションまたは xmpp フェデレーションを有効にしないようにします。 フェデレーションと XMPP フェデレーションは、現在、従来の Lync Server 2010 Edge サーバー経由でルーティングされます。 これらの機能は、移行の後のフェーズで構成されます。
    
    ![[機能の選択] ダイアログボックス](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "[機能の選択] ダイアログボックス")

5.  次に、次のウィザードページに進んでください。**外部 fqdn**、**内部 ip アドレスの定義**、**外部 ip アドレスの定義**を行います。

6.  [**次ホップの定義**] ページで、Lync Server 2010 Edge プールの次ホップのディレクターを選択します。
    
    ![[次ホップの定義] ダイアログボックス](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "[次ホップの定義] ダイアログボックス")

7.  [**フロントエンドまたは仲介プールの関連付け**] ページで、この時点ではプールをこのエッジプールに関連付けないでください。 外部メディアトラフィックは、現在、従来の Lync Server 2010 エッジサーバーを介してルーティングされています。 この設定は、移行の後のフェーズで構成されます。
    
    ![[フロントエンドプールの関連付け] ダイアログボックス](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "[フロントエンドプールの関連付け] ダイアログボックス")

8.  [**完了**] をクリックして、トポロジを**公開**します。

9.  展開ドキュメントの「 [Lync server 2013 用エッジサーバー](lync-server-2013-install-edge-servers.md)をインストールする」の手順に従って、新しいエッジサーバーにファイルをインストールし、証明書を構成して、サービスを開始します。

展開ドキュメントの「 [Lync Server 2013 での外部ユーザーアクセスの展開に](lync-server-2013-deploying-external-user-access.md)関するトピック」のガイドラインに従うことが非常に重要です。 このセクションでは、これらのサーバーの役割をインストールするときの構成設定について、いくつかのガイダンスを示しました。

Lync server 2013 Edge server の展開と並行して、従来の Lync Server 2010 Edge サーバーを展開する必要があります。 両方の展開が適切に実行されていることを確認し、サービスが開始されていることを確認します。次のフェーズに移行する前に、各展開を管理することができます。

</div>

<span> </span>

</div>

</div>

</div>

