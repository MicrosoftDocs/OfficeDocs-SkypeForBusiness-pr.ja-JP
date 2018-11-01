---
title: クライアント バージョン ポリシーを表示する
TOCTitle: クライアント バージョン ポリシーを表示する
ms:assetid: 6cd9a897-c694-4d6a-8259-2d3c01fce275
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ898479(v=OCS.15)
ms:contentKeyID: 52056616
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# クライアント バージョン ポリシーを表示する

 

_**トピックの最終更新日:** 2013-02-23_

クライアント バージョン ポリシーは、一連のクライアント バージョン管理ルールを、グローバルに、あるいは特定のサイト、プール、またはユーザーのグループに適用する目的で使用されます。Lync Server 2013 コントロール パネルまたは Lync Server 2013 管理シェルから、Lync Server 2013 環境で構成されたクライアント バージョン ポリシーを表示できます。

## Lync Server コントロール パネルを使用してクライアント バージョン ポリシーを表示するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**クライアント**\] をクリックし、\[**クライアント バージョン ポリシー**\] ナビゲーション ボタンをクリックします。

4.  クライアント バージョン ポリシーのルールを表示する場合は、\[**クライアント バージョン ポリシー**\] ページで、表示するポリシーをダブルクリックします。

## Windows PowerShell コマンドレットを使用してクライアント バージョン ポリシーを表示する

**Get-CsClientVersionPolicy** コマンドレットを使用してクライアント バージョン ポリシーを表示できます。このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## クライアント バージョン ポリシーを表示するには

  - すべてのクライアント バージョン ポリシーに関する情報を表示するには、Lync Server 管理シェルに次のコマンドを入力し、Enter キーを押します。
    
        Get-CsClientVersionPolicy
    
    次のような情報が表示されます。
    
        Identity    : Global
        Rules       : {RuleId=2336c611-a243-4c5d-994b-eea8a524d0e4;
                      Description=;Action=Block;ActionUrl=;MajorVersion=1;
                      MinorVersion=3;BuildNumber=;QfeNumber=;
                      UserAgent=RTC;UserAgentFullName=;Enabled=True;
                      CompareOp=LEQ, RuleId=342c9b90-4cef-483a-a73a-
                      4fe75c88711d;Description=;Action=Block;ActionUrl=;
                      MajorVersion=5;MinorVersion=;BuildNumber=;QfeNumber=;
                      UserAgent=WM;UserAgentFullName=;Enabled=True;
                      CompareOp=LEQ,RuleId=ea03af61-9db5-4bf9-af3f-042
                      ab8dd9994;Description=;Action=Block;ActionUrl=;
                      MajorVersion=3;MinorVersion=5;BuildNumber=6907;
                      QfeNumber=83;UserAgent=OC;UserAgentFullName=;
                      Enabled=True;CompareOp=LEQ, RuleId=831edb68-
                      e482-4431-a10e-add365ba8099;Description=;
                      Action=Block;ActionUrl=;MajorVersion=2;MinorVersion=0;
                      BuildNumber=5999;QfeNumber=;UserAgent=UCCP;
                      UserAgentFullName=;Enabled=True;CompareOp=LEQ...}
        Description :

詳細は、[Get-CsClientVersionPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClientVersionPolicy) コマンドレットのヘルプ トピックを参照してください。

