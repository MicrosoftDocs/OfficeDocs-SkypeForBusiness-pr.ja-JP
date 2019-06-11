---
title: 'Lync Server 2013: 自動検出用の DNS の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring DNS for Autodiscover
ms:assetid: f07a634c-3cf3-4958-8556-84596319ef54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945656(v=OCS.15)
ms:contentKeyID: 51541528
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c490cac475f3b9a9c8038636f4ac7f6670f22637
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840269"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-dns-for-autodiscover-in-lync-server-2013"></a>Lync Server 2013 での自動検出用の DNS の構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-12-12_

Lync クライアントの自動検出をサポートするには、次のドメインネームシステム (DNS) レコードを作成する必要があります。

  - 組織のネットワーク内から接続する Lync クライアントをサポートするための内部 DNS レコード

  - インターネットから接続する Lync クライアントをサポートするための、外部またはパブリックの DNS レコード

内部 DNS レコードと、各 SIP ドメイン用の外部 DNS レコードを作成する必要があります。

DNS レコードは、追加のサブジェクト代替名 (SAN) で新しい証明書を作成する機能に基づいて、(ホスト) レコードまたは CNAME レコードのいずれかにすることができます。 Lyncdiscover を使用して、新しい外部 (公開) 証明書を要求して展開できない場合。\<ドメイン名\> SAN で、HTTP/TCP ポート80を使用するための手順を使用します。 次の手順では、内部と外部の DNS レコードを作成する方法について説明します。

<div>

## <a name="to-create-dns-cname-records"></a>DNS CNAME レコードを作成するには

1.  次の手順で DNS サーバーにログオンします。
    
      - 内部 DNS レコードを作成するには、ドメイン管理者グループのメンバーまたは DnsAdmins グループのメンバーとして、ネットワーク内の DNS サーバーにログオンします。
    
      - 外部 DNS レコードを作成するには、パブリック DNS プロバイダーに接続します。

2.  DNS 管理スナップインを開きます。 [**スタート**] をクリックし、[**管理ツール**]、[ **dns**] の順にクリックします。

3.  次のいずれかの操作を行います。
    
      - 内部 DNS レコードの場合は、DNS サーバーのコンソールツリーで、Active Directory ドメインの [**前方参照ゾーン**] (たとえば、[コントソ]) を展開します。
        
        <div>
        

        > [!NOTE]  
        > このドメインは、Lync Server 2013&nbsp;監督プールとフロントエンドプールがインストールされている Active Directory ドメインです。

        
        </div>
    
      - 外部 DNS レコードの場合は、DNS サーバーのコンソールツリーで、SIP ドメインの [**前方参照ゾーン**] を展開します (たとえば、contoso.com)。

4.  ディレクタープールのホスト A レコードが次のように存在することを確認します。
    
      - 内部 DNS レコードの場合、ディレクタープールの内部 Web サービスの完全修飾ドメイン名 (FQDN) に対して、ホスト A レコードが存在している必要があります (たとえば、lyncwebdir01)。
    
      - 外部 DNS レコードの場合は、ディレクタープールの外部 web サービス FQDN (たとえば、lyncwebextdir.contoso.com) のホスト A レコードが存在している必要があります。

5.  フロントエンドプールのホスト A レコードが次のように存在することを確認します。
    
      - 内部 DNS レコードの場合は、フロントエンドプール用の内部 Web サービス FQDN (たとえば、lyncwebpool01) のホスト A レコードが存在している必要があります。
    
      - 外部 DNS レコードの場合は、フロントエンドプール用の外部 Web サービス FQDN にホスト A レコードが存在している必要があります (たとえば、lyncwebextpool01.contoso.com)。

6.  内部 DNS レコードの場合は、DNS サーバーのコンソールツリーで、SIP ドメインの [**前方参照ゾーン**] を展開します (たとえば、contoso.com)。
    
    <div>
    

    > [!NOTE]  
    > 外部 DNS レコードを作成する場合は、手順3で既に SIP ドメイン用の<STRONG>前方参照ゾーン</STRONG>が展開されています。

    
    </div>

7.  SIP ドメイン名を右クリックし、[**新しいエイリアス (CNAME)**] をクリックします。

8.  [**エイリアス名**] に、次のいずれかを入力します。
    
      - 内部の DNS レコードの場合は、内部の自動検出サービス URL のホスト名として「lyncdiscoverinternal」と入力します。
    
      - 外部 DNS レコードの場合は、外部自動検出サービス URL のホスト名として「lyncdiscover」と入力します。

9.  [ **Target host の完全修飾ドメイン名 (FQDN)**] で、次のいずれかの操作を行います。
    
      - 内部 DNS レコードの場合は、ディレクタープールの内部 Web サービス FQDN (たとえば、lyncwebdir01) を入力または参照して、[ **OK]** をクリックします。
    
      - 外部 DNS レコードの場合は、ディレクタープールの外部 Web サービス FQDN (たとえば、lyncwebextdir.contoso.com) を入力または参照して、[ **OK]** をクリックします。
    
    <div>
    

    > [!NOTE]  
    > ディレクターを使用しない場合は、フロントエンドプールに対して内部および外部の Web サービス FQDN を使用します。または、単一のサーバーの場合は、フロントエンドサーバーまたは Standard Edition サーバーの FQDN を使用します。

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 2013 環境でサポートしている各 SIP ドメインの前方参照ゾーンに新しい自動検出 CNAME レコードを作成する必要があります。

    
    </div>

