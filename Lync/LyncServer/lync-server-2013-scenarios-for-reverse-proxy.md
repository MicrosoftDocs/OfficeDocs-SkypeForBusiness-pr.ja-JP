---
title: 'Lync Server 2013: リバースプロキシのシナリオ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scenarios for reverse proxy
ms:assetid: 13108f59-a660-4ff1-8404-079d1cb646f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204691(v=OCS.15)
ms:contentKeyID: 48183468
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82d5874393e69083ee7058e4e737d21a2fe865ad
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144185"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scenarios-for-reverse-proxy-in-lync-server-2013"></a>Lync Server 2013 のリバースプロキシのシナリオ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-01-21_

会議およびダイヤルインの簡易 Url、アドレス帳、会議コンテンツ、配布リストの拡張、モビリティサービスなどのサービスやリソースへのアクセスを提供するには、Lync Server 2013 でリバースプロキシが必要です。 Lync Server 2013 の一般的なリバースプロキシシナリオは、外部クライアント (たとえば、デスクトップクライアントや Lync Web App クライアント) がディレクターまたはフロントエンドサーバーの外部 Web サービスにアクセスできるようにすることです。

**リバースプロキシと外部 web サービス**

![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")

計画フェーズでは、Lync Server 2013 の展開でリバースプロキシの要件を定義します。 リバースプロキシは、以下の外部クライアントの機能にアクセスできるようにします。

  - Microsoft Lync 2013 デスクトップクライアント

  - Microsoft Lync Web App

  - Microsoft Lync Mobile

  - Lync Windows ストアアプリ

Lync Server 2013 の展開を計画する場合は、Lync Server 2013 の実際の要件をリバースプロキシ機能にマッピングします。

1.  外部クライアントはポート TCP 443 上のリバースプロキシに接続し、secure socket layer (SSL) またはトランスポート層セキュリティ (TLS) を使用します。 Microsoft Lync Mobile クライアントは、ポート TCP 80 で接続できますが、Lync discovery services への最初の接続を実行し、管理者が正しいドメインネームシステム (DNS) の CNAME (またはエイリアス) レコードを構成している場合に限り、この通信は暗号化されません。

2.  Lync Server 2013 (フロントエンドサーバーまたはディレクターに展開された) 外部 web サービスは、ポート TCP 4443 上のリバースプロキシからの接続を想定しており、接続が SSL/TLS であると想定しています。
    
    <div>
    

    > [!IMPORTANT]  
    > 外部 web サービスに対して推奨される既定のリスニングポートは、HTTP トラフィックの場合は TCP 8080、HTTPS トラフィックの場合は TCP 4443 です。 トポロジビルダーでは、既定値を上書きし、外部 web サービス用に独自のリスニングポートを定義できます。 リバースプロキシが外部 web サービスと通信し、外部クライアントがリバースプロキシと通信することに注意することが重要です。 外部クライアントはポート TCP 443 でリバースプロキシと通信しますが、リバースプロキシがの外部 web サービスと通信するポートを再定義することができます。 トポロジビルダーのオプションを使用して web サービスの既定のリスニングポートを上書きすると、インフラストラクチャで発生する可能性があるリスニングポートの競合を解決できます。

    
    </div>

3.  Lync Server 2013 外部 web サービスは、クライアントが使用しようとしているサービスと web サーバーディレクトリを識別するために、クライアントからの変更されていないホストヘッダーを要求します。 要求はリバースプロキシから送信されたものとして表示される必要がある

4.  外部 web サービスは、クライアントに提供されるサービスを提供する定義済みの web サーバー仮想ディレクトリ (vDir) を使用します。 特定の外部的に識別可能な web サービスは次のとおりです。
    
      - Web 会議会議の "会議" という vDir
    
      - 電話によるアクセスと電話会議のための "ダイヤルイン" vDir
    
      - Lync Windows ストアアプリ、Lync Mobile、およびデスクトップクライアント Lync 2013 の "自動検出" vDir。 Lync Server 2013 の自動検出は、DNS 名 "lyncdiscover" によって認識されます。
    
      - 定義されていないサービスは、外部の web サービスへの直接の呼び出しによって外部クライアントによってアクセスされます。 たとえば、配布グループの展開 (DLX) とアドレス帳サービス (ABS) は、外部 web サービスへの直接呼び出しまたは関連付けられた vDirs によってアクセスされます。 クライアントは、vDir への実際のパスを知っており、この情報に基づいて uniform record locator (URL) を構築します。 クライアントは、のような URL を使用してアドレス帳サービスにアクセスします。`https://externalweb.contoso.com/abs/handler`
    
      - 会議が Lync Server トポロジの一部として定義および構成されている場合の Office Web Apps サーバー
        
        <div>
        

        > [!NOTE]  
        > Office Web Apps サーバーは個別の役割サーバーであり、外部 Web サービスの一部として構成されていません。 このサーバーは、クライアントアクセスに対して個別に公開されています。

        
        </div>

5.  各サービスの SSL ブリッジを定義します。 外部ポートの TCP 443 は、TCP 4443 の外部 web サービスポートにマップされます。 暗号化されていない HTTP の場合、ポート TCP 80 が外部 web サービスポート TCP 8080 にマップされます。

6.  Web サーバーリソースを発行するためのリバースプロキシリスナーを計画する

7.  提供されるサービスに基づいて、リバースプロキシの証明書を要求して構成します。 正しいサブジェクトの別名を使用して構成されている場合、この証明書はリバースプロキシサーバー上の構成されたすべてのリスナーで共有できます。

リバース プロキシの展開を計画するために使用できるリソースを次に示します。

  - [Lync Server 2013 のデータ収集](lync-server-2013-data-collection.md)

  - [証明書の概要-Lync Server 2013 のリバースプロキシ](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [ポートの概要-Lync Server 2013 のリバースプロキシ](lync-server-2013-port-summary-reverse-proxy.md)

  - [DNS の概要-Lync Server 2013 のリバースプロキシ](lync-server-2013-dns-summary-reverse-proxy.md)

</div>

<span> </span>

</div>

</div>

</div>

