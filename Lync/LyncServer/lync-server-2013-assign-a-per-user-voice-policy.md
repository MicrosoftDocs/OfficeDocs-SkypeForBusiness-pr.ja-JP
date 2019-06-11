---
title: 'Lync Server 2013: ユーザーごとの音声ポリシーを割り当てる'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user voice policy
ms:assetid: 9ee47ee7-1030-43b8-a4dc-bf685ea24659
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688155(v=OCS.15)
ms:contentKeyID: 49733758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e74bebc202a9e8d9fbc7b925c14bbe030e4c577
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848799"
---
# <a name="assign-a-per-user-voice-policy-in-lync-server-2013"></a>Lync Server 2013 でユーザーごとの音声ポリシーを割り当てる

 


グローバルおよびサイトレベルのボイスポリシーは、エンタープライズ Voip が有効になっているすべての Lync Server 2013 ユーザーアカウントに自動的に割り当てられます。 Lync Server 2013 コントロールパネルまたは Lync Server 2013 Management Shell を使用して、特定のユーザーに音声ポリシーを割り当てることもできます。 このトピックの手順を使用して、ユーザーごとのポリシーを Lync Server ユーザーに明示的に割り当てます。

## <a name="to-assign-a-user-specific-voice-policy-using-the-lync-server-control-panel"></a>Lync Server コントロールパネルを使用してユーザー固有のボイスポリシーを割り当てるには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーション バーで [**ユーザー**] をクリックし、構成するユーザー アカウントを検索します。

4.  検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。

5.  [**ボイスポリシー**] で**Lync Server ユーザーを編集**するには、適用するユーザーポリシーを選びます。
    

    > [!NOTE]  
    > <STRONG> &lt;自動&gt; </STRONG>設定では、既定のサーバーまたはグローバルポリシーの設定が適用されます。



## <a name="assigning-a-per-user-voice-policy-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してユーザーごとの音声ポリシーを割り当てる

ユーザーごとの音声ポリシーを割り当てるには、Windows PowerShell と**Grant-CsVoicePolicy**コマンドレットを使用します。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。

## <a name="to-assign-a-per-user-voice-policy-to-a-single-user"></a>ユーザーごとの音声ポリシーを1人のユーザーに割り当てるには

  - 次のコマンドでは、ユーザーごとのボイスポリシー RedmondVoicePolicy が Ken Myer に割り当てられます。
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

## <a name="to-assign-a-per-user-voice-policy-to-multiple-users"></a>ユーザーごとの音声ポリシーを複数のユーザーに割り当てるには

  - このコマンドを実行すると、ユーザーごとのボイスポリシー FinanceVoicePolicy が、Active Directory の Finance OU にアカウントを持つすべてのユーザーに割り当てられます。 このコマンドで使用される OU パラメーターの詳細については、「[ユーザーの取得](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\))」コマンドレットのドキュメントを参照してください。
    
        Get-CsUser -OU "ou=Finance,ou=North America,dc=litwareinc,dc=com" | Grant-CsVoicePolicy -PolicyName "FinanceVoicePolicy"

## <a name="to-unassign-a-per-user-voice-policy"></a>ユーザーごとの音声ポリシーを割り当て解除するには

  - 次のコマンドは、以前 Ken Myer に割り当てられていたユーザーごとの音声ポリシーを割り当て解除します。 ユーザー単位の PIN ポリシーが割り当て解除された後、Ken Myer は、グローバル ポリシー、または存在する場合は Ken Myer のローカル サイト ポリシーによって、自動的に管理されます。 サイト ポリシーは、グローバル ポリシーよりも優先されます。
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName $Null

詳細については、「 [Grant-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398828\(v=ocs.15\))コマンドレットのヘルプトピックを参照してください。

## <a name="see-also"></a>関連項目


[Lync Server 2013 でエンタープライズ Voip のユーザーを無効にする](lync-server-2013-disable-a-user-for-enterprise-voice.md)  


[Lync Server 2013 管理シェル](lync-server-2013-lync-server-management-shell.md)

