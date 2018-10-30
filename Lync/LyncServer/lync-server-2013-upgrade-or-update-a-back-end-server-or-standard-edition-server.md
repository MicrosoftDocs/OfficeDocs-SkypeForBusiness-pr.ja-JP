---
title: Lync Server 2013 でのバックエンド サーバーまたは Standard Edition サーバーのアップグレードまたは更新
TOCTitle: Lync Server 2013 でのバックエンド サーバーまたは Standard Edition サーバーのアップグレードまたは更新
ms:assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ721942(v=OCS.15)
ms:contentKeyID: 49887225
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのバックエンド サーバーまたは Standard Edition サーバーのアップグレードまたは更新

 

_**トピックの最終更新日:** 2012-11-01_

このトピックでは、Enterprise Editionバック エンド サーバーまたは Standard Edition サーバーで更新をインストールする方法について説明します。

アップグレード中にバックエンド サーバーが 30 分以上停止した場合、ユーザーは復元モードになることがあります。アップグレードが完了し、バックエンド サーバーがプール内のフロントエンド サーバーに再度接続されると、ユーザーは完全に元の機能に戻ります。アップグレードが 30 分未満の場合、ユーザーには影響ありません。

## バックエンド サーバーまたは Standard Edition サーバーを更新するには

1.  アップグレードするサーバーに CsAdministrator の役割のメンバーとしてログオンします。

2.  更新をダウンロードして、ローカル ハードディスクに抽出します。

3.  Lync Server 管理シェルを起動します。\[**スタート**\] ボタンをクリックし、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\] の順にポイントして、\[**Lync Server 管理シェル**\] をクリックします。

4.  Lync Server のサービスを停止します。コマンド ラインで次を入力します。
    
        Stop-CsWindowsService

5.  World Wide Web サービスを停止します。コマンド ラインで次を入力します。
    
        net stop w3svc

6.  Lync Server 管理シェルのウィンドウをすべて閉じます。

7.  更新をインストールします。

8.  Lync Server 管理シェルを起動します。\[**スタート**\] ボタンをクリックし、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\] の順にポイントして、\[**Lync Server 管理シェル**\] をクリックします。

9.  Lync Server のサービスを再度停止して、グローバル アセンブリ キャッシュ (GAC) –d アセンブリを取得します。コマンド ラインで次を入力します。
    
        Stop-CsWindowsService

10. World Wide Web サービスを再起動します。コマンド ラインで次を入力します。
    
        net start w3svc

11. 次のいずれかを実行して、LyncServerUpdateInstaller.exe が SQL Server データベースに対して行った変更を適用します。
    
      - これが Enterprise Editionバック エンド サーバーで、このサーバーにアーカイブ データベースや監視データベースなど、併置されたデータベースがない場合、コマンド ラインで次を入力します。
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    
      - これが Enterprise Editionバック エンド サーバーで、このサーバーに併置されたデータベースがある場合、コマンド ラインで次を入力します。
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    
      - Standard Edition サーバーの場合、コマンド ラインで次を入力します。
        
            Install-CsDatabase -Update -LocalDatabases

