---
title: 'Lync Server 2013: 外部ユーザーの接続の確認'
description: 'Lync Server 2013: 外部ユーザーの接続を確認します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify connectivity for external users
ms:assetid: 5c02bd6e-1c96-448a-a21d-58c9961c6640
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398402(v=OCS.15)
ms:contentKeyID: 48184249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50ef728157d01b93e7d0b8420442ce083a42b5b2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547093"
---
# <a name="verify-connectivity-for-external-users-in-lync-server-2013"></a>Lync Server 2013 での外部ユーザーの接続の確認

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-19_

外部ユーザーの接続を検証するには、ユーザーからアクセス エッジ サービスのサーバーおよびポートへの接続を確認する必要があります。

構成を確認し、外部ユーザーアクセスが必要とするシナリオに対して適切なメッセージを送受信する機能がリモート接続アナライザーサイト () であることを確認するための貴重なリソースです <http://www.testocsconnectivity.com> 。 サイトは、Microsoft サポートによって管理および管理されます。 リモート接続アナライザーにアクセスするには、ブラウザーでこの Web サイトを開き、指示に従ってシナリオを選択します。

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a>外部ユーザーの接続と外部アクセスをテストするには

外部ユーザー アクセスのテストには、次のいずれかまたはすべてなど、組織がサポートしている各外部ユーザー タイプを含める必要があります。

  - 少なくとも 1 つのフェデレーション ドメインのユーザーと、IM、プレゼンス、音声ビデオ、およびデスクトップ共有のテスト。

  - 組織がサポート (およびプロビジョニングが完了) している各パブリック IM サービス プロバイダーのユーザー。

  - 匿名ユーザー。

  - VPN を使用せずに Lync にリモートでログインする組織内のユーザー。

これらのテストで、エッジ サーバーが次のことを実行しているかどうかを確認します。

  - ネットワーク外から telnet クライアントを使用して必要なポートをリッスンする。
    
      - 例:  telnet sip.contoso.com 443
    
      - 展開に応じて、エッジ サーバーまたはエッジ サーバー プールで使用しているポートで上記のテストを実行します。

  - 正確な外部 DNS 解決を実行する。
    
      - ネットワーク外から、エッジまたはエッジ プールの各外部 FQDN で Ping を実行します。 Ping が失敗した場合でも、IP アドレスを確認できるため、割り当てた IP アドレスと比較できます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

