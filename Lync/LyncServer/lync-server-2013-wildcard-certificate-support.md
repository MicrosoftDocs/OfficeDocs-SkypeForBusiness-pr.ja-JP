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
ms.openlocfilehash: 8a3e64dcfd16212e618a8ebe152bd2516a25b26d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727497"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="wildcard-certificate-support-in-lync-server-2013"></a>Lync Server 2013 のワイルドカード証明書のサポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-03-21_

Lync Server 2013 は、証明書を使って通信の暗号化とサーバー id 認証を提供します。 リバースプロキシ経由の web 公開など、サービスを提供するサーバーの完全修飾ドメイン名 (FQDN) に一致する厳密なサブジェクト代替名 (SAN) エントリは必須ではありません。 このような場合は、ワイルドカード SAN エントリ (一般的には "ワイルドカード証明書" と呼ばれます) の証明書を使用して、公共の証明機関から要求された証明書のコストを削減し、証明書の計画プロセスの複雑さを軽減することができます。.

<div>


> [!WARNING]  
> 統合通信 (UC) デバイス (卓上電話など) の機能を維持するには、展開された証明書を慎重にテストして、ワイルドカード証明書の実装後にデバイスが正常に機能することを確認します。



</div>

ワイルドカードエントリは、どのロールのサブジェクト名 (共通名または CN とも呼ばれます) としてはサポートされません。 SAN でワイルドカードエントリを使用する場合、次のサーバーの役割がサポートされます。

  - <span></span>  
    **リバースプロキシ。**   簡単な URL (会議とダイヤルイン) の発行証明書については、ワイルドカード SAN エントリがサポートされています。

  - <span></span>  
    **リバースプロキシ。**   発行証明書の LYNCDISCOVER の san エントリで、ワイルドカード san エントリがサポートされています。

  - <span></span>  
    **監督。**   簡単な url (会議とダイヤルイン) でのワイルドカードによる san エントリ、およびディレクター web コンポーネントの LyncDiscover と LYNCDISCOVERINTERNAL の san エントリがサポートされています。

  - <span></span>  
    **フロントエンドサーバー (Standard Edition) とフロントエンドプール (Enterprise Edition)。** ワイルドカード SAN エントリは、単純な Url (会議とダイヤルイン) でサポートされています。また、フロントエンド web コンポーネントの LyncDiscover と LyncDiscoverInternal の SAN エントリに対応しています。

  - <span></span>  
    **Exchange ユニファイドメッセージング (UM)。**   サーバーでは、スタンドアロンサーバーとして展開する場合、SAN エントリは使用されません。

  - <span></span>  
    **Microsoft Exchange Server クライアントアクセスサーバー。**   SAN のワイルドカードエントリは、内部と外部のクライアントでサポートされています。

  - <span></span>  
    **同じサーバー上の exchange ユニファイドメッセージング (UM) と Microsoft Exchange Server クライアントアクセスサーバー。**   ワイルドカード SAN エントリがサポートされています。

このトピックでは対処できないサーバーの役割:

  - 内部サーバーの役割 (仲介サーバー、アーカイブおよび監視サーバー、Survivable Branch Appliance、または Survivable ブランチサーバーなどに限定されない)

  - 外部エッジサーバーインターフェイス

  - 内部エッジサーバー
    
    <div>
    

    > [!NOTE]  
    > 内部エッジサーバーインターフェイスの場合、ワイルドカードエントリは SAN に割り当てることができ、サポートされています。 内部エッジサーバー上の SAN は照会されず、ワイルドカード SAN エントリの値が制限されます。

    
    </div>

証明書でのワイルドカードの使用など、証明書の構成の詳細については、次のトピックを参照してください。

  - [Lync Server 2013 の内部サーバーに対する証明書要件](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [Lync Server 2013 における外部ユーザー アクセスに対する証明書要件](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [証明書の概要 - Lync Server 2013 の DNS および HLB による負荷分散](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [証明書の概要 - Lync Server 2013 の単一ディレクター](lync-server-2013-certificate-summary-single-director.md)

  - [証明書の概要 - Lync Server 2013 の拡張ディレクター プール、ハードウェア ロード バランサー](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [証明書の概要 - Lync Server 2013 リバース プロキシ](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [内部設置型ユニファイド メッセージングおよび Lync Server 2013 を統合するためのガイドライン](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

ワイルドカードの使用など、Exchange 用の証明書の構成の詳細については、「Exchange 2013 の製品ドキュメント」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

