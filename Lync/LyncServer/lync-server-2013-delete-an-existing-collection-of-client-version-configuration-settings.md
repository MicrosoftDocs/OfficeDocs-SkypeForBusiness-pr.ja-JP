---
title: クライアントバージョンの構成設定の既存のコレクションを削除する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an existing collection of client version configuration settings
ms:assetid: 70bf1216-d0d2-45ce-881f-b8edadf3cec7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898480(v=OCS.15)
ms:contentKeyID: 50873760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a71df7af1f0a6158cb61e780b44ed4227d32018
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833617"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-client-version-configuration-settings-in-lync-server-2013"></a>Lync Server 2013 でクライアントバージョンの構成設定の既存のコレクションを削除する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-23_

サイト用に以前に構成されていたクライアントの構成設定を削除する場合は、Lync Server 2013 コントロールパネルまたは Lync Server 2013 管理シェルから設定を削除します。

<div>

## <a name="to-remove-client-configuration-settings-by-using-lync-server-control-panel"></a>Lync Server コントロールパネルを使用してクライアント構成設定を削除するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[**クライアント**] をクリックし、[**クライアントバージョンの構成**] ナビゲーションボタンをクリックします。

4.  サイトを選択し、[**編集**] をクリックし、[**削除**] をクリックして、[ **OK]** をクリックします。

</div>

<div>

## <a name="removing-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してクライアントのバージョン構成設定を削除する

クライアントのバージョン設定を削除するには、 **** ユーザー設定コマンドレットを使用します。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。

<div>

## <a name="to-remove-a-specified-collection-of-client-version-configuration-settings"></a>指定したクライアントバージョンの構成設定のコレクションを削除するには

  - 次のコマンドは、Redmond サイトに適用されているクライアントのバージョン設定を削除します。
    
        Remove-CsClientVersionConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-client-version-configuration-settings-applied-to-the-site-scope"></a>サイトの範囲に適用されているすべてのクライアントバージョンの構成設定を削除するには

  - このコマンドは、サイトスコープで構成されているすべてのクライアントバージョンの構成設定を削除します。
    
        Get-CsClientVersionConfiguration -Filter site:* | Remove-CsClientVersionConfiguration

</div>

<div>

## <a name="to-remove-all-the-client-version-configuration-settings-based-on-the-value-of-the-defaultaction-property"></a>DefaultAction プロパティの値に基づいて、すべてのクライアントバージョンの構成設定を削除するには

  - このコマンドを実行すると、既定のアクションが "Block" に設定されているすべてのクライアントバージョンの構成設定が削除されます。
    
        Get-CsClientVersionConfiguration | Where-Object {$_.DefaultAction -eq "Block" | Remove-CsClientVersionConfiguration

</div>

詳細については、「 [CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg425925(v=OCS.15))コマンドレットのヘルプ」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

