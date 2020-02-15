---
title: 'Lync Server 2013: エッジコンポーネントの証明書の要求'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request certificates for edge components
ms:assetid: 8c72b877-febc-428f-89dc-389e7a7ac849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398708(v=OCS.15)
ms:contentKeyID: 48184779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10e7a724edd6e68602e4655a783f953ad1e2bc2c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046920"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-certificates-for-edge-components-in-lync-server-2013"></a>Lync Server 2013 のエッジコンポーネントの証明書を要求する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-11-07_

外部ユーザー アクセスのサポートに必要な証明書には、パブリック証明機関 (CA) が発行する証明書および内部のエンタープライズ CA が発行する証明書があります。

  - エッジサーバーとリバースプロキシの外部インターフェイスに必要な証明書は、パブリック CA によって発行される必要があります。

  - 内部インターフェイスに必要な証明書は、パブリック CA または内部のエンタープライズ CA のいずれかによって発行された証明書にすることができます。 公開証明書を使用する費用を節約するためにこれらの証明書を作成するには、内部 Windows Server 2008 CA、windows server 2008 R2 CA、windows server 2012 CA、または Windows Server 2012 R2 CA を使用することをお勧めします。

<div>


> [!IMPORTANT]  
> 証明書要求、特にパブリック CA への要求の処理には時間がかかるため、エッジ サーバーへの証明書は早めに要求して、エッジ サーバー コンポーネントの展開を開始する頃には使用できるようにしておく必要があります。 エッジサーバーの証明書要件の概要については、「 <A href="lync-server-2013-certificate-requirements-for-external-user-access.md">Lync Server 2013 の外部ユーザーアクセスの証明書要件</A>」を参照してください。



</div>

内部エッジの証明書にパブリック CA を使用するという選択肢もありますが、証明書のコストを最小限に抑える代わりに、これらの他の証明書には内部エンタープライズ CA を使用することをお勧めします。 エッジサーバーの証明書要件の概要については、「 [Lync Server 2013 の外部ユーザーアクセスの証明書要件](lync-server-2013-certificate-requirements-for-external-user-access.md)」を参照してください。

<div>


> [!NOTE]  
> エッジサーバーをインストールする場合、セットアップには、「 <A href="lync-server-2013-set-up-edge-certificates.md">Lync server 2013 のエッジ証明書の</A>セットアップ」セクションで説明されているように、証明書の要求、割り当て、およびインストールのタスクを容易にする証明書ウィザードが含まれています。 エッジサーバーをインストールする前に証明書を要求する必要がある場合 (たとえば、エッジサーバーコンポーネントの実際の展開時に時間を節約する場合など)、証明書をエクスポートして、すべてのを含めることができる限り、内部サーバーを使用することができます。必須のサブジェクトの別名。 このドキュメントでは、内部サーバーを使用して証明書を要求する手順については説明しません。



</div>

<div>

## <a name="request-certificates-from-a-public-ca"></a>証明書をパブリック CA に要求する

エッジサーバーの展開では、エッジサーバーの外部インターフェイスに対して単一のパブリック証明書が必要です。これは、アクセスエッジサービス、Web 会議エッジサービス、および音声ビデオ認証サービスに使用されます。 この証明書には、A/V 認証サービスがプール内のすべてのエッジサーバーで同じキーを使用するようにするための、エクスポート可能な秘密キーが必要です。 リバースプロキシは、Microsoft Internet Security and アクセラレーション (ISA) サーバー2006または Microsoft Forefront Threat Management Gateway 2010 で使用されています。また、パブリック証明書も必要です。

</div>

<div>

## <a name="request-certificates-from-an-internal-enterprise-ca"></a>証明書を内部エンタープライズ CA に要求する

内部エッジ インターフェイスに必要な証明書は、パブリック証明機関 (CA) または内部 CA から発行されます。 内部エンタープライズ CA を使用して、証明書のコストを最小限に抑えることができます。 組織で内部 CA が展開されている場合、内部エッジの証明書は内部 CA から発行されます。 内部証明書に内部エンタープライズ CA を使用すると、証明書のコストを削減できます。

エッジコンポーネントの証明書要件の概要については、「 [Lync Server 2013 の外部ユーザーアクセスの証明書要件](lync-server-2013-certificate-requirements-for-external-user-access.md)」を参照してください。 パブリック CA を使用した証明書の取得の詳細については、「 [Lync Server 2013 のエッジコンポーネントの証明書を要求](lync-server-2013-request-certificates-for-edge-components.md)する」を参照してください。 証明書の要求、インストール、および割り当ての詳細については、「 [Lync Server 2013 のエッジ証明書のセットアップ](lync-server-2013-set-up-edge-certificates.md)」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

