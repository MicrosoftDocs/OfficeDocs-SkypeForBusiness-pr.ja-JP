---
title: ビジネス サーバー 2015 の Skype では、TLS 1.0 または 1.1 を無効にします。
ms.reviewer: ''
ms.author: heidip
author: heidip
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: '概要: を準備してお客様の環境で TLS 1.0 および 1.1 を無効にするを実装します。'
ms.openlocfilehash: dc835a68e47f9fac6036724d92ad336ead795e50
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/30/2019
ms.locfileid: "31012934"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a>ビジネス サーバー 2015 の Skype では、TLS 1.0 または 1.1 を無効にします。

この資料の目的は、準備し、TLS 1.0 および 1.1 を無効にすることをお客様の環境で実装するために必要なガイダンスを提供します。 このプロセスには、綿密な計画と準備が必要です。 確認してください慎重にこの資料の情報をすべて TLS 1.0 と 1.1 の組織を無効にするための計画を行うとします。 多くの外部の依存関係および TLS 1.0 または 1.1 を無効にすることによって影響を受ける可能性があります接続条件があるため広範な計画とテストが保証されていることに注意します。

## <a name="in-this-article"></a>この資料に記載されて

- [背景とスコープ](#background)
- [前提条件とプロセス](#prerequisites-and-process)
- [高度な展開シナリオ](#advanced-deployment-scenarios)

## <a name="background"></a>背景

TLS 1.0 と 1.1 を無効にするためのサポート Skype のビジネス サーバー設置型を提供する主な構成要素は、支払いカード業界 (PCI セキュリティ スタンダード カウンシルと連邦情報処理標準の要件です。 PCI 要件の詳細についてを参照して[ここで](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls)。  マイクロソフトは、これらやその他の要件に準拠する組織が必要かどうかに関するガイダンスを提供することはできません。 TLS 1.0 および 1.1 の環境で無効にするために必要なかどうかを決定する必要があります。

マイクロソフトが TLS 利用可能な[ここでは](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)、上のホワイト ペーパーを作成し、読み取り、この[ブログの Exchange](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)で使用可能な背景もお勧めします。

## <a name="supportability-scope"></a>サポート範囲

*スコープ*は、サポート範囲を参照します。 Skype のビジネス サーバー設置型の場合は、*スコープ内で*完全にサポートされ、TLS 1.0 と表示されている製品のバージョン 1.1 を無効にするテストを意味します。 *現在調査中*というだけです。TLS がサポートを無効にするは、スコープ内にこれらの製品を導入を積極的に調査します。 *スコープの外*には、これらの製品のバージョンが無効にすると、TLS 1.0 または 1.1 をサポートしていないとは、以下の例外を意味します。

### <a name="fully-tested-and-supported-servers"></a>完全にテストされ、サポートされているサーバー

- Skype for Business Server 2019
- Skype ビジネス サーバー 2015 CU6 HF2 ([2018年 3 月更新](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) 6.0.9319.516 のではそれ以上とします。 
    - (KB 3140245 に優先する更新プログラム) の Windows Server 2012、2012 R2 または 2016
- インプレース アップグレードの Skype ビジネス サーバー 2015、CU6 HF2 とではそれ以上の 
    - Windows Server 2008 R2、2012 で KB [3140245](https://support.microsoft.com/en-us/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in)または優先する更新プログラムを使用)、または 2012 R2
- Exchange の接続と Outlook Web App で Exchange Server 2010 の SP3 RU19 以降のガイダンス[は、ここ](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)
- Skype サーバー 2015 CU6 HF2 のビジネスまたはそれ以上でリカバリ性に優れたブランチ アプライアンス (SBA) (確認の製造元に問い合わせて、適切な更新プログラムをパッケージ化し、アプライアンスで利用できる必要になった)
- Skype サーバー 2015 CU6 HF2 のビジネスまたはそれ以上でリカバリ性に優れたブランチ サーバー (SBS)
- Lync Server 2013**エッジ ロールのみ**、これはエッジの役割では、ファブリックの 1.0 を Windows には、依存関係はありません。


### <a name="fully-tested-and-supported-clients"></a>完全にテストされ、サポートされているクライアント

- Lync 2013 (ビジネス用の Skype) デスクトップ クライアント、MSI および Basic を含む、C2R [15.0.5023.1000 以上](https://support.microsoft.com/en-us/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)
- Skype ビジネス 2016年のデスクトップ クライアント、MSI の[16.0.4678.1000 以上](https://support.microsoft.com/en-us/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323)、Basic を含む
- Skype ビジネス 2016年] をクリックしますを実行するには、 [2018年 4 月](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus)の更新が必要です。 
    - 毎月および対象とする半年、16\.0\.9126\.2152 と高い
    - 半年と延期チャネル、16\.0\.8431\.2242 と高い
- Mac 16.15 とそれ以上のビジネスのための Skype
- IOS および Android 6.19 のビジネスおよび高い Skype
- Skype Web App 2015 CU6 HF2 と高い (サーバーが付属)

### <a name="currently-being-investigated"></a>現在調査中

#### <a name="devices"></a>デバイス

- Lync ルーム システム (別名 SRSv1)
- マイクロソフトのチーム会議室
- Surface Hub
- 2015 ベースのリカバリ性に優れたブランチ アプライアンス (SBA) またはリカバリ性に優れたブランチ サーバー (SBS)

#### <a name="other"></a>その他

- 品質のダッシュ ボードを呼び出す (TLS 1.0、1.1 以降後の新しいインストールを無効にされている、以下を参照してください) *
 
### <a name="out-of-scope"></a>スコープ外

を除きは、次の製品は、TLS 1.0 または 1.1 を無効にするサポートの対象ではないと、TLS 1.0 および 1.1 がされて無効になっている環境では動作しません。  これが何を意味します。 範囲外のサーバーまたはクライアントを引き続き利用する場合を更新またはビジネス サーバー設置型展開のため、TLS 1.0 または 1.1、Skype で任意の場所を無効にする必要がある場合は、これらを削除する必要があります。

- Lync Server 2013
- Lync Server 2010
- 2008 と下の Windows サーバー
- Lync for Mac 2011
- モバイルの iOS、Android や Windows Phone、iPad の Lync 2013
- "MX"Windows ストアの Lync クライアント
- すべての Lync 2010 クライアント
- Lync の電話のエディション - 更新されたガイド[は、ここ](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035)です。
- 2013 ベースのリカバリ性に優れたブランチ アプライアンス (SBA) またはリカバリ性に優れたブランチ サーバー (SBS)
- クラウド コネクタ エディション (CCE)
- Windows Phone 版 Skype for Business

### <a name="exceptions"></a>例外

#### <a name="lync-server-2013"></a>Lync Server 2013

Lync Server 2013 では、Windows ファブリック 1.0 のバージョンの依存関係がかかります。  Lync Server 2013 のデザインの段階で、レプリケーション、高可用性、およびフォールト トレランスを提供する説得力のある新しい分散アーキテクチャのファブリックの 1.0 を Windows が選択されました。  時間の経過とともにビジネス サーバーと Windows のファブリックの両方の Skype がこの共同のアーキテクチャの大幅な再設計以降のバージョンでは大幅に向上します。  ビジネス 2015年のサーバーの現在の Skype では、たとえば Windows ファブリック 3.0 を使用します。

残念ながら、Windows ファブリック 1.0**は TLS 1.2 をサポートしていません。 TLS 1.2 を使用するのには、Lync Server 2013 の更新は、** です。 これについては、Lync Server 2013 の次の累積的な更新プログラムで出勤します。  共存、移行、フェデレーション、およびハイブリッドのシナリオを有効にするのには TLS 1.2 のサポートを提供しています。

TLS 1.0 および 1.1 を無効にするのには、組織が必要な場合は、現在、Lync Server 2013 を使用することをお勧め計画プロセスを開始する、可能性にインプレース アップグレードする必要がありますまたはサイド バイ サイド移行 (新しいプール、ユーザーの移動) の Skype2015 またはそれ以上のビジネスのサーバーです。  または、オンライン ビジネスの Skype への移行を促進することができます。

#### <a name="call-quality-dashboard"></a>通話品質ダッシュボード

設置呼び出し品質ダッシュ ボード現在に依存している TLS 1.0 (最初に、オンプレミス環境にインストールする) の新規インストール中にします。  この問題は現在調査中し、近い将来に修正プログラムをリリースする予定です。  救難をインストールして、TLS 1.0 を無効にも計画していることを最初に、救難のインストールを完了し、TLS 1.0 を無効にすることをお勧めします。

#### <a name="third-party-devices"></a>サード ・ パーティ製デバイス

3PIP 電話などのサードパーティ製のデバイスでビデオ会議、リバース プロキシとロード バランサーでは、必ず TLS 1.2 のサポート性を検証、慎重にテストが必要な場合、ベンダーにお問い合わせください。

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a>エッジ トランスポート サーバーで TLS 1.0 または 1.1 を無効にすると、フェデレーションに関する考慮事項

慎重の計画し、エッジ トランスポート サーバーに TLS 1.0 または 1.1 を無効にすることの影響を考慮する必要があります。  TLS 1.0 および 1.1 を無効にすると、他の組織は不要になったできる組織とフェデレーションを行うことがあります。

TLS 1.0 または 1.1 適用されていない (デバイス 2015、Lync 2013) との下位互換性を維持するために、エッジ サーバーで有効にしておくことを選択するか、古い (2010) の外部システムです。

マイクロソフトを出せないアドバイスや推奨事項であるかどうか、ネットワークのエッジ (または任意のネットワーク) を下回った PCI の標準であります。個々 の会社で決定する必要があります。

ビジネス オンラインの Skype は TLS 1.2 現在では、オンラインでは、ハイブリッドまたはフェデレーションへの影響はありませんのでです。

Skype コンシューマー サービスには、PIC (パブリック IM 接続): 予定です[Skype の接続性](../../deploy/deploy-skype-connectivity.md)に影響を与えるに TLS 1.0 または 1.1 を無効にします。Microsoft PIC ゲートウェイが TLS 1.2 の機能では既にあります。

## <a name="prerequisites-and-process"></a>前提条件とプロセス

TLS 1.0 および 1.1 は、無効な範囲外のサーバー、クライアントとデバイスは、正しく、またはすべての機能になった後、上記で説明した場合を除きます。 一時停止し、Microsoft から更新済みのガイダンスを待機する必要があります。 セットアップを完了してすべての要件を満たすし、隔たりに対処する計画があることを確認したら、続行します。

高レベルは、ビジネス サーバー 2019 の Skype がインストールでは、プロシージャの準備ができてビジネス サーバー 2015 の Skype が必要 CU6 HF2、.NET と SQL、展開の前提条件となるレジストリ キー、および最後に、個別に事前に必要な更新プログラムを適用することをインストールすることOS 構成のラウンドは、(すなわち無効にする TLS 1.0 と 1.1 を使用してレジストリ ファイルのインポート) を更新します。 ビジネス サーバー 2015 CU6 HF2、TLS 1.0 と 1.1 を環境内の任意のサーバーを無効にする前に Skype を含むすべての必須コンポーネントのインストールを完了することがきわめて重要です。 ビジネス サーバー、エッジの役割と SQL バックエンドを含むすべての Skype では、更新プログラムが必要です。 また (スコープ) 内のすべてのサポートされているクライアントが必要な最小バージョンに更新されていることを確認します。 同様の管理ワークステーションを更新することを忘れないでください。

Skype をビジネスのサーバーのアップグレードの次の「表裏」操作通常順序にします。 ディレクター プール、永続的なチャット、およびプールの対応するを通常の方法と同じ方法で扱います。 順序とアップグレードの方法については、[ここ](topology.md)と[ここ](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)。

### <a name="high-level-process"></a>高度なプロセス

1. 運用サーバーを構成する前にテスト環境ですべての手順をテストします。
2. バックアップし、更新するすべての個々 のサーバーにエクスポートしたレジストリのコピーを保持します。 サーバー間でレジストリを共有することはできません。ベースのコンピューターの一意のキーが含まれます。
3. ビジネス 2015年サーバーのすべての Skype は、CU6 HF2 以降にアップグレードします。 (ビジネス サーバー 2019 の Skype での CU は必要ありません)
4. すべてのサーバーにすべての必須コンポーネントをインストールします。
5. 前提条件となるレジストリ キーを展開します。
6. スコープ内のすべてのクライアントが更新されていることを確認します。
7. TLS 1.0 および 1.1 レジストリ ・ インポートを使用して無効にします。
8. ワークロードが期待どおりに機能しているかを検証します。
    - 問題が発生した場合のトラブルシューティングおよび解決するには、または
    - TLS 1.0 を再度有効にするのには 2 と 1.1 の手順でレジストリを復元します。
9. TLS 1.2 のみが使用されていることを検証します。

### <a name="install-prerequisites-to-all-servers"></a>すべてのサーバーに前提条件をインストールします。

TLS 1.0 と 1.1 は、オペレーティング システム レベルでサーバー 2015 のビジネス展開では、Skype で無効にする開始する前に、大規模な依存関係の更新が必要です。 TLS 1.2 をサポートする最小のバージョンを次に示します。 TLS 1.0 および 1.1 を無効にすることを開始する前に、環境内のビジネス サーバーのすべての Skype 経由ですべての必須更新プログラムを展開します。

- Skype のビジネス サーバー 2015 CU6 HF2 ([2018年 3 月更新](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) 6.0.9319.516 またはそれ以上
- [.NET Framework 4.7](https://www.microsoft.com/en-us/download/details.aspx?id=55167)以上 (下記参照) のレジストリで有効になっている SchUseStrongCrypto と
- ビジネス 2015年のサーバーとバックエンドのすべての Skype の SQL を更新する必要があります。 エンタープライズ エディションのプールの SQL バックエンド、最初に更新、それぞれの専用 FEs。 
    - SQL Server 2014 SP1 + CU5 ([リンク](https://support.microsoft.com/help/3130926)) またはそれ以上と SQL Server 2012 の SP2 + CU16 またはそれ以上/rtm 版 SQL Server の 2014 + CU12 ([リンク](https://support.microsoft.com/en-us/help/3130923/cumulative-update-12-for-sql-server-2014)) またはそれ以上/2014 SP2 の SQL Server
    - SQL Server ネイティブ クライアントを SQL Server 2012 年 5 号 ([リンク](https://www.microsoft.com/en-us/download/details.aspx?id=50402))
    - Microsoft ODBC ドライバーの 11 以上の SQL Server ([リンク](https://www.microsoft.com/en-us/download/details.aspx?id=36434))
    - 2014 SP2 ([リンク](https://www.microsoft.com/en-in/download/details.aspx?id=42295)) の SQL Server の管理オブジェクトを共有します。
    - SQL server SP2 の 2014 ([リンク](https://www.microsoft.com/en-in/download/details.aspx?id=42295)) の SQLSysClrTypes

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a>操作の推奨される順序で、必須コンポーネントをインストールするのには基本的な手順を実行します。

1. ビジネス サーバー CU6HF2 は、Skype をインストール (6.0.9319.516) のすべてのサーバーを更新します。 
    1. アップデーターを使用してコンポーネントに更新プログラムをインストールします。
    2. 文書化された手順に従って、データベースを更新します。 指示が記載されています[https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)。
    3. その他の変更に進む展開の製品の機能を検証します。
2. .NET 4.7 をダウンロードするオフラインのインストーラーです。 
    1. 参照。[https://www.microsoft.com/en-us/download/details.aspx?id=55167](https://www.microsoft.com/en-us/download/details.aspx?id=55167)
    2. サーバー 2015 のビジネス サービスの Skype がフロント エンド サーバー上で停止していることを確認します。
    3. 参照。[https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)
    4. 停止-CsWindowsServices ex (標準エディション)。
    5. (Enterprise Edition): ex を呼び出す-CsComputerFailover
    6. インストーラー パッケージを実行します。
    7. サーバーを再起動します。
3. すべてのサーバー上の SQL Express 2014 を更新します。 
    1. 参照。[https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server)
    2. SQL 2014 SP2 をダウンロードします。 
        - 参照。[https://www.microsoft.com/en-us/download/details.aspx?id=53168](https://www.microsoft.com/en-us/download/details.aspx?id=53168)
    3. インストール メディアをサーバー上のフォルダーにコピーする (例: C:\01_2014SqlSp2)
    4. Skype をフロント エンド サーバーでサービスが停止して、ビジネス サーバー 2015 のことを確認します。 
        - 停止-CsWindowsService ex (標準エディション)。
        - (Enterprise Edition): ex を呼び出す-CsComputerFailove
    5. 管理者のコマンド プロンプトを開き、インストールされているすべてのコンポーネントおよびインスタンスをアップグレード 
        - 例: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe/qs/IAcceptSQLServerLicenseTerms 行いました修正プログラム/AllInstances を =
4. SQL ネイティブ クライアントを更新します。 
    1. 参照: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server)。
    2. ダウンロードします。[https://www.microsoft.com/en-us/download/details.aspx?id=50402](https://www.microsoft.com/en-us/download/details.aspx?id=50402)
    3. フロント エンド サーバーでサービスが停止して、ビジネス サーバー 2015 の Skype をことを確認します。 
        - 停止-CsWindowsServices ex (標準エディション)。
        - (Enterprise Edition): ex を呼び出す-CsComputerFailove
    4. 実行がインストールされている SQL インスタンスを停止します。 
        - Ex: Get サービス 'MSSQL$ RTCLOCAL' |停止サービス
        - Ex: Get サービス 'MSSQL$ LYNCLOCAL' |停止サービス
        - (Standard Edition のみ): ex Get サービス 'MSSQL$ RTC' |停止サービス
    5. 更新をインストールします。
5. SQL Server の ODBC ドライバー 11 を更新します。 
    1. 参照: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server)。
    2. ダウンロードします。[https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434](https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434)
    3. サーバー 2015 のビジネス サービスの Skype がフロント エンド サーバー上で停止していることを確認します。 
        - 停止-CsWindowsService ex (標準エディション)。
        - (Enterprise Edition): ex を呼び出す-CsComputerFailove
    4. 更新をインストールします。
6. 前提条件となるレジストリ キーを展開します。

### <a name="pre-requisite-registry-keys"></a>必須のレジストリ キー

メモ帳に次のテストをコピー/貼り付けと TLSPreReq.reg または任意の名前の名前を変更し、インポートします。

```
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v2.0.50727]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v4.0.30319]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v2.0.50727]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp]

"DefaultSecureProtocols"=dword:00000AA0

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp]

"DefaultSecureProtocols"=dword:00000AA0

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Client]

"DisabledByDefault"=dword:00000000

"Enabled"=dword:00000001

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Server]

"DisabledByDefault"=dword:00000000

"Enabled"=dword:00000001
```

SQL の背面の端のエンタープライズ エディションのプール、前提条件、および TLS を無効にする必要がありますとして扱われ、SQL、または OS の更新プログラムは次のようです。参照してください。[https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)

前提条件となるアプリケーションと手順を無効にすると TLS の両方を組み合わせることができます、中に TLS 1.0 と 1.1 は、オペレーティング システム レベルでの無効化を続行する前にすべての前提条件を適用するを強くお勧めします。 後で先に進むには、TLS 1.0 または 1.1 を無効にし、すべての作業負荷を正しくして、期待どおりの機能を検証するすべての前提条件を展開することにより、環境を準備するのには、ベスト プラクティスに基づくアプローチになります。

### <a name="disable-tls-10-and-11-via-registry-import"></a>TLS 1.0 と 1.1 レジストリ ・ インポートを使用して無効にします。

*すべての前提条件を完了し、Skype のビジネス サーバーを更新するかどうかを確認*、次の手順に進む前にできます。

メモ帳ファイルに次のテキストをコピーし、 **TLSDisable.reg**名前を変更します。

```
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Cryptography\Configuration\SSL\00010002]

"Functions"="TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384_P384,TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256_P256,TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384_P384,TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256_P256,TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA384_P384,TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA256_P256,TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384_P384,TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256_P256,TLS_RSA_WITH_AES_256_GCM_SHA384,TLS_RSA_WITH_AES_128_GCM_SHA256,TLS_RSA_WITH_AES_256_CBC_SHA256,TLS_RSA_WITH_AES_128_CBC_SHA256"

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL]

"AllowInsecureRenegoClients"=dword:00000000

"AllowInsecureRenegoServers"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\AES 128/128]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\AES 256/256]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\DES 56/56]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\NULL]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 128/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 40/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 56/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 56/56]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 128/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 40/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 56/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 64/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\Triple DES 168]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\MD5]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA256]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA384]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA512]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\Diffie-Hellman]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\ECDH]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\PKCS]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000
```

TLS 1.0 を無効にする各サーバーおよび 1.1 で .reg ファイルをインポートします。 サーバーを再起動します。 サービスがオンラインに戻る、次のサーバーに移動します。 エンタープライズ エディションのプールの実行方法については、OS の更新プログラムを実行します。

お気付き TLS 1.0 および 1.1 をここでは無効にするより多くを行っています。 暗号パッケージ ・ プログラムは、(上記を参照) のように再注文し、いくつかの古い脆弱な暗号化を無効にすることをサポートします。 これは私たちが公式にサポートされて SCHANNEL、Crypto API にこれらの変更 Skype のビジネスのサーバーの最初の時間であり、私たちをサポートし、この時点でのテストが唯一のものは、これらの変更することが重要。 将来、追加の構成を検討することができますが、ここでは、変更しないでください実装では、レジストリ ファイルのインポート。

### <a name="validate-that-workloads-are-functioning-as-expected"></a>ワークロードが期待どおりに機能しているかを検証します。

TLS 1.0 および 1.1 は、お客様の環境で無効になっています後、は、メインの作業負荷が期待どおりに機能していることを確認して IM & プレゼンス、P2P 通話、エンタープライズ VoIP などなど。

**検証のみ TLS 1.2 を使用します。**

古いプロトコル TLS 1.0 および 1.1 が使用されていないビジネス トラフィック用の Skype の新しい監査を実行する、セキュリティ チームがあります。

また、TLS 1.0 と 1.1 の TLS を無効にした後、Skype からビジネス サーバー 2015 の TLS 接続を web サービスをテストするのには、Internet Explorer を使用できます。

1. Internet Explorer を起動します。
2. **ツール**を選択して > **インター ネット オプション**。
3. [**詳細設定**] タブを選択します。
4. [**設定**] の一番下までスクロールします。
5. TLS 1.0、TLS 1.1 および TLS 1.2 が有効になっていることを確認します。
6. (正常に接続)、デバイスの 2015年プールの内部の Web サービスの URL を参照してください。
7. Internet Explorer に戻るし、 **TLS 1.2 を使用**するオプションのみを無効にします。
8. (接続に失敗する必要があります) もう一度デバイス 2015年プールの内部の Web サービスの URL を参照してください。

![インターネット オプション](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a>高度な展開シナリオ

ビジネス Ser 2015 の Skype で TLS 1.2 をサポートするためにいくつかの依存関係の前提条件が必要であるため、TLS 1.0 および 1.1 が無効になってすべてのシステムで失敗 RTM 版からをインストールすます。

**環境内で、TLS 1.0 および 1.1 が無効になっていると、新しいの Standard Edition Server またはエンタープライズ エディションのプールを展開します。**

**オプション 1:**[SmartSetup](../../deploy/install/install-skype-for-business-server.md)を使用します。 CU、将来の更新された SQL バイナリに対応するために SmartSetup を更新し、将来的にこの資料を更新ことに注意してください。

**オプション 2:**(RTCLOCAL および LYNCLOCAL)、ローカルの SQL インスタンスをインストールする前

1. ダウンロードし、SQL Express 2014 SP2 (SQLEXPR_x64.exe) を FE 上のローカル フォルダーにコピーします。 フォルダー パスの <SQL_FOLDER_PATH> を考えてみましょう。
2. PowerShell またはコマンド プロンプトを起動し、<SQL_FOLDER_PATH> に移動します。
3. 次のコマンドを実行して、RTCLOCAL の SQL インスタンスを作成します。 続行する前に SQLEXPR_x64.exe が完了するまでに待機します。

    SQLEXPR_x64.exe/Q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE 行いました = インストール機能 = SQLEngine、ツールの/INSTANCENAME = RTCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT ="NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS ="Builtin\管理者"/BROWSERSVCSTARTUPTYPE =「自動」/AGTSVCACCOUNT ="NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = 自動的
1. 次のコマンドを実行して、LYNCLOCAL の SQL インスタンスを作成します。 SQLEXPR_x64.exe は、次の手順に進む前に完了するまでに待機します。

    SQLEXPR_x64.exe/Q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE 行いました = インストール機能 = SQLEngine、ツールの/INSTANCENAME = LYNCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT ="NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS ="Builtin\管理者"/BROWSERSVCSTARTUPTYPE =「自動」/AGTSVCACCOUNT ="NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = 自動
1. Skype をビジネス サーバー 2015 の rtm 版のセットアップを実行します。
2. 上記の前提条件」セクションから、残り手順を実行します。

**オプション 3:** ローカル インストール メディアのディレクトリにバイナリを次のように手動で置き換えることが。

1. [ビジネス サーバーの Skype のための前提条件をインストールします。](../../deploy/install/install-prerequisites.md)  
2. 2. .NET 4.7 をインストールします。 
      - **注:** まず、Skype で .NET 4.7 のサポートの業務サーバー 2015 CU5 + (6.0.9319.281) を導入しました。 したがって、次以降の手順で私たちが更新されます。 コア コンポーネント メインのインストールの前にします。
      - ダウンロード先: https://www.microsoft.com/en-us/download/details.aspx?id=55167。
      - 参照:[サーバー 2015 のビジネスを展開するため、Skype の前にインストールするソフトウェア](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)
3. ISO ファイルとフォルダーをコピーします。 
    - として接続されているドライブのルート ディレクトリを開くと、Skype ビジネス サーバー 2015 ISO が接続されているのでは、(例: d:\)ファイル エクスプ ローラーでします。
    - すべてのフォルダーとファイルをローカル ディスク上のフォルダーにコピーする (例: C:\SkypeForBusiness2015ISO)。
    - **注:** コンポーネントをインストールする前にいくつかのファイルは、TLS 1.2 をサポートするために更新する必要があります。
4. MSI および EXE パッケージを置き換えます。 
    - /Setup/amd64 フォルダーをローカル コンピューター上のインストール メディアので、既存の MSI および EXE パッケージを交換してください。
    - SQL 2014 SP2 の高速。https://www.microsoft.com/en-us/download/details.aspx?id=53167 
        - ローカルのマシンでは、SQLEXPR_x64 に名前を変更し、セットアップまたは amd64 では、既存のファイルを置き換えると、インストール メディアのフォルダーです。
    - SQL ネイティブ クライアント:https://www.microsoft.com/en-us/download/details.aspx?id=50402 
        - **注:** Sqlncli.msi、およびセットアップまたは amd64 に存在する既存のファイルを交換する必要がある場合は、名前を変更またはインストール メディアのフォルダーです。
    - SQL 管理オブジェクト:https://www.microsoft.com/en-us/download/details.aspx?id=53164 
        - **注:** Feature pack には、ダウンロードできる項目の多くがあります。 だけ SharedManagementObjects.msi をダウンロードするを選択します。
        - **注:** セットアップと amd64 に存在する既存のファイルを置き換えると、インストール メディアのフォルダーです。
    - SQL CLR の種類:https://www.microsoft.com/en-us/download/details.aspx?id=53164 
        - **注:** Feature pack には、ダウンロードできる項目の多くがあります。 だけ CQLSysClrTypes.msi をダウンロードするを選択します。
        - **注**: セットアップまたは amd64 に存在する既存のファイルを置き換えるとインストール メディアのフォルダーです。
5. コア コンポーネントをインストールします。 
    - セットアップと amd64 から Setup.exe を実行またはインストール メディアのフォルダーです。 コア コンポーネントをインストールする指示に従います
    - コア コンポーネントを終了します。
6. コア コンポーネントを更新します。 
    - ビジネスの更新プログラムのインストーラーは、Skype をダウンロードしてください。
    - コア コンポーネントを更新し、パフォーマンス カウンターをインストールするインストーラーを実行します。
    - **注:** CU6HF2 のリリースでは、自動更新機能現在のみがインストールされます CU6 まで。 したがって、アップデーターは、6.0.9319.516 をコア ・ コンポーネントを更新するのには個別に実行してください。
    - 参照。https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015
7. (省略可能) の管理ツールをインストールします。 
    - SQL Server 2014 更新されたファイルを使用して (x64) の Microsoft SQL Server 2012 のネイティブ クライアント、SQL Server 2014 管理オブジェクト (x64)、および Microsoft システムの CLR 型がインストールされます。 さらに、ビジネス サーバー 2015 のトポロジ ビルダーおよびコントロール パネルの Skype はローカル コンピューターで利用可能になります。
8. ローカル構成ストア (ステップ 1) をインストールします。 
     - 展開ウィザードを開く、サーバーのビジネス システムのインストールまたは更新プログラムの Skype をクリックしてし、**実行**を手順 1 でをクリックします。 ローカル構成ストアのインストールします。
     - **次**の**ローカル構成ストアのインストール**] ダイアログ ボックスをクリックします。
     ![ローカル構成ストアのインストール] ダイアログ ボックス](../../media/local-configuration-store.png)
     - 結果を確認し、タスクの進捗状況が完了したことを確認します。 **ログの表示**] をクリックして、ログ ・ ファイルを確認します。
     ![完了としてタスクの進捗状況を示しています](../../media/local-configuration-task-completed.png)
     - [**完了**] をクリックします。
9. 設定または解除 Skype ビジネス サーバー コンポーネント (ステップ 2)。
    - 展開ウィザードを開く、[**インストール]、またはサーバーのビジネス システムの更新プログラムの Skype**、および手順 2 での**実行**] をクリックします設定または Skype をビジネスのサーバー コンポーネントの削除。
    - 内で**次**の設定を Skype ビジネス サーバー コンポーネント] ダイアログ ボックスをクリックします。
    ![ビジネス サーバー コンポーネント] ウィンドウの設定を Skype](../../media/set-up-skype-for-business-server-components-window.png)
    - ログの表示] を使用してログを確認し、問題なく完了する設定を検証します。 
    - [**完了**] をクリックします。
10. 追加インストールし、必要に応じて構成を続行 (通常のインストール手順をこの時点でに再開することができます)。
