---
title: 'Lync Server 2013: DNS インフラストラクチャのサポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Domain Name System (DNS) infrastructure support
ms:assetid: 37777c16-94ce-436d-b517-bcf53a564513
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425850(v=OCS.15)
ms:contentKeyID: 48183878
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9aa9670761e16032abf0c205bbb740cbe1f43c4a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833374"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-infrastructure-support-in-lync-server-2013"></a>Lync Server 2013 での DNS インフラストラクチャのサポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-03-08_

Lync Server 2013 には、ドメインネームシステム (DNS) が必要です。次のような方法で使用します。

  - 内部サーバーまたはサーバー間通信のプールを検出します。

  - クライアントが、さまざまな SIP トランザクションに使用されるフロントエンドプールまたは Standard Edition サーバーを検出できるようにします。

  - 会議の単純な Url を会議をホストしているサーバーに関連付けます。

  - 外部サーバーとクライアントが、エッジサーバーまたはインスタントメッセージング (IM) または会議の HTTP リバースプロキシに接続できるようにします。

  - ログインしていないユニファイドコミュニケーション (UC) デバイスを有効にして、デバイス更新 Web サービスが実行されているフロントエンドプールまたは Standard Edition server を検出し、更新プログラムを入手してログを送信します。

  - モバイルクライアントがデバイス設定で Url を手動で入力する必要なく、Web サービスのリソースを自動的に検出できるようにする。

  - DNS の負荷分散の場合。

<div>


> [!NOTE]  
> Lync Server 2013 は、国際化ドメイン名 (Idn) をサポートしていません。



</div>

<div>


> [!IMPORTANT]  
> 指定する名前が、サーバーで構成されているコンピューター名と同じである必要があります。 既定では、ドメインに参加していないコンピューターのコンピューター名は、完全修飾ドメイン名 (FQDN) ではなく短い名前です。 トポロジ ビルダーでは、短い名前ではなく FQDN を使用します。 そのため、エッジ サーバーとして展開する、ドメインに参加していないコンピューターの名前で DNS サフィックスを構成する必要があります。 Lync Server、エッジ サーバー、およびプールの FQDN を割り当てる場合に使用できる文字は、<STRONG>標準文字のみ</STRONG> (A ～ Z、a ～ z、0 ～ 9、およびハイフン) です。 Unicode 文字およびアンダースコアは使用しないでください。 一般に、外部 DNS および公的 CA では、FQDN に非標準文字はサポートされていません (証明書で FQDN を SN に割り当てることが必要になります)。



</div>

</div>

<span> </span>

</div>

</div>

</div>

