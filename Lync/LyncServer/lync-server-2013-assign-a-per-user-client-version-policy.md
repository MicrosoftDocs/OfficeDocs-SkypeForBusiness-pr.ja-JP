---
title: ユーザー単位のクライアント バージョン ポリシーの割り当て
TOCTitle: ユーザー単位のクライアント バージョン ポリシーの割り当て
ms:assetid: f7e8ba2f-62dc-4e7d-8b63-682986f10240
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg182607(v=OCS.15)
ms:contentKeyID: 48274099
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ユーザー単位のクライアント バージョン ポリシーの割り当て

 

_**トピックの最終更新日:** 2013-02-22_

クライアント バージョン ポリシーは、Lync Server コントロール パネルで構成可能なユーザー アカウントの個別の設定の 1 つです。

1 つ以上のユーザーごとのクライアント バージョン ポリシーを展開するかどうかはオプションです。グローバル レベルのクライアント バージョン ポリシーのみを展開するか、サイト レベルやプール レベルのクライアント バージョン ポリシーを展開することもできます。ユーザー単位のポリシーを展開する場合は、ポリシーをユーザー、グループ、または連絡先オブジェクトに明示的に割り当てる必要があります。特定のサイト レベル、プール レベル、またはユーザーごとのポリシーが割り当てられていない場合、Lync Server 2013 に登録することを許可される既定のクライアントは、グローバル レベルのクライアント バージョン ポリシーで定義されているクライアントです。

少なくとも 1 つのユーザーごとのクライアント バージョン ポリシーを作成したら、このトピックで示す手順に従って、Lync Server に登録することを許可するクライアント バージョンを指定するポリシーを割り当てます。

ユーザーごとのクライアント バージョン ポリシーの作成の詳細については、「[Lync Server 2013 のログオンに使用するクライアント アプリケーションの指定](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md)」を参照してください。

## ユーザーごとのクライアント バージョン ポリシーを割り当てるには

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
    > 同じユーザーごとのクライアント バージョン ポリシーを複数のユーザーに適用する場合は、検索結果から複数のユーザーを選択し、[<STRONG>アクション</STRONG>] をクリックして、[<STRONG>ポリシーの割り当て</STRONG>] をクリックします。



7.  \[**ポリシーの割り当て**\] の \[**クライアント バージョン ポリシー**\] の下で、次のいずれかの操作を行います。
    
    > [!NOTE]
    > [<strong>ポリシーの割り当て</strong>] ダイアログ ボックスを使用して構成できるポリシーは 1 つではないため、ダイアログ ボックスではすべてのポリシーについてそれぞれ既定で [<strong>&lt;現状のまま保持&gt;</strong>] が選択されます。 この設定を変更しない場合は、以前にユーザーに割り当てたポリシーを使用して続行します。
    
      - Lync Server に、自動的にグローバル レベル ポリシーを選択させるか、定義済みの場合は、サイト レベル ポリシーかプール レベル ポリシーを選択させます。
    
      - \[**クライアント バージョン ポリシー**\] ページで前に定義したユーザーごとのクライアント バージョン ポリシーの名前をクリックします。
        

        > [!TIP]
        > 割り当てるポリシーの決定に役立てるために、ポリシー名をクリックしたら [<STRONG>表示</STRONG>] をクリックして、ポリシーで定義されているユーザー権限やアクセス許可を確認します。



8.  終了したら、\[**OK**\] をクリックします。

## Lync Server 管理シェル コマンドレットを使ってユーザーごとのクライアント バージョン ポリシーを割り当てるには

Grant-CsClientVersionPolicy コマンドレットを使ってユーザーごとのクライアント バージョン ポリシーを割り当てます。このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## 単一のユーザーにユーザーごとのクライアント バージョン ポリシーを割り当てるには

  - 次のコマンドでは、RedmondClientVersionPolicy というユーザーごとのクライアント バージョン ポリシーをユーザー Ken Myer に割り当てます。
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName "RedmondClientVersionPolicy"

## 複数のユーザーにユーザーごとのクライアント バージョン ポリシーを割り当てるには

  - このコマンドでは、RedmondVoicePolicy という音声ポリシーを現在割り当てられているすべてのユーザーに、RedmondClientVersionPolicy というユーザーごとのクライアント バージョン ポリシーを割り当てます。このコマンドで使用されている Filter パラメーターの詳細については、[Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) コマンドレットのドキュメントを参照してください。
    
        Get-CsUser -Filter {VoicePolicy -eq "RedmondVoicePolicy"} | Grant-CsClientVersionPolicy -PolicyName "RedmondClientVersionPolicy"

## ユーザーごとのクライアント バージョン ポリシーの割り当てを解除するには

  - 次のコマンドは、以前に Ken Myer に割り当てられたすべてのユーザーごとのクライアント バージョン ポリシーを解除します。ユーザーごとのポリシーが解除された後、Ken Myer はグローバル ポリシー、ローカル サイト ポリシー (存在する場合)、またはレジストラーに割り当てられたサービス スコープ ポリシーによって自動的に管理されることになります。サービス スコープ ポリシーはサイト ポリシーより優先され、サイト ポリシーはグローバル ポリシーより優先されます。
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName $Null

詳細については、[Grant-CsClientVersionPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsClientVersionPolicy) コマンドレットのヘルプ トピックを参照してください。

## 関連項目

#### その他のリソース

[ユーザー単位のポリシーの割り当て](lync-server-2013-assigning-per-user-policies.md)  
[Lync Server 2013 でのデバイス、電話、クライアント アプリケーションの管理](lync-server-2013-managing-devices-phones-and-client-applications.md)

