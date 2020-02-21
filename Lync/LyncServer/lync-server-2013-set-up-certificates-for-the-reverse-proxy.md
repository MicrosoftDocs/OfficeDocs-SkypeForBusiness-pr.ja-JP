---
title: 'Lync Server 2013: リバースプロキシの証明書の設定'
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
ms.openlocfilehash: 9c7a4e6ede9afe8d521d8dea3bd9350801588b90
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182200"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-reverse-proxy-in-lync-server-2013"></a>Lync Server 2013 でリバースプロキシの証明書をセットアップする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-08_

各リバースプロキシサーバーは、リスニングサービスで使用する web サーバー証明書を必要とします。 Web サーバー証明書は、パブリック証明機関 (CA) によって発行される必要があります。

この他の証明書の要件の詳細については、「 [Lync Server 2013 の外部ユーザーアクセスの証明書要件](lync-server-2013-certificate-requirements-for-external-user-access.md)」を参照してください。

<div>

## <a name="to-set-up-a-web-services-certificate-for-the-reverse-proxy"></a>リバースプロキシの Web サービス証明書を設定するには

  - Web サービス証明書の設定を含めて、リバースプロキシを既にセットアップしておく必要があります。 エッジサーバーの展開を開始する前に実行していない場合は、「 [Lync Server 2013 のリバースプロキシサーバーの設定](lync-server-2013-setting-up-reverse-proxy-servers.md)」の手順を使用して要求を作成し、web サービス証明書をインストールしてから、各 web 公開ルールを作成して、証明書を使用するように構成します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

