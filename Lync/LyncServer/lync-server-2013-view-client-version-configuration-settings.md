---
title: クライアント バージョン構成設定の表示
TOCTitle: クライアント バージョン構成設定の表示
ms:assetid: c72df4e6-a889-4cb6-86f7-8334d7774c6e
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ923062(v=OCS.15)
ms:contentKeyID: 52056702
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# クライアント バージョン構成設定の表示

 

_**トピックの最終更新日:** 2013-02-23_

クライアント バージョンの構成設定は、クライアント バージョンの制御を有効または無効にするために使用します。グローバル クライアント バージョンの構成は Lync Server 2013 と共にインストールされ、サーバーの展開全体に対するクライアント バージョンの制御を有効または無効にするために使用されます。グローバル構成を有効にすると、ユーザーがログオンを試みたときに、適用されているすべてのクライアント バージョン ポリシーが有効になります。Lync Server 2013 コントロール パネルまたは Lync Server 2013 管理シェルからクライアント バージョンの構成設定を表示できます。

> [!NOTE]
> 匿名ユーザーをユーザー、サイト、またはサービスに関連付けることはできないため、匿名ユーザーが影響を受けるのはグローバル レベルのポリシーだけです。


## Lync Server コントロール パネル を使用して、クライアント バージョンの構成設定を表示するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**クライアント**\] をクリックし、\[**クライアント バージョンの構成**\] ナビゲーション ボタンをクリックします。

4.  表示するクライアント バージョンの構成の名前をダブルクリックします。

## Windows PowerShell コマンドレットを使用して、クライアント バージョンの構成設定を表示する

**Get-CsClientVersionConfiguration** コマンドレットを使用して、クライアント バージョンの構成設定を表示できます。このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## クライアント バージョン構成情報を表示するには

  - すべてのクライアント バージョンの構成設定の情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、Enter キーを押します。
    
        Get-CsClientVersionConfiguration
    
    次のような情報が表示されます。
    
        Identity      : Global
        DefaultAction : Allow
        DefaultURL    :
        Enabled       : True

詳細については、[Get-CsClientVersionConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClientVersionConfiguration) コマンドレットに関するヘルプ トピックを参照してください。

