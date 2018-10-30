---
title: クライアント バージョン ポリシー ルールを表示する
TOCTitle: クライアント バージョン ポリシー ルールを表示する
ms:assetid: f3a0215f-f72f-4e9b-a07b-25858dc4203a
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ923060(v=OCS.15)
ms:contentKeyID: 52056749
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# クライアント バージョン ポリシー ルールを表示する

 

_**トピックの最終更新日:** 2013-02-23_

クライアント バージョン ポリシーは、一連のクライアント バージョン ポリシー ルールで構成されます。これらのルールでは、ユーザーが特定のクライアントおよびクライアント バージョンでログオンしようとしたときに実行するアクションが定義されています。クライアント バージョン ポリシー ルールは Lync Server 2013 コントロール パネルまたは Lync Server 2013 管理シェルから表示できます。

## Lync Server コントロール パネルを使用してクライアント バージョン ポリシー ルールを表示するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**クライアント**\] をクリックし、\[**クライアント バージョン ポリシー**\] ナビゲーション ボタンをクリックします。

4.  \[**クライアント バージョン ポリシー**\] ページで、表示するクライアント バージョン ポリシーをダブルクリックします。

5.  \[**編集 クライアント バージョン ポリシー**\] ページにルールが表示されます。ルールの詳細を表示するには、ルールを選択し、\[**詳細の表示**\] をクリックします。

## Windows PowerShell コマンドレットを使用してクライアント バージョン ポリシー ルールを表示する

クライアント バージョン ポリシー ルールは Lync Server 管理シェルおよび **Get-CsClientVersionPolicyRule** コマンドレットを使用して表示できます。このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモート セッションのどちらからでも実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## クライアント バージョン ポリシー ルールを表示するには

  - クライアント バージョン ポリシー ルールを表示するには、Lync Server 管理シェルに次のコマンドを入力し、Enter キーを押します。
    
        Get-CsClientVersionPolicyRule
    
    構成されているルールごとに次のような情報が表示されます。
    
        Identity          : Global/2336c611-a243-4c5d-994b-eea8a524d0e4
        Priority          : 0
        RuleId            : 2336c611-a243-4c5d-994b-eea8a524d0e4
        Description       :
        Action            : Block
        ActionUrl         :
        MajorVersion      : 1
        MinorVersion      : 3
        BuildNumber       :
        QfeNumber         :
        UserAgent         : RTC
        UserAgentFullName :
        Enabled           : True
        CompareOp         : LEQ

詳細については、[Get-CsClientVersionPolicyRule](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClientVersionPolicyRule) コマンドレットに関するヘルプ トピックを参照してください。

