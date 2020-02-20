---
title: 'Lync Server 2013: 自動検出のための DNS の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring DNS for Autodiscover
ms:assetid: f07a634c-3cf3-4958-8556-84596319ef54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945656(v=OCS.15)
ms:contentKeyID: 51541528
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 70aa869c353e0acba0d526823f7624334b445767
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151579"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-dns-for-autodiscover-in-lync-server-2013"></a>Lync Server 2013 での自動検出用の DNS の構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-12-12_

Lync クライアントの自動検出をサポートするには、次のドメインネームシステム (DNS) レコードを作成する必要があります。

  - 組織のネットワーク内から接続する Lync クライアントをサポートするための内部 DNS レコード

  - インターネットから接続する Lync クライアントをサポートするための外部 (パブリック) DNS レコード

内部 DNS レコードと外部 DNS レコードは SIP ドメインごとに作成する必要があります。

追加のサブジェクト代替名 (SAN) を使用して新しい証明書を作成する機能に基づいて、DNS レコードを (ホスト) レコードまたは CNAME レコードのいずれかにすることができます。 Lyncdiscover を使用して新しい外部 (パブリック) 証明書を要求および展開できない場合。\<ドメイン名\> SAN で、HTTP/TCP ポート80を使用するための手順を使用します。 次の手順では、内部および外部 DNS レコードを作成する方法を説明します。

<div>

## <a name="to-create-dns-cname-records"></a>DNS CNAME レコードを作成するには

1.  次のように、DNS サーバーにログオンします。
    
      - 内部 DNS レコードを作成するには、Domain Admins グループのメンバーまたは DnsAdmins グループのメンバーとして、ネットワーク内の DNS サーバーにログオンします。
    
      - 外部 DNS レコードを作成するには、パブリック DNS プロバイダーに接続します。

2.  DNS 管理スナップインを開きます。[**スタート**] ボタンをクリックし、[**管理ツール**]、[**DNS**] の順にクリックします。

3.  次のどちらかの操作を行います。
    
      - 内部 DNS レコードの場合、DNS サーバーのコンソール ツリーで、使用する Active Directory ドメイン (例: contoso.local) の [**前方参照ゾーン**] を展開します。
        
        <div>
        

        > [!NOTE]  
        > このドメインは、Lync Server 2013&nbsp;ディレクタープールおよびフロントエンドプールがインストールされている Active Directory ドメインです。

        
        </div>
    
      - 外部 DNS レコードの場合、DNS サーバーのコンソール ツリーで、使用する SIP ドメイン (例: contoso.com) の [**前方参照ゾーン**] を展開します。

4.  ディレクタープールのホスト A レコードが存在することを確認するには、次のようにします。
    
      - 内部 DNS レコードの場合、ホスト A レコードは、ディレクタープールの内部 Web サービス完全修飾ドメイン名 (FQDN) (たとえば、lyncwebdir01.contoso.local) に対して存在する必要があります。
    
      - 外部 DNS レコードの場合、ホスト A レコードは、ディレクタープールの外部 web サービス FQDN (たとえば、lyncwebextdir.contoso.com) に対して存在する必要があります。

5.  次のように、フロントエンドプールのホスト A レコードが存在することを確認します。
    
      - 内部 DNS レコードの場合、ホスト A レコードはフロントエンドプールの内部 Web サービス FQDN (たとえば、: lyncwebpool01.contoso.local) に対して存在する必要があります。
    
      - 外部 DNS レコードの場合、ホスト A レコードはフロントエンドプールの外部 Web サービス FQDN (たとえば、lyncwebextpool01.contoso.com) に対して存在する必要があります。

6.  内部 DNS レコードの場合、DNS サーバーのコンソール ツリーで、使用する SIP ドメイン (例: contoso.com) の [**前方参照ゾーン**] を展開します。
    
    <div>
    

    > [!NOTE]  
    > 外部 DNS レコードを作成する場合、使用する SIP ドメインの [<STRONG>前方参照ゾーン</STRONG>] は手順 3. で既に展開されています。

    
    </div>

7.  SIP ドメイン名を右クリックして、[**新しいエイリアス (CNAME)**] をクリックします。

8.  [**エイリアス名**] に、次のどちらかを入力します。
    
      - 内部 DNS レコードの場合、内部自動検出サービス URL のホスト名として、「lyncdiscoverinternal」と入力します。
    
      - 外部 DNS レコードの場合、自動検出サービスの外部 URL のホスト名として、「lyncdiscover」と入力します。

9.  [**ターゲット ホスト用の完全修飾ドメイン名 (FQDN)**] で、次のどちらかの操作を行います。
    
      - 内部 DNS レコードの場合は、ディレクタープールの内部 Web サービス FQDN (たとえば、lyncwebdir01.contoso.local) を入力または参照し、[ **OK]** をクリックします。
    
      - 外部 DNS レコードの場合は、ディレクタープールの外部 Web サービス FQDN (たとえば、lyncwebextdir.contoso.com) を入力または参照し、[ **OK]** をクリックします。
    
    <div>
    

    > [!NOTE]  
    > ディレクターを使用しない場合は、フロントエンドプールに内部および外部 Web サービスの FQDN を使用します。または、単一サーバーの場合は、フロントエンドサーバーまたは Standard Edition サーバーの FQDN を使用します。

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 2013 環境でサポートされている各 SIP ドメインの前方参照ゾーンで、新しい自動検出 CNAME レコードを作成する必要があります。

    
    </div>

