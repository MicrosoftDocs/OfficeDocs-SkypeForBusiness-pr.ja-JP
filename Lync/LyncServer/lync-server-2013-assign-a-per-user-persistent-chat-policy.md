---
title: ユーザー単位の常設チャット ポリシーの割り当て
TOCTitle: ユーザー単位の常設チャット ポリシーの割り当て
ms:assetid: e22168f2-fde1-4f0a-b194-1fc881436822
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ721908(v=OCS.15)
ms:contentKeyID: 49887180
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ユーザー単位の常設チャット ポリシーの割り当て

 

_**トピックの最終更新日:** 2013-02-22_

Lync Server 2013 コントロール パネルまたは Lync Server 2013 管理シェルでユーザー単位の常設チャット ポリシーを割り当てることができます。常設チャット サーバー 用のユーザー ポリシーの作成に関する詳細については、「[Lync Server 2013 で常設チャット用のユーザー ポリシーを作成する](lync-server-2013-create-a-user-policy-for-persistent-chat.md)」を参照してください。

## Lync Server コントロール パネルでユーザー単位の常設チャット ポリシーを割り当てるには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**ユーザー**\] をクリックします。

4.  ユーザーを探すには、次のいずれかの方法を使用します。
    
      - \[**ユーザーの検索\]** ボックスに、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、またはユーザー アカウントの回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、 \[**検索\]** をクリックします。
    
      - 保存したクエリがある場合は、 \[**クエリを開く\]** アイコンをクリックし、 \[**開く\]** ダイアログ ボックスを使用してそのクエリ (.usf ファイル) を取得して、 \[**検索\]** をクリックします。

5.  (オプション) 結果を絞り込むための追加の検索条件を次のように指定します。
    
    1.  \[**フィルターの追加**\] をクリックします。
    
    2.  ユーザーのプロパティを入力するか、ドロップダウン リストの矢印をクリックして選択し、プロパティを指定します。
    
    3.  \[**次の値に等しい**\] ドロップダウン リストで、演算子 (例: \[**次の値に等しい**\]、\[**次の値に等しくない**\]) をクリックします。
    
    4.  選択したユーザー プロパティによっては、検索結果のフィルターに使用する条件を入力するか、ドロップダウン リストの矢印をクリックして指定します。
        

        > [!TIP]
        > クエリにその他の検索句を追加するには、[<STRONG>フィルターの追加</STRONG>] をクリックします。

    
    5.  \[**検索**\] をクリックします。

6.  検索結果のユーザーをクリックし、\[**アクション**\] をクリックして、\[**ポリシーの割り当て**\] をクリックします。
    

    > [!TIP]
    > 同じユーザー単位の常設チャット ポリシーを複数のユーザーに適用する場合は、検索結果で複数のユーザーを選択して、[<STRONG>アクション</STRONG>] をクリックし、[<STRONG>ポリシーの割り当て</STRONG>] をクリックします。



7.  \[**ポリシーの割り当て**\] の \[**常設チャット ポリシー**\] で、次のいずれかの操作を行います。
    
    > [!NOTE]
    > [<strong>ポリシーの割り当て]</strong> ダイアログ ボックスを使用して構成できるポリシーは 1 つではないため、ダイアログ ボックスではすべてのポリシーについてそれぞれ既定で [<strong>&lt;現状のまま保持&gt;]</strong> が選択されます。 この設定を変更しない場合は、以前にユーザーに割り当てたポリシーを使用して続行します。
    
      - \[**\<自動\>**\] を選択すると、Lync Server 2013 でグローバルレベルのポリシーまたはサイトレベルのポリシー (定義されている場合) のどちらかを自動で選択できるようになります。
    
      - \[**常設チャット ポリシー**\] ページであらかじめ定義した、ユーザー単位の常設チャット ポリシーの名前をクリックします。
        

        > [!TIP]
        > 割り当てるポリシーの決定に役立てるために、ポリシー名をクリックしたら [<STRONG>表示]</STRONG> をクリックして、ポリシーで定義されているユーザー権限やアクセス許可を確認します。



8.  終了したら、\[**OK**\] をクリックします。

## Lync Server PowerShell コマンドレットを使用してユーザー単位の常設チャット ポリシーを割り当てる

ユーザー単位の常設チャット ポリシーは、Lync Server PowerShell および Grant-CsPersistentChatPolicy コマンドレットを使用して割り当てることもできます。このコマンドレットは、Lync Server 2013 管理シェルから実行することも、Windows PowerShellリモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。 のリモート セッションから実行することもできます。

## ユーザー単位の常設チャット ポリシーを 1 人のユーザーに割り当てる

  - 次のコマンドは、ユーザー単位の常設チャット ポリシー RedmondPersistentChatPolicy ユーザー Ken Myer に割り当てます。
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName "RedmondPersistentChatPolicy"

## ユーザー単位の常設チャット ポリシーを複数のユーザーに割り当てる

  - このコマンドは、ユーザー単位の常設チャット ポリシー RedmondUsersPersistentChatPolicy を、IT 部門で働くすべてのユーザーに割り当てます。このコマンドで使用されている LdapFilter パラメーターの詳細については、[Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) コマンドレットのドキュメントを参照してください。
    
        Get-CsUser -LdapFilter "Department=IT" | Grant-CsPersistentChatPolicy -PolicyName "RedmondUsersPersistentChatPolicy"

## ユーザー単位の常設チャット ポリシーの割り当てを解除する

  - 次のコマンドは、Ken Myer に割り当てられたユーザー単位の常設チャット ポリシーの割り当てを解除します。ユーザー単位のポリシーの割り当てが解除された後、Ken Myer は、グローバル ポリシー、または存在する場合は Ken Myer のローカル サイト ポリシーによって、自動的に管理されます。サイト ポリシーは、グローバル ポリシーよりも優先されます。
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName $Null

詳細については、[Grant-CsPersistentChatPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsPersistentChatPolicy) コマンドレットのヘルプ トピックを参照してください。

## 関連項目

#### 概念

[Lync Server 2013 で常設チャット用のユーザー ポリシーを作成する](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

