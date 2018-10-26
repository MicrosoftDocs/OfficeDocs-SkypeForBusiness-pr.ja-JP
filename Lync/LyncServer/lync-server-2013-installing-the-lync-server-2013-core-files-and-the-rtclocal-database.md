---
title: Lync Server 2013 コア ファイルおよび RTCLocal データベースのインストール
TOCTitle: Lync Server 2013 コア ファイルおよび RTCLocal データベースのインストール
ms:assetid: 206f0c1d-40f7-45b6-aa62-88aaef6cf7f6
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204734(v=OCS.15)
ms:contentKeyID: 48271480
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 コア ファイルおよび RTCLocal データベースのインストール

 

_**トピックの最終更新日:** 2012-10-20_

Lync Server 2013 のコア ファイルをコンピューターにインストールするには、以下の手順を実行します。RTCLocal データベースは、コア ファイルをインストールするときに自動的にインストールされます。SQL Server をウォッチャー ノードにインストールする必要はありません。代わりに、SQL Server Express が自動的にインストールされます。

Lync Server 2013 のコア ファイルと RTCLocal データベースをインストールするには、次の手順を実行します。

1.  ウォッチャー ノード コンピューターで、\[**スタート**\] ボタンをクリックし、\[**すべてのプログラム**\]、\[**アクセサリ**\] の順にクリックします。次に、\[**コマンド プロンプト**\] を右クリックし、\[**管理者として実行**\] をクリックします。

2.  コンソール ウィンドウで、次のコマンドを入力して Enter キーを押します。Lync Server セットアップ ファイルのパスは各自の環境に合わせてください。
    
        D:\Setup.exe /BootstrapLocalMgmt

Lync Server のコア コンポーネントが正しくインストールされたかどうかを確認するには、\[**スタート**\] ボタンをクリックし、\[**すべてのプログラム**\] をクリックします。次に、\[**Lync Server 2013**\] をクリックし、\[**Lync Server 管理シェル**\] をクリックします。Lync Server 2013 管理シェルで、次の Windows PowerShell コマンドを入力し、Enter キーを押します。

    Get-CsWatcherNodeConfiguration

最初にこのコマンドを実行したときは、まだウォッチャー ノード コンピューターを構成していないので何もデータが表示されません。コマンドを実行してエラーが表示されなければ、Lync Server セットアップは正常に完了したと見なすことができます。

ウォッチャー ノード コンピューターが境界ネットワーク内にある場合は、次のコマンドを実行して Lync Server 2013 のインストールを確認できます。

    Get-CsPinPolicy

組織で構成されている暗証番号 (PIN) ポリシーの数に応じて、次のような情報が表示されます。

    Identity             : Global
    Description          :
    MinPasswordLength    : 5
    PINHistoryCount      : 0
    AllowCommonPatterns  : False
    PINLifetime          : 0
    MaximumLogonAttempts :

PIN ポリシーに関する情報が表示された場合は、コア コンポーネントが正常にインストールされています。

