---
title: Lync Phone Edition の構成設定の既存のコレクションを削除する
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
ms.openlocfilehash: dbf7d49a14ce45550777c6c122cd799f6a511f76
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737407"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a>Lync Server 2013 で既存の Lync Phone エディション構成の設定を削除する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

Lync Phone Edition を実行しているデバイスの設定のコレクションを使用する必要がなくなった場合は、削除します。 サイトのコレクションを削除すると、そのサイトの電話にグローバル設定が適用されます。 グローバルコレクションは削除できません。

<div>


> [!NOTE]
> コレクションを削除する代わりに、設定の一部を変更することが必要になる場合もあります。 その方法の詳細については、「lync <A href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">Server 2013 で Lync Phone Edition 構成設定のコレクションを作成または変更</A>する」を参照してください。



</div>

<div>

## <a name="to-delete-a-collection-of-lync-phone-edition-configuration-settings"></a>Lync Phone エディション構成設定のコレクションを削除するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[**クライアント**] をクリックし、[**デバイス構成**] ナビゲーションボタンをクリックします。

4.  [**デバイスの構成**] ページで、削除するコレクションをクリックし、[**編集**] メニューをクリックして、[**削除**] をクリックします。
    
    <div>
    

    > [!NOTE]
    > グローバルコレクションを削除した場合、設定は既定の設定に戻ります。 コレクションは移動しません。

    
    </div>

5.  確認ボックスで [ **OK]** をクリックします。

</div>

<div>

## <a name="removing-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用した、Lync Phone Edition 構成設定の削除

Lync Phone Edition の構成設定は、Windows PowerShell と**CsUCConfiguration**コマンドレットを使用して削除できます。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-remove-a-specified-collection-of-lync-phone-edition-configuration-settings"></a>指定した Lync Phone エディション構成設定のコレクションを削除するには

  - このコマンドは、Redmond サイトに適用されている UC 電話構成設定を削除します。
    
        Remove-CsUCPhoneConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-applied-to-the-site-scope"></a>サイトの範囲に適用されているすべての Lync Phone エディション構成設定を削除するには

  - このコマンドにより、サービスの範囲に適用されているすべての UC 電話構成設定が削除されます。
    
        Get-CsUCPhoneConfiguration -Filter "site:*" | Remove-CsUCPhoneConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-where-phone-locking-is-disabled"></a>電話のロックが無効になっている Lync Phone エディションの構成設定をすべて削除するには

  - このコマンドは、電話のロックが無効になっている UC 電話構成設定のコレクションをすべて削除します。
    
        Get-CsUCPhoneConfiguration | Where-Object {$_.EnforcePhoneLock -eq $False} | Remove-CsUCPhoneConfiguration

</div>

詳細については、「 [Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398249(v=OCS.15))」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

