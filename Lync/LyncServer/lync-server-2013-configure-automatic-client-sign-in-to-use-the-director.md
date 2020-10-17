---
title: 'Lync Server 2013: ディレクターを使用するように自動クライアント Sign-In を構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Automatic Client Sign-In to use the Director
ms:assetid: 85369ffc-53ae-43be-8a23-84a094faecff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398678(v=OCS.15)
ms:contentKeyID: 48184703
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e174e55a2564dcf60b0405819e2996e4bf3d8f95
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522964"
---
# <a name="configure-automatic-client-sign-in-to-use-the-director-in-lync-server-2013"></a>Lync Server 2013 でディレクターを使用するようにクライアントの自動 Sign-In を構成する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-08_

Lync Server 2013、ディレクター、またはディレクターのプールを展開する場合、ベストプラクティスとして、自動クライアント Sign-In を使用することをお勧めします。 自動クライアントサインイン用に DNS サーバーを構成する方法の詳細については、「計画」のドキュメントの「 [Lync Server 2013 での自動クライアントサインインの dns 要件](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md) 」を参照してください。

自動クライアント サインインを既に展開している場合は、次のセクションを参照してディレクターに構成してください。

<div>

## <a name="single-director-instance"></a>単一のディレクター インスタンス

既に自動クライアント Sign-In を展開していて、フロントエンドサーバーまたはフロントエンドプールを指している場合は、そのディレクターをポイントするように DNS SRV レコードを変更する必要があります。

</div>

<div>

## <a name="director-pool"></a>ディレクター プール

クライアントの自動 Sign-In が既に展開されていて、フロントエンドサーバーまたはフロントエンドプールを指している場合は、そのディレクタープールをポイントするように DNS SRV レコードを変更する必要があります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

