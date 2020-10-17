---
title: 'Lync Server 2013: フロントエンドサーバーのアップグレードまたは更新'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Upgrade or update Front End Servers
ms:assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
ms:mtpsurl: https://technet.microsoft.com/library/JJ204736(v=OCS.15)
ms:contentKeyID: 48183597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 32a537dc701f7b3e613cc9364c786cb561cadb50
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530324"
---
# <a name="upgrade-or-update-front-end-servers-in-lync-server-2013"></a>Lync Server 2013 でのフロントエンドサーバーのアップグレードまたは更新

<div data-xmlns="https://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-06-28_

Enterprise Edition プール内のフロントエンド サーバーは、アップグレード ドメイン** にまとめられます。 これらはプール内のフロントエンド サーバーのサブセットです。 アップグレードドメインは、トポロジビルダーによって自動的に作成されます。

サーバーをアップグレードするときには、一度に1つのアップグレードドメインを使用する必要があります。 各サーバーを1つのアップグレードドメインから下に移動し、アップグレードしてから、別のアップグレードドメインに移行する前に再起動します。 これまでにアップグレードしたアップグレードドメインとサーバーを常に追跡してください。 各サーバーをアップグレードする場合は、次のフローチャート図を使用します。

![フロントエンド サーバーのアップグレードまたは更新](images/upgradeupdatefrontendserverslync2013.png)

<div>

## <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a>プール内のフロントエンドサーバーにアップグレードを適用するには

1.  プール内のフロントエンド サーバーで、次のコマンドレットを実行します。
    
    **Get-cspoolupgradereadinessstate 戻し**
    
    *Poolupgradestate*の値が**ビジー**の場合は、10分間待ってからもう一度**get-cspoolupgradereadinessstate 戻し**を実行してください。 少なくとも3回の連続する時間に [**ビジー** ] が表示される場合、各試行の間に10分待機した後、または**Poolupgradestate**の**InsufficientActiveFrontEnds**結果が表示された場合は、プールに問題があります。 このプールが障害復旧トポロジの別のフロントエンド プールとペアになっている場合は、プールをバックアップ プールにフェールオーバーし、そのプール内のサーバーを更新します。 詳細については、「 [Lync Server 2013 でのプールのフェールオーバー](lync-server-2013-failing-over-a-pool.md)」を参照してください。
    
    PoolUpgradeState** の値が **Ready** の場合は、手順 2. に進みます。

2.  **Get-cspoolupgradereadinessstate 戻し**コマンドレットは、プール内の各アップグレードドメインに関する情報、および各アップグレードドメインにあるフロントエンドサーバーについても返します。 アップグレードするサーバーが含まれているアップグレードドメインの **ReadyforUpgrade** 値が **True** の場合は、これらのサーバーをすぐにアップグレードできます。 アップグレードを行うには、次の手順を実行します。
    
    1.  コマンドレットを使用して、アップグレードするフロントエンドサーバーへの新しい接続を停止し `Stop-CsWindowsService -Graceful -Verbose` ます。
        
        <div>
        

        > [!NOTE]  
        > スケジュールされたサーバーのダウンタイム中にこれらのサーバーのアップグレードを実行する場合は、次のように、このコマンドレットを '-<STRONG>正常</STRONG>' パラメーターなしで実行できます。 <STRONG>Stop-cswindowsservice</STRONG>。 これにより、すべての既存のサービス要求がいっぱいになるのを待たずに、直ちにサービスがシャットダウンされます。

        
        </div>
    
    2.  このアップグレードドメインに関連付けられているサーバーをアップグレードします。
    
    3.  サーバーを再起動し、新しい接続を受け入れていることを確認します。

3.  すべてのフロントエンドサーバーがアップグレードされるまで、プール内の他のすべてのアップグレードドメインに対して手順1と2を繰り返します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

