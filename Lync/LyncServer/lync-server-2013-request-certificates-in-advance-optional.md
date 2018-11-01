---
title: 'Lync Server 2013: 事前の証明書の要求 (オプション)'
TOCTitle: 事前の証明書の要求 (オプション)
ms:assetid: 9d6d7de6-ff2a-46da-b1b7-a354c8e383e4
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412733(v=OCS.15)
ms:contentKeyID: 48272989
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の事前の証明書の要求 (オプション)

 

_**トピックの最終更新日:** 2013-02-21_

各 Enterprise Editionフロント エンド サーバー、 Standard Edition サーバー、 ディレクター、 エッジ サーバー、およびスタンドアロンの 仲介サーバーなど、 Lync Server 2013 を実行するすべての内部サーバーで証明書が必要です。内部サーバーには内部のエンタープライズ証明機関 (CA) をお勧めしますが、パブリック CA を使用することもできます。証明書の要件およびパブリック CA の使用の詳細については、「計画」のドキュメントの「[Lync Server 2013 の内部サーバーに対する証明書要件](lync-server-2013-certificate-requirements-for-internal-servers.md)」を参照してください。

Lync Server 2013 のセットアップには、証明書ウィザードが含まれています。このウィザードを使用すると展開時の証明書の要求、割り当て、およびインストール タスクが円滑になります。サーバーのインストールの前に証明書を要求する場合 (たとえば、サーバーの実際の展開時に時間を節約するため) は、Lync Server 2013 管理ツールがインストールされているコンピューターを使用するか、または組織で定義されている証明書要求手順を使用して、証明書を要求できます。ただし、要求する証明書をエクスポートできることとその証明書が必要なすべてのサブジェクトの別名を含んでいることを確認してください。サーバー インストール前の証明書要求はオプションです。事前に要求していない場合は、証明書が必要な各サーバーのセットアップ プロセスで要求する必要があります。

「展開」のドキュメントには、セットアップ プロセスで証明書ウィザードを使用して証明書を要求するための手順が示されています。この「展開」のドキュメントの各セクション (「[Lync Server 2013 でのサーバーの証明書の構成](lync-server-2013-configure-certificates-for-servers.md)」、「[Lync Server 2013 でのディレクターの証明書の構成](lync-server-2013-configure-certificates-for-the-director.md)」、および「[Lync Server 2013 仲介サーバーのファイルのインストール](lync-server-2013-install-the-files-for-mediation-server.md)」) を参照してください。事前に証明書を要求する場合は、上記の各セクションの証明書の展開手順を必要に応じて変更し、展開時には証明書を要求するのではなくインポートして割り当てるようにします。

> [!NOTE]
> Lync Server 2013 は、 Windows Vista、 Windows Server 2008、 Windows Server 2008 R2、および Windows 7 オペレーティング システムと Lync Phone Edition を実行しているクライアントからの接続のための SHA-256 証明書のサポートを含んでいます。SHA-256 を使用する外部アクセスをサポートするには、SHA-256 を使用するパブリック CA が外部証明書を発行する必要があります。

