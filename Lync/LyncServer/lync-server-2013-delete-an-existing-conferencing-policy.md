---
title: 'Lync Server 2013: 既存の会議ポリシーの削除'
description: 'Lync Server 2013: 既存の会議ポリシーを削除します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing conferencing policy
ms:assetid: 709ed771-790f-4bf1-a4de-b37ca5168688
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688089(v=OCS.15)
ms:contentKeyID: 49733688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b64e51acc6e6dc91b938244da28057b01957069
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572833"
---
# <a name="delete-an-existing-conferencing-policy-in-lync-server-2013"></a>Lync Server 2013 で既存の会議ポリシーを削除する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

ユーザーレベルまたはサイトレベルの会議ポリシーを削除するには、次の手順を実行します。

<div>


> [!NOTE]  
> グローバル電話会議ポリシーを削除することはできません。



</div>

<div>

## <a name="to-delete-a-site-or-user-conferencing-policy"></a>サイトまたはユーザーの電話会議ポリシーを削除するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**会議**] をクリックし、[**電話会議ポリシー**] をクリックします。

4.  電話会議ポリシーの一覧で、削除するサイトポリシーまたはユーザーポリシーをクリックし、[ **編集**] をクリックして、[ **削除**] をクリックします。

</div>

<div>

## <a name="removing-conferencing-policies-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して電話会議ポリシーを削除する

Lync Server 管理シェルと **get-csconferencingpolicy** コマンドレットを使用して、会議ポリシーを削除することができます。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-remove-a-specified-conferencing-policy"></a>指定した電話会議ポリシーを削除するには

  - 次のコマンドは、ID RedmondConferencingPolicy を持つ電話会議ポリシーを削除します。
    
        Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"

</div>

<div>

## <a name="to-remove-all-of-the-conferencing-policies-applied-to-the-per-user-scope"></a>ユーザーごとのスコープに適用されているすべての電話会議ポリシーを削除するには

  - 次のコマンドは、ユーザーごとのスコープで構成されているすべての電話会議ポリシーを削除します。
    
        Get-CsConferencingPolicy -Filter "tag:*" | Remove-CsConferencingPolicy

</div>

<div>

## <a name="to-remove-all-of-the-conferencing-polices-that-allow-recording-by-external-users"></a>外部ユーザーによる記録を許可するすべての電話会議ポリシーを削除するには

  - 次のコマンドは、外部ユーザーに会議の記録を許可するすべての電話会議ポリシーを削除します。
    
        Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy

</div>

詳細については、「 [get-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsConferencingPolicy)」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

