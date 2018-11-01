---
title: ユーザー PIN のロックまたはロック解除
TOCTitle: ユーザー PIN のロックまたはロック解除
ms:assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688028(v=OCS.15)
ms:contentKeyID: 49886924
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ユーザー PIN のロックまたはロック解除

 

_**トピックの最終更新日:** 2013-02-23_

ユーザーの PIN は、Lync Server 2013 コントロール パネルの \[**ユーザー**\] セクションからロックまたはロック解除できます。

## Lync Server コントロール パネルでユーザーの PIN をロックするには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**ユーザー**\] をクリックします。

4.  ユーザーを探すには、次のどちらかの方法を使用します。
    
      - \[**ユーザーの検索**\] ボックスに、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、またはユーザー アカウントの回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、\[**検索**\] をクリックします。
    
      - 保存したクエリがある場合は、\[**クエリを開く**\] アイコンをクリックし、\[**開く**\] ダイアログ ボックスを使用してそのクエリ (.usf ファイル) を取得し、\[**検索**\] をクリックします。

5.  (オプション) 結果を絞り込むための追加の検索条件を次のように指定します。
    
    1.  \[**フィルターの追加**\] をクリックします。
    
    2.  ユーザーのプロパティを入力するか、ドロップダウン リストの矢印をクリックして選択し、プロパティを指定します。
    
    3.  \[**次の値に等しい**\] ドロップダウン リストで、演算子 (例: \[**次の値に等しい**\] または \[**次の値に等しくない**\]) をクリックします。
    
    4.  選択したユーザー プロパティに応じて、検索結果のフィルターに使用する条件を入力するか、ドロップダウン リストの矢印をクリックして指定します。
        

        > [!TIP]
        > クエリにその他の検索句を追加するには、[<STRONG>フィルターの追加</STRONG>] をクリックします。

    
    5.  \[**検索**\] をクリックします。
    
    6.  ユーザーをクリックし、\[**アクション**\] をクリックして、\[**PIN のロック**\] をクリックします。

## Lync Server コントロール パネルでユーザーの PIN のロックを解除するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**ユーザー**\] をクリックします。

4.  ユーザーを探すには、次のどちらかの方法を使用します。
    
      - \[**ユーザーの検索**\] ボックスに、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、またはユーザー アカウントの回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、\[**検索**\] をクリックします。
    
      - 保存したクエリがある場合は、\[**クエリを開く**\] アイコンをクリックし、\[**開く**\] ダイアログ ボックスを使用してそのクエリ (.usf ファイル) を取得し、\[**検索**\] をクリックします。

5.  (オプション) 結果を絞り込むための追加の検索条件を次のように指定します。
    
    1.  \[**フィルターの追加**\] をクリックします。
    
    2.  ユーザーのプロパティを入力するか、ドロップダウン リストの矢印をクリックして選択し、プロパティを指定します。
    
    3.  \[**次の値に等しい**\] ドロップダウン リストで、演算子 (例: \[**次の値に等しい**\] または \[**次の値に等しくない**\]) をクリックします。
    
    4.  選択したユーザー プロパティに応じて、検索結果のフィルターに使用する条件を入力するか、ドロップダウン リストの矢印をクリックして指定します。
        

        > [!TIP]
        > クエリにその他の検索句を追加するには、[<STRONG>フィルターの追加</STRONG>] をクリックします。

    
    5.  \[**検索**\] をクリックします。
    
    6.  ユーザーをクリックし、\[**アクション**\] をクリックして、\[**PIN のロック解除**\] をクリックします。

## Lync Server 管理シェル コマンドレットを使用して、ユーザー PIN をロックおよびロック解除するには

Windows PowerShell と Lock-CsClientPin および Unlock-CsClientPin コマンドレットを使用して、ユーザー PIN をロックおよびロック解除することもできます。このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## ユーザー PIN をロックするには

  - ユーザー PIN をロックするには、Lock-CsClientPin コマンドレットを使用します。次に例を示します。
    
        Lock-CsClientPin -Identity "Ken Myer"

## ユーザー PIN のロックを解除するには

  - ユーザー PIN のロックを解除するには、Unlock-CsClientPin コマンドレットを使用します。次に例を示します。
    
        Unlock-CsClientPin -Identity "Ken Myer"

詳細については、[Lock-CsClientPin](https://docs.microsoft.com/en-us/powershell/module/skype/Lock-CsClientPin) および [Unlock-CsClientPin](https://docs.microsoft.com/en-us/powershell/module/skype/Unlock-CsClientPin) コマンドレットのヘルプ トピックを参照してください。

