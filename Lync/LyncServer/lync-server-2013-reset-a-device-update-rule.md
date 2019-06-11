---
title: 'Lync Server 2013: デバイス更新ルールをリセットする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reset a Device Update rule
ms:assetid: d1f597e7-dffd-4756-af07-10613a5d8729
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994069(v=OCS.15)
ms:contentKeyID: 51803980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab03c5c28db28ddbd883f3f50845eaf91d4fd1a9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823211"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reset-a-device-update-rule-in-lync-server-2013"></a>Lync Server 2013 でのデバイス更新ルールのリセット

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-23_

テストデバイスで更新プログラムが動作しない場合は、デバイス更新ルールをリセットすることができます。これにより、ルールの保留状態が削除され、テストデバイスから更新プログラムがアンインストールされます。

Lync Server コントロールパネルまたは Windows PowerShell を使用して、デバイス更新ルールを削除することができます。

<div>


> [!NOTE]  
> 既に承認済みの (ロールアウトされた) ルールを復元するには、それを復元します。 詳細については、「 <A href="lync-server-2013-restore-a-device-update-rule.md">Lync Server 2013 でデバイス更新ルールを復元する</A>」を参照してください。



</div>

<div>

## <a name="to-reset-a-device-update-rule-by-using-lync-server-control-panel"></a>Lync Server コントロールパネルを使用してデバイス更新ルールをリセットするには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[**クライアント**] をクリックし、[**デバイスの更新**] ナビゲーションボタンをクリックします。

4.  [**デバイス更新**] ページで、次のいずれかの操作を行います。
    
      - 1つのルールをリセットするには、再設定するルールを選びます。
    
      - すべてのルールをリセットするには、[**編集**] メニューの [**すべて選択**] をクリックします。
    
      - 1つのブランドのすべてのルールをリセットするには、**ブランド**の列メニューを使用します。

5.  [**アクション**] をクリックし、[**保留中の更新をキャンセル**] をクリックします。
    
    <div>
    

    > [!TIP]  
    > キャンセルしたデバイス更新ルールをロールアウトしたくない場合は、削除することをお勧めします。 詳細については、「 <A href="lync-server-2013-remove-a-device-update-rule.md">Lync Server 2013 でデバイス更新ルールを削除する</A>」を参照してください。

    
    </div>

</div>

<div>

## <a name="resetting-a-device-update-rule-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してデバイス更新ルールをリセットする

デバイス更新ルールは、Windows PowerShell と**CsDeviceUpdateRule**コマンドレットを使用してリセットすることもできます。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。

<div>


> [!NOTE]  
> リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください<A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。



</div>

<div>

## <a name="to-reset-a-specific-device-update-rule-on-a-server"></a>サーバー上の特定のデバイス更新ルールをリセットするには

  - 次のコマンドを実行すると、d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 の Web サーバーの atl-cs-001.litwareinc.com のデバイス更新ルールがリセットされます。
    
        Reset-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-reset-all-the-device-update-rules-on-a-server"></a>サーバー上のすべてのデバイス更新ルールをリセットするには

  - このコマンドを実行すると、Web サーバー atl-cs-001.litwareinc.com 上のすべてのデバイス更新ルールがリセットされます。
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"  | Reset-CsDeviceUpdateRule

</div>

<div>

## <a name="to-reset-all-the-device-updates-rules-that-have-a-specific-brand"></a>特定のブランドを持つすべてのデバイス更新ルールをリセットするには

  - この例では、組織全体で、Microsoft と同等のブランドを持つすべてのデバイス更新がリセットされます。
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Reset-CsDeviceUpdateRule

</div>

詳細については、 [CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Reset-CsDeviceUpdateRule)コマンドレットのヘルプトピックを参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でデバイス更新ルールを承認する](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

