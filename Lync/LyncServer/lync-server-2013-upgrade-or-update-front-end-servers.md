---
title: 'Lync Server 2013: フロントエンドサーバーのアップグレードまたは更新'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Upgrade or update Front End Servers
ms:assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204736(v=OCS.15)
ms:contentKeyID: 48183597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e4edb5ea009960fe0456f266a428431049f542b
ms.sourcegitcommit: de7e0afbd40bbe52994ab99d85cf9e95ecbc4a6c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2019
ms.locfileid: "37435171"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="upgrade-or-update-front-end-servers-in-lync-server-2013"></a>Upgrade or update Front End Servers in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-06-28_

Enterprise Edition プールのフロントエンドサーバーは、*アップグレードドメイン*として編成されています。 これらは、プール内のフロントエンドサーバーのサブセットです。 アップグレードドメインは、トポロジビルダーによって自動的に作成されます。

サーバーをアップグレードする場合は、一度に1つのアップグレードドメインを使用する必要があります。 各サーバーを1つのアップグレードドメインに移動してアップグレードし、それを再起動してから別のアップグレードドメインに移行します。 これまでにアップグレードしたアップグレードドメインとサーバーを常に把握しておいてください。 各サーバーをアップグレードする場合は、次のフローチャート図を使用します。

:::image type="content" source="images/UpgradeUpdateFrontEndServerslync2013.png" alt-text="フロントエンドサーバーのアップグレードまたは更新":::

<div>

## <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a>プール内のフロントエンド サーバーにアップグレードを適用する

1.  プール内のフロントエンドサーバーで、次のコマンドレットを実行します。
    
    **Get-CsPoolUpgradeReadinessState**
    
    *Poolupgradestate*の値が**Busy**の場合は、10分間待ってから、もう一度**CsPoolUpgradeReadinessState**を試してください。 3回以上連続して [**取り込み中**] と表示されている場合、それぞれの試行の間に10分待ってから、または**InsufficientActiveFrontEnds**の**poolupgradestate**の結果が表示された場合は、プールに問題があります。 このプールが、障害回復トポロジの別のフロントエンドプールとペアリングされている場合は、プールをバックアッププールにフェールオーバーし、このプール内のサーバーを更新する必要があります。 詳細については、「 [Lync Server 2013 でのプールのフェールオーバー](lync-server-2013-failing-over-a-pool.md)」を参照してください。
    
    *Poolupgradestate*の値の準備が**でき**ている場合は、手順2に進みます。

2.  **CsPoolUpgradeReadinessState**コマンドレットは、プール内の各アップグレードドメインについての情報と、各アップグレードドメインに含まれるフロントエンドサーバーについても返します。 アップグレードするサーバーが含まれているアップグレードドメインに対して**ReadyforUpgrade**値が**True**の場合は、これらのサーバーを現在安全にアップグレードできます。 そのためには、次の操作を行います。
    
    1.  アップグレードするフロントエンドサーバーへの新しい接続を停止するには、 `Stop-CsWindowsService -Graceful -Verbose`コマンドレットを使用します。
        
        <div>
        

        > [!NOTE]  
        > スケジュールされたサーバーのダウンタイムにサーバーのアップグレードを実行している場合は、次のように、"-<STRONG>正常</STRONG>" パラメーターを指定せずにこのコマンドレットを実行でき<STRONG>ます。</STRONG> これにより、すべての既存のサービスリクエストがいっぱいになるのを待たずに、すぐにサービスが終了します。

        
        </div>
    
    2.  このアップグレードドメインに関連付けられているサーバーをアップグレードします。
    
    3.  サーバーを再起動して、新しい接続を受け入れていることを確認します。

3.  すべてのフロントエンドサーバーがアップグレードされるまで、プール内の各アップグレードドメインについて、手順1と2を繰り返します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

