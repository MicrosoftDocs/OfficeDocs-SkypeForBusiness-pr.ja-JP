---
title: 'Lync Server 2013: リバース プロキシの証明書の設定'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up certificates for the reverse proxy
ms:assetid: c03a08ec-a67b-4f11-b0d7-6677461beaaa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412938(v=OCS.15)
ms:contentKeyID: 48185291
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe45f9e7d422da53e9dc531721d4b678685eb2b1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764663"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-reverse-proxy-in-lync-server-2013"></a>Lync Server 2013 でのリバース プロキシの証明書の設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-08_

各リバースプロキシサーバーでは、リスニングサービスで使用するために web サーバー証明書が必要です。 Web サーバー証明書は、公開証明機関 (CA) によって発行されている必要があります。

このような証明書の要件の詳細については、「 [Lync Server 2013 の外部ユーザーアクセスの証明書の要件](lync-server-2013-certificate-requirements-for-external-user-access.md)」を参照してください。

<div>

## <a name="to-set-up-a-web-services-certificate-for-the-reverse-proxy"></a>リバースプロキシの Web サービス証明書を設定するには

  - Web サービス証明書のセットアップなど、リバースプロキシを既にセットアップしている必要があります。 エッジサーバーの展開を開始する前に、この操作を行っていない場合は、「 [Lync Server 2013 用のリバースプロキシサーバー](lync-server-2013-setting-up-reverse-proxy-servers.md)をセットアップして web サービスの証明書をインストールする」の手順を実行して、各 web 発行ルールを作成して、証明書を使用するように構成します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

