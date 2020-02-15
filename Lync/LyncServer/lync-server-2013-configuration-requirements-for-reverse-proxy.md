---
title: 'Lync Server 2013: リバースプロキシの構成要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration requirements for reverse proxy
ms:assetid: c37d688a-28e4-4822-80cc-6add59c71052
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945651(v=OCS.15)
ms:contentKeyID: 51541518
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efa0124bb66974755a7cae0ab799dc66cc48fd1e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040535"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuration-requirements-for-reverse-proxy-in-lync-server-2013"></a>Lync Server 2013 でのリバースプロキシの構成要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-03-05_

Lync Server 2013 は、ディレクター、ディレクタープール、フロントエンドサーバー、またはフロントエンドプールでホストされている外部 Web サービスに渡される、外部クライアントからの通信に関していくつかの要件を課しています。 また、リバースプロキシは、ユーザーに電話会議を提供している場合は、Office Web Apps サーバーを公開する役割も担います。

<div>


> [!NOTE]  
> Lync Server 2013 では、使用する必要がある特定のリバースプロキシが指定されていません。 Lync Server 2013 では、リバースプロキシが実行できる運用要件のみが定義されています。 通常、インフラストラクチャに既に展開されているリバースプロキシが要件を満たすことができる場合があります。



</div>

<div>

## <a name="reverse-proxy-requirements"></a>リバース プロキシの要件

Lync Server 2013 によって実行されるリバースプロキシが必要とする機能の操作は次のとおりです。

  - Secure socket layer (SSL) とトランスポート層セキュリティ (TLS) を使用します。これは、パブリック証明機関から取得した証明書を使用して、ディレクター、ディレクタープール、フロントエンドサーバー、またはフロントエンドプールの公開された外部 Web サービスに接続することによって実装されます。 ディレクターおよびフロントエンドサーバーは、ハードウェアロードバランサーを使用して負荷分散されたプールに配置できます。

  - 暗号化用の証明書を使用して内部 Web サイトを公開するか、必要に応じて暗号化されていない方法で公開することができます。

  - 完全修飾ドメイン名 (FQDN) を使用して、内部でホストされている web サイトを外部に公開できます。

  - ホストされている web サイトのすべてのコンテンツを公開できます。 既定では、ほとんどの web ** / **サーバーで認識されるディレクティブを使用して、"web サーバー上のすべてのコンテンツを公開" という意味を持つことができます。 また、ディレクティブ ( **/Uwca/\*** など) を変更することもできます。これは、「仮想ディレクトリの下にあるすべてのコンテンツを公開する」という意味です。

  - 公開された web サイトのコンテンツを要求するクライアントとの Secure Sockets Layer (SSL) またはトランスポート層セキュリティ (TLS) 接続が必要な場合は、構成する必要があります。

  - サブジェクトの別名 (SAN) エントリで証明書を受け取る必要があります。

  - 外部 web サービスの FQDN が解決されるリスナーまたはインターフェイスに証明書のバインドを許可できる必要があります。 リスナー構成は、インターフェイスに推奨されます。 多くのリスナーは、1つのインターフェイスで構成できます。

  - ホストヘッダー処理の構成を許可する必要があります。 多くの場合、要求元のクライアントによって送信される元のホストヘッダーは、リバースプロキシによって変更されるのではなく、透過的に渡される必要があります。

  - 外部で定義された1つのポート (たとえば、tcp 443) から別の定義済みポート (たとえば、TCP 4443) への SSL および TLS トラフィックのブリッジ。 リバースプロキシは、受信時にパケットの暗号化を解除し、送信時にパケットを再度暗号化することができます。

  - 1つのポート (たとえば、tcp 80) から別のポート (たとえば、TCP 8080) への暗号化されていない TCP トラフィックのブリッジ。

  - NTLM 認証の構成を許可するか、認証を行わずに認証を行い、パススルー認証を許可します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

