---
title: 'Lync Server 2013: リバースプロキシサーバーの設定'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up reverse proxy servers
ms:assetid: 00bc138a-243f-4389-bfa5-9c62fcc95132
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398069(v=OCS.15)
ms:contentKeyID: 48183225
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f4ff853e3f31804e4bca55bd6a4576e25702b6c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182000"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-reverse-proxy-servers-for-lync-server-2013"></a>Lync Server 2013 用のリバースプロキシサーバーのセットアップ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-05-08_

Microsoft Lync Server 2013 エッジサーバー展開の場合、外部クライアントがディレクターおよびユーザーのホームプールで Lync Server 2013 Web サービス (Office Communications Server の*Web コンポーネント*と呼ばれます) にアクセスするには、境界ネットワーク内の HTTPS リバースプロキシが必要です。 リバース プロキシ経由の外部アクセスが必要な機能には、次のようなものがあります。

  - 外部ユーザーが会議の会議コンテンツをダウンロードできるようにする。

  - 外部ユーザーが配布グループを展開できるようにする。

  - リモート ユーザーがアドレス帳サービスからファイルをダウンロードできるようにする。

  - Lync Web App クライアントにアクセスする。

  - [ダイヤルイン会議の設定] Web ページにアクセスする。

  - 外部デバイスからデバイス更新 Web サービスに接続して更新プログラムを入手できるようにする。

  - モバイルアプリケーションが自動的に検出してインターネットからのモビリティ (Mcx) Url を使用できるようにする。

  - Lync 2013 クライアント、Lync Windows ストアアプリ、Lync 2013 Mobile クライアントを有効にして、Lync discovery (自動検出) Url を検索し、統合コミュニケーション Web API (UCWA) を使用します。

HTTP リバース プロキシは、すべてのプールのすべての Web サービスを公開するように設定することをお勧めします。 Https://ExternalFQDN の発行\* /プールのすべての IIS 仮想ディレクトリを公開します。 組織内の Standard Edition サーバー、フロントエンド プール、またはディレクターやディレクター プールごとに、公開ルールが 1 つずつ必要です。

さらに、簡単な Url を公開する必要があります。 組織にディレクターまたはディレクタープールがある場合、HTTP リバースプロキシは簡単な Url に対する HTTP/HTTPS 要求をリッスンし、ディレクターまたはディレクタープールの外部 Web サービス仮想ディレクトリにプロキシを送信します。 ディレクターを展開していない場合は、簡易 Url への要求を処理するプールを1つ指定する必要があります。 (これがユーザーのホームプールでない場合は、ユーザーのホームプールの Web サービスにリダイレクトされます)。 簡易 Url は専用の web 公開ルールによって処理されることも、ディレクターの web 公開ルールのパブリック名に追加することもできます。 外部自動検出サービスの URL も公開する必要があります。

リバースプロキシとしてアプリケーション要求ルーティング (IIS ARR) を使用して、Microsoft Forefront Threat Management Gateway 2010、Microsoft インターネットセキュリティとアクセラレータ (ISA) サーバー 2006 SP1、または Internet Information Server 7.0、7.5 または8.0 を使用できます。 このセクションの詳細な手順では、Forefront Threat Management Gateway 2010 を構成する方法と、ISA Server 2006 を構成する手順をほぼ同一にする方法について説明します。 IIS のガイダンスも提供されています。 別のリバースプロキシを使用している場合は、その製品のドキュメントを参照し、ここで定義されている要件を他のリバースプロキシの関連付けられている機能にマップします。

<div>


