---
title: 'Lync Server 2013: リバース プロキシ サーバーの設定'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up reverse proxy servers
ms:assetid: 00bc138a-243f-4389-bfa5-9c62fcc95132
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398069(v=OCS.15)
ms:contentKeyID: 48183225
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef13f2351ab74c0e3b2ba558a9dbf0aef43d71b5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848736"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-reverse-proxy-servers-for-lync-server-2013"></a>Lync Server 2013 のリバース プロキシ サーバーの設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-05-08_

Microsoft Lync Server 2013 Edge Server 展開の場合、外部クライアントがディレクター上の Lync Server 2013 Web サービス (Office Communications Server の*Web コンポーネント*と呼ばれます) にアクセスするには、境界ネットワーク内に HTTPS 逆プロキシが必要です。ユーザーのホームプール。 リバースプロキシを介して外部アクセスを必要とする機能には、次のようなものがあります。

  - 外部ユーザーによる会議の会議コンテンツのダウンロードを有効にします。

  - 外部ユーザーが配布グループを展開できるようにします。

  - リモートユーザーがアドレス帳サービスからファイルをダウンロードできるようにします。

  - Lync Web App クライアントへのアクセス。

  - ダイヤルイン会議の設定の web ページにアクセスします。

  - デバイス更新 web サービスに接続して更新プログラムを取得するために、外部デバイスを有効にします。

  - モバイルアプリケーションを有効にして、インターネット上のモビリティー (Mcx) Url を自動的に検出して使用できるようにします。

  - Lync 2013 クライアント、Lync Windows ストアアプリ、Lync 2013 モバイルクライアントを有効にして、Lync Discover (自動検出) Url を検索し、ユニファイドコミュニケーションの Web API (UCWA) を使用します。

すべてのプールのすべての Web サービスを公開するように HTTP リバースプロキシを構成することをお勧めします。 公開 https://ExternalFQDN/\*プールのすべての IIS 仮想ディレクトリを公開します。 組織内の標準エディションサーバー、フロントエンドプール、またはディレクターまたはディレクタープールごとに1つの公開ルールが必要です。

さらに、単純な Url を公開する必要があります。 組織がディレクターまたはディレクタープールを使用している場合、HTTP リバースプロキシは、HTTP/HTTPS 要求をリッスンし、その Url をディレクターまたはディレクタープールの外部 Web サービスの仮想ディレクトリにプロキシします。 ディレクターを展開していない場合は、単純な Url への要求を処理するために、1つのプールを指定する必要があります。 (これがユーザーのホームプールではない場合は、ユーザーのホームプールの Web サービスにリダイレクトされます)。 単純な Url は、専用の web 発行ルールによって処理することも、ディレクターの web 公開ルールのパブリック名に追加することもできます。 また、外部自動検出サービス URL を公開する必要もあります。

