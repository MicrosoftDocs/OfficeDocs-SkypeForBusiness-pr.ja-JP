---
title: 'Lync Server 2013: ユーザーごとの常設チャットポリシーを割り当てる'
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
ms.openlocfilehash: 616a171d4aedcc6014ddea3c5993a097d410a5e5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722827"
---
# <a name="assign-a-per-user-persistent-chat-policy-in-lync-server-2013"></a>Lync Server 2013 でユーザーごとの常設チャットポリシーを割り当てる

 


ユーザーごとの常設チャットポリシーは、Lync Server 2013 コントロールパネルまたは Lync Server 2013 Management Shell を使って割り当てることができます。 常設チャットサーバーのユーザーポリシーの作成について詳しくは、「 [Lync server 2013 で常設チャットのユーザーポリシーを作成](lync-server-2013-create-a-user-policy-for-persistent-chat.md)する」をご覧ください。

## <a name="to-assign-a-per-user-persistent-chat-policy-with-lync-server-control-panel"></a>Lync Server コントロールパネルを使用して、ユーザーごとの常設チャットポリシーを割り当てるには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーション バーで [**ユーザー**] をクリックします。

4.  ユーザーを探すには、次のいずれかの方法を使用します。
    
      - [**ユーザーの検索**] ボックスに、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、またはユーザー アカウントの回線 URI (Uniform Resource Identifier) の全体か先頭部分の文字列を入力して、[**検索**] をクリックします。
    
      - 保存したクエリがある場合は、[**クエリを開く**] アイコンをクリックして、[**開く**] ダイアログ ボックスを使用してそのクエリ (.usf ファイル) を取得してから、[**検索**] をクリックします。

5.  (オプション) 結果を絞り込むための追加の検索条件を次のように指定します。
    
    1.  [**フィルターの追加**] をクリックします。
    
    2.  ユーザーのプロパティを入力するか、ドロップダウン リストの矢印をクリックして選択し、プロパティを指定します。
    
    3.  [**次の値に等しい**] ドロップダウン リストで、演算子 (例: [**次の値に等しい**]、[**次の値に等しくない**]) をクリックします。
    
    4.  選択したユーザー プロパティによっては、検索結果のフィルターに使用する条件を入力するか、ドロップダウン リストの矢印をクリックして指定します。
        

        > [!TIP]  
        > クエリにその他の検索句を追加するには、[<STRONG>フィルターの追加</STRONG>] をクリックします。

    
    5.  [**検索**] をクリックします。

6.  検索結果のユーザーをクリックして、[**アクション**] をクリックしてから、[**ポリシーの割り当て**] をクリックします。
    

    > [!TIP]  
    > 複数のユーザーに同一の常設チャットポリシーを適用する場合は、検索結果で複数のユーザーを選択し、[<STRONG>アクション</STRONG>] をクリックして、[<STRONG>ポリシーの割り当て</STRONG>] をクリックします。



7.  [**ポリシーの割り当て**] の [**常設チャットポリシー**] で、次のいずれかの操作を行います。
    

    > [!NOTE]  
    > [<STRONG>ポリシーの割り当て</STRONG>] ダイアログボックスを使って構成できる複数のポリシーがあるため、ダイアログボックスのすべてのポリシーで既定で [ <STRONG> &lt;その&gt;まま</STRONG>実行する] が選択されています。 この設定を変更しないで、以前にユーザーに割り当てたポリシーを使用して続行します。

    
      - [ ** \<自動\> ** ] を選択して、Lync Server 2013 でグローバルレベルポリシーを自動的に選ぶか、定義されている場合はサイトレベルポリシーを自動的に選択するように設定します。
    
      - [**常設チャットポリシー** ] ページで以前に定義した、ユーザーごとの常設チャットポリシーの名前をクリックします。
        

        > [!TIP]  
        > 割り当てるポリシーの決定に役立てるために、ポリシー名をクリックしたら [<STRONG>表示</STRONG>] をクリックして、ポリシーで定義されているユーザー権限やアクセス許可を確認します。



8.  終了したら、[**OK**] をクリックします。

## <a name="assigning-a-per-user-persistent-chat-policy-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して、ユーザーごとの常設チャットポリシーを割り当てる

また、 **Grant-CsPersistentChatPolicy**コマンドレットを使用して、ユーザーごとの常設チャットポリシーを割り当てることもできます。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

## <a name="to-assign-a-per-user-persistent-chat-policy-to-a-single-user"></a>ユーザーごとの常設チャットポリシーを1人のユーザーに割り当てるには

  - 次のコマンドを実行すると、ユーザーごとの常設チャットポリシー RedmondPersistentChatPolicy が Ken Myer に割り当てられます。
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName "RedmondPersistentChatPolicy"

## <a name="to-assign-a-per-user-persistent-chat-policy-to-multiple-users"></a>ユーザーごとの常設チャットポリシーを複数のユーザーに割り当てるには

  - このコマンドは、IT 部門で利用するすべてのユーザーに、ユーザーごとの常設チャットポリシー RedmondUsersPersistentChatPolicy を割り当てます。 このコマンドで使用される LdapFilter パラメーターの詳細については、「[ユーザーの取得](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\))」コマンドレットのドキュメントを参照してください。
    
        Get-CsUser -LdapFilter "Department=IT" | Grant-CsPersistentChatPolicy -PolicyName "RedmondUsersPersistentChatPolicy"

## <a name="to-unassign-a-per-user-persistent-chat-policy"></a>ユーザーごとの常設チャットポリシーを割り当て解除するには

  - 次のコマンドでは、以前に Ken Myer に割り当てられている各ユーザーの常設チャットポリシーは割り当て解除されます。 ユーザー単位の PIN ポリシーが割り当て解除された後、Ken Myer は、グローバル ポリシー、または存在する場合は Ken Myer のローカル サイト ポリシーによって、自動的に管理されます。 サイト ポリシーは、グローバル ポリシーよりも優先されます。
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName $Null

詳細については、「 [Grant-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/jj204907\(v=ocs.15\))コマンドレットのヘルプトピックを参照してください。

## <a name="see-also"></a>関連項目


[Lync Server 2013 で常設チャット用のユーザー ポリシーを作成する](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

