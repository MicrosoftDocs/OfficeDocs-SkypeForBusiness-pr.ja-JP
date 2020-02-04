---
title: 'Lync Server 2013: アーカイブ構成の削除'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting an Archiving configuration
ms:assetid: a8744d39-5cf2-474c-9a99-a0f3a37f846f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205167(v=OCS.15)
ms:contentKeyID: 48185093
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e4a0c1acf9f605fc927d7006ff50b1f4470c68d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763121"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-an-archiving-configuration-in-lync-server-2013"></a>Lync Server 2013 でアーカイブ構成を削除する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

サイト構成またはプール構成を削除できます。 グローバル構成を削除することはできません。 グローバル構成を削除すると、グローバル構成は自動的に既定値にリセットされます。 アーカイブ構成の実装方法について詳しくは、「指定できるオプションやアーカイブ構成の階層」をご覧ください。「計画ドキュメント、展開ドキュメント、または操作のドキュメントでの[Lync Server 2013 でのアーカイブの動作](lync-server-2013-how-archiving-works.md)」を参照してください。

<div>

## <a name="to-delete-a-site-or-pool-configuration-for-archiving"></a>アーカイブ用のサイトまたはプールの構成を削除するには

1.  CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。

4.  アーカイブ構成のリストで、削除するサイトまたはプールの構成をクリックし、[**編集**] をクリックして、[**削除**] をクリックします。

5.  [**コミット**] をクリックします。

</div>

<div>

## <a name="removing-archiving-configuration-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してアーカイブ構成設定を削除する

アーカイブ構成設定は、Windows PowerShell と**CsArchivingConfiguration**コマンドレットを使用して削除できます。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-remove-a-specified-collection-of-archiving-configuration-settings"></a>指定したアーカイブ構成設定のコレクションを削除するには

  - 次のコマンドは、Redmond サイトに適用されているアーカイブ構成設定を削除します。
    
        Remove-CsArchivingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-archiving-configuration-settings-applied-to-the-site-scope"></a>サイトの範囲に適用されているすべてのアーカイブ構成設定を削除するには

  - このコマンドにより、サービスの範囲に適用されているすべてのアーカイブ構成設定が削除されます。
    
        Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration

</div>

<div>

## <a name="to-remove-archiving-configuration-settings-based-on-a-specified-property-value"></a>指定したプロパティ値に基づいてアーカイブ構成設定を削除するには

  - このコマンドを実行すると、Exchange アーカイブが無効になっているアーカイブ構成の設定がすべて削除されます。
    
        Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration

</div>

詳細については、 [CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingConfiguration)コマンドレットのヘルプトピックを参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのアーカイブのしくみ](lync-server-2013-how-archiving-works.md)  


[Lync Server 2013 での内部および外部通信のアーカイブの管理](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

