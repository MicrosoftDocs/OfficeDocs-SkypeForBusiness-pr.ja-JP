---
title: SIP トランク構成設定の既存コレクションの削除
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of SIP trunk configuration settings
ms:assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688024(v=OCS.15)
ms:contentKeyID: 49733614
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 657efcf53b48c0aab2df661ddf142587e02e235e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134653"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-lync-server-2013"></a>Lync Server 2013 の SIP トランク構成設定の既存コレクションの削除

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-22_

SIP トランクの構成では、仲介サーバーと、公衆交換電話網 (PSTN) ゲートウェイ、IP-PBX (Public Branch Exchange)、サービス プロバイダーのセッション境界コントローラー (SBC) のいずれかとの間の関係および機能を定義します。たとえば、次の設定ができます。

  - トランクでメディア バイパスを有効化するか。

  - Real-time Transport Control Protocol (RTCP) パケットが送信される条件。

  - 各トランクでセキュア リアルタイム プロトコル (SRTP) 暗号化を要求するか。

Microsoft Lync Server 2013 をインストールすると、SIP トランク構成設定のグローバルコレクションが作成されます。 この設定のグローバル コレクションは削除できません。 ただし、Lync Server コントロールパネルまたは[get-cstrunkconfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15))コマンドレットを使用して、グローバルコレクションのプロパティを既定値に "リセット" することができます。 たとえば、Enable3pccRefer プロパティを True に設定した場合、グローバル コレクションをリセットすると、Enable3pccRefer プロパティは既定値である False に戻ります。

管理者がサイト スコープまたはサービス スコープでカスタム トランク構成設定を作成することもできます (個別の PSTN ゲートウェイの場合)。これらのカスタム設定は削除できます。カスタム設定を削除するときは、次の点に注意してください。

  - サービス スコープの設定を削除すると、その設定で管理されていた SIP トランクは、サイトに適用されている設定で管理されます (その設定が存在する場合)。サイトの設定が存在しない場合、これらのトランクは、トランク構成設定のグローバル コレクションによって管理されます。

  - サイト スコープの設定を削除すると、その設定で管理されていたすべての SIP トランクが、トランク構成設定のグローバル コレクションによって管理されます。

<div>

## <a name="to-remove-trunk-configuration-settings-with-lync-server-control-panel"></a>Lync Server コントロールパネルを使用してトランク構成設定を削除するには

1.  Lync Server コントロールパネルで、[**音声のルーティング**] をクリックし、[**トランク構成**] をクリックします。

2.  [**トランク構成**] タブで、削除する SIP トランク構成設定のコレクションを選択し、[**編集**]、[**削除**] の順にクリックします。同じ操作で複数のコレクションを削除するには、削除する最初のコレクションをクリックし、Ctrl キーを押しながら、削除するその他のコレクションをクリックします。

3.  コレクションの [**状態**] プロパティが [**コミットされていません**] に更新されます。変更をコミットし、コレクションを削除するには、[**コミット**]、[**すべてコミット**] の順にクリックします。

4.  [**コミットされていない音声構成設定**] ダイアログ ボックスで、[**OK**] をクリックします。

5.  [**Microsoft Lync Server 2013 Control Panel**] ダイアログ ボックスで、[**OK**] をクリックします。

6.  後でコレクションを削除しないことにした場合は、[**コミット**]、[**コミットされていないすべての変更を取り消し**] の順にクリックします。[**Microsoft Lync Server 2013 Control Panel**] ダイアログ ボックスが表示されたら、[**OK**] をクリックします。

</div>

<div>

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してトランク構成設定を削除する

トランク構成設定は、Windows PowerShell と**get-cstrunkconfiguration**コマンドレットを使用して削除できます。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-remove-a-specified-collection-of-settings"></a>指定した設定のコレクションを削除するには

  - 次のコマンドを実行すると、Redmond サイトに適用されていたトランク構成設定が削除されます。
    
        Remove-CsTrunkConfiguration -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a>サイトスコープに適用されているすべてのコレクションを削除するには

  - 次のコマンドを実行すると、サービス スコープに適用されているすべてのトランク構成設定が削除されます。
    
        Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration

</div>

<div>

## <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a>メディアバイパスが有効になっているすべてのコレクションを削除するには

  - 次のコマンドを実行すると、メディア バイパスが有効になっているすべてのトランク構成設定が削除されます。
    
        Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration

</div>

詳細については、 [get-cstrunkconfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15))コマンドレットのヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

