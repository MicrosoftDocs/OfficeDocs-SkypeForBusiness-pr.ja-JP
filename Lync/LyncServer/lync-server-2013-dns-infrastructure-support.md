---
title: 'Lync Server 2013: DNS インフラストラクチャのサポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Domain Name System (DNS) infrastructure support
ms:assetid: 37777c16-94ce-436d-b517-bcf53a564513
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425850(v=OCS.15)
ms:contentKeyID: 48183878
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 190e0160532ca0ac26ce4f818f260848ea68f0a1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034809"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-infrastructure-support-in-lync-server-2013"></a>Lync Server 2013 での DNS インフラストラクチャのサポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-03-08_

Lync Server 2013 にはドメインネームシステム (DNS) が必要であり、次の方法で使用されます。

  - サーバー間通信用の内部のサーバーまたはプールを検出する。

  - クライアントによる、さまざまな SIP トランザクションに使用されるフロントエンド プールまたは Standard Edition サーバーの検出を有効にする。

  - 会議用の簡易 URL をこれらの会議をホストするサーバーに関連付ける。

  - 外部のサーバーおよびクライアントによる、インスタント メッセージング (IM) または会議用のエッジ サーバーまたは HTTP リバース プロキシへの接続を有効にする。

  - ログインされていない統合コミュニケーション (UC) デバイスによる、デバイス更新 Web サービスを実行しているフロントエンド プールまたは Standard Edition サーバーの検出、更新プログラムの取得、およびログの送信を有効にする。

  - モバイル クライアントによる、ユーザーがデバイスの設定で URL を手動で入力する必要がない、Web サービス リソースの自動検出を有効にする。

  - DNS 負荷分散のため。

<div>


> [!NOTE]  
> Lync Server 2013 は、国際化ドメイン名 (Idn) をサポートしていません。



</div>

<div>


> [!IMPORTANT]  
> 指定する名前が、サーバーに構成されているコンピューター名と同じである必要があります。 既定では、ドメインに参加していないコンピューターのコンピューター名は、完全修飾ドメイン名 (FQDN) ではなく短い名前です。 トポロジ ビルダーでは、短い名前ではなく FQDN を使用します。 そのため、エッジ サーバーとして展開する、ドメインに参加していないコンピューターの名前には、DNS サフィックスを構成する必要があります。 Lync Server、エッジ サーバー、およびプールの FQDN を割り当てる場合に使用できる文字は、<STRONG>標準文字のみ</STRONG> (A ～ Z、a ～ z、0 ～ 9、およびハイフン) です。 Unicode 文字およびアンダースコアは使用しないでください。 一般に、外部 DNS および公的 CA では、FQDN に非標準文字はサポートされていません (証明書で FQDN を SN に割り当てることが必要になります)。



</div>

</div>

<span> </span>

</div>

</div>

</div>

