---
title: 'Lync Server 2013: 自動検出サービスの要件'
description: 'Lync Server 2013: 自動検出サービスの要件。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Autodiscover service requirements
ms:assetid: 0ac5dbf7-9acd-4d25-b21a-932022b8b983
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690012(v=OCS.15)
ms:contentKeyID: 48183368
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61e963bc9e921cc0a571f63d4be50f09d237c2dd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572993"
---
# <a name="autodiscover-service-requirements-for-lync-server-2013"></a>Lync Server 2013 の自動検出サービスの要件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-25_

Microsoft Lync Server 2013 自動検出サービスは、ディレクターおよびフロントエンドプールサーバー上で実行され、DNS で公開されると、Lync Mobile を実行しているモバイルデバイスでモビリティサービスを検索するために使用できます。 Lync Mobile を実行しているモバイルデバイスが自動検出を利用できるようにするには、自動検出を利用する前に、自動検出サービスを実行しているすべてのディレクターおよびフロントエンドサーバーで証明書のサブジェクトの別名の一覧を変更する必要があります。 さらに、リバースプロキシの外部 web サービス公開ルールに使用される証明書のサブジェクトの別名の一覧を変更する必要がある場合があります。

ディレクター、フロントエンドサーバー、およびリバースプロキシに必要なサブジェクトの別名エントリの詳細については、「Planning for Mobility」の「 [Lync Server 2013 でのモビリティの技術要件](lync-server-2013-technical-requirements-for-mobility.md) 」を参照してください。

リバース プロキシでのサブジェクトの別名リストの使用については、自動検出サービスをポート 80 またはポート 443 のどちらで公開するかに基づいて決定します。

  - **ポート 80**     で公開自動検出サービスへの最初のクエリがポート80で行われる場合、証明書の変更は必要ありません。 これは、Lync を実行しているモバイルデバイスがポート80のリバースプロキシに外部でアクセスし、内部でポート8080のディレクターまたはフロントエンドサーバーにリダイレクトされるためです。 詳細については、このトピックの後半の「ポート80を使用した最初の自動検出プロセス」を参照してください。

  - **ポート 443**     で公開外部 web サービス公開ルールで使用される証明書のサブジェクトの別名リストには、lyncdiscover が含まれている必要があり*ます。 \<sipdomain\> * 組織内の各 SIP ドメインのエントリ。

内部証明機関を使用した証明書の再発行は通常、単純なプロセスですが、web サービス公開ルールで使用されるパブリック証明書については、複数のサブジェクトの別名エントリを追加するとコストがかかる場合があります。 この問題を回避するために、ポート80経由の最初の自動検出接続をサポートします。その後、ディレクターまたはフロントエンドサーバーのポート8080にリダイレクトされます。

たとえば、Lync Mobile を実行しているモバイルクライアントが、最初の要求に HTTP を使用して自動検出機能を使用して Lync Server 2013 にサインインするように構成されているとします。

<div>

## <a name="initial-autodiscover-process-for-mobile-devices-using-port-80"></a>ポート80を使用したモバイルデバイスの初期自動検出プロセス

1.  Lync Mobile を実行しているモバイルデバイスは、A レコードが存在する DNS を使用して lyncdiscover.contoso.com を検索します。

2.  外部 DNS は、外部 web サービスの IP アドレスをクライアントに返します。

3.  Lync Mobile を実行しているモバイルデバイスが http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com リバースプロキシに要求を送信する

4.  Web 公開ルールは、ポート80からの要求を内部でポート8080にブリッジし、ディレクターまたはフロントエンドサーバーのいずれかにルーティングします。
    
    要求は HTTP なので (HTTPS ではない)、自動検出サービスをサポートするように外部 Web サービス公開ルール上の証明書を変更する必要はありません。

5.  自動検出サービスは外部 Web サービスの URL (HTTPS 形式) を返します。

