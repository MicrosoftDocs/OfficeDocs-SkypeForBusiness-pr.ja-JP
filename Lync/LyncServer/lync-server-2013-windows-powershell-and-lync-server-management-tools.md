---
title: 'Lync Server 2013: Windows PowerShell と Lync Server の管理ツール'
TOCTitle: Windows PowerShell と Lync Server 2013 の管理ツール
ms:assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Dn481130(v=OCS.15)
ms:contentKeyID: 59679284
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Windows PowerShell と Lync Server 2013 の管理ツール

 

_**トピックの最終更新日:** 2016-12-08_

Microsoft Lync Server 2013 では、Windows PowerShell を使って管理ツールが実装されています。Windows PowerShell には、コマンド ライン環境、製品固有のコマンド、およびすべてのスクリプト言語が含まれています。Windows PowerShell を使って実装された Lync Server 2013 ツールは、次のとおりです。

  - **トポロジ ビルダー**: トポロジ ビルダーを使って、計画トポロジを作成、調整、および公開できます。また、サーバーのインストールを開始する前にトポロジを検証します。Lync Server 2013 を個々のサーバーにインストールするときに、インストール プロセスの一環として、公開されたトポロジが個々のサーバーに読み取られ、インストール プログラムがトポロジの指示に従ってサーバーを展開します。セットアップの後、構成情報はすべてのサーバーに自動的にレプリケートされます。トポロジ ビルダーを使ってのみ、展開にコンポーネントを追加できます。

  - **Lync Server 管理シェル**: Lync Server 管理シェルを使って、展開を完全にコマンド ライン管理できます。

  - **Lync Server コントロール パネル**: Microsoft Lync Server 2013 コントロール パネル ユーザー インターフェイスを使って、展開内の最も一般的なタスクを管理できます。

これらのツールでは、約 550 個の製品固有のコマンドレットを含めて、Windows PowerShell コマンドレットを使って展開を管理します。Lync Server 2013 に含まれるセキュリティのコマンドレットは、主に認証や、ユーザー権限とアクセス許可の管理に使用します。認証の管理には、さまざまなコマンドレット (証明書と暗証番号 (PIN) の認証用のコマンドレットなど) を使用できます。さらに、新しい役割ベースのアクセス制御 (RBAC) 機能を使用して Lync Server 2013 の管理機能を委任できるようにするためのコマンドレットも多数あります。Lync Server コマンドレットについて詳しくは、「操作」ドキュメントの「[Lync Server 2013 管理シェル](lync-server-2013-lync-server-management-shell.md)」をご覧ください。トポロジ ビルダー および Lync Server 2013 コントロール パネル を使って展開を管理する方法について詳しくは、「操作」ドキュメントの「[Lync Server 2013 コントロール パネル](https://technet.microsoft.com/ja-jp/library/gg133224\(v=ocs.15\))」をご覧ください。

Windows PowerShell のスクリプト セキュリティ機能は、Microsoft Visual Basic Scripting Edition (VBScript) など、古いテクノロジにおけるスクリプト関連のいくつかのセキュリティ問題を回避するように特別に設計されています。Windows PowerShell のセキュリティ機能は、ユーザーが簡単に、または知らないうちにスクリプトを実行できない環境を作成することを目的としています。既定では、Windows PowerShell のセキュリティ機能は有効です。これらの機能の状態は、スクリプトに関するニーズと多様なセキュリティの目標に応じて変更できます。シェルによってユーザーがスクリプトを実行できないようにするというわけではありません。あくまでも、ユーザー自身がスクリプトを実行しているという認識を持たずにスクリプトを実行することを、既定で困難にするということです。詳しくは、「Windows PowerShell スクリプト セキュリティ (英語)」([http://go.microsoft.com/fwlink/p/?LinkId=213145](http://go.microsoft.com/fwlink/p/?linkid=213145)) をご覧ください。

