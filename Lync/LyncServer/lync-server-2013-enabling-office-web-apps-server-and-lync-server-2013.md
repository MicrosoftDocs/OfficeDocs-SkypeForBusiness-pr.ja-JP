---
title: 'Lync Server 2013: Lync Server 2013 と Office Web Apps サーバーの有効化'
TOCTitle: Lync Server 2013 と Office Web Apps サーバーの有効化
ms:assetid: 3370ab55-9949-4f32-b88b-5cffed6aaad8
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204792(v=OCS.15)
ms:contentKeyID: 48271721
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 と Office Web Apps サーバーの統合の構成

 

_**トピックの最終更新日:** 2016-12-08_

Lync Server 2013は、Office Web Apps サーバー を使用して、PowerPoint プレゼンテーションを処理します。この手法の利点については、「[Lync Server 2013 での Web 会議の概要](lync-server-2013-web-conferencing-overview.md)」を参照してください。

これらの新しい機能を使用するには、管理者が Office Web Apps サーバー をインストールする必要があり、これらが Office Web Apps サーバー と通信するには、Lync Server 2013 を構成する必要があります。このドキュメントでは、Office Web Apps サーバー を使用できるように Lync Server 2013 を構成する方法について説明します。このドキュメントでは、Office Web Apps サーバー 自体をインストールする方法は説明しません。この方法については [http://go.microsoft.com/fwlink/?linkid=257525\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=257525%26clcid=0x411) の Microsoft Office Web Apps 展開 Web サイトを参照してください。このガイドには Office Web Apps サーバー の詳細な必須コンポーネント情報が含まれます。 Office Web Apps サーバー は、Lync Server、Microsoft SQL Server、またはすべてのその他のサーバー アプリケーションを実行していない、スタンドアロンのコンピューターにインストールする必要があることに注意してください (そのコンピューターには、バージョンを問わず、Microsoft Office はインストールしないでください)。また、Office Web Apps サーバー の実行に使用するすべてのコンピューターには、(.NET Framework 4.5 と Windows PowerShell 3.0 を含め) 一連の特定のソフトウェアをインストールする必要があります。これらの要件は、証明書および インターネット インフォメーション サービス (IIS) を構成する方法と共に、[http://go.microsoft.com/fwlink/?linkid=257525\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=257525%26clcid=0x411) の Microsoft Office Web Apps 展開 Web サイトで詳細に説明されています。

このドキュメントでは次のトピック領域について説明します。

  - [Office Web Apps サーバーと連携する Lync Server 2013 の構成](lync-server-2013-configuring-lync-server-2013-to-work-with-office-web-apps-server.md)

  - [Lync Server 2013 でリバース プロキシ サーバーを使用して Office Web Apps サーバーを公開する](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md)

  - [Office Web Apps サーバーの構成の検証](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)

  - [Office Web Apps サーバーで使用するクライアントの構成](lync-server-2013-configuring-clients-for-use-with-office-web-apps-server.md)

