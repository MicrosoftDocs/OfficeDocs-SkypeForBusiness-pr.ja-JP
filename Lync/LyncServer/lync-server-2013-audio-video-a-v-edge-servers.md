---
title: 'Lync Server 2013: 音声ビデオ (A/V) エッジサーバー'
description: 'Lync Server 2013: 音声ビデオ (A/V) エッジサーバー。'
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
ms.openlocfilehash: d5aefd4516540485b84ba0eb80f1a809d89eba0e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568793"
---
# <a name="audiovideo-av-edge-servers-in-lync-server-2013"></a>Lync Server 2013 の音声ビデオ (A/V) エッジサーバー

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

音声ビデオ エッジ サービスを使用すると、内部ユーザー (組織のネットワークにログオンしているユーザー) は外部ユーザー (組織のネットワークにログオンしていないユーザー) とオーディオおよびビデオを共有できるようになります。音声およびビデオに加え、音声ビデオ エッジ サービスはデスクトップ共有やファイル送信などもサポートします。

音声ビデオ エッジ サービスは主に音声ビデオ エッジ構成を使用して管理されます。これらの設定を使用すると、ポートごとおよびユーザーごとに割り当てる最大帯域幅を管理したり、認証トークンを更新する前に使用できる時間の長さを指定したりすることができます。音声ビデオ エッジ構成設定は、サイトまたは個々の音声ビデオ エッジ サーバーに適用できます。優先する設定のコレクションを判断するときは、以下のガイドを使用します。

  - サービス スコープで (つまり個々のサーバーで) 構成した設定は最優先されます。

  - サイト スコープで構成した設定は、グローバル スコープで構成した設定より優先されます。ただし、サービス スコープ設定はサイトスコープ設定を置き換えます。

  - グローバル スコープで構成した設定は、個々のサーバーで構成されたサービス設定がなく、サーバーが配置されているサイトのサイト設定がない場合にのみ使用されます。

音声ビデオエッジサービスは、Lync Server PowerShell と Get-csavedgeconfiguration コマンドレットを使用してのみ管理できます。

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 での音声ビデオエッジサーバーの構成情報の取得](lync-server-2013-return-a-v-edge-server-configuration-information.md)

  - [Lync Server 2013 での音声ビデオエッジサーバー構成設定のコレクションの作成または変更](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)

  - [Lync Server 2013 の音声ビデオエッジサーバー構成設定の既存コレクションの削除](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

