---
title: クライアント バージョン管理を有効または無効にする
TOCTitle: クライアント バージョン管理を有効または無効にする
ms:assetid: 33a98cb9-a979-4bb6-afb2-512f601d7ac5
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ898475(v=OCS.15)
ms:contentKeyID: 52056569
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# クライアント バージョン管理を有効または無効にする

 

_**トピックの最終更新日:** 2013-02-23_

クライアント バージョンの構成設定を使用して、クライアント バージョンの制御をグローバルにまたは特定のサイトに対して有効または無効にします。グローバル クライアント バージョン構成は Lync Server 2013 と共にインストールされます。この構成を使用して、サーバー展開全体に対してクライアント バージョンの制御を有効または無効にします。グローバル構成を有効にすると、ユーザーがログオンを試みたときに、適用されているすべてのクライアント バージョン ポリシーが有効になります。クライアント バージョン制御を行わないようにする場合は、グローバル クライアントバージョン構成を無効にできます。クライアント バージョン管理は、Lync Server 2013 コントロール パネルまたは Lync Server 2013 管理シェルで有効または無効にできます。

> [!NOTE]
> 匿名ユーザーをユーザー、サイト、またはサービスに関連付けることはできないため、匿名ユーザーが影響を受けるのはグローバル レベルのポリシーだけです。


## Lync Server コントロール パネルを使用して、クライアント バージョン管理を有効または無効にするには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**クライアント**\] をクリックし、\[**クライアント バージョンの構成**\] ナビゲーション ボタンをクリックします。

4.  次の手順を実行します。
    
      - クライアント バージョン管理をグローバルに有効または無効にするには、\[**グローバル**\] 構成をダブルクリックし、設定を変更します。
    
      - 特定のサイトに対してクライアント バージョン管理を有効または無効にするには、\[**新規**\] をクリックし、サイトを選択して \[**OK**\] をクリックし、サイトの設定を変更します。

## Windows PowerShell コマンドレットを使用してクライアント バージョン管理を有効または無効にする

**Set-CsClientVersionConfiguration** コマンドレットを使用してクライアント バージョン管理を有効または無効にできます。このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## クライアント バージョン管理を有効にするには

  - **Enabled** プロパティを True ($True) に設定することで、クライアント バージョン管理を有効にできます。
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

## クライアント バージョン管理を無効にするには

  - **Enabled** プロパティを False ($False) に設定することで、クライアント バージョン管理を無効にできます。
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

詳細については、[Set-CsClientVersionConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientVersionConfiguration) コマンドレットに関するヘルプ トピックを参照してください。

