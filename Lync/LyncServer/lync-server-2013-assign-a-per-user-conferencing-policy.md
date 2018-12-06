---
title: ユーザー単位の会議ポリシーの割り当て
TOCTitle: ユーザー単位の会議ポリシーの割り当て
ms:assetid: 72f12c72-65f7-44fe-ab81-0f57cb2f87d1
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg521015(v=OCS.15)
ms:contentKeyID: 48272517
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ユーザー単位の会議ポリシーの割り当て

 

_**トピックの最終更新日:** 2013-02-22_

会議ポリシーは、Lync Server コントロール パネルで構成できるユーザー アカウントの個別設定の 1 つです。

ユーザーは 1 つまたは複数のユーザー単位の会議ポリシーを展開できますが、この展開はオプションです。また、グローバルレベルの会議ポリシーまたはサイトレベルの会議ポリシーだけを展開することもできます。ユーザー単位のポリシーを展開する場合は、ポリシーをユーザー、グループ、または連絡先オブジェクトに明示的に割り当てる必要があります。特定のサイトレベルのポリシーやユーザー単位のポリシーが割り当てられていない場合は、会議のユーザー権限やアクセス許可により、グローバルレベルの会議ポリシーで定義された既定の設定が自動的に適用されます。

ユーザー単位の会議ポリシーを 1 つ以上作成した後、このトピックの手順を使用してポリシーを割り当て、特定のユーザーが開催する会議に対してサーバーが許可するユーザー権限とアクセス許可を指定します。

利用可能なすべての会議ポリシー設定の一覧については、「[Lync Server 2013 での会議ポリシー設定の参照](lync-server-2013-conferencing-policy-settings-reference.md)」を参照してください。

会議ポリシーの作成手順の詳細については、「[Lync Server 2013 での会議ポリシーの作成または変更](lync-server-2013-create-or-modify-a-conferencing-policy.md)」を参照してください。

## ユーザー単位の会議ポリシーを割り当てるには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**ユーザー**\] をクリックします。

4.  ユーザーを探すには、次のどちらかの方法を使用します。
    
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
    > 同じユーザー単位の会議ポリシーを複数のユーザーに適用する場合は、検索結果で複数のユーザーを選択して、[<STRONG>アクション</STRONG>] をクリックし、[<STRONG>ポリシーの割り当て</STRONG>] をクリックします。



7.  \[**ポリシーの割り当て**\] の \[**会議ポリシー**\] で、次のどちらかの手順を実行します。
    
    > [!NOTE]
    > [<strong>ポリシーの割り当て</strong>] で構成できるポリシーは複数あるため、ダイアログ ボックスではすべてのポリシーについてそれぞれ既定で [<strong>&lt;現状のまま保持&gt;</strong>] が選択されます。 この設定を変更しない場合は、以前にユーザーに割り当てたポリシーを使用して続行します。
    
      - \[**\<自動\>**\] を選択すると、Lync Server 2013 でグローバルレベルのポリシーまたはサイトレベルのポリシー (定義されている場合) のどちらかを自動で選択できるようになります。
    
      - \[**会議ポリシー**\] ページであらかじめ定義した、ユーザー単位の会議ポリシーの名前をクリックします。
        

        > [!TIP]
        > 割り当てるポリシーの決定に役立てるために、ポリシー名をクリックしたら [<STRONG>表示</STRONG>] をクリックして、ポリシーで定義されているユーザー権限やアクセス許可を確認します。



8.  終了したら、\[**OK**\] をクリックします。

## Lync Server PowerShell コマンドレットを使用したユーザー単位の会議ポリシーの割り当て

ユーザー単位の会議ポリシーは、Lync Server PowerShell および Grant-CsConferencingPolicy コマンドレットを使用して割り当てることもできます。このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## 単一ユーザーへのユーザー単位の会議ポリシーの割り当て

  - 次のコマンドは、ユーザー単位の会議ポリシー RedmondConferencingPolicy をユーザー Ken Myer に割り当てます。
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName "RedmondConferencingPolicy"

## 複数のユーザーへのユーザー単位の会議ポリシーの割り当て

  - 次のコマンドは、ユーザー単位の会議ポリシー HRConferencingPolicy を "Human Resources/人事" 部門に勤務するすべてのユーザーに割り当てます。このコマンドで使用される LdapFilter パラメーターの詳細については、[Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) コマンドレットのドキュメントを参照してください。
    
        Get-CsUser -LdapFilter "Department=Human Resources" | Grant-CsConferencingPolicy -PolicyName "HRConferencingPolicy"

## ユーザー単位の会議ポリシーの割り当て解除

  - 次のコマンドは、以前に Ken Myer に割り当てたユーザー単位の会議ポリシーのすべての割り当てを解除します。ユーザー単位のポリシーが割り当て解除された後、Ken Myer は自動的にグローバル ポリシーを使用して管理されるか、存在する場合には自身のローカル サイト ポリシーを使用して管理されます。サイト ポリシーはグローバル ポリシーより優先されます。
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName $Null

詳細については、[Grant-CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsConferencingPolicy) コマンドレットのヘルプ トピックを参照してください。

## 関連項目

#### タスク

[Lync Server 2013 での会議ポリシーの作成または変更](lync-server-2013-create-or-modify-a-conferencing-policy.md)  

#### その他のリソース

[ユーザー単位のポリシーの割り当て](lync-server-2013-assigning-per-user-policies.md)

