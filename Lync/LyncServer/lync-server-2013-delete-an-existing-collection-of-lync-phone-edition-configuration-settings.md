---
title: Lync Phone Edition 構成設定の既存コレクションの削除
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of Lync Phone Edition configuration settings
ms:assetid: 1bfc427d-4dcd-4199-b25f-8d5cfec2164f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687984(v=OCS.15)
ms:contentKeyID: 49733574
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e5c601726cfc18d230519741ebcc7561da54d73
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202719"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a>Lync Server 2013 の Lync Phone Edition 構成設定の既存コレクションの削除

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

Lync Phone Edition を実行しているデバイスの設定のコレクションを使用する必要がなくなった場合は、それを削除します。 サイトのコレクションを削除すると、そのサイト内の電話にはグローバル設定が適用されます。 グローバル コレクションは削除できません。

<div>


> [!NOTE]
> コレクションを削除するのではなく、一部の設定の変更のみ必要な場合があります。 これを行う方法の詳細については、「 <A href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">Lync Server 2013 の Lync Phone Edition 構成設定のコレクションを作成または変更</A>する」を参照してください。



</div>

<div>

## <a name="to-delete-a-collection-of-lync-phone-edition-configuration-settings"></a>Lync Phone Edition 構成設定のコレクションを削除するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**クライアント**] をクリックし、[**デバイスの構成**] 移動ボタンをクリックします。

4.  [**デバイスの構成**] ページで、削除するコレクションをクリックし、[**編集**] メニューの [**削除**] をクリックします。
    
    <div>
    

    > [!NOTE]
    > グローバル コレクションを削除すると、設定が既定の設定に戻ります。コレクションがなくなることはありません。

    
    </div>

5.  確認ボックスで [**OK**] をクリックします。

</div>

<div>

## <a name="removing-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して Lync Phone Edition の構成設定を削除する

Lync Phone Edition の構成設定は、Windows PowerShell と**CsUCConfiguration**コマンドレットを使用して削除できます。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-remove-a-specified-collection-of-lync-phone-edition-configuration-settings"></a>指定された Lync Phone Edition 構成設定のコレクションを削除するには

  - 次のコマンドは、Redmond サイトに適用される UC 電話の構成設定を削除します。
    
        Remove-CsUCPhoneConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-applied-to-the-site-scope"></a>サイトスコープに適用されているすべての Lync Phone Edition 構成設定を削除するには

  - 次のコマンドは、サービス スコープに適用される UC 電話の構成設定をすべて削除します。
    
        Get-CsUCPhoneConfiguration -Filter "site:*" | Remove-CsUCPhoneConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-where-phone-locking-is-disabled"></a>電話のロックが無効になっているすべての Lync Phone Edition の構成設定を削除するには

  - 次のコマンドは、電話のロックが無効にされている UC 電話の構成設定のコレクションをすべて削除します。
    
        Get-CsUCPhoneConfiguration | Where-Object {$_.EnforcePhoneLock -eq $False} | Remove-CsUCPhoneConfiguration

</div>

詳細については、「 [get-csucphoneconfiguration](https://technet.microsoft.com/library/Gg398249(v=OCS.15))」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

