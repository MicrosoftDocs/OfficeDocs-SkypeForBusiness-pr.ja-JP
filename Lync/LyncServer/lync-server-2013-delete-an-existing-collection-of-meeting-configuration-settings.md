---
title: 会議の構成設定の既存のコレクションを削除する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an existing collection of meeting configuration settings
ms:assetid: 92ff8a91-05c5-4047-a533-5dff12f22299
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688136(v=OCS.15)
ms:contentKeyID: 49733736
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10d564cf8fbcfb8c66df5e84841aae456913f1dc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833612"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-meeting-configuration-settings-in-lync-server-2013"></a>Lync Server 2013 で既存の会議構成設定のコレクションを削除する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-23_

サイトまたはユーザーの構成を削除できます。 グローバル構成を削除することはできません。 グローバル構成を削除すると、グローバル構成は自動的に既定値にリセットされます。

<div>

## <a name="to-delete-a-site-or-user-meeting-configuration"></a>サイトまたはユーザーの会議の設定を削除するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[**会議**] をクリックし、[**会議の設定**] をクリックします。

4.  会議構成の一覧で、削除するサイトまたはプールの構成をクリックし、[**編集**] をクリックして、[**削除**] をクリックします。

</div>

<div>

## <a name="removing-meeting-configuration-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して会議の構成設定を削除する

会議の設定を削除するには、Windows PowerShell を使用するか、または、Csmeeting 構成コマンドレットを使用します。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。

<div>

## <a name="to-remove-a-specified-collection-of-meeting-configuration-settings"></a>会議の構成設定の指定したコレクションを削除するには

  - このコマンドを実行すると、Redmond サイトに適用された会議の構成設定が削除されます。
    
        Remove-CsMeetingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-meeting-configuration-settings-applied-to-the-site-scope"></a>サイトの範囲に適用されているすべての会議の設定を削除するには

  - このコマンドを実行すると、サイトのスコープに適用されているすべての会議の構成設定が削除されます。
    
        Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration

</div>

<div>

## <a name="to-remove-all-the-meeting-configuration-settings-that-admit-anonymous-users-by-default"></a>既定で匿名ユーザーを許可する会議の構成設定をすべて削除するには

  - また、匿名ユーザーが既定で許可される設定をすべて削除します。
    
        Get-CsMeetingConfiguration | Where-Object {$_.AdmitAnonymousUsersByDefault -eq $True} | Remove-CsMeetingConfiguration

</div>

詳細については、「 [Cs会議構成の削除](https://technet.microsoft.com/en-us/library/Gg412775(v=OCS.15))」コマンドレットのヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

