---
title: 'Lync Server 2013: ユーザー単位の音声ポリシーの割り当て'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user voice policy
ms:assetid: 9ee47ee7-1030-43b8-a4dc-bf685ea24659
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688155(v=OCS.15)
ms:contentKeyID: 49733758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6a10e2fb6d8e17352eb8a96be57b24e706fc5d5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134393"
---
# <a name="assign-a-per-user-voice-policy-in-lync-server-2013"></a>Lync Server 2013 でユーザーごとの音声ポリシーを割り当てる

 


エンタープライズ Voip が有効になっているすべての Lync Server 2013 ユーザーアカウントに対して、グローバルおよびサイトレベルの音声ポリシーが自動的に割り当てられます。 また、Lync Server 2013 コントロールパネルまたは Lync Server 2013 管理シェルのいずれかを使用して、特定のユーザーに音声ポリシーを割り当てることもできます。 このトピックの手順を使用して、ユーザーごとのポリシーを Lync Server ユーザーに明示的に割り当てます。

## <a name="to-assign-a-user-specific-voice-policy-using-the-lync-server-control-panel"></a>Lync Server コントロールパネルを使用してユーザー固有の音声ポリシーを割り当てるには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**ユーザー**] をクリックし、構成するユーザー アカウントを検索します。

4.  検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。

5.  [ **Lync Server ユーザーの編集**] の [**音声ポリシー**] で、適用するユーザーポリシーを選択します。
    

    > [!NOTE]  
    > [ <STRONG> &lt;自動&gt; </STRONG> ] 設定では、既定のサーバーまたはグローバルポリシーの設定が適用されます。



## <a name="assigning-a-per-user-voice-policy-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用したユーザー単位の音声ポリシーの割り当て

Windows PowerShell と**set-csvoicepolicy**コマンドレットを使用して、ユーザーごとの音声ポリシーを割り当てることができます。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

## <a name="to-assign-a-per-user-voice-policy-to-a-single-user"></a>ユーザー単位の音声ポリシーを1人のユーザーに割り当てるには

  - 次のコマンドは、ユーザーごとの音声ポリシー RedmondVoicePolicy をユーザー Ken Myer に割り当てます。
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

## <a name="to-assign-a-per-user-voice-policy-to-multiple-users"></a>ユーザー単位の音声ポリシーを複数のユーザーに割り当てるには

  - このコマンドは、Active Directory 内の Finance OU にアカウントを持つすべてのユーザーに、ユーザーごとの音声ポリシー FinanceVoicePolicy を割り当てます。 このコマンドで使用されている OU パラメーターの詳細については、「 [Get-help user](https://technet.microsoft.com/library/gg398125\(v=ocs.15\))コマンドレットのドキュメント」を参照してください。
    
        Get-CsUser -OU "ou=Finance,ou=North America,dc=litwareinc,dc=com" | Grant-CsVoicePolicy -PolicyName "FinanceVoicePolicy"

## <a name="to-unassign-a-per-user-voice-policy"></a>ユーザー単位の音声ポリシーの割り当てを解除するには

  - 次のコマンドは、既に Ken Myer に割り当てられているユーザーごとの音声ポリシーを割り当てません。 ユーザーごとのポリシーの割り当てを解除された後の Ken Myer は、グローバル ポリシーまたは存在する場合はローカル サイト ポリシーを使用して、自動的に管理されます。 サイト ポリシーの方がグローバル ポリシーより優先されます。
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName $Null

詳細については、 [set-csvoicepolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\))コマンドレットのヘルプトピックを参照してください。

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのエンタープライズ Voip のユーザーの無効化](lync-server-2013-disable-a-user-for-enterprise-voice.md)  


[Lync Server 2013 管理シェル](lync-server-2013-lync-server-management-shell.md)