</div>

<div>

## <a name="to-create-dns-a-records"></a>DNS A レコードを作成するには

1.  次のように、DNS サーバーにログオンします。
    
      - 内部 DNS レコードを作成するには、Domain Admins グループのメンバーまたは DnsAdmins グループのメンバーとして、ネットワーク内の DNS サーバーにログオンします。
    
      - 外部 DNS レコードを作成するには、パブリック DNS プロバイダーまたは外部 DNS サーバーに接続します。

2.  DNS 管理スナップインを開きます。[**スタート**] ボタンをクリックし、[**管理ツール**]、[**DNS**] の順にクリックします。

3.  次のどちらかの操作を行います。
    
      - 内部 DNS レコードの場合、DNS サーバーのコンソール ツリーで、使用する Active Directory ドメイン (例: contoso.local) の [**前方参照ゾーン**] を展開します。
        
        <div>
        

        > [!NOTE]  
        > このドメインは、Lync Server 2013&nbsp;ディレクタープールおよびフロントエンドプールがインストールされている Active Directory ドメインです。

        
        </div>
    
      - 外部 DNS レコードの場合、DNS サーバーのコンソール ツリーで、使用する SIP ドメイン (例: contoso.com) の [**前方参照ゾーン**] を展開します。

4.  次のように、ディレクタープールのホスト A (IPv6, AAAA) レコードが存在することを確認します。
    
      - 内部 DNS レコードの場合、ホスト A (IPv6 では AAAA) レコードは、ディレクタープールの内部 Web サービス FQDN (たとえば、lyncwebdir01.contoso.local) に対して存在する必要があります。
    
      - 外部 DNS レコードの場合、ホスト A (IPv6 では AAAA) レコードは、ディレクタープールの外部 Web サービス FQDN (たとえば、lyncwebextdir.contoso.com) に対して存在する必要があります。

5.  次のように、フロントエンドプールのホスト A (IPv6, AAAA) レコードが存在することを確認します。
    
      - 内部 DNS レコードの場合、ホスト A (IPv6 では AAAA) レコードは、フロントエンドプールの内部 Web サービス FQDN (たとえば、: lyncwebpool01.contoso.local) に対して存在する必要があります。
    
      - 外部 DNS レコードの場合、ホスト A (IPv6 では AAAA) レコードは、フロントエンドプールの外部 Web サービス FQDN (たとえば、lyncwebextpool01.contoso.com) に対して存在する必要があります。

6.  内部 DNS レコードの場合、DNS サーバーのコンソール ツリーで、使用する SIP ドメイン (例: contoso.com) の [**前方参照ゾーン**] を展開します。
    
    <div>
    

    > [!NOTE]  
    > 外部 DNS レコードを作成する場合、使用する SIP ドメインの [<STRONG>前方参照ゾーン</STRONG>] は手順 3. で既に展開されています。

    
    </div>

7.  SIP ドメイン名を右クリックして、[**新しいホスト (A または AAAA)**] をクリックします。

8.  [**名前**] に、ホスト名を次のように入力します。
    
      - 内部 DNS レコードの場合、内部自動検出サービス URL のホスト名として、「lyncdiscoverinternal」と入力します。
    
      - 外部 DNS レコードの場合、自動検出サービスの外部 URL のホスト名として、「lyncdiscover」と入力します。
    
    <div>
    

    > [!NOTE]  
    > ドメイン名は、レコードが定義されるゾーンから取られるため、A レコードの一部として入力する必要はありません。

    
    </div>

9.  [**IP アドレス**] に、IP アドレスを次のように入力します。
    
      - 内部 DNS レコードの場合は、ディレクターの内部 Web サービス IP アドレスを入力します (または、ロードバランサーを使用する場合は、ディレクターロードバランサーの仮想 IP (VIP) を入力します)。
        
        <div>
        

        > [!NOTE]  
        > ディレクターを使用しない場合は、フロントエンドサーバーまたは Standard Edition サーバーの IP アドレスを入力するか、ロードバランサーを使用する場合は、フロントエンドプールのロードバランサーの VIP を入力します。

        
        </div>
    
      - 外部 DNS レコードの場合、リバース プロキシの外部またはパブリック IP アドレスを入力します。

10. [**ホストの追加**] をクリックし、[**OK**] をクリックします。

11. 追加の A レコードを作成するには、手順 8. ～ 10. を繰り返します。
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 2013 環境でサポートされている各 SIP ドメインの前方参照ゾーンで、新しい lyncdiscover および lyncdiscoverinternal A レコードを作成する必要があります。

    
    </div>

12. A (IPv6 では AAAA) レコードの作成が完了した後で、[**完了**] をクリックします。

</div>

</div>

<span> </span>

</div>

</div>

</div>

