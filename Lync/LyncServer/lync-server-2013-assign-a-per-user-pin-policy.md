---
title: ユーザー単位の PIN ポリシーの割り当て
TOCTitle: ユーザー単位の PIN ポリシーの割り当て
ms:assetid: d8211c64-0b63-4193-a074-673da7d14287
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg182594(v=OCS.15)
ms:contentKeyID: 48273799
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ユーザー単位の PIN ポリシーの割り当て

 

_**トピックの最終更新日:** 2013-02-22_

ダイヤルイン会議の暗証番号 (PIN) ポリシーは、Lync Server 2013 コントロール パネルで構成可能な、ユーザー アカウントの個別の設定の 1 つです。

ユーザーは 1 つまたは複数のユーザー単位の PIN ポリシーを展開できますが、この展開はオプションです。 また、グローバルレベルの PIN ポリシーまたはサイトレベルの PIN ポリシーだけを展開することもできます。 ユーザー単位のポリシーを展開する場合は、ポリシーをユーザー、グループ、または連絡先オブジェクトに明示的に割り当てる必要があります。 特定のサイトレベルのポリシーやユーザー単位のポリシーが割り当てられていない場合は、ダイヤルイン会議での PIN の使用に関するユーザーの権限およびアクセス許可により、グローバルレベルの PIN ポリシーで定義された既定の設定が自動的に適用されます。

ユーザー単位の PIN ポリシーを 1 つ以上作成した後、このトピックの手順を使用してポリシーを割り当て、特定のユーザーが作成したか、特定のユーザーが使用する PIN にサーバーが課す制約を指定します。

ユーザー単位のダイヤルイン会議 PIN ポリシーの作成の詳細については、「[サイトまたはユーザーのグループ向けに Lync Server 2013 でダイヤルイン会議の PIN 設定を作成または変更する](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)」を参照してください。

## ユーザー単位の PIN ポリシーを割り当てるには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**ユーザー**\] をクリックします。

4.  ユーザーを探すには、次のいずれかの方法を使用します。
    
      - \[**ユーザーの検索**\] ボックスに、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、またはユーザー アカウントの回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、\[**検索**\] をクリックします。
    
      - 保存したクエリがある場合は、\[**クエリを開く**\] アイコンをクリックし、\[**開く**\] ダイアログ ボックスを使用してそのクエリ (.usf ファイル) を取得して、\[**検索**\] をクリックします。

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
    > 同じユーザー単位の PIN ポリシーを複数のユーザーに適用する場合は、検索結果で複数のユーザーを選択して、[<STRONG>アクション</STRONG>] をクリックしてから [<STRONG>ポリシーの割り当て</STRONG>] をクリックします。



7.  \[**ポリシーの割り当て**\] の \[**PIN ポリシー**\] で、次のいずれかの手順を実行します。
    
    > [!NOTE]
    > [<strong>ポリシーの割り当て</strong>] ダイアログ ボックスを使用して構成できるポリシーは 1 つではないため、ダイアログ ボックスではすべてのポリシーについてそれぞれ既定で [<strong>&lt;現状のまま保持&gt;</strong>] が選択されます。 この設定を変更しない場合は、以前にユーザーに割り当てたポリシーを使用して続行します。
    
      - Lync Server 2013 が、グローバルレベルのポリシーまたはサイトレベルのポリシー (定義されている場合) のいずれかを自動で選択できるようにします。
    
      - \[**PIN ポリシー**\] ページであらかじめ定義した、ユーザー単位の PIN ポリシーの名前をクリックします。
        

        > [!TIP]
        > 割り当てるポリシーの決定に役立てるために、ポリシー名をクリックしたら [<STRONG>表示</STRONG>] をクリックして、ポリシーで定義されているユーザー権限やアクセス許可を確認します。



8.  終了したら、\[**OK**\] をクリックします。

## Lync Server 管理シェル コマンドレットを使用してユーザー単位の PIN ポリシーを割り当てる

Lync Server 管理シェル コマンドレットおよび **Grant-CsPinPolicy** コマンドレットを使用して、ユーザー単位の PIN ポリシーを割り当てることができます。このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## ユーザー単位の PIN ポリシーを単一のユーザーに割り当てるには

  - 次のコマンドは、ユーザー単位の PIN ポリシー RedmondPinPolicy をユーザー「Ken Myer」に割り当てます。
    
        Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"

## ユーザー単位の PIN ポリシーを複数のユーザーに割り当てるには

  - 次のコマンドは、ユーザー単位の PIN ポリシー RedmondUsersPinPolicy を Redmond 市で働くすべてのユーザーに割り当てます。このコマンドで使用する LdapFilter パラメーターについては、「[Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser)」を参照してください。
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"

## ユーザー単位の PIN ポリシーを割り当て解除するには

  - 次のコマンドは、Ken Myer に割り当てられたユーザー単位の PIN ポリシーを割り当て解除します。ユーザー単位の PIN ポリシーが割り当て解除された後、Ken Myer は、グローバル ポリシー、または存在する場合は Ken Myer のローカル サイト ポリシーによって、自動的に管理されます。サイト ポリシーは、グローバル ポリシーよりも優先されます。
    
        Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null

詳細については、「[Grant-CsPinPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsPinPolicy)」を参照してください。

## 関連項目

#### タスク

[新しい PIN ポリシーの作成](lync-server-2013-create-a-new-pin-policy.md)  

#### その他のリソース

[ユーザー単位のポリシーの割り当て](lync-server-2013-assigning-per-user-policies.md)

