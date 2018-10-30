---
title: 'Lync Server 2013: SQL Server のシステム要件'
TOCTitle: SQL Server のシステム要件
ms:assetid: 9c235085-cbfa-4e9e-9cec-3f5749039a6b
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205112(v=OCS.15)
ms:contentKeyID: 48273019
ms.date: 07/20/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の SQL Server のシステム要件

 

_**トピックの最終更新日:** 2013-10-25_

Enterprise Edition サーバーを展開する前に、Microsoft SQL Server 2008 R2 または Microsoft SQL Server 2012 を、ハードウェア要件を満たす専用のコンピューターにインストールします。ハードウェア要件の詳細については、「サポート」のドキュメントの「[Lync Server 2013　用のサーバー ハードウェア プラットフォーム](lync-server-2013-server-hardware-platforms.md)」を参照してください。ソフトウェア要件の詳細については、「サポート」のドキュメントの「[Lync Server 2013 でのデータベース ソフトウェアのサポート](lync-server-2013-database-software-support.md)」を参照してください。展開に必要なアクセス許可の詳細については、「[Lync Server 2013 の SQL Server の展開のアクセス許可](lync-server-2013-deployment-permissions-for-sql-server.md)」を参照してください。

また、フロントエンド プールを作成する前に、Lync Server 2013 が特定のポートを経由して SQL Server にアクセスできるように Windows ファイアウォールを構成する必要があります。そのためには、SQL Server 構成マネージャーを使用するサーバー用のポートを定義し、それらのポートをセキュリティが強化された Windows ファイアウォールで開きます。