6.  Lync Mobile を実行しているモバイルデバイスは、ポート443のリバースプロキシに再接続することができ、4443経由でユーザーのホームプールで実行されている mobility service にリダイレクトされます。
    
    HTTPS クエリは自動検出サービスの URL に対する外部 Web サービスの URL に送信されるため、この HTTPS クエリは成功します。これは、外部 Web サービスの完全修飾ドメイン名 (FQDN) に対するサブジェクトの別名エントリが証明書に既に含まれるためです。
    
    このシナリオでは、モビリティをサポートするように証明書を変更する必要はありません。
    
    <div>
    

    > [!NOTE]  
    > 対象の Web サーバーに含まれる証明書に、サブジェクトの別名リストの値として、lyncdiscover.contoso.com に一致する値が含まれない場合:<BR>a。 &nbsp; &nbsp; &nbsp;Web サーバーは "サーバー Hello" で応答し、証明書は応答しません。<BR>b。 &nbsp; &nbsp; &nbsp;Lync Mobile を実行しているモバイルデバイスは、すぐにセッションを終了します。<BR>対象の Web サーバーに含まれる証明書に、サブジェクトの別名リストの値として、lyncdiscover.contoso.com が含まれる場合:<BR>a。 &nbsp; &nbsp; &nbsp;Web サーバーは、"サーバー hello" と "証明書" で応答します。<BR>b。 &nbsp; &nbsp; &nbsp;Lync Mobile を実行しているモバイルデバイスは、証明書を検証してハンドシェイクを完了します。

    
    </div>

リバース プロキシ サーバーのポート 80 を使用する、自動検出サービスへの初期接続をサポートするには、Forefront Threat Management Gateway 2010 リバース プロキシ Web 公開ルールに対して、この例に類似した http 公開ルールを作成できます。

1.  新しい Web 公開ルール (例: **Lync Server Autodiscover (HTTP)**) を作成します。

2.  [**パブリック名**] に「lyncdiscover.contoso.com」と入力します。

3.  [**ブリッジ**] タブで、要求をポート 80 からポート 8080 に橋渡しするオプションのみを選択します。

4.  [**認証**] タブで、[**認証なし**] および [**クライアントは直接認証できません**] を選択します。

5.  変更を確定して、ルールを Lync ルールの一覧の先頭 (最初に処理する順序) に移動します。

</div>

<div>

## <a name="mobility-for-the-split-domain-deployment"></a>分割ドメイン展開でのモビリティ

共有済みの SIP アドレス スペースは、"分割ドメイン"** または "ハイブリッド展開"** とも呼ばれる構成で、ユーザーは社内展開とオンライン展開をまたいで展開されます。 この構成では、ホーム サーバーの設置場所 (社内またはオンラインのどちらであるか) に関係なく、展開にログインしたユーザーは、そのホーム サーバーの設置場所にリダイレクトされることが望まれます。 これを実現するために、Microsoft Lync Server 2013 の自動検出機能を使用して、オンラインユーザーをオンライントポロジにリダイレクトします。 これを行うには、Lync Server 管理シェルを使用して自動検出の URL (uniform resource locator) を構成し、コマンドレットに **-cshostingprovider** および **Set-cshostingprovider**を使用します。

次の展開属性を収集して記録する必要があります。

  - Lync Server 管理シェルで、と入力します。
    
        Get-CsHostingProvider

  - 実行結果から、**ProxyFQDN** 属性を持つオンライン プロバイダー (たとえば、sipfed.online.lync.com) を見つけます。

  - ProxyFQDN の値を記録します。

  - オンプレミスの Lync Server コントロールパネルでフェデレーションを有効にして、オンラインプロバイダーとのフェデレーションを許可する

  - オンライン プロバイダーに対してフェデレーションを有効にします。既定では、ドメイン フェデレーションに対してすべてのオンライン ユーザーが有効になり、すべてのドメインと通信できます。

  - 禁止ドメインと許可ドメインを定義する場合は、明示的に許可するドメイン、または明示的に禁止するドメインを決めます。

  - オンライン フェデレーションの場合、ファイアウォールに期待する動作、証明書、および DNS ホスト (A、または IPv6 を使用する場合は AAAA) レコードを計画する必要があります。 また、フェデレーション ポリシーを構成する必要もあります。 詳細については、「 [Planning For Lync Server 2013 And Office Communications server federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md) 」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

