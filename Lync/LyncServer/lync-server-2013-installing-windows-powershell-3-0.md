---
title: 'Lync Server 2013: Windows PowerShell 3.0 のインストール'
TOCTitle: Windows PowerShell 3.0 のインストール
ms:assetid: d87bf21e-0a43-41cb-8fdc-626cedec8538
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205328(v=OCS.15)
ms:contentKeyID: 48273805
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 用の Windows PowerShell 3.0 のインストール

 

_**トピックの最終更新日:** 2016-12-08_

Lync Server 2013 を適切に展開するには、Lync Server トポロジの一部である各コンピューター上に Windows PowerShell 3.0 が必要です。

Windows Server 2012 または Windows Server 2012 R2 を実行しているシステムの場合、PowerShell 3.0 はこれらのオペレーティング システムに含まれているため、ここでの作業は不要で、展開の次の段階に進むことができます。


> [!IMPORTANT]
> ただし、Windows Server 2008 R2 SP1 を実行しているシステムの場合は、Lync Server 2013 をインストールする前に前提条件として PowerShell 3.0 をインストールする必要があります。インストールしないと、正常に機能しません。PowerShell 3.0 をインストールするには、「<A href="http://go.microsoft.com/fwlink/p/?linkid=329800">Windows Management Framework 3.0</A>」を参照してください。これは PowerShell 3.0 のダウンロード ページへの直接リンクで、インストールの成功に関連する情報も含まれます。



インストールを完了しているか、Lync Server 環境の操作を続行する前にチェックして確認する場合は、次のように操作するとサーバー上に PowerShell 3.0 が存在することを簡単に確認できます。

1.  チェックするサーバー上で、\[**スタート**\] ボタンをクリックし、\[**すべてのプログラム**\]、\[**アクセサリ**\]、\[**Windows PowerShell**\] の順に選択し、\[**Windows PowerShell**\] をクリックします。

2.  Windows PowerShell コンソールのコマンド プロンプトで、次のコマンドを入力し、Enter キーを押します。
    
        Get-Host | Select-Object Version

3.  Windows PowerShell 3.0 がインストールされている場合は、次のように表示されます。
    
        Version
        -------
        3.0

