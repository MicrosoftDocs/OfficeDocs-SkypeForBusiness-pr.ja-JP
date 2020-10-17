---
title: 'Lync Server 2013: Lync Online の顧客との通信を確認する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify communications with a Lync Online customer
ms:assetid: c8287b15-e1bb-4b26-8354-0ec90b2fcfe7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202189(v=OCS.15)
ms:contentKeyID: 48185378
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0269c66ad88f7be7f34874a8e4370fb65b954ccf
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518664"
---
# <a name="verify-communications-with-a-lync-online-customer-in-lync-server-2013"></a>Lync Server 2013 で Lync Online の顧客との通信を確認する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-08_

組織内の Lync ユーザーが Microsoft Lync Online 2010 顧客のユーザーと通信できるようにするには、次の手順を完了している必要があります。

  - すべての前提条件を満たします。 このための作業には、内部サーバーとエッジ サーバーを展開する、組織に対してフェデレーションのサポートを有効にする、ユーザー アカウントを設定するなどがあります。 詳細については、「lync [Server 2013 での Lync Online の顧客とのフェデレーションの前提条件](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md)」を参照してください。

  - 内部展開にドメイン アクセスのサポートを構成します。 これには、Lync Online の顧客のドメインからのアクセスを許可するように、ホストプロバイダエントリを作成し、展開を構成することが含まれます。 詳細については、「 [Lync Server 2013 で Lync Online ドメインのフェデレーションサポートを構成する](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md)」を参照してください。

  - フェデレーションをサポートするようにユーザー アカウントを構成します。 詳細については、「lync [Server 2013 で Lync Online の顧客とのフェデレーションのユーザーアクセスを構成する](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md)」を参照してください。

これらの手順をすべて完了し、Lync Online 2010 お客様の管理者が、組織とのフェデレーションをサポートするオンラインサービスのすべての構成を完了したら、組織内の内部ユーザーと Lync Online のユーザーの間の通信をテストして通信を確認します。 通信が成功しなかった場合は、エッジサーバーのログツールを使用して、問題のトラブルシューティングのためにログとトレースファイルをキャプチャします。 ログツールの使用の詳細については、「操作」のドキュメントの「 [Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md) 」を参照してください。 ログツールの詳細については、TechNet ライブラリの Lync Server 2010 ログツールに関するドキュメントを参照してください [https://go.microsoft.com/fwlink/p/?linkId=199265](https://go.microsoft.com/fwlink/p/?linkid=199265) 。

</div>

<span> </span>

</div>

</div>

</div>

