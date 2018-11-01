---
title: ユーザー PIN 情報の表示
TOCTitle: ユーザー PIN 情報の表示
ms:assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688067(v=OCS.15)
ms:contentKeyID: 49886968
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ユーザー PIN 情報の表示

 

_**トピックの最終更新日:** 2013-02-23_

Active Directory ドメイン サービス (AD DS) の資格情報を持つ Lync Server 2013 ユーザーが、認証されたユーザーとしてダイヤルイン会議に参加するには、暗証番号 (PIN) が必要です。ユーザーの PIN 情報は、Lync Server 2013 コントロール パネルから表示できます。

> [!NOTE]
> PIN が設定されているかどうかや PIN の最終変更日時などの PIN 状態情報を表示することはできますが、PIN の状態を調べても最新の PIN は確認できません。ユーザーが PIN をなくした場合は、「<a href="lync-server-2013-set-a-user-s-dial-in-conferencing-pin.md">Lync Server 2013 でのユーザーのダイヤルイン会議 PIN の設定</a>」の手順に従って PIN をリセットできます。


## Lync Server コントロール パネルでユーザーの PIN を表示するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**ユーザー**\] をクリックします。

4.  ユーザーを探すには、次のどちらかの方法を使用します。
    
      - \[**ユーザーの検索**\] ボックスに、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、またはユーザー アカウントの回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、\[**検索**\] をクリックします。
    
      - 保存済みのクエリがある場合は、\[**クエリを開く**\] アイコンをクリックします。\[**開く**\] ダイアログ ボックスを使用してそのクエリ (.usf ファイル) を取得し、\[**検索**\] をクリックします。

5.  (オプション) 結果を絞り込むための追加の検索条件を次のように指定します。
    
    1.  \[**フィルターの追加**\] をクリックします。
    
    2.  ユーザーのプロパティを入力するか、ドロップダウン リストの矢印をクリックして選択し、プロパティを指定します。
    
    3.  \[**次の値に等しい**\] ドロップダウン リストで、演算子 (例: \[**次の値に等しい**\] または \[**次の値に等しくない**\]) をクリックします。
    
    4.  選択したユーザー プロパティに応じて、検索結果のフィルターに使用する条件を入力するか、ドロップダウン リストの矢印をクリックして指定します。
        

        > [!TIP]
        > クエリにその他の検索句を追加するには、[<STRONG>フィルターの追加</STRONG>] をクリックします。

    
    5.  \[**検索**\] をクリックします。
    
    > [!NOTE]
    > PIN がロックされている場合は、ロックを解除しないと PIN を設定できません。PIN のロックを解除するには、ユーザーをクリックし、[<strong>アクション</strong>] をクリックして、[<strong>PIN のロック解除</strong>] をクリックします。


6.  検索結果でユーザーをクリックし、\[**アクション**\] をクリックして、\[**PIN の状態を表示**\] をクリックします。

## Lync Server 管理シェル コマンドレットを使用してユーザーの PIN 情報を表示するには

Get-CsClientPinInfo コマンドレットを使用して、ユーザーの PIN 情報を表示できます。このコマンドレットは、Lync Server 2013 管理シェルから実行することも、Windows PowerShell のリモート セッションから実行することもできます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## ユーザーの PIN 情報を表示するには

  - ユーザーの PIN 情報を表示するには、Lync Server 管理シェルで次のようなコマンドを入力し、Enter キーを押します。
    
        Get-CsClientPinInfo -Identity "Ken Myer"
    
    これは次のような情報を返します。
    
        Identity          : sip:kenmyer@litwareinc.com
        IsPinSet          : False
        IsLockedOut       : False
        LastPinChangeTime : 9/25/2012 1:35:03 PM
        PinExpirationTime :

詳細については、[Get-CsConferenceDisclaimer](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsConferenceDisclaimer) コマンドレットに関するヘルプ トピックを参照してください。

## 関連項目

#### タスク

[Lync Server 2013 でのユーザーのダイヤルイン会議 PIN の設定](lync-server-2013-set-a-user-s-dial-in-conferencing-pin.md)  
[ユーザー PIN のロックまたはロック解除](lync-server-2013-lock-or-unlock-a-user-pin.md)