> [!IMPORTANT]  
> インターネットインフォメーションサービスアプリケーション要求ルーティング (IIS ARR) は、Lync Server 2010 および Lync Server 2013 のリバースプロキシを実装するための完全にテストおよびサポートされたオプションです。 2012年11月日、Microsoft ceased ライセンス販売の ForeFront Threat Management Gateway 2010、または TMG。 TMG は、完全にサポートされている製品で、サードパーティが販売しているアプライアンスでも引き続き販売できます。 また、サードパーティのハードウェアロードバランサーとファイアウォールの多くはリバースプロキシサポートを提供しています。 リバースプロキシ機能を提供するハードウェアロードバランサーとファイアウォールについては、各製品を構成して、Lync Server のリバースプロキシサポートを提供する方法について、ベンダーに確認してください。 また、製品のドキュメントを Microsoft に送信した第三者を表示することもできます。 サポートは、サードパーティのソリューションによって提供されます。 ソリューションを提供するためにアクティブなサードパーティを確認するには、「 <A href="https://go.microsoft.com/fwlink/?linkid=268730">Microsoft Lync 用のインフラストラクチャ認定</A>」を参照してください。



</div>

以下のトピックと手順では、展開および構成手順の基礎として Forefront Threat Management Gateway 2010 と IIS ARR を使用しています。

  - [Lync Server 2013 用に web ファーム Fqdn を構成する](lync-server-2013-configure-web-farm-fqdns.md)

  - [Lync Server 2013 でネットワークアダプターを構成する](lync-server-2013-configure-network-adapters.md)

  - [Lync Server 2013 でのリバース HTTP プロキシの証明書の要求と構成](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)

  - [Lync Server 2013 での単一の内部プールの web 公開ルールの構成](lync-server-2013-configure-web-publishing-rules-for-a-single-internal-pool.md)

  - [Lync Server 2013 で IIS 仮想ディレクトリの認証と証明書を検証または構成する](lync-server-2013-verify-or-configure-authentication-and-certification-on-iis-virtual-directories.md)

  - [Lync Server 2013 でリバースプロキシサーバーの DNS レコードを作成する](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)

  - [Lync Server 2013 でリバースプロキシ経由のアクセスを確認する](lync-server-2013-verify-access-through-your-reverse-proxy.md)

<div>

## <a name="before-you-begin"></a>作業を始める前に

Forefront Threat Management Gateway 2010 をリバース プロキシとして正しく展開するには、Forefront Threat Management Gateway 2010 のドキュメントに定義されている前提条件およびハードウェア要件を使用してサーバーを設定および構成する必要があります。 続行する前に、「ハードウェアを適切に構成し、Forefront Threat Management Gateway 2010 をサーバーにインストールするには、次のトピックを参照してください。

  - <span></span>  
    [Forefront Threat Management Gateway (TMG) 2010](https://go.microsoft.com/fwlink/?linkid=291292)

  - <span></span>  
    [Forefront TMG 2010 ハードウェアに関する推奨事項](https://go.microsoft.com/fwlink/?linkid=291293)

IIS ARR をリバースプロキシとして正常に展開するには、次のトピックを参照してハードウェアおよび前提条件のソフトウェアを構成します。

  - <span></span>  
    IIS を Windows Server 2008 または Windows Server 2008 R2 にインストールするには、「 [Windows server 2008 または Windows server 2008 r2 に iis 7](https://go.microsoft.com/fwlink/?linkid=291296)をインストールする」を参照してください。

  - <span></span>  
    Windows Server 2012 に IIS をインストールするには、「 [Windows server 2012 で iis 8 をインストール](https://go.microsoft.com/fwlink/?linkid=291297)する」を参照してください。

  - <span></span>  
    Windows Server 2012 R2 に IIS をインストールするには、「 [Windows server 2012 r2 に iis 8.5 を](https://go.microsoft.com/fwlink/?linkid=330687)インストールする」を参照してください。

  - <span></span>  
    IIS のアプリケーション要求ルーティング拡張機能をダウンロードするには、「[アプリケーション要求ルーティング](https://go.microsoft.com/fwlink/?linkid=291298)V2.0 のダウンロード」に記載されている手順に従ってください。

  - <span></span>  
    ARR をインストールするには、「[アプリケーション要求ルーティングバージョン2のインストール](https://go.microsoft.com/fwlink/?linkid=291299)」の手順に従ってください。
    
    <div>
    

    > [!NOTE]  
    > 現在投稿されている命令は、ARR 2.0 に対応しています。 拡張機能のインストールでは、2つのバージョンの間に違いはありません。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

