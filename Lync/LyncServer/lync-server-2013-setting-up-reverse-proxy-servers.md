---
title: 'Lync Server 2013: リバース プロキシ サーバーの設定'
TOCTitle: リバース プロキシ サーバーの設定
ms:assetid: 00bc138a-243f-4389-bfa5-9c62fcc95132
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398069(v=OCS.15)
ms:contentKeyID: 48271058
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 のリバース プロキシ サーバーの設定

 

_**トピックの最終更新日:** 2016-12-08_

Microsoft Lync Server 2013 のエッジ サーバーの展開の場合、ディレクターおよびユーザーのホーム プール上の Lync Server 2013 Web サービス (Office Communications Server では *Web コンポーネント*と呼ばれます) に外部クライアントがアクセスするには、境界ネットワーク内の HTTPS リバース プロキシが必要です。リバース プロキシ経由の外部アクセスが必要な機能には、次のようなものがあります。

  - 外部ユーザーが会議の会議コンテンツをダウンロードできるようにする。

  - 外部ユーザーが配布グループを展開できるようにする。

  - リモート ユーザーがアドレス帳サービスからファイルをダウンロードできるようにする。

  - Lync Web App クライアントにアクセスする。

  - \[ダイヤルイン会議の設定\] Web ページにアクセスする。

  - 外部デバイスからデバイス更新 Web サービスに接続して更新プログラムを入手できるようにする。

  - モバイル アプリケーションがインターネットからモビリティ (Mcx) URL を自動的に検出して使用できるようにする。

  - Lync 2013 クライアント、Lync Windows ストア アプリ、Lync 2013 モバイル クライアントが Lync Discover (自動検出) URL を見つけて統合コミュニケーション API (UCWA) を使用できるようにする。

HTTP リバース プロキシは、すべてのプールのすべての Web サービスを公開するように設定することをお勧めします。https:// *ExternalFQDN* /\* を公開すると、プールの IIS 仮想ディレクトリがすべて公開されます。組織内の Standard Edition サーバー、フロント エンド プール、または ディレクターや ディレクター プールごとに、公開ルールが 1 つずつ必要です。

また、簡易 URL を公開する必要があります。組織に ディレクターまたは ディレクター プールがある場合は、HTTP リバース プロキシは簡易 URL に対する HTTP/HTTPS 要求をリッスンし、ディレクターまたは ディレクター プール上の外部 Web サービス仮想ディレクトリにプロキシ化します。 ディレクターを展開していない場合は、簡易 URL に対する要求を処理するプールを 1 つ指定する必要があります (これがユーザーのホーム プールでない場合、要求はユーザーのホーム プール上の Web サービスへリダイレクトされます)。簡易 URL は専用の Web 公開ルールで処理するか、ディレクターの Web 公開ルールのパブリック名に追加できます。自動検出サービスの外部 URL も公開する必要があります。

Microsoft Forefront Threat Management Gateway 2010、Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1、Internet Information Server 7.0、7.5 または 8.0 Application Request Routing (IIS ARR) を、リバース プロキシとして使用できます。このセクションの詳細ステップでは、Forefront Threat Management Gateway 2010 の構成方法について説明します。また、ISA Server 2006 を構成するためのステップはほとんど同じです。別のリバース プロキシを使用する場合は、対応する製品のドキュメントを確認し、ここで定義されている要件を他のリバース プロキシの関連する機能に対応付けてください。IIS ARR に関するガイダンスも提供されています。