</div>

<div>

## <a name="to-create-dns-a-records"></a>DNS A レコードを作成するには

1.  次の手順で DNS サーバーにログオンします。
    
      - 内部 DNS レコードを作成するには、ドメイン管理者グループのメンバーまたは DnsAdmins グループのメンバーとして、ネットワーク内の DNS サーバーにログオンします。
    
      - 外部 DNS レコードを作成するには、パブリック DNS プロバイダーまたは外部 DNS サーバーに接続します。

2.  DNS 管理スナップインを開きます。 [**スタート**] をクリックし、[**管理ツール**]、[ **dns**] の順にクリックします。

3.  次のいずれかの操作を行います。
    
      - 内部 DNS レコードの場合は、DNS サーバーのコンソールツリーで、Active Directory ドメインの [**前方参照ゾーン**] (たとえば、[コントソ]) を展開します。
        
        <div>
        

        > [!NOTE]  
        > このドメインは、Lync Server 2013&nbsp;監督プールとフロントエンドプールがインストールされている Active Directory ドメインです。

        
        </div>
    
      - 外部 DNS レコードの場合は、DNS サーバーのコンソールツリーで、SIP ドメインの [**前方参照ゾーン**] を展開します (たとえば、contoso.com)。

4.  ディレクタープールに対して、次のようにホスト A (IPv6, AAAA) レコードが存在することを確認します。
    
      - 内部 DNS レコードの場合は、ディレクタープールの内部 Web サービス FQDN (たとえば、lyncwebdir01) に対して host A (IPv6、AAAA) レコードが存在している必要があります。
    
      - 外部 DNS レコードの場合は、ディレクタープールの外部 Web サービス FQDN (たとえば、lyncwebextdir.contoso.com) に対して、host A (IPv6、AAAA) レコードが存在している必要があります。

5.  次のようにして、フロントエンドプールに対して host A (IPv6, AAAA) レコードが存在することを確認します。
    
      - 内部 DNS レコードの場合は、フロントエンドプール用の内部 Web サービス FQDN (たとえば、lyncwebpool01) に対して、host A (IPv6, AAAA) レコードが存在している必要があります。
    
      - 外部 DNS レコードの場合は、フロントエンドプールの外部 Web サービス FQDN (たとえば、lyncwebextpool01.contoso.com) に対して、host A (IPv6, AAAA) レコードが存在している必要があります。

6.  内部 DNS レコードの場合は、DNS サーバーのコンソールツリーで、SIP ドメインの [**前方参照ゾーン**] を展開します (たとえば、contoso.com)。
    
    <div>
    

    > [!NOTE]  
    > 外部 DNS レコードを作成する場合は、手順3で既に SIP ドメイン用の<STRONG>前方参照ゾーン</STRONG>が展開されています。

    
    </div>

7.  SIP ドメイン名を右クリックし、[**新しいホスト (A または AAAA)**] をクリックします。

8.  [**名前**] に、次のようにホスト名を入力します。
    
      - 内部の DNS レコードの場合は、内部の自動検出サービス URL のホスト名として「lyncdiscoverinternal」と入力します。
    
      - 外部 DNS レコードの場合は、外部自動検出サービス URL のホスト名として「lyncdiscover」と入力します。
    
    <div>
    

    > [!NOTE]  
    > このドメイン名は、レコードが定義されているゾーンと見なされるため、A レコードの一部として入力する必要はありません。

    
    </div>

9.  [ **Ip アドレス**] に、次のように ip アドレスを入力します。
    
      - 内部 DNS レコードの場合は、ディレクターの内部 Web サービスの IP アドレスを入力します (または、ロードバランサーを使っている場合は、ディレクターロードバランサーの仮想 IP (VIP) を入力します)。
        
        <div>
        

        > [!NOTE]  
        > ディレクターを使用しない場合は、フロントエンドサーバーまたは Standard Edition サーバーの IP アドレスを入力するか、ロードバランサーを使っている場合は、フロントエンドプールのロードバランサーの VIP を入力します。

        
        </div>
    
      - 外部 DNS レコードの場合は、リバースプロキシの外部またはパブリック IP アドレスを入力します。

10. [**ホストの追加**] をクリックし、[ **OK**] をクリックします。

11. 追加のレコードを作成するには、手順8から10を繰り返します。
    
    <div>
    

    > [!IMPORTANT]  
    > 新しい lyncdiscover を作成し、Lync Server 2013 環境でサポートしている各 SIP ドメインの前方参照ゾーンにレコードを lyncdiscoverinternal する必要があります。

    
    </div>

12. (IPv6、AAAA) レコードの作成が完了したら、[**完了**] をクリックします。

</div>

</div>

<span> </span>

</div>

</div>

</div>

