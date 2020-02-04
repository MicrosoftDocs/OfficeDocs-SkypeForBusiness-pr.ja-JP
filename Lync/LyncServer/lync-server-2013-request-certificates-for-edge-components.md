---
title: 'Lync Server 2013: エッジ コンポーネントの証明書を要求する'
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
ms.openlocfilehash: 096603b48e6a3636a397c4abf7c19c2b4237f132
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763319"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-certificates-for-edge-components-in-lync-server-2013"></a>Lync Server 2013 でエッジ コンポーネントの証明書を要求する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-11-07_

外部ユーザーアクセスをサポートするために必要な証明書には、パブリック証明機関 (CA) によって発行された証明書と、社内のエンタープライズ CA によって発行された証明書があります。

  - エッジサーバーの外部インターフェイスに必要な証明書とリバースプロキシは、パブリック CA によって発行されている必要があります。

  - 内部インターフェイスに必要な証明書は、公開 CA または内部のエンタープライズ CA のいずれかによって発行できます。 公開証明書を使用するための経費を節約するために、これらの証明書を作成するには、内部の Windows Server 2008 CA、Windows Server 2008 R2 CA、windows server 2012 CA、または Windows Server 2012 R2 CA の使用をお勧めします。

<div>


> [!IMPORTANT]  
> 証明書の要求、特にパブリック Ca への要求を処理するのに時間がかかる場合があるため、エッジサーバーコンポーネントの展開を開始するときに使用できるようにするために、最初にエッジサーバーの証明書を要求する必要があります。 エッジサーバーの証明書の要件の概要については、「 <A href="lync-server-2013-certificate-requirements-for-external-user-access.md">Lync Server 2013 での外部ユーザーアクセスの証明書の要件</A>」を参照してください。



</div>

内部のエッジ証明書にパブリック CA を使用することもできますが、証明書のコストを最小限に抑えるため、その他の証明書には内部のエンタープライズ CA を使用することをお勧めします。 エッジサーバーの証明書の要件の概要については、「 [Lync Server 2013 での外部ユーザーアクセスの証明書の要件](lync-server-2013-certificate-requirements-for-external-user-access.md)」を参照してください。

<div>


> [!NOTE]  
> エッジサーバーをインストールする場合、セットアップには、「 <A href="lync-server-2013-set-up-edge-certificates.md">Lync server 2013 の edge 証明書のセットアップ</A>」セクションで説明されているように、証明書の要求、割り当て、インストールのタスクを容易にする証明書ウィザードが含まれています。 エッジサーバーをインストールする前に証明書を要求する場合 (たとえば、エッジサーバーコンポーネントの実際の展開中に時間を節約する場合など)、証明書がエクスポート可能であり、すべての必須の件名の代替名。 このドキュメントでは、内部サーバーを使用して証明書を要求する手順は説明していません。



</div>

<div>

## <a name="request-certificates-from-a-public-ca"></a>パブリック CA から証明書を要求する

エッジサーバーの展開には、アクセスエッジサービス、Web 会議エッジサービス、A/V 認証サービス用に使用されるエッジサーバーの外部インターフェイスに対して、1つの公開証明書が必要です。 この証明書には、A/V 認証サービスがプール内のすべてのエッジサーバーで同じキーを使用するように、エクスポート可能な秘密キーが必要です。 リバースプロキシは、Microsoft インターネットセキュリティとアクセラレータ (ISA) サーバー2006または Microsoft Forefront Threat Management Gateway 2010 と共に使用されます。また、公開証明書も必要です。

</div>

<div>

## <a name="request-certificates-from-an-internal-enterprise-ca"></a>社内のエンタープライズ CA から証明書を要求する

内部エッジインターフェイスに必要な証明書は、公開証明機関 (CA) または内部 CA のいずれかによって発行できます。 社内のエンタープライズ CA を使用して、証明書のコストを最小限に抑えることができます。 組織に内部 CA が展開されている場合、内部境界の証明書は、内部 CA によって発行される必要があります。 内部のエンタープライズ CA を内部証明書に使用すると、証明書のコストを削減できます。

エッジコンポーネントの証明書の要件の概要については、「 [Lync Server 2013 での外部ユーザーアクセスの証明書の要件](lync-server-2013-certificate-requirements-for-external-user-access.md)」を参照してください。 パブリック CA を使用して証明書を取得する方法について詳しくは、「 [Lync Server 2013 でエッジコンポーネントの証明書を要求](lync-server-2013-request-certificates-for-edge-components.md)する」をご覧ください。 証明書の要求、インストール、割り当ての詳細については、「 [Lync Server 2013 での Edge 証明書のセットアップ](lync-server-2013-set-up-edge-certificates.md)」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

