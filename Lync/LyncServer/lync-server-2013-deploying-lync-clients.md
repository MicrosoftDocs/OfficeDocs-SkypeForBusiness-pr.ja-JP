---
title: Lync Server 2013 での Lync クライアントの展開
TOCTitle: Lync Server 2013 での Lync クライアントの展開
ms:assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204827(v=OCS.15)
ms:contentKeyID: 48271837
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での Lync クライアントの展開

 

_**トピックの最終更新日:** 2012-10-03_

Lync 2013 では、クライアント展開に異なる角度からアプローチできるようになりました。以前のリリースとは異なり、Lync 2013 には独自のインストーラーがありません。代わりに、Office 2013 セットアップ プログラムに Lync が含まれます。Lync 2013 は、Office 2013 のインストール方法およびカスタマイズ ツールを使用してユーザーに展開できます。

  - **Office 2013 Windows インストーラー:** Windows インストーラー ベースのインストール パッケージで、複数の MSI ファイルで構成されます。言語に依存しないコア MSI パッケージと 1 つ以上の言語固有のパッケージが組み合わされ 1 つの完全な製品になっています。セットアップによって個々のパッケージがアセンブルされ、ユーザーのコンピューターへの Office のインストール中およびインストール後に、カスタマイズ タスクとメンテナンス タスクが実行されます。このセクションのトピックでは、Office 2013 Windows インストーラーを使用/カスタマイズし、Lync 2013 を展開する方法について説明します。

  - **Office 2013 クイック実行:** Office セットアップ ファイルを Microsoft Office 365 ポータルからユーザーにストリームするインストール プログラムです。インストールのカスタマイズは、管理者がクイック実行用の Office 展開ツールを使用して行います。Office 2013 クイック実行は主に Microsoft Office 365 環境で使用されるので、このセクションでは、このインストール方法については詳しくは説明しません。クイック実行インストールの使用およびカスタマイズの詳細については、Office 2013 リソース キットのドキュメントを参照してください。管理者は、Office 2013 クイック実行プログラムおよび言語ソース ファイルを社内にダウンロードすることもできます。ネットワークの需要を最小限に抑えたいとき、または社内セキュリティ要件により、ユーザーがインターネットからソフトウェアをインストールできないようにしたいときに、社内にダウンロードすると便利です。

このセクションのトピックでは、Office 2013 MSI ベースのインストーラーを使用してクライアントを展開する方法を中心に説明します。主要な参照文献は Office 2013 リソース キットのドキュメントです。このドキュメントでは、インフラストラクチャの準備、セットアップのカスタマイズ、および Office 2013 の展開方法について解説します。また、Office のドキュメントもこのセクションのトピックと合わせてご利用ください。Office ドキュメントには、Lync 2013 に固有の展開に関する考慮事項が記載されています。

> [!NOTE]  
> <ul><li><p>Outlook メッセージングおよびコラボレーション クライアント内から会議管理をサポートする Lync 2013 用オンライン ミーティング アドインは、Lync 2013 と共に自動的にインストールされます。</p></li>
> <li><p>Office 2013 セットアップ プログラムを実行しても、以前のバージョンの Lync や Office Communicator はアンインストールされません。Lync 2013 クライアントは、他の Lync クライアントや Office Communicator クライアントと共存する形でインストールされます。</p></li></ul>


## このセクションの内容

  - [クライアント インストールのカスタマイズ](lync-server-2013-customizing-client-installation.md)

  - [Lync の動作とユーザー インターフェイスのカスタマイズ](lync-server-2013-customizing-lync-behavior-and-the-user-interface.md)

  - [Lync Server 2013 でのオンライン ミーティング アドインのカスタマイズ](lync-server-2013-customizing-the-online-meeting-add-in.md)

  - [Lync Server 2013 での会議参加ページの構成](lync-server-2013-configuring-the-meeting-join-page.md)

  - [サポートされているクライアント バージョンの構成](lync-server-2013-configuring-supported-client-versions.md)

  - [拡張プレゼンス プライバシー モードの構成](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)

