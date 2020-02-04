---
title: A/V Edge サーバー構成設定のコレクションを作成または変更する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of A/V Edge Server configuration settings
ms:assetid: 43899518-59c6-4be4-8892-d6f6207bfaab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688039(v=OCS.15)
ms:contentKeyID: 49733630
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c4b45b34b5c52d0eb138fbc16c37e5aaee7262b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763369"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a>Lync Server 2013 での A/V Edge サーバー構成設定のコレクションを作成または変更する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

A/V Edge サービスは、内部ユーザー (組織のネットワークにログオンしているユーザー) が、外部ユーザー (組織のネットワークにログオンしていないユーザー) とオーディオやビデオを共有できるようにするための手段を提供します。 A/V edge サービスは、主に、A/V Edge 構成設定を使用して管理されます。これは、サイトスコープまたはサービスの範囲で構成できます (つまり、個々の A/V Edge サーバー用に構成できます)。

Lync Server をインストールすると、A/V Edge のグローバルコレクションが設定されます。 さらに、Windows PowerShell と CsAVEdgeConfiguration コマンドレットを使用して、サイトのスコープまたはサービスのスコープ (つまり、個別の A/V Edge サーバーの場合) で新しい設定を作成することもできます。 新しい設定を作成する場合は、次の点に注意してください。

  - サービスの範囲 (つまり個々のサーバー) で構成された設定は、すべてのユーザーに対して優先順位を持ちます。

  - サイトのスコープで構成された設定は、グローバルスコープで構成されている設定よりも優先されます。 ただし、サービスの範囲設定は、サイトの範囲設定にも優先されます。

  - グローバルスコープの設定は、個々のサーバーで構成されているサービス設定がなく、そのサーバーが配置されているサイトのサイト設定がない場合にのみ使用されます。

設定を変更するには、CsAVEdgeConfiguration コマンドレットを使用します。 詳細については、 [CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15))および[CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15))コマンドレットのヘルプトピックを参照してください。

<div>

## <a name="to-create-new-av-edge-configuration-settings-at-the-site-scope"></a>新しい A/V Edge の構成設定をサイトのスコープで作成するには

  - 次のコマンドは、Redmond サイトの A/V Edge 構成設定の新しいコレクションを作成します。
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-site-scope"></a>ユーザー設定の A/V Edge の構成設定をサイトのスコープで作成するには

  - 追加のパラメーターが含まれていないため、これらの新しい設定では、A/V Edge サービスの既定値が使用されます。 または、追加のパラメーターとパラメーター値を追加して、カスタムコレクションを作成することもできます。 たとえば、次のコマンドは MaxTokenLifetime プロパティを4時間 (04 時間:00 分:00 秒) に設定します。
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-service-scope"></a>カスタムの A/V Edge の構成設定をサービスのスコープで作成するには

  - このコマンドは、A/V Edge サーバー atl-edge-001.litwareinc.com に適用される同様のコレクションを作成します。
    
        New-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-modify-existing-av-edge-configuration-settings"></a>既存の A/V Edge の構成設定を変更するには

  - この例では、CsAVEdgeConfiguration コマンドレットを使用して、Redmond サイトの最大トークンの有効期間を12時間に変更します。
    
        Set-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "12:00:00"

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 で A/V Edge サーバーの構成情報を返す](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[Lync Server 2013 での既存の A/V エッジサーバー構成の設定を削除する](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[Lync Server 2013 の音声/ビデオ (A/V) エッジサーバー](lync-server-2013-audio-video-a-v-edge-servers.md)  
[新規-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15))  
[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

