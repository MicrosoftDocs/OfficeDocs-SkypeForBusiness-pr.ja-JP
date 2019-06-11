---
title: Lync Server 2013 の証明書インフラストラクチャのサポート
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate infrastructure support
ms:assetid: 47aa5c95-eb60-4d4b-81d5-7fdaef1a1145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425950(v=OCS.15)
ms:contentKeyID: 48184047
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13e04e2e6746dac9c40eaa6df0c3b33d52c6a547
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840659"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-infrastructure-support-in-lync-server-2013"></a>Lync Server 2013 での証明書インフラストラクチャのサポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-11-07_

Lync Server 2013 では、トランスポート層セキュリティ (TLS) と相互 TLS (MTLS) 接続をサポートするために公開キー基盤 (PKI) が必要です。 既定では、Lync Server 2013 は、クライアントとサーバー間の接続に TLS を使用するように構成されています。 MTLS は、サーバー間の接続に使用されます。

MTLS 証明書は、Lync Server 2013 の信頼された証明機関 (Ca) によって発行される必要があります。 Lync Server は、次の Ca から発行された証明書をサポートしています。

  - 内部 CA から発行された証明書:
    
      - Windows Server 2003 オペレーティングシステム CA
    
      - Windows Server 2008 オペレーティングシステム CA
    
      - Windows Server 2008 R2 オペレーティングシステム CA
    
      - Windows Server 2012 オペレーティングシステム CA
    
      - Windows Server 2012 R2 オペレーティングシステム CA

  - パブリック CA から発行された証明書

他のアプリケーションやサーバー (Exchange 2013 など) との通信には、他のアプリケーションや製品でサポートされている証明書が必要です。 2013リリース、Lync Server 2013、および Exchange 2013 および SharePoint Server を含むその他の Microsoft サーバー製品については、サーバー間の認証と承認のための Open Authorization (OAuth) プロトコルをサポートしています。 詳細については、展開ドキュメントまたは運用マニュアルの「 [Lync server 2013 でサーバー間認証 (OAuth) とパートナーアプリケーションを管理する](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)」を参照してください。

Windows 7 オペレーティングシステム、Windows Server 2008 R2 オペレーティングシステム、および Microsoft Office Communicator 2007 Phone Edition を実行しているクライアントからの接続の場合、Lync Server 2013 は、SHA-256 を使用して署名された証明書をサポートしています (ただし必須ではありません)。暗号化ハッシュ関数。 SHA-256 を使って外部アクセスをサポートするために、外部証明書は SHA-256 を使ってパブリック CA によって発行されます。

証明書の要件の詳細については、「計画ドキュメントの「 [Lync Server 2013 の証明書インフラストラクチャの要件](lync-server-2013-certificate-infrastructure-requirements.md)」を参照してください。 証明書でのワイルドカードの使用の詳細については、サポートドキュメントの「 [Lync Server 2013 でのワイルドカード証明書のサポート](lync-server-2013-wildcard-certificate-support.md)」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

