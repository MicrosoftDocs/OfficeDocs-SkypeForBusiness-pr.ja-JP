---
title: 会議構成設定の既存のコレクションを削除する
description: 会議構成設定の既存のコレクションを削除します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of meeting configuration settings
ms:assetid: 92ff8a91-05c5-4047-a533-5dff12f22299
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688136(v=OCS.15)
ms:contentKeyID: 49733736
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9fc0985023a1459130c7d589327535436145a0ac
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572843"
---
# <a name="delete-an-existing-collection-of-meeting-configuration-settings-in-lync-server-2013"></a>Lync Server 2013 で会議の構成設定の既存のコレクションを削除する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

サイトやユーザーの構成は削除できます。グローバル構成は削除できません。グローバル構成を削除すると、グローバル構成は自動的に既定値にリセットされます。

<div>

## <a name="to-delete-a-site-or-user-meeting-configuration"></a>サイトまたはユーザーの会議構成を削除するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで、[**会議**] をクリックし、[**会議の構成**] をクリックします。

4.  会議の構成の一覧で、削除するサイトまたはプールの構成をクリックし、[ **編集**] をクリックして、[ **削除**] をクリックします。

</div>

<div>

## <a name="removing-meeting-configuration-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して会議の構成設定を削除する

会議の設定は、Windows PowerShell と Remove-CsMeetingConfiguration コマンドレットを使用して削除できます。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-remove-a-specified-collection-of-meeting-configuration-settings"></a>指定した会議構成設定のコレクションを削除するには

  - このコマンドは、Redmond サイトに適用された会議構成設定を削除します。
    
        Remove-CsMeetingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-meeting-configuration-settings-applied-to-the-site-scope"></a>サイトスコープに適用されているすべての会議構成設定を削除するには

  - このコマンドは、サイト スコープに適用された会議構成設定をすべて削除します。
    
        Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration

</div>

<div>

## <a name="to-remove-all-the-meeting-configuration-settings-that-admit-anonymous-users-by-default"></a>匿名ユーザーに既定で許可されているすべての会議構成設定を削除するには

  - このコマンドは、匿名ユーザーの参加を既定で許可する設定をすべて削除します。
    
        Get-CsMeetingConfiguration | Where-Object {$_.AdmitAnonymousUsersByDefault -eq $True} | Remove-CsMeetingConfiguration

</div>

詳細については、「 [削除](https://technet.microsoft.com/library/Gg412775(v=OCS.15)) 」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

