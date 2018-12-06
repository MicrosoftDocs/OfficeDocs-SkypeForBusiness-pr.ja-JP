---
title: 'Lync Server 2013: Lync Server の Windows 更新プログラム'
TOCTitle: Lync Server 2013 の Windows 更新プログラム
ms:assetid: fe26ab32-b1a9-421d-9227-506703d4b834
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Dn518337(v=OCS.15)
ms:contentKeyID: 60498642
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の Windows 更新プログラム

 

_**トピックの最終更新日:** 2013-12-05_

Windows Update サービスを使用して、更新プログラムおよびセキュリティ更新プログラムの確認と適用を頻繁に行ってください。これは、他のシステム コンポーネントの脆弱性を利用した攻撃者が管理者権限で Microsoft Lync Server 2013 を実行するサーバーにアクセスして Lync Server 2013 に危害を加えるのを防ぐのに役立ちます。

Microsoft SQL Server 2008 Express (64 ビット版) 用の更新プログラムは、個々の Lync Server 2013 Standard Edition サーバー (バックエンド データベースの場合) および他のすべての Lync Server 2013 サーバーの役割 (ローカル構成ストアの場合) で実行します。ただし、これらのデータベースを SQL Server 2008 R2 Express にアップグレードしていないことが条件です。フロントエンド プールのバックエンド データベース、監視データベース、およびアーカイブ データベースでの SQL Server と同様に、これらのデータベースは日常的なセキュリティ更新プログラム管理の一部と考える必要があります。

## ベスト プラクティス

  - Windows Update を使用して、コンピューターを常に最新の状態に保ちます。

