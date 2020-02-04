---
title: 'Lync Server 2013: 外部ユーザー アクセスに関するサイト ポリシーまたはユーザー ポリシーの削除'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a site or user policy for external user access
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b928fcb1347fdbc89099a5b0dc649deefffa19e6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742547"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-site-or-user-policy-for-external-user-access-in-lync-server-2013"></a>Lync Server 2013 での外部ユーザー アクセスに関するサイト ポリシーまたはユーザー ポリシーの削除

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-22_

[**外部アクセスポリシー** ] ページの [Lync Server コントロールパネル] に表示されているサイトまたはユーザーポリシーは削除できます。 グローバルポリシーを削除しても、実際に削除されるわけではありませんが、外部ユーザーアクセスオプションのサポートは含まれていない既定の設定にリセットされるだけです。 グローバルポリシーのリセットの詳細については、「 [Lync Server 2013 で外部ユーザーアクセスのグローバルポリシーをリセット](lync-server-2013-reset-the-global-policy-for-external-user-access.md)する」を参照してください。

<div>

## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a>外部ユーザーアクセスのサイトまたはユーザーポリシーを削除するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  [**外部ユーザーアクセス**] をクリックし、[**外部アクセスポリシー**] をクリックします。

4.  [**外部アクセスポリシー** ] タブで、削除するサイトまたはユーザーのポリシーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。

5.  削除を確認するメッセージが表示されたら、[ **OK**] をクリックします。

</div>

<div>

## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して PIN ポリシーを削除する

外部アクセスポリシーは、Windows PowerShell と CsExternalAccessPolicy コマンドレットを使用して削除できます。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-remove-a-specific-external-access-policy"></a>特定の外部アクセスポリシーを削除するには

  - このコマンドは、Redmond サイトに適用されている外部アクセスポリシーを削除します。
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a>ユーザーごとのスコープに適用されたすべての外部アクセスポリシーを削除するには

  - このコマンドは、ユーザーごとのスコープで構成されたすべての外部アクセスポリシーを削除します。
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy

</div>

<div>

## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a>外部ユーザーアクセスが無効になっている外部アクセスポリシーをすべて削除するには

  - このコマンドは、外部ユーザーアクセスが無効になっている外部アクセスポリシーをすべて削除します。
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy

</div>

詳細については、 [CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)コマンドレットのヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

