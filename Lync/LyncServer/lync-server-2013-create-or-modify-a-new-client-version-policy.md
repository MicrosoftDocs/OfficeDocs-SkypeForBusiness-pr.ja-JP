---
title: 新しいクライアント バージョン ポリシーの作成または変更
TOCTitle: 新しいクライアント バージョン ポリシーの作成または変更
ms:assetid: 4be6e449-aa82-4b46-abb1-d31281573a72
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ898476(v=OCS.15)
ms:contentKeyID: 52056598
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 新しいクライアント バージョン ポリシーの作成または変更

 

_**トピックの最終更新日:** 2013-02-23_

クライアント バージョン ポリシーを使用すると、環境でサポートされるクライアントのバージョンを指定できます。クライアント バージョン管理機能は、複数バージョンのクライアントのサポート コストを抑えるのに役立ちます。また、この機能により、全体的なユーザー エクスペリエンスも向上します。これは、以前のバージョンと新しいバージョンのクライアントが対話するとき、使用できる機能は、以前のバージョンのクライアントによって制限される場合があるからです。クライアント バージョン ポリシーを作成または変更するには、Lync Server 2013 コントロール パネルまたは Lync Server 2013 管理シェルを使用します。

## Lync Server コントロール パネルを使用して、クライアント バージョン ポリシーを作成または変更するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**クライアント**\] をクリックします。
    
    > [!NOTE]
    > 既定では、[<strong>クライアント バージョン ポリシー</strong>] タブが選択されます。


4.  \[**クライアント バージョン ポリシー**\] ページで、次のどちらかの操作を行います。
    
      - 新しいクライアント バージョン ポリシーを作成するには、\[**新規**\] をクリックし、\[**サイト ポリシー**\]、\[**プール ポリシー**\]、または \[**ユーザー ポリシー**\] を選択して、\[**OK**\] をクリックします。
    
      - グローバル ポリシーまたは他の既存のクライアント バージョン ポリシーを変更するには、ポリシーを選択し、\[**編集**\]、\[**詳細の表示**\] の順にクリックします。

5.  「[新しいクライアント バージョン ポリシー ルールを作成または変更する](lync-server-2013-create-or-modify-a-new-client-version-policy-rule.md)」に従って、\[**編集 クライアント バージョン ポリシー**\] ページで、ルールを作成または変更します。

## Windows PowerShell コマンドレットを使用してクライアント バージョン ポリシーを作成または変更する

クライアント バージョン ポリシーを作成するには、**New-CsClientVersionPolicy** コマンドレットを使用します。変更するには、**Set-CsClientVersionPolicy** コマンドレットを使用します。これらのコマンドレットは、Lync Server 2013 管理シェルから実行することも、Windows PowerShell のリモート セッションから実行することもできます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## 新しいサイト スコープのクライアント バージョン ポリシーを作成するには

  - 次のコマンドを実行すると、Redmond サイトに適用される新しいクライアント バージョン ポリシーが作成されます。追加のパラメーターが指定されていないので、新しいポリシーでは、既定のクライアント バージョン設定が使用されます。
    
        New-CsClientVersionPolicy -Identity "site:Redmond"

## ユーザーごとのクライアント バージョン ポリシーを新しく作成するには

  - ユーザーごとのポリシーを作成するには、次のようなコマンドを使用します。
    
        New-CsClientVersionPolicy -Identity "RedmondClientVersionPolicy"

詳細については、[New-CsClientVersionPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClientVersionPolicy) コマンドレットおよび [Set-CsClientVersionPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientVersionPolicy) コマンドレットに関するヘルプ トピックを参照してください。

