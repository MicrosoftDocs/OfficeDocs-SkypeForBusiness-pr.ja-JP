---
title: Operation Manager エージェント ファイルのインストール
TOCTitle: Operation Manager エージェント ファイルのインストール
ms:assetid: e2246c44-0c75-43fc-8b04-26e53c5dd572
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205345(v=OCS.15)
ms:contentKeyID: 48273941
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Operation Manager エージェント ファイルのインストール

 

_**トピックの最終更新日:** 2012-10-20_

Operations Manager エージェント ファイルをコンピューターにインストールするには、次のステップを実行します。

1.  System Center セットアップ メディアで、\[**SetupOM.exe**\] をクリックします。

2.  System Center Operation Manager セットアップで、\[**Operations Manager エージェントのインストール**\] をクリックします。

3.  System Center Setup ウィザードの \[**System Center Operations Manager セットアップへようこそ**\] ウィザード ページで、\[**次へ**\] をクリックします。

4.  \[**インストール先フォルダー**\] ページで、Operations Manager エージェント ファイルがインストールされるフォルダーを選択し、\[**次へ**\] をクリックします。

5.  \[**管理グループの構成**\] ページで、\[**管理グループ情報の指定**\] を選択し、\[**次へ**\] をクリックします。

6.  \[**管理グループの構成**\] ページで、\[**管理グループ名**\] ボックスに Operations Manager 管理グループの名前を入力し、\[**管理サーバー**\] ボックスに Operations Manager サーバーのホスト名 (たとえば、tl-scom-001) を入力します。Operations Manager が使用するポート番号を変更した場合は、\[管理サーバー ポート\] ボックスに新しいポート番号を入力します。そうしない場合は、ポートを既定の値 5723 のままにし、\[**次へ**\] をクリックします。

7.  \[**エージェント アクション アカウント**\] ページで、\[**ローカル システム**\] を選択し、\[**次へ**\] をクリックします。

8.  \[**Microsoft Update**\] ページで、\[**Microsoft Update を使用しない**\] を選択し、\[**次へ**\] をクリックします。

9.  \[**インストールの準備完了**\] ページで、\[**インストール**\] をクリックします。

10. \[**System Center Operations Manager セットアップ ウィザードを完了しています**\] ページで、\[**完了**\] をクリックします。

11. \[**終了**\] をクリックします。

System Center 2007 R2 を使用している場合は、\[**スタート**\]、\[**すべてのプログラム**\]、\[**System Center Operations Manager 2007 R2**\]、\[**Operations Manager シェル**\] の順にクリックして、エージェントが作成されていることを確認できます。Operations Manager シェルで、次の Windows PowerShell コマンドを入力し、Enter キーを押します。

    Get-Agent 

Operations Manager エージェントの一覧が画面に表示されます。

System Center 2012 を使用している場合は、Operations 2012 Manager シェルからこのコマンドを実行します。

    Get-SCOMAgent

