---
title: 'Lync Server 2013: 外部ユーザーの接続の確認'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify connectivity for external users
ms:assetid: 5c02bd6e-1c96-448a-a21d-58c9961c6640
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398402(v=OCS.15)
ms:contentKeyID: 48184249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 577ba970e272e2306aae3a587d9ae014ba75ba17
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848239"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-connectivity-for-external-users-in-lync-server-2013"></a>Lync Server 2013 での外部ユーザーの接続の確認

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-19_

外部ユーザーへの接続を検証するには、ユーザーからサーバーおよびアクセスエッジサービスのポートへの接続を確認する必要があります。

構成を確認し、外部ユーザーのアクセスに必要なシナリオに対して適切なメッセージの接続、送受信、受信を行うことができるようにするため<http://www.testocsconnectivity.com>の重要なリソース。リモート接続アナライザーサイト ()。 このサイトは、Microsoft サポートによって管理および管理されます。 リモート接続アナライザーにアクセスするには、ブラウザーで Web サイトを開き、手順に従ってシナリオを選択します。

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a>外部ユーザーと外部アクセスの接続性をテストする

外部ユーザーアクセスのテストには、次のいずれか、またはすべてを含む、組織がサポートしている各種類の外部ユーザーを含める必要があります。

  - 少なくとも1つのフェデレーションドメインのユーザーを対象に、IM、プレゼンス、A/V、およびデスクトップ共有をテストします。

  - 組織でサポートされている各パブリック IM サービスプロバイダーのユーザー (およびプロビジョニングが完了している場合)。

  - 匿名ユーザー。

  - リモートで Lync にログインしていて、VPN を使用していない組織内のユーザー。

これらのテストは、エッジサーバーが次の条件を持つかどうかを決定します。

  - ネットワーク外から telnet クライアントを使用して必要なポートをリッスンする。
    
      - 例: telnet sip.contoso.com 443
    
      - 展開に応じて、エッジサーバーまたはエッジサーバープールで使用しているポートに対して、前のテストを実行します。

  - 正確な外部 DNS 解決を実行する。
    
      - ネットワークの外部から、エッジまたはエッジプールの外部 FQDN のそれぞれについて ping を行います。 Ping が失敗した場合でも、IP アドレスが表示されます。これは、割り当てられているアドレスと比較できます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

