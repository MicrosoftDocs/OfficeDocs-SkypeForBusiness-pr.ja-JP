---
title: 'Lync Server 2013: ユーザーのダイヤルイン会議 PIN の設定'
TOCTitle: ユーザーのダイヤルイン会議 PIN の設定
ms:assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg520985(v=OCS.15)
ms:contentKeyID: 48271909
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのユーザーのダイヤルイン会議 PIN の設定

 

_**トピックの最終更新日:** 2014-06-10_

Active Directory ドメイン サービス (AD DS) の資格情報を持つ Lync Server 2013 ユーザーが、認証されたユーザーとしてダイヤルイン会議に参加するには、暗証番号 (PIN) が必要です。ユーザーがダイヤルイン会議 PIN を忘れている場合や Lync Server を使用して PIN を設定していない場合は、Lync Server コントロール パネルでユーザーの PIN を設定できます。PIN は自動で生成することも手動で作成することもできます。

> [!NOTE]
> 最小サイズなど、PIN の具体的な特性は、ポリシーとして構成できます。グローバル ポリシーに加えて、個々のサイトまたはユーザーを対象にした PIN ポリシーを構成できます。PIN ポリシーの構成の詳細については、「<a href="lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md">ダイヤルイン会議の暗証番号 (PIN) ルールの構成</a>」を参照してください。


## ユーザーの PIN を設定するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[ **ユーザー**\] をクリックします。

4.  ユーザーを探すには、次のいずれかの方法を使用します。
    
      - \[**ユーザーの検索**\] ボックスに、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、またはユーザー アカウントの回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、\[**検索**\] をクリックします。
    
      - 保存したクエリがある場合は、\[**クエリを開く**\] アイコンをクリックし、\[**開く**\] ダイアログ ボックスを使用してそのクエリ (.usf ファイル) を取得して、\[**検索**\] をクリックします。

5.  (オプション) 結果を絞り込むための追加の検索条件を次のように指定します。
    
    1.  \[**フィルターの追加**\] をクリックします。
    
    2.  ユーザーのプロパティを入力するか、ドロップダウン リストの矢印をクリックして選択し、プロパティを指定します。
    
    3.  \[**次の値に等しい**\] ドロップダウン リストで、演算子 (例: \[**次の値に等しい**\]、\[**次の値に等しくない**\]) をクリックします。
    
    4.  選択したユーザー プロパティに応じて、検索結果のフィルターに使用する条件を入力するか、ドロップダウン リストの矢印をクリックして指定します。
        

        > [!TIP]
        > クエリにその他の検索句を追加するには、[<STRONG>フィルターの追加</STRONG>] をクリックします。

    
    5.  \[**検索**\] をクリックします。
    
    > [!NOTE]
    > PIN がロックされている場合は、ロックを解除しないと PIN を設定できません。 PIN のロックを解除するには、ユーザーをクリックし、[<strong>アクション</strong>] をクリックして、[<strong>PIN のロック解除</strong>] をクリックします。


6.  検索結果のユーザーをクリックし、\[**アクション**\] をクリックして、\[**暗証番号 (PIN) の設定**\] をクリックします。

7.  \[**暗証番号 (PIN) の設定**\] ダイアログ ボックスで、次のどちらかの手順を実行します。
    
      - Lync Server 2013 がユーザーの PIN を生成できるようにするには、\[**有効な PIN の自動生成**\] (既定) を選択します。
    
      - 自分の PIN を作成するには、\[**特定の PIN を手動で入力**\] をクリックして、テキスト ボックスをクリックし、PIN のポリシー設定で指定されている PIN の要件を満たす PIN を入力します。

8.  \[**OK**\] をクリックします。

9.  \[**暗証番号 (PIN) の設定**\] で、次のどちらかの手順を実行します。
    
      - \[**PIN の表示**\] チェック ボックスをオンにして PIN を表示し、PIN をコピーし、組織で推奨される方法を使用しているユーザーに伝えます。
    
      - PIN を電子メールで送信するには、\[**新しい PIN をユーザーに送信するために電子メール アプリケーションを開く**\] をクリックします。 使用している電子メール クライアントが Microsoft Office Outlook の場合、PIN は新しい電子メール メッセージに自動的にコピーされます。 他の電子メール クライアントを使用している場合は、\[**PIN の表示**\] チェック ボックスをオンにして PIN を表示し、電子メール メッセージにコピーしてください。

10. \[**閉じる**\] をクリックします。

## Windows PowerShell コマンドレットを使用してユーザー PIN を割り当てる

Set-CsClientPin コマンドレットを使用して、PIN 番号を割り当てることができます。このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## PIN 番号をユーザーに割り当てるには

  - 次のコマンドでは、PIN 番号を Ken Myer というユーザーに割り当てます。Pin パラメーターが含まれないので、Lync Server が自動的に PIN 番号を生成して割り当てます。
    
        Set-CsClientPin -Identity "Ken Myer" 

## 特定の PIN 番号をユーザーに割り当てるには

  - このコマンドでは、Pin パラメーターを使用して PIN 番号 121989 を Ken Myer というユーザーに割り当てます。
    
        Set-CsClientPin -Identity "Ken Myer" -Pin 121989

詳細については、[Set-CsClientPin](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPin) コマンドレットのヘルプ トピックを参照してください。

## 関連項目

#### 概念

[ダイヤルイン アクセス番号](https://technet.microsoft.com/ja-jp/library/gg133674\(v=ocs.15\))  

#### その他のリソース

[ダイヤルイン会議の暗証番号 (PIN) ルールの構成](lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md)

