---
title: 'Lync Server 2013: リバース プロキシのシナリオ'
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
ms.openlocfilehash: 82e1dffa55d6af8d131d3a94710c76277cfa75d9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764965"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scenarios-for-reverse-proxy-in-lync-server-2013"></a>Lync Server 2013 のリバース プロキシのシナリオ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-01-21_

会議とダイヤルインのシンプルな Url、アドレス帳、会議コンテンツ、配布リストの展開、モビリティサービスなどのサービスとリソースへのアクセスを提供するために、Lync Server 2013 で逆プロキシを使用する必要があります。 Lync Server 2013 の一般的なリバースプロキシシナリオでは、外部クライアント (デスクトップクライアントや Lync Web App クライアントなど) がディレクターまたはフロントエンドサーバーの外部 Web サービスにアクセスすることを許可します。

**リバースプロキシと外部 web サービス**

![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")

計画フェーズでは、Lync Server 2013 展開でのリバースプロキシの要件を定義します。 リバースプロキシは、次の外部クライアントの機能にアクセスできるようにします。

  - Microsoft Lync 2013 デスクトップクライアント

  - Microsoft Lync Web App

  - Microsoft Lync Mobile

  - Lync Windows ストア アプリ

Lync Server 2013 の展開を計画する場合は、Lync Server 2013 の実際の要件をリバースプロキシ機能にマップします。

1.  外部クライアントは、ポート TCP 443 上のリバースプロキシに接続し、セキュアソケットレイヤー (SSL) またはトランスポートレイヤーセキュリティ (TLS) を使用します。 Microsoft Lync モバイルクライアントは、ポート TCP 80 に接続できますが、Lync discover サービスへの最初の接続を実行していて、管理者が適切なドメインネームシステム (DNS) CNAME (または alias) レコードを構成している場合にのみ、この操作を受け付けることができます。通信は暗号化されません。

2.  Lync Server 2013 の外部 web サービス (フロントエンドサーバーまたはディレクターに展開) では、ポート TCP 4443 上のリバースプロキシとの接続を想定しており、接続が SSL/TLS であると想定しています。
    
    <div>
    

    > [!IMPORTANT]  
    > 外部 web サービスの既定のリスニングポートとして、HTTP トラフィックの場合は TCP 8080、HTTPS トラフィックの場合は TCP 4443 が推奨されます。 トポロジビルダーでは、既定値を上書きして、外部 web サービスの独自のリッスンポートを定義できます。 逆プロキシは外部の web サービスと通信し、外部クライアントはリバースプロキシと通信することに注意する必要があります。 外部クライアントは、ポート TCP 443 上のリバースプロキシと通信しますが、リバースプロキシがの外部 web サービスと通信するポートを再定義することができます。 トポロジビルダーのオプションを使用して、web サービスの既定のリスニングポートを上書きすると、インフラストラクチャで発生する可能性があるリッスンポートの競合を解決することができます。

    
    </div>

3.  Lync Server 2013 の外部 web サービスは、クライアントが使用しようとしているサービスおよび web サーバーディレクトリを特定するために、クライアントから変更されていないホストヘッダーを要求します。 要求はリバースプロキシから送信された場合と同じように表示される

4.  外部 web サービスでは、定義済みの web サーバー仮想ディレクトリ (vDir) を使って、クライアントに提供されるサービスを提供します。 特定の外部特定の web サービス:
    
      - Web 会議の「会議」
    
      - 電話へのアクセスと電話会議の「ダイヤルイン」の vDir
    
      - Lync Windows ストアアプリ、Lync Mobile、デスクトップクライアント Lync 2013 用の "自動検出" の vDir。 Lync Server 2013 での自動検出は、DNS 名 "lyncdiscover" によって認識されます。
    
      - 定義されていないサービスは、外部の web サービスに直接通話を発信することによって、外部クライアントによってアクセスされます。 たとえば、配布グループの展開 (DLX) とアドレス帳サービス (ABS) は、外部の web サービスと関連する vDirs に直接通話を発信することによってアクセスされます。 クライアントは、vDir への実際のパスを認識し、この情報に基づいて uniform レコードロケーター (URL) を構築します。 クライアントは、のような URL を使ってアドレス帳サービスにアクセスします。`https://externalweb.contoso.com/abs/handler`
    
      - 会議が Lync Server トポロジの一部として定義および構成されている場合の Office Web Apps サーバー
        
        <div>
        

        > [!NOTE]  
        > Office Web Apps サーバーは独立した役割サーバーであり、外部 Web サービスの一部としては構成されていません。 このサーバーは、クライアントアクセス用に個別に公開されます。

        
        </div>

5.  各サービスの SSL ブリッジングを定義します。 外部ポートの TCP 443 は、TCP 4443 の外部 web サービスポートにマッピングされます。 暗号化されていない HTTP の場合、ポート TCP 80 は外部 web サービスポート TCP 8080 にマッピングされます。

6.  Web サーバーリソースを公開するためのリバースプロキシリスナーを計画する

7.  提供されるサービスに基づいて、リバースプロキシ用の証明書を要求して構成します。 正しいサブジェクト代替名で構成されている場合、この証明書はリバースプロキシサーバー上で構成されたすべてのリスナーで共有できます。

リバースプロキシの展開を計画するために利用可能なリソース:

  - [Lync Server 2013 のデータの収集](lync-server-2013-data-collection.md)

  - [証明書の概要 - Lync Server 2013 リバース プロキシ](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [ポートの概要 - Lync Server 2013 のリバース プロキシ](lync-server-2013-port-summary-reverse-proxy.md)

  - [DNS の概要 - Lync Server 2013 でのリバース プロキシ](lync-server-2013-dns-summary-reverse-proxy.md)

</div>

<span> </span>

</div>

</div>

</div>

