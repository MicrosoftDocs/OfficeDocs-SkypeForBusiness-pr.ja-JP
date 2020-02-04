---
title: 'Lync Server 2013: 音声/ビデオ (A/V) エッジサーバー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Audio/Video (A/V) Edge Servers
ms:assetid: b0cc538b-77eb-47fb-be82-5ab0631c6219
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721852(v=OCS.15)
ms:contentKeyID: 49733785
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c99cc3522c13ece937c6e2a0ba06f995431e08d8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722647"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiovideo-av-edge-servers-in-lync-server-2013"></a>Lync Server 2013 の音声/ビデオ (A/V) エッジサーバー

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

A/V Edge サービスは、内部ユーザー (組織のネットワークにログオンしているユーザー) が、外部ユーザー (組織のネットワークにログオンしていないユーザー) とオーディオやビデオを共有できるようにするための手段を提供します。 オーディオとビデオに加えて、A/V Edge サービスでは、デスクトップ共有やファイル転送などの機能もサポートしています。

A/V Edge サービスは、主に、A/V Edge 構成を使って管理されます。これらの設定では、1つのポートとユーザーごとに割り当てることができる帯域幅の最大量を管理できます。また、そのトークンが更新されるまでに認証トークンを使うことができる時間の長さを指定します。 A/V Edge の構成設定は、サイトまたは個々の A/V エッジサーバーに適用できます。 優先される設定のコレクションを決定する際には、次のガイドを使用します。

  - サービスの範囲 (つまり個々のサーバー) で構成された設定は、すべてのユーザーに対して優先順位を持ちます。

  - サイトのスコープで構成された設定は、グローバルスコープで構成されている設定よりも優先されます。 ただし、サービスの範囲設定は、サイトの範囲設定にも優先されます。

  - グローバルスコープの設定は、個々のサーバーで構成されているサービス設定がなく、そのサーバーが配置されているサイトのサイト設定がない場合にのみ使用されます。

A/V Edge サービスを管理するには、Lync Server PowerShell と CsAVEdgeConfiguration コマンドレットを使用する必要があります。

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 で A/V Edge サーバーの構成情報を返す](lync-server-2013-return-a-v-edge-server-configuration-information.md)

  - [Lync Server 2013 での A/V Edge サーバー構成設定のコレクションを作成または変更する](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)

  - [Lync Server 2013 での既存の A/V エッジサーバー構成の設定を削除する](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

