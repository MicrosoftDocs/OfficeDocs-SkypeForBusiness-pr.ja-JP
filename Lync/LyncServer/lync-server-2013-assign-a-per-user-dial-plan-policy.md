---
title: ユーザー単位のダイヤル プラン ポリシーの割り当て
TOCTitle: ユーザー単位のダイヤル プラン ポリシーの割り当て
ms:assetid: 9fea861f-7770-4cae-9b1f-2a960595bfc9
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688156(v=OCS.15)
ms:contentKeyID: 49887076
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ユーザー単位のダイヤル プラン ポリシーの割り当て

 

_**トピックの最終更新日:** 2013-02-22_

エンタープライズ VoIP のユーザーまたはダイヤルイン会議のユーザーのどちらかのユーザー アカウント構成を完了するには、ユーザーにダイヤル プランを割り当てる必要があります。既存のユーザーごとのダイヤル プランを明示的に割り当てないと、ユーザー アカウントでは、グローバル ダイヤル プランまたは存在する場合はサイト レベルのダイヤル プランが自動的に使用されます。エンタープライズ VoIP に対して有効になっているすべてのユーザーでグローバルまたはサイトのダイヤル プランを使用する場合は、このセクションを省略できます。

## Lync Server 2013 コントロール パネルを使用してダイヤル プランを割り当てるには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**ユーザー**\] をクリックします。

4.  \[**ユーザーの検索**\] ボックスに、有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、\[**検索**\] をクリックします。

5.  表で、ダイヤル プランを割り当てるユーザー アカウントをクリックします。

6.  \[**編集**\] メニューの \[**詳細の表示**\] をクリックします。

7.  \[**Lync Server ユーザーの編集**\] ページの \[**テレフォニー**\] で、\[**エンタープライズ VoIP**\] をクリックします。

8.  \[**ダイヤル プラン ポリシー**\] をクリックし、目的のダイヤル プランを選択します。

9.  \[**確定**\] をクリックします。

ダイヤル プランの構成の詳細については、「[Lync Server 2013 でのダイヤル プランの構成](lync-server-2013-configuring-dial-plans.md)」を参照してください。

## Lync Server 2013 管理シェルを使用してダイヤル プランを割り当てるには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  ユーザー固有のダイヤル プランを割り当てるには、コマンド プロンプトで次のコマンドを実行します。
    
        Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
    
    次に例を示します。
    
        Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
    
    この例では、Bob Kelly という表示名のユーザーに、**DialPlanJapan** という名前のユーザー ダイヤル プランを割り当てています。

ユーザー ダイヤル プランの割り当てまたは **Grant-CsDialPlan** コマンドレットの実行の詳細については、「[Lync Server 2013 管理シェル](lync-server-2013-lync-server-management-shell.md)」のドキュメントを参照してください。

## Windows PowerShell コマンドレットを使用してユーザーごとのダイヤル プランを割り当てる

ユーザーごとのダイヤル プランは、Windows PowerShell と **Grant-CsdialPlan** コマンドレットを使用して割り当てることもできます。このコマンドレットは、Lync Server 2013 管理シェルから実行することも、Windows PowerShell のリモート セッションから実行することもできます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## ユーザーごとのダイヤル プランを 1 人のユーザーに割り当てる

  - 次のコマンドは、ユーザーごとのダイヤル プラン RedmondDialPlan をユーザー Ken Myer に割り当てます。
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"

## ユーザーごとのダイヤル プランを複数のユーザーに割り当てる

  - このコマンドは、ユーザーごとのダイヤル プラン RedmondDialPlan を、Redmond 市で働くすべてのユーザーに割り当てます。このコマンドで使用されている LdapFilter パラメーターの詳細については、[Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) コマンドレットのドキュメントを参照してください。
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"

## ユーザーごとのダイヤル プランの割り当てを解除する

  - 次のコマンドは、以前に Ken Myer に割り当てられたユーザーごとのダイヤル プランの割り当てを解除します。ユーザーごとのダイヤル プランの割り当てを解除すると、Ken Myer は自動的にグローバル ダイヤル プラン、 ローカル サイト ダイヤル プラン (存在する場合)、またはこのユーザーのレジストラーまたは PSTN ゲートウェイに割り当てられたサービス スコープのダイヤル プランを使用して管理されるようになります。サービス スコープのダイヤル プランはサイト ダイヤル プランより優先され、サイト ダイヤル プランはグローバル ダイヤル プランより優先されます。
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null

詳細については、[Grant-CsDialPlan](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsDialPlan) コマンドレットのヘルプ トピックを参照してください。

## 関連項目

#### その他のリソース

[Lync Server 2013 でのダイヤル プランの構成](lync-server-2013-configuring-dial-plans.md)  
[Lync Server 2013 に対して有効なユーザー アカウント](lync-server-2013-user-accounts-enabled-for-lync-server.md)

