---
title: クライアント バージョン構成設定のコレクションの作成または変更
TOCTitle: クライアント バージョン構成設定のコレクションの作成または変更
ms:assetid: 4e6faffd-a36f-40f1-8734-78d84b7df921
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ898477(v=OCS.15)
ms:contentKeyID: 52056593
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# クライアント バージョン構成設定のコレクションの作成または変更

 

_**トピックの最終更新日:** 2013-02-23_

クライアント バージョンの構成設定は、クライアント バージョンの制御を有効または無効にするために使用します。グローバル クライアント バージョンの構成は Lync Server と共にインストールされ、サーバーの展開全体に対するクライアント バージョンの制御を有効または無効にするときに使用されます。個別のサイトに対して、クライアント バージョンの構成設定を構成することもできます。クライアント バージョンの構成設定を作成または変更するには、Lync Server 2013 コントロール パネルまたは Lync Server 2013 管理シェルを使用します。

> [!NOTE]
> 匿名ユーザーをユーザー、サイト、またはサービスに関連付けることはできないため、匿名ユーザーが影響を受けるのはグローバル レベルのポリシーだけです。


## Lync Server コントロール パネルを使用して、クライアント バージョンの構成設定を作成または変更するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**クライアント**\] をクリックし、\[**クライアント バージョンの構成**\] ナビゲーション ボタンをクリックします。

4.  \[**クライアント バージョンの構成**\] ページで、次の操作を行います。
    
      - 新しい構成を作成するには、\[**新規**\] をクリックし、サイトを選択して \[**OK**\] をクリックし、設定を更新します。
    
      - 構成を変更するには、構成を選択し、\[**編集**\]、\[**詳細の表示**\] の順にクリックして、設定を変更します。

## Windows PowerShell コマンドレットを使用してクライアント バージョンの構成設定を作成または変更する

クライアント バージョンの構成設定を作成するには、**New-CsClientVersionConfiguration** コマンドレットを使用します。変更するには、**Set-CsClientVersionConfiguration** コマンドレットを使用します。これらのコマンドレットは、Lync Server 2013 管理シェルから実行することも、Windows PowerShell のリモート セッションから実行することもできます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## クライアント バージョンの構成設定の新しいコレクションを作成するには

  - 次のコマンドを実行すると、Redmond サイトに適用されるクライアント バージョンの構成設定の新しいコレクションが作成されます。この例では、Redmond サイトのクライアントのバージョン管理が無効になります。
    
        New-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $False

## サイトのクライアントのバージョン管理を有効にするには

  - 次のコマンドでは、Redmond サイトのクライアントのバージョン管理を有効にします。
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

## 組織全体でクライアントのバージョン管理を無効にするには

  - 次の例では、組織で使用されているすべてのクライアント バージョンの構成設定で、クライアントのバージョン管理が無効になります。
    
        Get-CsClientVersionConfiguration | Set-CsClientVersionConfiguration  -Enabled $False

詳細については、[New-CsClientVersionConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClientVersionConfiguration) および [Set-CsClientVersionConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientVersionConfiguration) コマンドレットのヘルプ トピックを参照してください。

