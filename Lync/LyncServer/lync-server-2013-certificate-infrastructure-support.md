---
title: Lync Server 2013 証明書インフラストラクチャのサポート
description: Lync Server 2013 証明書インフラストラクチャのサポート。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate infrastructure support
ms:assetid: 47aa5c95-eb60-4d4b-81d5-7fdaef1a1145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425950(v=OCS.15)
ms:contentKeyID: 48184047
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc08719e5b1c58a4dc3c1cab07db5e9842d46d5c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544233"
---
# <a name="certificate-infrastructure-support-in-lync-server-2013"></a>Lync Server 2013 での証明書インフラストラクチャのサポート

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-11-07_

Lync Server 2013 は、トランスポート層セキュリティ (TLS) と相互 TLS (MTLS) 接続をサポートするために公開キー基盤 (PKI) を必要とします。 既定では、Lync Server 2013 は、クライアントとサーバー間の接続に TLS を使用するように構成されています。 MTLS は、サーバー間の接続に使用されます。

MTLS 証明書は、Lync Server 2013 の信頼された証明機関 (CAs) によって発行される必要があります。 Lync Server は、次の Ca から発行された証明書をサポートしています。

  - 内部 CA から発行される証明書:
    
      - Windows Server 2003 オペレーティングシステムの CA
    
      - Windows Server 2008 オペレーティングシステムの CA
    
      - Windows Server 2008 R2 オペレーティングシステムの CA
    
      - Windows Server 2012 オペレーティングシステムの CA
    
      - Windows Server 2012 R2 オペレーティングシステムの CA

  - パブリック CA から発行される証明書

Exchange 2013 などの他のアプリケーションやサーバーと通信するには、他のアプリケーションと製品でサポートされている証明書が必要です。 2013リリース、Lync Server 2013、および Exchange 2013 および SharePoint Server を含むその他の Microsoft サーバー製品については、サーバー間の認証と承認のための Open Authorization (OAuth) プロトコルをサポートしています。 詳細については、「展開」のドキュメントまたは「操作」のドキュメントの「 [Lync server 2013 でのサーバー間認証 (OAuth) およびパートナーアプリケーションの管理](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) 」を参照してください。

Windows 7 オペレーティングシステム、Windows Server 2008 R2 オペレーティングシステム、および Microsoft Office Communicator 2007 Phone Edition を実行しているクライアントからの接続については、Lync Server 2013 では、SHA-256 暗号化ハッシュ関数を使用して署名された証明書をサポートしていますが、必須ではありません。 SHA-256 を使用する外部アクセスをサポートするには、SHA-256 を使用するパブリック CA が外部証明書を発行する必要があります。

証明書の要件の詳細については、「計画」のドキュメントの「 [Lync Server 2013 の証明書インフラストラクチャ要件](lync-server-2013-certificate-infrastructure-requirements.md) 」を参照してください。 証明書でのワイルドカードの使用の詳細については、「サポート」のドキュメントの「 [Lync Server 2013 でのワイルドカード証明書のサポート](lync-server-2013-wildcard-certificate-support.md) 」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

