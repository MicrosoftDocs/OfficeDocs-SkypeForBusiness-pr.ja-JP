---
title: 'Lync Server 2013: ミラー化データベースのフェールオーバー'
TOCTitle: ミラー化データベースのフェールオーバー
ms:assetid: 70185476-e3d4-440a-9316-fa24b226343e
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204991(v=OCS.15)
ms:contentKeyID: 48272428
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのミラー化データベースのフェールオーバー

 

_**トピックの最終更新日:** 2014-03-14_

ミラーリング監視を伴う同期されたミラーリングを使用するようにバックエンド データベースを構成している場合、フェールオーバーは自動で行われます。ミラーリング監視を伴わない同期されたミラーリングを構成している場合は、以下の手順を使用して、データベースのフェールオーバーとフェールバックを実行できます。また、これらの手順を使用すると、ミラーリング監視を構成している場合でも、データベースのフェールオーバーとフェールバックを手動で実行できます。

## バックエンド データベースをフェールオーバーするには

1.  フェールオーバーを行う前に、次のコマンドレットを入力して、どのバックエンド データベースがプリンシパルでどれがミラーであるかを確認します。
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType User

2.  中央管理ストアがこのプール内でホストされている場合は、次のコマンドレットを入力して、中央管理ストアのプリンシパルとミラーをそれぞれ確認します。
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt

3.  ユーザー データベースのフェールオーバーを以下のように実行します。
    
      - プライマリに障害が発生してミラーにフェールオーバーする場合は、次のコマンドレットを入力します。
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal mirror -Verbose
    
      - ミラーに障害が発生してプライマリにフェールオーバーする場合は、次のコマンドレットを入力します。
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal primary -Verbose

4.  プールで 中央管理サーバーをホストしている場合は、以下のように 中央管理ストアのフェールオーバーを実行します。
    
      - プライマリに障害が発生してミラーにフェールオーバーする場合は、次のコマンドレットを入力します。
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal mirror -Verbose
    
      - ミラーに障害が発生してプライマリにフェールオーバーする場合は、次のコマンドレットを入力します。
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal primary -Verbose

