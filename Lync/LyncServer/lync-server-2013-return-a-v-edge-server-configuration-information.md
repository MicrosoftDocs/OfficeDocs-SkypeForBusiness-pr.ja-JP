---
title: 'Lync Server 2013: A/V Edge サーバー構成情報を返す'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Return A/V Edge Server configuration information
ms:assetid: b041f5a4-2387-4075-846c-ec4f99640903
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721850(v=OCS.15)
ms:contentKeyID: 49733783
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ea7d7ed1ef74c092dac60ecfb2f009219564455
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733077"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="return-av-edge-server-configuration-information-in-lync-server-2013"></a>Lync Server 2013 で A/V Edge サーバーの構成情報を返す

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

A/V Edge サービスは、内部ユーザー (組織のネットワークにログオンしているユーザー) が、外部ユーザー (組織のネットワークにログオンしていないユーザー) とオーディオやビデオを共有できるようにするための手段を提供します。 A/V edge サービスは、主に、A/V Edge 構成設定を使用して管理されます。これは、サイトスコープまたはサービスの範囲で構成できます (つまり、個々の A/V Edge サーバー用に構成できます)。

組織で使用されている A/V Edge 構成の設定に関する情報を返すには、Windows PowerShell と CsAVEdgeConfiguration コマンドレットを使用する必要があります。 詳細については、 [CsAVEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration)コマンドレットのヘルプトピックを参照してください。

CsAVEdgeConfiguration コマンドレットから返される情報は、次のようになります。

    Identity              : Global
    MaxTokenLifetime      : 08:00:00
    MaxBandwidthPerUserKb : 10000
    MaxBandwidthPerPortKb : 3000

<div>

## <a name="to-return-information-for-all-your-av-edge-configuration-settings"></a>すべての A/V Edge の構成設定に関する情報を返すには

  - 次のコマンドは、組織で現在使用されているすべての A/V Edge の構成設定に関する情報を返します。
    
        Get-CsAVEdgeConfiguration

</div>

<div>

## <a name="to-return-information-for-site-scoped-av-edge-configuration-settings"></a>サイトスコープの A/V Edge の構成設定に関する情報を返すには

  - A/V Edge の構成設定の特定のコレクションに関する情報を返すには、CsAVEdgeConfiguration コマンドレットを実行するときにそのコレクションの Id を指定します。 たとえば、次のコマンドは、Redmond サイトに適用されている設定についてのみ情報を返します。
    
        Get-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-return-information-for-service-scoped-av-edge-configuration-settings"></a>サービススコープの A/V Edge の構成設定に関する情報を返すには

  - このコマンドは、特定の A/V エッジサーバーに適用された設定についてのみ情報を返します。
    
        Get-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での A/V Edge サーバー構成設定のコレクションを作成または変更する](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  
[Lync Server 2013 での既存の A/V エッジサーバー構成の設定を削除する](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[Lync Server 2013 の音声/ビデオ (A/V) エッジサーバー](lync-server-2013-audio-video-a-v-edge-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

