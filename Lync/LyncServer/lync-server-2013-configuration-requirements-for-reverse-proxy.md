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
ms.openlocfilehash: 37a2a535ddaa90efa2f4140236b52788fa58e41a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741377"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuration-requirements-for-reverse-proxy-in-lync-server-2013"></a>Lync Server 2013 でのリバースプロキシの構成要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-03-05_

Lync Server 2013 は、ディレクター、ディレクタープール、フロントエンドサーバー、フロントエンドプールでホストされる外部の Web サービスに渡される外部クライアントからの通信について、いくつかの要件を課しています。 リバースプロキシは、ユーザーに会議を提供している場合は、Office Web Apps サーバーを公開する責任も担います。

<div>


> [!NOTE]  
> Lync Server 2013 は、使用する必要がある特定のリバースプロキシを指定していません。 Lync Server 2013 では、リバースプロキシが実行できる運用要件のみが定義されています。 通常、インフラストラクチャに既に展開されている逆プロキシは、要件を満たすことができます。



</div>

<div>

## <a name="reverse-proxy-requirements"></a>プロキシのリバース要件

Lync Server 2013 がリバースプロキシを実行することを期待する機能操作は、次のとおりです。

  - セキュリティで保護されたソケットレイヤー (SSL) とトランスポート層セキュリティ (TLS) を使用するには、パブリック証明機関から取得した証明書を使用して、ディレクター、ディレクタープール、フロントエンドサーバー、またはフロントエンドプールの公開された外部 Web サービスに接続します。 ディレクターとフロントエンドサーバーは、ハードウェアロードバランサーを使って、負荷分散プールに存在することができます。

  - 暗号化用の証明書を使って内部 Web サイトを公開したり、必要に応じて暗号化されていない方法で公開したりすることができます。

  - 完全修飾ドメイン名 (FQDN) を使用して、内部でホストされた web サイトを外部で公開することができます。

  - ホストされている web サイトのすべてのコンテンツを公開できます。 既定では、ほとんどの web ** / **サーバーによって認識されるディレクティブを使用できます。これは、web サーバー上のすべてのコンテンツを公開することを意味します。 また、ディレクティブ (たとえば、 **/Uwca/\*** など) を変更することもできます。これは、「仮想ディレクトリのすべてのコンテンツを公開する」という意味です。

  - 公開された web サイトのコンテンツを要求するクライアントとの Secure Sockets Layer (SSL) またはトランスポートレイヤーセキュリティ (TLS) 接続を要求するように構成できる必要があります。

  - サブジェクトの代替名 (SAN) エントリを含む証明書を受け取る必要があります。

  - 外部 web サービスの FQDN で解決されるリスナーまたはインターフェイスへの証明書のバインドを許可する必要があります。 インターフェイスの構成よりリスナーの構成をお勧めします。 多くのリスナーは、単一のインターフェイスで構成できます。

  - ホストヘッダー処理の構成が許可されている必要があります。 通常、要求側のクライアントによって送信された元のホストヘッダーは、リバースプロキシによって変更されるのではなく、透過的に渡す必要があります。

  - 外部定義のポート (たとえば、TCP 443) から別の定義済みポート (TCP 4443 など) への SSL および TLS トラフィックのブリッジ。 リバースプロキシは、受信時にパケットの暗号化を解除し、送信時にパケットを再度暗号化することができます。

  - 1つのポート (たとえば、TCP 80) から別のポート (TCP 8080 など) への暗号化されていない TCP トラフィックのブリッジ。

  - NTLM 認証、認証、パススルー認証を許可しません。

</div>

</div>

<span> </span>

</div>

</div>

</div>

