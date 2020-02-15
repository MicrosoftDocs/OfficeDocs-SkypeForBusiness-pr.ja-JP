---
title: 'Lync Server 2013: ユーザー単位の常設チャットポリシーの割り当て'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user Persistent Chat policy
ms:assetid: e22168f2-fde1-4f0a-b194-1fc881436822
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721908(v=OCS.15)
ms:contentKeyID: 49733842
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 335f14018e9e489dbb6ca4db5a4d6138eb330faf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030130"
---
# <a name="assign-a-per-user-persistent-chat-policy-in-lync-server-2013"></a>Lync Server 2013 でユーザー単位の常設チャットポリシーを割り当てる

 


ユーザー単位の常設チャットポリシーは、Lync Server 2013 コントロールパネルまたは Lync Server 2013 管理シェルのいずれかを使用して割り当てることができます。 常設チャットサーバーのユーザーポリシーの作成の詳細については、「 [Lync Server 2013 で常設チャット用のユーザーポリシーを作成する](lync-server-2013-create-a-user-policy-for-persistent-chat.md)」を参照してください。

## <a name="to-assign-a-per-user-persistent-chat-policy-with-lync-server-control-panel"></a>Lync Server コントロールパネルを使用してユーザー単位の常設チャットポリシーを割り当てるには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**ユーザー**] をクリックします。

4.  ユーザーを探すには、次のどちらかの方法を使用します。
    
      - [**ユーザーの検索**] ボックスに、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、またはユーザー アカウントの回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、[**検索**] をクリックします。
    
      - 保存したクエリがある場合は、[**クエリを開く**] アイコンをクリックし、[**開く**] ダイアログ ボックスを使用してそのクエリ (.usf ファイル) を取得して、[**検索**] をクリックします。

5.  (オプション) 結果を絞り込むための追加の検索条件を次のように指定します。
    
    1.  [**フィルターの追加**] をクリックします。
    
    2.  ユーザーのプロパティを入力するか、ドロップダウン リストの矢印をクリックして選択し、プロパティを指定します。
    
    3.  [**次の値に等しい**] ドロップダウン リストで、演算子 (例: [**次の値に等しい**]、[**次の値に等しくない**]) をクリックします。
    
    4.  選択したユーザー プロパティによっては、検索結果のフィルターに使用する条件を入力するか、ドロップダウン リストの矢印をクリックして指定します。
        

        > [!TIP]  
        > クエリにその他の検索句を追加するには、[<STRONG>フィルターの追加</STRONG>] をクリックします。

    
    5.  [**検索**] をクリックします。

6.  検索結果のユーザーをクリックし、[**アクション**] をクリックして、[**ポリシーの割り当て**] をクリックします。
    

    > [!TIP]  
    > 同じユーザー単位の常設チャット ポリシーを複数のユーザーに適用する場合は、検索結果で複数のユーザーを選択して、[<STRONG>アクション</STRONG>] をクリックし、[<STRONG>ポリシーの割り当て</STRONG>] をクリックします。



7.  [**ポリシーの割り当て**] の [**常設チャット ポリシー**] で、次のいずれかの操作を行います。
    

    > [!NOTE]  
    > [<STRONG>ポリシーの割り当て</STRONG>] ダイアログボックスを使用して複数のポリシーを構成できるので、ダイアログボックスのすべてのポリシーに対して、既定で [ <STRONG> &lt;&gt;そのまま保持</STRONG>] が選択されています。 この設定を変更しない場合は、以前にユーザーに割り当てたポリシーを使用して続行します。

    
      - [ ** \<自動\> ** ] を選択すると、Lync Server 2013 でグローバルレベルのポリシーまたはサイトレベルのポリシー (定義されている場合) のいずれかを自動的に選択できるようになります。
    
      - [**常設チャット ポリシー**] ページであらかじめ定義した、ユーザー単位の常設チャット ポリシーの名前をクリックします。
        

        > [!TIP]  
        > 割り当てるポリシーの決定に役立てるために、ポリシー名をクリックしたら  [<STRONG>表示] </STRONG> をクリックして、ポリシーで定義されているユーザー権限やアクセス許可を確認します。



8.  終了したら、[**OK**] をクリックします。

## <a name="assigning-a-per-user-persistent-chat-policy-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してユーザー単位の常設チャットポリシーを割り当てる

**Get-cspersistentchatpolicy 戻し**コマンドレットを使用して、ユーザー単位の常設チャットポリシーを割り当てることもできます。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

## <a name="to-assign-a-per-user-persistent-chat-policy-to-a-single-user"></a>ユーザー単位の常設チャットポリシーを1人のユーザーに割り当てるには

  - 次のコマンドは、ユーザー単位の常設チャット ポリシー RedmondPersistentChatPolicy ユーザー Ken Myer に割り当てます。
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName "RedmondPersistentChatPolicy"

## <a name="to-assign-a-per-user-persistent-chat-policy-to-multiple-users"></a>ユーザー単位の常設チャットポリシーを複数のユーザーに割り当てるには

  - このコマンドは、ユーザー単位の常設チャット ポリシー RedmondUsersPersistentChatPolicy を、IT 部門で働くすべてのユーザーに割り当てます。 このコマンドで使用されている LdapFilter パラメーターの詳細については、「 [Get-help user](https://technet.microsoft.com/library/gg398125\(v=ocs.15\))コマンドレットのドキュメント」を参照してください。
    
        Get-CsUser -LdapFilter "Department=IT" | Grant-CsPersistentChatPolicy -PolicyName "RedmondUsersPersistentChatPolicy"

## <a name="to-unassign-a-per-user-persistent-chat-policy"></a>ユーザー単位の常設チャットポリシーの割り当てを解除するには

  - 次のコマンドは、Ken Myer に割り当てられたユーザー単位の常設チャット ポリシーの割り当てを解除します。ユーザー単位のポリシーの割り当てが解除された後、Ken Myer は、グローバル ポリシー、または存在する場合は Ken Myer のローカル サイト ポリシーによって、自動的に管理されます。サイト ポリシーは、グローバル ポリシーよりも優先されます。
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName $Null

詳細については、 [get-cspersistentchatpolicy 戻し](https://technet.microsoft.com/library/jj204907\(v=ocs.15\))コマンドレットのヘルプトピックを参照してください。

## <a name="see-also"></a>関連項目


[Lync Server 2013 で常設チャット用のユーザーポリシーを作成する](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