Microsoft Forefront Threat Management Gateway 2010、Microsoft インターネットセキュリティとアクセラレータ (ISA) サーバー 2006 SP1、または Internet Information Server 7.0、7.5 または 8.0 (アプリケーション要求ルーティング (IIS) をリバースプロキシとして使うことができます。 このセクションの詳細な手順では、Forefront Threat Management Gateway 2010 を構成する方法と ISA Server 2006 を構成する手順について説明します。 ガイダンスは、IIS の ARR にも提供されています。 別のリバースプロキシを使用している場合は、その製品のドキュメントを参照して、ここで定義されている要件を、他のリバースプロキシの関連機能にマップします。

<div>


> [!IMPORTANT]  
> インターネット Information Server アプリケーション要求ルーティング (IIS ARR) は、Lync Server 2010 および Lync Server 2013 のリバースプロキシを実装するための完全にテストされ、サポートされるオプションです。 2012年11月、Microsoft おの ForeFront Threat Management Gateway 2010、または TMG のライセンス販売。 TMG は、完全にサポートされる製品であり、サードパーティによって販売されているアプライアンスで販売することもできます。 また、多くのサードパーティ製ハードウェアロードバランサーおよびファイアウォールでは、リバースプロキシのサポートが提供されています。 ハードウェアロードバランサーとリバースプロキシ機能を提供するファイアウォールについては、「Lync Server のリバースプロキシサポートを提供するためにその製品を構成する方法については、ベンダーに確認する」を参照してください。 お客様の製品のドキュメントを Microsoft に送信している第三者を表示することもできます。 サポートは、お客様のソリューションのサードパーティによって提供されます。 ソリューションの提供でアクティブなサードパーティを確認するには、「 <A href="http://go.microsoft.com/fwlink/?linkid=268730">Microsoft Lync 用のインフラストラクチャ認定</A>」を参照してください。



</div>

次のトピックと手順では、展開と構成手順のベースとして Forefront Threat Management Gateway 2010 と IIS ARR を使用します。

  - [Lync Server 2013 向けの Web ファームの FQDN の構成](lync-server-2013-configure-web-farm-fqdns.md)

  - [Lync Server 2013 ネットワーク アダプターの構成](lync-server-2013-configure-network-adapters.md)

  - [Lync Server 2013 でのリバース HTTP プロキシ用の証明書の要求と構成](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)

  - [Lync Server 2013 での単一内部プールの Web 公開ルールの構成](lync-server-2013-configure-web-publishing-rules-for-a-single-internal-pool.md)

  - [Lync Server 2013 で IIS 仮想ディレクトリの認証と証明書を検証または構成する](lync-server-2013-verify-or-configure-authentication-and-certification-on-iis-virtual-directories.md)

  - [Lync Server 2013 でのリバース プロキシ サーバーの DNS レコードの作成](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)

  - [Lync Server 2013 でリバース プロキシ経由のアクセスを確認する](lync-server-2013-verify-access-through-your-reverse-proxy.md)

<div>

## <a name="before-you-begin"></a>始める前に

リバースプロキシとして Forefront Threat Management Gateway 2010 を正常に展開するには、Forefront Threat Management Gateway 2010 ドキュメントで定義されている前提条件とハードウェア要件を使用してサーバーをセットアップして構成する必要があります。 続行する前に、次のトピック「ハードウェアを適切に構成し、Forefront Threat Management Gateway 2010 をサーバーにインストールする」を参照してください。

  - <span></span>  
    [Forefront Threat Management Gateway (TMG) 2010](http://go.microsoft.com/fwlink/?linkid=291292)

  - <span></span>  
    [Forefront TMG 2010 ハードウェア推奨事項](http://go.microsoft.com/fwlink/?linkid=291293)

IIS ARR をリバースプロキシとして正常に展開するには、次のトピックを参照して、ハードウェアおよび必要なソフトウェアを構成します。

  - <span></span>  
    Windows Server 2008 または Windows Server 2008 R2 に IIS をインストールする方法については、「 [Windows server 2008 または Windows server 2008 r2 で iis 7 をインストール](http://go.microsoft.com/fwlink/?linkid=291296)する」を参照してください。

  - <span></span>  
    Windows Server 2012 に IIS をインストールする方法については、「 [Windows server 2012 で iis 8](http://go.microsoft.com/fwlink/?linkid=291297)をインストールする」を参照してください。

  - <span></span>  
    Windows Server 2012 R2 に IIS をインストールする方法については、「 [Windows server 2012 r2 で iis 8.5](http://go.microsoft.com/fwlink/?linkid=330687)をインストールする」を参照してください。

  - <span></span>  
    IIS のアプリケーション要求ルーティング拡張機能をダウンロードするには、「[アプリケーション要求ルーティング v 2.5 のダウンロード](http://go.microsoft.com/fwlink/?linkid=291298)」の指示に従ってください。

  - <span></span>  
    [アプリケーション要求ルーティングバージョン2のインストール](http://go.microsoft.com/fwlink/?linkid=291299)の手順については、ARR をインストールする
    
    <div>
    

    > [!NOTE]  
    > 現在投稿されている命令は、ARR 2.0 に対応しています。 拡張機能のインストールでは、2つのバージョンの違いはありません。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