> [!IMPORTANT]
> Internet Information Server Application Request Routing (IIS ARR) は、Lync Server 2010 と Lync Server 2013 のリバース プロキシを実装するためにサポートされている、完全にテスト済みのオプションです。2012 年 11 月、Microsoft は ForeFront Threat Management Gateway 2010 (TMG) のライセンス販売を終了しました。TMG は引き続き完全にサポートされている製品であり、サード パーティが販売するアプライアンス用に引き続き購入できます。また、多くのサード パーティ製ハードウェアのロード バランサーとファイアウォールが、リバース プロキシをサポートしています。リバース プロキシ機能を持つロード バランサーとファイアウォールについては、Lync Server のリバース プロキシ サポートを提供するための具体的な製品の構成手順をベンダーに確認してください。また、自社製品に関する資料をマイクロソフトに提出済みのベンダーを確認することもできます。サード パーティは自社のソリューションに関するサポートを提供しています。現在ソリューションを提供しているサード パーティを確認するには、「<A href="http://go.microsoft.com/fwlink/?linkid=268730">Infrastructure qualified for Microsoft Lync</A>」を参照してください。



次のトピックと手順では、展開および構成手順の基盤として、Forefront Threat Management Gateway 2010 と IIS ARR を使用します。

  - [Lync Server 2013 向けの Web ファームの FQDN の構成](lync-server-2013-configure-web-farm-fqdns.md)

  - [Lync Server 2013 ネットワーク アダプターの構成](lync-server-2013-configure-network-adapters.md)

  - [Lync Server 2013 でのリバース HTTP プロキシ用の証明書の要求と構成](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)

  - [Lync Server 2013 での単一内部プールの Web 公開ルールの構成](lync-server-2013-configure-web-publishing-rules-for-a-single-internal-pool.md)

  - [Lync Server 2013 で IIS 仮想ディレクトリの認証と証明書を検証または構成する](lync-server-2013-verify-or-configure-authentication-and-certification-on-iis-virtual-directories.md)

  - [Lync Server 2013 でのリバース プロキシ サーバーの DNS レコードの作成](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)

  - [Lync Server 2013 でリバース プロキシ経由のアクセスを確認する](lync-server-2013-verify-access-through-your-reverse-proxy.md)

## 作業を始める前に

Forefront Threat Management Gateway 2010 をリバース プロキシとして正しく展開するには、Forefront Threat Management Gateway 2010 のドキュメントに定義されている前提条件およびハードウェア要件を使用してサーバーを設定および構成する必要があります。次のトピックを参照して、ハードウェアを正しく構成し、サーバーに Forefront Threat Management Gateway 2010 をインストールしてから次に進んでください。

  - [Forefront Threat Management Gateway (TMG) 2010](http://go.microsoft.com/fwlink/?linkid=291292)

  - [Forefront TMG 2010 のハードウェア推奨事項](http://go.microsoft.com/fwlink/?linkid=291293)

IIS ARR をリバース プロキシとして正しく展開するには、次のトピックでハードウェアの構成と前提条件となるソフトウェアを確認します。

  - IIS を Windows Server 2008 または Windows Server 2008 R2 にインストールするには、「[Installing IIS 7 on Windows Server 2008 or Windows Server 2008 R2](http://go.microsoft.com/fwlink/?linkid=291296)」を参照してください。

  - IIS を Windows Server 2012 にインストールするには、「[Installing IIS 8 on Windows Server 2012](http://go.microsoft.com/fwlink/?linkid=291297)」を参照してください。

  - IIS を Windows Server 2012 R2 にインストールするには、「[IIS 8.5 の Windows Server 2012 R2 へのインストール (Installing IIS 8.5 on Windows Server 2012 R2)](http://go.microsoft.com/fwlink/?linkid=330687)」を参照してください。

  - IIS 用の Application Request Routing 拡張機能をダウンロードするには、「[Application Request Routing v2.5 Download](http://go.microsoft.com/fwlink/?linkid=291298)」にある手順に従ってください。

  - ARR をインストールするには、「[Install Application Request Routing Version 2](http://go.microsoft.com/fwlink/?linkid=291299)」の手順を参照してください。
    
> [!NOTE]
> 現在の記事は ARR 2.0 が対象です。拡張機能のインストールに関して 2 つのバージョンに違いはありません。
