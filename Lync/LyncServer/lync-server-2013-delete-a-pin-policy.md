---
title: 'Lync Server 2013: PIN ポリシーの削除'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a PIN policy
ms:assetid: 7c378927-2e41-418e-9721-327021bd2e45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521020(v=OCS.15)
ms:contentKeyID: 48184609
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38f8c9899665353d33682cc0c780cd7411b0abfd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006323"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-pin-policy-in-lync-server-2013"></a>Lync Server 2013 で PIN ポリシーを削除する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

暗証番号 (PIN) ポリシーを削除するには、次の手順を実行します。

<div>


> [!NOTE]  
> グローバル PIN ポリシーを削除することはできません。



</div>

<div>

## <a name="to-delete-a-pin-policy-in-lync-server-2013-control-panel"></a>Lync Server 2013 コントロールパネルで PIN ポリシーを削除するには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Lync Server 2013 を展開したネットワーク内の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**PIN ポリシー**] をクリックします。

4.  [**PIN ポリシー**] ページの検索フィールドにで、削除するポリシーの名前または名前の一部を入力します。

5.  ポリシーのリストで対象のポリシーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。

6.  **[OK]** をクリックします。

</div>

<div>

## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して PIN ポリシーを削除する

PIN ポリシーは、Windows PowerShell と Get-cspinpolicy コマンドレットを使用して削除できます。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモート Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Microsoft Lync Server 2010 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)を使用したリモート PowerShell の管理」を参照してください。

<div>

## <a name="to-remove-a-specific-pin-policy"></a>特定の PIN ポリシーを削除するには

  - 次のコマンドは、Identity が RedmondPinPolicy の PIN ポリシーを削除します。
    
        Remove-CsPinPolicy -Identity "RedmondPinPolicy"

</div>

<div>

## <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a>サイトスコープに適用されているすべての PIN ポリシーを削除するには

  - 次のコマンドは、サイト スコープで構成されたすべての PIN ポリシーを削除します。
    
        Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy

</div>

<div>

## <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a>共通パターンの使用を許可するすべての PIN ポリシーを削除するには

  - 次のコマンドは、共通パターン G の使用を許可するすべての PIN ポリシーを削除します。
    
        et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy

</div>

詳細については、 [get-cspinpolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsPinPolicy)コマンドレットのヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

