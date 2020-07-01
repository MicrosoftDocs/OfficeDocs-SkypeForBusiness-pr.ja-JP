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
ms.openlocfilehash: 1528ef6124193023a0e5938caac7b40c2c6187a2
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "44943930"
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
    > [ <STRONG> &lt; 自動 &gt; </STRONG> ] 設定では、既定のサーバーまたはグローバルポリシーの設定が適用されます。



## <a name="assign-per-user-voice-policies"></a>ユーザー単位の音声ポリシーの割り当て

Windows PowerShell と**set-csvoicepolicy**コマンドレットを使用して、ユーザーごとの音声ポリシーを割り当てることができます。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法については、この Lync Server Windows PowerShell ブログ投稿:[クイックスタート: リモート PowerShell を使用して Microsoft Lync server 2010 を管理](https://go.microsoft.com/fwlink/p/?linkId=255876)する」を参照してください。

### <a name="assign-a-per-user-voice-policy-to-a-single-user"></a>ユーザー単位の音声ポリシーを1人のユーザーに割り当てる

  - 次のコマンドは、ユーザーごとの音声ポリシー RedmondVoicePolicy をユーザー Ken Myer に割り当てます。
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

## <a name="assign-a-per-user-voice-policy-to-multiple-users"></a>ユーザーごとの音声ポリシーを複数のユーザーに割り当てる

  - このコマンドは、Active Directory 内の Finance OU にアカウントを持つすべてのユーザーに、ユーザーごとの音声ポリシー FinanceVoicePolicy を割り当てます。 このコマンドで使用されている OU パラメーターの詳細については、「 [Get-help user](https://technet.microsoft.com/library/gg398125\(v=ocs.15\))コマンドレットのドキュメント」を参照してください。
    
        Get-CsUser -OU "ou=Finance,ou=North America,dc=litwareinc,dc=com" | Grant-CsVoicePolicy -PolicyName "FinanceVoicePolicy"

## <a name="unassign-a-per-user-voice-policy"></a>ユーザー単位の音声ポリシーの割り当て解除

  - 次のコマンドは、既に Ken Myer に割り当てられているユーザーごとの音声ポリシーを割り当てません。 ユーザーごとのポリシーの割り当てを解除された後の Ken Myer は、グローバル ポリシーまたは存在する場合はローカル サイト ポリシーを使用して、自動的に管理されます。 サイト ポリシーの方がグローバル ポリシーより優先されます。
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName $Null

詳細については、 [set-csvoicepolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\))コマンドレットのヘルプトピックを参照してください。

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのエンタープライズ Voip のユーザーの無効化](lync-server-2013-disable-a-user-for-enterprise-voice.md)  


[Lync Server 2013 管理シェル](lync-server-2013-lync-server-management-shell.md)

