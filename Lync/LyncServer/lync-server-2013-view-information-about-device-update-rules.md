---
title: 'Lync Server 2013: デバイス更新ルールに関する情報を表示する'
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
ms.openlocfilehash: 6e26b67aba2bf792b3248e7771f938a8bced1668
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765658"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-information-about-device-update-rules-in-lync-server-2013"></a>Lync Server 2013 でのデバイス更新ルールに関する情報を確認する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

更新が適用されるデバイスの種類、モデル、およびブランドを含む、既にインポートされているデバイス更新ルールについての詳細を表示します。更新プログラムのバージョンと種類更新プログラムのロケールとプール。 インポートされたすべてのデバイス更新ルール (承認待ち、展開済み、承認済み)、リコール (復元)、および使用しないことを決定したもの (リセット) に関する情報を利用できます。 Lync Server コントロールパネルまたは Windows PowerShell から、この情報にアクセスします。

<div>


> [!NOTE]  
> 仕分けルールのインポート、承認、リセット、復元、および削除を行う方法の詳細については、「 <A href="lync-server-2013-device-update-rules.md">Lync Server 2013 のデバイス更新ルール</A>」に記載されているトピックを参照してください。



</div>

<div>

## <a name="to-view-device-update-rules-by-using-lync-server-control-panel"></a>Lync Server コントロールパネルを使用してデバイス更新ルールを表示するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[**クライアント**] をクリックし、[**デバイスの更新**] ナビゲーションボタンをクリックします。 インポートしたルールは、[**デバイスの更新**] ページに一覧表示されます。

</div>

<div>

## <a name="viewing-device-update-rules-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用したデバイス更新ルールの表示

すべてのデバイス更新ルールに関する詳細情報は、Windows PowerShell と**CsDeviceUpdateRule**コマンドレットを使用して表示することもできます。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。

<div>


> [!NOTE]  
> リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を<A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>で参照してください。



</div>

<div>

## <a name="to-view-all-your-device-update-rules"></a>すべてのデバイス更新ルールを表示するには

  - 次のコマンドは、組織で使用するように構成されているすべてのデバイス更新規則に関する情報を返します。
    
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

## <a name="to-view-all-the-device-update-rules-on-a-specific-web-server"></a>特定の web サーバーですべてのデバイス更新ルールを表示するには

  - 特定のコンピューターでデバイス更新ルールを表示するには、フィルターパラメーターの後にサーバー Id とワイルドカード文字 (\*) を使用します。 次に例を示します。
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"

</div>

詳細については、 [CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateRule)コマンドレットのヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

