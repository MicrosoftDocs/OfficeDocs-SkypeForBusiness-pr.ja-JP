---
title: 'Lync Server 2013: デバイス更新ルールをリセットする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reset a Device Update rule
ms:assetid: d1f597e7-dffd-4756-af07-10613a5d8729
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994069(v=OCS.15)
ms:contentKeyID: 51803980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68162e0661090ac57bfaacecfd22eea1261911e8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144864"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="reset-a-device-update-rule-in-lync-server-2013"></a>Lync Server 2013 でのデバイス更新ルールのリセット

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

テストデバイスで更新プログラムが動作しないようにするには、デバイス更新ルールをリセットします。これにより、ルールの保留状態が削除され、テストデバイスから更新プログラムがアンインストールされます。

デバイス更新ルールを削除するには、Lync Server コントロールパネルまたは Windows PowerShell を使用します。

<div>


> [!NOTE]  
> 既に承認されている (つまり、ロールアウトされた) ルールをアンインストールするには、それを復元します。 詳細については、「 <A href="lync-server-2013-restore-a-device-update-rule.md">Lync Server 2013 でのデバイス更新ルールの復元</A>」を参照してください。



</div>

<div>

## <a name="to-reset-a-device-update-rule-by-using-lync-server-control-panel"></a>Lync Server コントロールパネルを使用してデバイス更新ルールをリセットするには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーションバーで [**クライアント**] をクリックし、[**デバイスの更新**] ナビゲーションボタンをクリックします。

4.  [**デバイスの更新**] ページで、次のいずれかの操作を行います。
    
      - 1つのルールをリセットするには、リセットするルールを選択します。
    
      - すべてのルールをリセットするには、[**編集**] メニューの [**すべて選択**] をクリックします。
    
      - 1つのブランドのすべてのルールをリセットするには、[**ブランド**] 列メニューを使用します。

5.  [**アクション**] をクリックし、[**保留中の更新の取り消し**] をクリックします。
    
    <div>
    

    > [!TIP]  
    > 取り消したデバイス更新ルールをロールアウトしたくない場合は、それらを削除することをお勧めします。 詳細については、「 <A href="lync-server-2013-remove-a-device-update-rule.md">Remove a Device Update rule In Lync Server 2013</A>」を参照してください。

    
    </div>

</div>

<div>

## <a name="resetting-a-device-update-rule-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してデバイス更新ルールをリセットする

デバイス更新ルールは、Windows PowerShell と**get-csdeviceupdaterule**コマンドレットを使用してリセットすることもできます。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。

<div>


> [!NOTE]  
> リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を<A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>で参照してください。



</div>

<div>

## <a name="to-reset-a-specific-device-update-rule-on-a-server"></a>サーバー上の特定のデバイス更新ルールをリセットするには

  - 次のコマンドは、d5ce3c10-2588-420a-82ac-dc2d9b1222ff9-82ac-82ac-dc2d9b1222ff9 on the Web server atl-cs-001.litwareinc.com のデバイス更新ルールをリセットします。
    
        Reset-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-reset-all-the-device-update-rules-on-a-server"></a>サーバー上のすべてのデバイス更新ルールをリセットするには

  - このコマンドは、Web サーバー atl-cs-001.litwareinc.com 上のすべてのデバイス更新ルールをリセットします。
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"  | Reset-CsDeviceUpdateRule

</div>

<div>

## <a name="to-reset-all-the-device-updates-rules-that-have-a-specific-brand"></a>特定のブランドを持つすべてのデバイス更新ルールをリセットするには

  - この例では、Microsoft と同等のブランドを持つ、組織全体のすべてのデバイス更新がリセットされます。
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Reset-CsDeviceUpdateRule

</div>

詳細については、 [get-csdeviceupdaterule](https://docs.microsoft.com/powershell/module/skype/Reset-CsDeviceUpdateRule)コマンドレットのヘルプトピックを参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのデバイス更新ルールの承認](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

