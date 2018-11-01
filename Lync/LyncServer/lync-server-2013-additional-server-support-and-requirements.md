---
title: 'Lync Server 2013: 追加サーバー サポートおよび要件'
TOCTitle: 追加サーバー サポートおよび要件
ms:assetid: 7622986b-abd6-4f45-8b5b-d5e2368521e8
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398577(v=OCS.15)
ms:contentKeyID: 48272503
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の追加サーバー サポートおよび要件

 

_**トピックの最終更新日:** 2016-12-08_

Lync Server 2013 には、この「サポート」のドキュメントの他のセクションに記載されているソフトウェアのサポートに加えて、以下のサポート制限があります。

  - Lync Server 2013 では、ドメイン ネーム システム (DNS) とハードウェア負荷分散を特定のサーバーの役割でサポートしています。また、仲介サーバーのアプリケーション負荷分散も、必要に応じてサポートします。それぞれをいつ使用するかについて詳しくは、「計画」のドキュメントを参照してください。

  - Lync Server 2013 では、配布リスト展開プロトコル (DLX) を使用して配布リストを展開します。このプロトコルは、配布リストのメンバーシップの取得に使用される Web サービス メソッドも指定します。 Microsoft Exchange Server では、動的なグループをサポートします。動的なグループは、静的に割り当てられたメンバーを持ちません。代わりにこれらのグループは、グループの展開時に評価されるクエリを格納します。DLX は動的な配布リストをサポートしていません。

  - ユーザーの有効化ウィザードでは、英語以外の文字の SIP 準拠 URI への自動変換はサポートされていません。したがって、SIP アドレスを手動で変更する必要があります。

  - ウイルス対策ソフトウェアを実行するサーバーの場合、推奨されるウイルスの除外、およびその他のセキュリティ関連の推奨事項については、「 [Lync Server 2013 用のウイルス スキャン除外範囲](lync-server-2013-antivirus-scanning-exclusions.md)」をご覧ください。

  - IPsec を使用する場合は、音声およびビデオ トラフィックに使用されるポート範囲に対する IPsec を無効にすることをお勧めします。詳しくは、「計画」のドキュメントの「 [IPSec 例外](lync-server-2013-ipsec-exceptions.md)」をご覧ください。

  - 組織でサービスの品質 (QoS) インフラストラクチャが使用されている場合、メディア サブシステムは、この既存のインフラストラクチャで機能するように設計されています。QoS の実装について詳しくは、「操作」のドキュメントの「 [サービスの品質 (QoS) の管理](lync-server-2013-managing-quality-of-service-qos.md)」をご覧ください。

  - オペレーティング システムのファイアウォールの使用がサポートされています。 Lync Server 2013 では、Microsoft SQL Server データベース ソフトウェアを除くオペレーティング システムのファイアウォールでファイアウォール例外を管理します。SQL Server のファイアウォール要件の詳細については、SQL Server のドキュメントを参照してください。

  - 外部ユーザー アクセスのサポートの実装で使用する外部インターフェイスは、内部インターフェイスと同じネットワーク上 *ではなく* 、別のサブネット上にある必要があります。

  - Lync Server 2013 の XMPP 機能は、Google Talk とのインスタント メッセージングのフェデレーションについては Microsoft によってテストとサポートが行われています。その他の XMPP システムについては、Lync Server 2013 とのフェデレーションのサポートや、展開またはトラブルシューティングの推奨事項に関して、サード パーティ ベンダーに問い合わせて確認してください。

  - Lync Server 2013 の累積的な更新プログラム (2013 年 7 月) のリリースにより、 Lync Server 2013 では 2 要素認証をサポートするようになりました。詳しくは、「 [2 要素認証の展開の計画](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md)」をご覧ください。

  - ほとんどの内部サーバーでは、 **Open Authentication** (OAuth) として定義された証明書タイプが必要です。 Lync Server 展開ウィザードの **証明書の要求、インストール、および割り当て**のフェーズの間に、OAuth 証明書を要求して割り当てる必要があります。OAuth 証明書キーの最小サイズは 1,024 ビットです。長さが 2,048 ビット未満のキーで証明書を要求すると、警告が表示される場合があります。警告されるのではなく長さが 2,048 ビットのキーが強制的に使用された場合の問題の可能性を防ぐため、OAuth 証明書には長さが 2,048 のキーを常に使用することを強くお勧めします。

  - Windows Server 2008 R2 オペレーティング システムがシステム暗号化に Federal Information Processing Standard (FIPS) 140-2 アルゴリズムを使用するように構成されている場合、 Lync Server 2013 および Microsoft Exchange Server 2010 Service Pack 1 (SP1) は FIPS 140-2 アルゴリズムをサポートして動作します。FIPS サポートを実装するには、 Lync Server 2013 を実行する各サーバーで FIPS のサポートを構成する必要があります。FIPS 準拠のアルゴリズムの詳細および FIPS サポートの実装方法については、Microsoft サポート技術情報の記事 811833「システム暗号化: Windows XP およびそれ以降のバージョンの Windows で暗号化、ハッシュ、署名のセキュリティ設定に FIPS 準拠アルゴリズムを使用する (英語)」( <http://support.microsoft.com/kb/811833/ja-jp>) を参照してください。Exchange 2010 における FIPS 140-2 のサポートと制限について詳しくは、「Exchange 2010 SP1 と FIPS 準拠アルゴリズムのサポート (英語)」( <http://go.microsoft.com/fwlink/?linkid=205335>) を参照してください。

Lync Server 2013 では、展開前または展開中に特定のコンポーネントに対して他のソフトウェアをインストールする必要があります。これには、オペレーティング システムで入手できるソフトウェア、ダウンロード可能なソフトウェア、 Lync Server 2013 のインストール中に自動的にインストールされるソフトウェアなどが含まれます。以下に、必要になる可能性がある追加のソフトウェアの一覧を示します。

  - Windows Update

  - Windows Identity Foundation

  - Microsoft .NET 4.5 Framework

  - Microsoft Visual C++ 2012 (再頒布可能)
    
    > [!NOTE]
    > Microsoft Visual C++ 2012 (再頒布可能) は、 Lync Server 2013 をインストールすると自動的にインストールされます。他のバージョンをインストールして使用しないでください。


  - URL Rewrite Module Version 2.0 (再頒布可能)

  - Windows Media フォーマット ランタイム

  - Windows PowerShell バージョン 3.0

  - Microsoft Silverlight 4 ブラウザー プラグイン (Lync Server コントロール パネルの場合は Silverlight 4.0.50524.0 または最新バージョン)

  - Active Directory ドメイン サービス ツール

上記のソフトウェア要件の中には、特定のサーバーの役割またはコンポーネントに対してのみ適用されるものもあります。これらのソフトウェア要件について詳しくは、「計画」のドキュメントの「 [Lync Server 2013 の追加ソフトウェア要件](lync-server-2013-additional-software-requirements.md)」をご覧ください。

