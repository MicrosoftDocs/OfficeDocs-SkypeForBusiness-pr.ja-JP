---
title: 'Lync Server 2013: デバイス更新ルールに関する情報を表示する'
description: 'Lync Server 2013: デバイス更新ルールに関する情報を表示します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View information about Device Update rules
ms:assetid: d6677ca4-024b-4816-8511-8d7630788107
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994077(v=OCS.15)
ms:contentKeyID: 51803988
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4aecfd0dd778b576ea4a672e550f9e27d7ca463e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569633"
---
# <a name="view-information-about-device-update-rules-in-lync-server-2013"></a>Lync Server 2013 でのデバイス更新ルールに関する情報の表示

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

更新プログラムが適用されるデバイスの種類、モデル、およびブランドを含む、既にインポートされているデバイス更新ルールに関する詳細を表示します。更新のバージョンと種類。更新プログラムのロケールとプール。 インポートされたすべてのデバイス更新ルール (承認待ち、展開 (承認済み)、リコール (復元)、および使用しない (リセット) に関する情報を利用できます。 この情報には、Lync Server コントロールパネルまたは Windows PowerShell からアクセスします。

<div>


> [!NOTE]  
> ルールのインポート、承認、リセット、復元、および削除の詳細については、「 <A href="lync-server-2013-device-update-rules.md">Lync Server 2013 のデバイス更新ルール</A>」に記載されているトピックを参照してください。



</div>

<div>

## <a name="to-view-device-update-rules-by-using-lync-server-control-panel"></a>Lync Server コントロールパネルを使用してデバイス更新ルールを表示するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーションバーで [ **クライアント**] をクリックし、[ **デバイスの更新** ] ナビゲーションボタンをクリックします。 インポートされたルールは、[ **デバイスの更新** ] ページに一覧表示されます。

</div>

<div>

## <a name="viewing-device-update-rules-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してデバイス更新ルールを表示する

すべてのデバイス更新ルールに関する詳細情報は、Windows PowerShell および **get-csdeviceupdaterule** コマンドレットを使用して表示することもできます。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。

<div>


> [!NOTE]  
> リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を<A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>で参照してください。



</div>

<div>

## <a name="to-view-all-your-device-update-rules"></a>すべてのデバイス更新ルールを表示するには

  - 次のコマンドは、組織で使用するように構成されているすべてのデバイス更新規則に関する情報を戻します。
    
        Get-CsDeviceUpdateRule
    
    このコマンドは、デバイス更新ルールごとに、次のような情報を返します。
    
        Identity        : Service:WebServer:pool0.vdomain.com/2de8cbf6-9441-4f61-b755-1e4bef1effde
        Id              : 2de8cbf6-9441-4f61-b755-1e4bef1effde
        DeviceType      : UCPhone
        Brand           : Microsoft
        Model           : CPE
        Revision        : A
        Locale          : ENU
        UpdateType      : CPE
        ApprovedVersion :
        RestoreVersion  :
        PendingVersion  : 4.0.7577.4066

</div>

<div>

## <a name="to-view-all-the-device-update-rules-on-a-specific-web-server"></a>特定の web サーバー上のすべてのデバイス更新ルールを表示するには

  - 特定のコンピューターのデバイス更新ルールを表示するには、Filter パラメーターの後にサーバー Id とワイルドカード文字 () を使用し \* ます。 以下に例を示します。
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"

</div>

詳細については、 [get-csdeviceupdaterule](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateRule) コマンドレットのヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

