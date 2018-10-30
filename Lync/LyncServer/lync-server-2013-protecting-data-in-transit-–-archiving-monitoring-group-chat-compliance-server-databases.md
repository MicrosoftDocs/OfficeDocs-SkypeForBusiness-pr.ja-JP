---
title: "Lync Server 2013: 転送中データの保護 (アーカイブ、監視、グループ チャット コンプライアンス サーバーのデータベース)"
TOCTitle: Lync Server 2013 での転送中のデータの保護 (アーカイブ データベース、監視データベース、グループ チャット コンプライアンス サーバー データベース)
ms:assetid: ea219705-1015-43a7-890b-e7e67b451e7c
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Dn518336(v=OCS.15)
ms:contentKeyID: 60498629
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での転送中のデータの保護 (アーカイブ データベース、監視データベース、グループ チャット コンプライアンス サーバー データベース)

 

_**トピックの最終更新日:** 2016-12-08_

Microsoft Lync Server 2013 のアーカイブ サーバーと監視サーバーはどちらも、メッセージ キュー (別名 MSMQ) サービスを使用して、コレクション ポイントからデータ メッセージを収集し、それらをリポジトリ サーバーに確実に移動します。コンプライアンス サービスはグループ チャット サーバーと連携してデータを収集し、この場合もメッセージ キューが使用されます。

Lync Server 2013 では、回線上のデータの内部保護はありません。ただし、このトラフィックをセキュリティで保護する必要がある場合、メッセージ キュー サービスでは、送信側メッセージ キューでメッセージ レベルの暗号化を提供できます。この機能は、Active Directory ドメイン サービスによって管理される証明書を使用して実現されます。詳細については、「付録 D: Windows Server 2008 のメッセージ キューとインターネット通信」([http://go.microsoft.com/fwlink/p/?LinkId=145238](http://go.microsoft.com/fwlink/p/?linkid=145238))、または Windows Server 2008 R2 の場合は「付録 I: Windows Server 2008 R2 のメッセージ キューとインターネット通信 (英語)」([http://go.microsoft.com/fwlink/p/?LinkId=211883](http://go.microsoft.com/fwlink/p/?linkid=211883)) を参照してください。

