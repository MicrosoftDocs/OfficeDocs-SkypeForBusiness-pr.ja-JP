---
title: Lync Server 2013 のワイルドカード証明書のサポート
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Wildcard certificate support
ms:assetid: 0bae2aa8-b6dc-46f5-a3be-3fe7581809d4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202161(v=OCS.15)
ms:contentKeyID: 48183382
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 998787b3f052d2271eb2323bcdb71ddc106b57f6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210233"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="wildcard-certificate-support-in-lync-server-2013"></a>Lync Server 2013 でのワイルドカード証明書のサポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-03-21_

Lync Server 2013 は、証明書を使用して通信の暗号化とサーバー id 認証を提供します。 リーバース プロキシ経由の Web 公開など、状況によっては、サービスを提供するサーバーの完全修飾ドメイン名 (FQDN) と一致する厳密なサブジェクトの別名 (SAN) エントリが不要な場合もあります。 そのような場合には、ワイルドカード SAN エントリが含まれる証明書 (一般に "ワイルドカード証明書" といいます) を使用でき、それによって、公的証明機関から請求される証明書コストを削減し、証明書の計画プロセスの複雑さを緩和できます。

<div>


> [!WARNING]  
> 統合コミュニケーション (UC) デバイス (電話など) の機能を保持するには、展開された証明書を十分にテストして、ワイルカード証明書を実装した後もデバイスが正しく動作することを確認してください。



</div>

サブジェクト名 (共通名 (CN) ともいいます) としてのワイルドカード エントリは、どの役割でもサポートされません。SAN のワイルドカード エントリ使用は、次のサーバーの役割でサポートされます。

  - <span></span>  
    **リバースプロキシ。**   簡単な URL (会議とダイヤルイン) 発行証明書では、ワイルドカード SAN エントリがサポートされています。

  - <span></span>  
    **リバースプロキシ。**   発行証明書の LYNCDISCOVER の san エントリでは、ワイルドカード san エントリがサポートされています。

  - <span></span>  
    **ディレクター。**   シンプルな url (会議とダイヤルイン)、およびディレクター web コンポーネントの LyncDiscover および LYNCDISCOVERINTERNAL の san エントリに対して、ワイルドカード SAN エントリがサポートされています。

  - <span></span>  
    **フロントエンドサーバー (Standard Edition) およびフロントエンドプール (Enterprise Edition)。** 簡単な Url (会議とダイヤルイン)、およびフロントエンド web コンポーネントの LyncDiscover および LyncDiscoverInternal の SAN エントリに対して、ワイルドカード SAN エントリがサポートされています。

  - <span></span>  
    **Exchange ユニファイドメッセージング (UM)。**   スタンドアロンサーバーとして展開されている場合、サーバーは SAN エントリを使用しません。

  - <span></span>  
    **Microsoft Exchange Server クライアントアクセスサーバー。**   SAN のワイルドカードエントリは、内部クライアントと外部クライアントでサポートされています。

  - <span></span>  
    **同じサーバー上の exchange ユニファイドメッセージング (UM) と Microsoft Exchange Server クライアントアクセスサーバー。**   ワイルドカード SAN エントリがサポートされています。

次のサーバーの役割は、このトピックの対象外です。

  - 内部サーバーの役割 (仲介サーバー、アーカイブおよび監視サーバー、存続可能ブランチアプライアンス、または存続可能ブランチサーバーに制限はありません)

  - 外部エッジサーバーのインターフェイス

  - 内部エッジサーバー
    
    <div>
    

    > [!NOTE]  
    > 内部エッジサーバーインターフェイスでは、ワイルドカードエントリを SAN に割り当てることができ、サポートされています。 内部エッジサーバー上の SAN はクエリされず、ワイルドカード SAN エントリの値が制限されます。

    
    </div>

証明書にワイルドカードを使用するなど、証明書の構成の詳細については、以下のトピックを参照してください。

  - [Lync Server 2013 の内部サーバーの証明書要件](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [Lync Server 2013 での外部ユーザーアクセスの証明書要件](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [証明書の概要-Lync Server 2013 での DNS および HLB の負荷分散](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [証明書の概要-Lync Server 2013 の単一ディレクター](lync-server-2013-certificate-summary-single-director.md)

  - [証明書の概要-Lync Server 2013 の拡張ディレクタープール、ハードウェアロードバランサー](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [証明書の概要-Lync Server 2013 のリバースプロキシ](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [オンプレミスのユニファイドメッセージングと Lync Server 2013 を統合するためのガイドライン](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

ワイルドカードの使用を含む、Exchange 用の証明書の構成の詳細については、「Exchange 2013 製品のドキュメント」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

