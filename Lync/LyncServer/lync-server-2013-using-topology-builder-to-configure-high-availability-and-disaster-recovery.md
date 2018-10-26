---
title: 'Lync Server 2013: トポロジ ビルダーを使用して高可用性と障害回復を構成する'
TOCTitle: トポロジ ビルダーを使用して高可用性と障害回復を構成する
ms:assetid: abc1a25d-1f5e-46ef-91d2-0144fc847206
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205172(v=OCS.15)
ms:contentKeyID: 48273242
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でトポロジ ビルダーを使用して高可用性と障害回復を構成する

 

_**トピックの最終更新日:** 2012-10-06_

トポロジ ビルダーで次の手順を実行して、 常設チャット サーバーの高可用性と障害復旧を構成します。

1.  ミラー データベースとログ配布セカンダリ データベースの SQL Server ストアを追加します。

2.  常設チャット サーバー のサービス プロパティを次のように編集します。
    
    1.  プライマリ データベースのミラーリングを有効にします。
    
    2.  プライマリ ミラーの SQL Server ストアを追加します。
    
    3.  SQL Server のログ配布データベースを有効にします。
    
    4.  SQL Server のログ配布セカンダリ SQL Server ストアを追加します。
    
    5.  セカンダリ データベースの SQL Server ストア ミラーを追加します。
    
    6.  トポロジを公開します。

