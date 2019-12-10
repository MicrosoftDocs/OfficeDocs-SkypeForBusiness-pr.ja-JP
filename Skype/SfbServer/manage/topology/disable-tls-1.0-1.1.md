---
title: Skype for Business Server 2015 で TLS 1.0/1.1 を無効にする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: '概要: お客様の環境で TLS 1.0 および1.1 を無効にするための準備と実装を行います。'
ms.openlocfilehash: f6fa608174bc22bc91512a69cc67a688b9bc7bb9
ms.sourcegitcommit: 0dba0ad1f8f00415c6437cadabed0548ce3281b1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2019
ms.locfileid: "39919311"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 で TLS 1.0/1.1 を無効にする

この記事の目的は、お客様の環境で TLS 1.0 および1.1 を無効にするための準備と実装に必要なガイダンスを提供することです。 このプロセスには、さまざまな計画と準備が必要です。 組織で TLS 1.0 および1.1 を無効にする計画を立てるときは、この記事のすべての情報を慎重に確認してください。 TLS 1.0/1.1 を無効にすることによって影響を受ける可能性のある外部依存関係と接続性の条件が多数あるため、十分な計画とテストを行う必要があることに注意してください。

## <a name="in-this-article"></a>この記事の内容

- [背景と範囲](#background)
- [前提条件とプロセス](#prerequisites-and-process)
- [高度な展開シナリオ](#advanced-deployment-scenarios)

## <a name="background"></a>背景

オンプレミスの Skype for Business Server のサポートを無効にするため 1.1 1.0 の主なドライバーは、支払いカード産業 (PCI) セキュリティ規格協議会と連邦情報処理規格の要件です。 PCI の要件の詳細については、[こちら](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls)を参照してください。  Microsoft は、組織がこれらの要件に従う必要があるかどうかについてのガイダンスを提供することはできません。 使用している環境で TLS 1.0 および1.1 を無効にする必要があるかどうかを判断する必要があります。

Microsoft は、TLS に関するホワイトペーパーを[ここ](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)で提供しています。また、この[Exchange ブログ](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)で利用できる背景の読み取りもお勧めします。

## <a name="supportability-scope"></a>サポート範囲

*スコープ*は、サポート性の境界を意味します。 *完全にテストされ、サポートさ*れているということは、一覧されている製品バージョンの TLS 1.0 および1.1 の無効化を完全にサポートし、テストしていることです。 *現在調査中*であることを意味します。microsoft は、これらの製品をスコープ内で TLS のサポート対象にすることを積極的に調査しています。 *スコープ外の*場合、これらの製品バージョンは、TLS 1.0 または1.1 の無効化をサポートしておらず、例外が報告されていても動作しません。

### <a name="fully-tested-and-supported-servers"></a>完全にテストおよびサポートされたサーバー

- Skype for Business Server 2019 CU1 17.0.2046.123 (2019 年6月) 以降
- Skype for Business Server 2015 CU9 6.0.9319.548 (2019 年5月) 以上の Windows Server 2012 (KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in)または置き換えられた更新プログラム)、2012 R2、2016。
- Windows Server 2008 R2、2012 (KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in)または置き換えられた更新プログラム)、または 2012 R2 を使用したインプレースアップグレードされた Skype For business SERVER 2015 CU9 6.0.9319.548 (2019 年5月) 以降。
- Exchange 接続と Outlook Web App (Exchange Server 2010 SP3 RU19 以降)、[ここで](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)のガイダンス
- Skype for Business Server 2015 CU6 HF2 以上を搭載した Survivable Branch Appliance (SBA) (お使いのベンダーに、適切な更新プログラムをパッケージしており、お使いのアプライアンスで利用可能になったことを確認してください)
- Survivable Branch Server (SBS) と Skype for Business Server 2015 CU6 HF2 以降
- Lync Server 2013 **Edge の役割のみ**。これは、edge の役割が Windows Fabric 1.0 に依存していないことを意味します。

### <a name="fully-tested-and-supported-clients"></a>完全にテストおよびサポートされているクライアント

- Lync 2013 (Skype for Business) デスクトップクライアント、MSI、C2R (基本的な[15.0.5023.1000 です](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)など)
- Skype for Business 2016 デスクトップクライアント、MSI [16.0.4678.1000 以上](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323)(Basic を含む)
- Skype for Business 2016 を実行するには、 [2018 年4月](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus)の更新プログラムが必要です。 
    - 毎月および半年のターゲット、16\.0\.9126\.2152 以上
    - 半期および段階的提供チャネル、16\.0\.8431\.2242 以上
- Mac 16.15 以降の Skype for Business
- Skype for Business for iOS および Android 6.19 以降
- Microsoft Teams 室 (以前は Skype Room System V2 SRS V2 と呼ばれていました) 4.0.64.0 (12 月 2018) 以降
- KB4499162 に基づく Team edition 向け Surface Hub 更新プログラム (2019 年5月、OS ビルド 15063.1835) 以上
- Skype Web App 2015 CU6 HF2 以上 (サーバーに付属)

### <a name="currently-being-investigated"></a>現在調査中

- 通話品質ダッシュボード (TLS 1.0 の後の新規インストール、1.1 が無効になりました、下記参照) *
 
### <a name="out-of-scope"></a>範囲外

特に注記がない限り、次の製品は、TLS 1.0/1.1 のサポートを無効にすることはできません。また、TLS 1.0 および1.1 が無効になっている環境では機能しません。 その意味: まだスコープ外のサーバーまたはクライアントを使用している場合は、Skype for Business Server のオンプレミスの展開で TLS 1.0/1.1 を無効にする必要がある場合は、これらを更新または削除する必要があります。

- Lync Server 2013
- Lync Server 2010
- Windows Server 2008 またはそれ以降
- Lync for Mac 2011
- Lync 2013 for Mobile-iOS、iPad、Android、または Windows Phone
- Lync "MX" Windows ストアクライアント
- Lync Room System (別名 SRSv1). LRS は、2018年10月9日にサポートが終了しました。 TLS 1.2 をサポートするように更新されることはありません。
- すべての Lync 2010 クライアント
- Lync Phone Edition-[ここで](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035)更新されたガイダンス。
- 2013ベースの Survivable Branch Appliance (SBA) または Survivable Branch Server (SBS)
- Cloud Connector Edition (CCE)
- Windows Phone 版 Skype for Business

### <a name="exceptions"></a>例外

#### <a name="lync-server-2013"></a>Lync Server 2013

Lync Server 2013 は、Windows ファブリックバージョン1.0 に依存しています。  Lync Server 2013 の設計フェーズでは、新しい分散アーキテクチャが採用され、レプリケーション、高可用性、フォールトトレランスを提供するために、Windows Fabric 1.0 が選ばれました。  時間の経過と共に、Skype for Business Server と Windows Fabric のどちらも、以降のバージョンでの大幅な再設計によって、この共同アーキテクチャが大幅に改善されました。  現在の Skype for Business 2015 Server では、たとえば Windows Fabric 3.0 が使用されています。

残念ながら、Windows Fabric 1.0**は TLS 1.2 をサポートしていません。 ただし、Lync Server 2013 は、TLS 1.2 と連携するように更新され**ます。 これは、Lync Server 2013 の次の累積的な更新プログラムで提供されます。  Microsoft は、共同作業、移行、フェデレーション、ハイブリッドシナリオを可能にするために、TLS 1.2 サポートを提供しています。

お客様の組織が TLS 1.0 および1.1 を無効にする必要があり、現在 Lync Server 2013 を使用している場合は、計画プロセスを開始することをお勧めします。インプレースアップグレードまたはサイドバイサイド移行 (新規プール、ユーザーの移動) が Skype for Business にインストールされている可能性があります。Business Server 2015 以降。  または、Skype for Business Online への移行を迅速化したい場合があります。

#### <a name="call-quality-dashboard"></a>通話品質ダッシュボード

オンプレミスの通話品質ダッシュボードは、現在、新しいインストール中に TLS 1.0 に依存しています (初めてオンプレミス環境にインストールするとき)。  現在、この問題を調査しており、近い将来、修正プログラムをリリースする予定です。  CQD のインストールを計画していて、TLS 1.0 も無効にしている場合は、最初に CQD のインストールを完了してから、TLS 1.0 無効化を続行することをお勧めします。

#### <a name="third-party-devices"></a>サードパーティ製のデバイス

3PIP 電話、ビデオ会議、リバースプロキシ、ロードバランサーなどのサードパーティ製デバイスでは、TLS 1.2 のサポート性を検証し、必要に応じてベンダーに連絡してください。

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a>エッジサーバーで TLS 1.0/1.1 を無効にするときのフェデレーションに関する考慮事項

エッジサーバーで TLS 1.0/1.1 を無効にすることによる影響について慎重に計画する必要があります。  TLS 1.0 および1.1 を無効にすると、他の組織が組織とフェデレーションできなくなることがあります。

エッジサーバーで TLS 1.0/1.1 を有効にしたままにして、更新プログラム (SfB 2015、Lync 2013)、または古い (2010) 外部システムとの下位互換性を維持することができます。

Microsoft は、Edge ネットワーク (またはネットワーク) が PCI standard の下にあるかどうかに関するアドバイスや推奨事項を提供することはできません。これは、個々の会社によって決定される必要があります。

Skype for Business Online は現在、TLS 1.2 に対応しているため、オンラインとのハイブリッド/フェデレーションへの影響は期待されません。

Skype コンシューマーサービスへの PIC (パブリック IM 接続) の利用: [skype の接続](../../deploy/deploy-skype-connectivity.md)に影響を与えるために TLS 1.0/1.1 の無効化は予期していません。Microsoft PIC ゲートウェイは、既に TLS 1.2 に対応しています。

## <a name="prerequisites-and-process"></a>前提条件とプロセス

上記の手順を除き、TLS 1.0 および1.1 では、スコープ外のサーバーが無効になっている場合、クライアントとデバイスは適切に機能しなくなります。 これは、Microsoft からの更新されたガイダンスを一時停止して待つ必要があることを意味します。 すべての要件を満たし、ギャップの対処計画があることを確認したら、続行します。

高レベルでは、Skype for business Server 2019 を2015インストールしているときに、CU9 をインストールし、必須の更新プログラムを .NET と SQL に適用する必要があります。また、必須のレジストリキーを展開して、最終的に別の方法で作成する必要があります。OS 構成の更新 (レジストリファイルのインポートによる TLS 1.0 および1.1 の無効化) のラウンド。 環境内のすべてのサーバーで TLS 1.0 と1.1 を無効にする前に、Skype for Business Server 2015 CU6 HF2 を含むすべての前提条件のインストールを完了しておくことが非常に重要です。 すべての Skype for Business server (Edge の役割と SQL バックエンドを含む) には、更新プログラムが必要です。 また、サポートされている (スコープ内) クライアントがすべて、必要な最小バージョンに更新されていることを確認します。 管理ワークステーションも更新することを忘れないでください。

Skype for Business サーバーのアップグレードには、"インサイド out" 機能の通常の順序に従う必要があります。 通常の場合と同じ方法で、ディレクタープール、常設チャット、およびペアリングされたプールを扱うことができます。 アップグレードの注文と方法については[、ここ](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)[で説明し](topology.md)ます。

### <a name="high-level-process"></a>高レベルプロセス

1. 運用サーバーを構成する前に、ラボのすべての手順をテストします。
2. エクスポートされたレジストリのコピーをバックアップして、個々のサーバーごとに保持します。 サーバー間でレジストリを共有することはできません。マシンベースの一意のキーが含まれています。
3. すべての Skype for Business 2015 サーバーを CU9 以降にアップグレードします。 Skype for Business Server 2019 の場合は、CU1 以降にアップグレードしてください。
4. すべての前提条件をすべてのサーバーにインストールします。
5. 必須のレジストリキーを展開します。
6. スコープ内のすべてのクライアントが更新されていることを確認します。
7. レジストリのインポートを使用して、TLS 1.0 および1.1 を無効にします。
8. ワークロードが予期したとおりに機能していることを確認します。
    - 問題が発生した場合は、トラブルシューティングと解決、または
    - 手順2のレジストリを復元して、TLS 1.0 および1.1 を再度有効にする
9. TLS 1.2 のみが使用されていることを確認します。

### <a name="install-prerequisites-to-all-servers"></a>すべてのサーバーに前提条件をインストールする

TLS 1.0 および1.1 を Skype for Business Server 2015 展開のオペレーティングシステムレベルで無効にする前に、依存関係の詳細な更新が必要です。 TLS 1.2 をサポートできる最小バージョンを次に示します。 TLS 1.0 および1.1 の無効化を開始する前に、環境内のすべての Skype for Business サーバーにあるすべての必須更新プログラムを展開します。

- Skype for Business Server 2015 CU9 6.0.9319.548 (2019 年5月以降) 以降
- レジストリで SchUseStrongCrypto が有効になっている場合の[.Net Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167)以上 (以下に記載されています)
- SQL は、すべての Skype for Business 2015 サーバーとバックエンドで更新する必要があります。 最初に Enterprise Edition プール SQL バックエンドを更新し、次にそれぞれの FEs を更新します。 
    - [Sql server 2014 SP1 + cu5 以降](https://support.microsoft.com/help/3130926)、またはそれ以降の sql SERVER 2012 SP2 + CU16 以上/sql SERVER [2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014)、またはそれ以降の sql server 2014 SP2
     - [Sql server Native Client for SQL Server 2012](https://www.microsoft.com/download/details.aspx?id=50402)
     - [MICROSOFT ODBC Driver 11 FOR SQL Server](https://www.microsoft.com/download/details.aspx?id=36434)(以降)
     - [SQL Server 2014 SP2 の共有管理オブジェクト](https://www.microsoft.com/download/details.aspx?id=53164)
     - [SQL server 2014 SP2 の SQLSysClrTypes](https://www.microsoft.com/download/details.aspx?id=42295)

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a>推奨される操作の順序で必須条件をインストールするための基本的な手順

1. Skype for Business Server CU9 の更新プログラムをすべてのサーバーにインストールします。 
    1. アップデーターを使ってコンポーネントの更新プログラムをインストールします。
    2. ドキュメントに記載されている手順に従ってデータベースを更新します。 Skype for Business Server 2015 の場合は、「KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)」を参照してください。
    3. 他の変更を加える前に、展開の製品機能を検証します。
2. .NET 4.7 のオフラインインストーラーをダウンロードします。 
    1. 文献[https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)
    2. フロントエンドサーバーで Skype for Business Server 2015 サービスが停止していることを確認します。
    3. 文献[https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)
    4. Ex (標準エディション):```Stop-CsWindowsService```
    5. Ex (Enterprise Edition):```Invoke-CsComputerFailover```
    6. インストーラパッケージを実行します。
    7. サーバーを再起動します。
3. すべてのサーバーの SQL Express 2014 を更新します。 
    1. 文献[https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)
    2. SQL 2014 SP2 をダウンロードする 
        - 文献[https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)
    3. インストールメディアをサーバー上のフォルダーにコピーする (例: C:\ 01_2014SqlSp2)
    4. フロントエンドサーバーで Skype for Business Server 2015 サービスが停止していることを確認する 
        - Ex (標準エディション):```Stop-CsWindowsService```
        - Ex (Enterprise Edition):```Invoke-CsComputerFailover```
    5. 管理コマンドプロンプトを開き、インストールされているすべてのコンポーネントとインスタンスをアップグレードする 
        - 例: C:\ 01_2014SqlSp2 \SQLServer2014SP2-KB3171021-x64-ENU.exe/qs/IAcceptSQLServerLicenseTerms/Action = Patch/allinstances
4. SQL Native Client を更新します。 
    1. リファレンス: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)。
    2. ダウンロード元[https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)
    3. フロントエンドサーバーで Skype for Business Server 2015 サービスが停止していることを確認します。 
        - Ex (標準エディション):```Stop-CsWindowsServices```
        - Ex (Enterprise Edition):```Invoke-CsComputerFailover```
    4. インストールされている SQL インスタンスの実行を停止する 
        - 例```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```
        - 例```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```
        - Ex (標準エディションのみ):```Get-Service 'MSSQL$RTC' | Stop-Service```
    5. 更新をインストールします。
5. SQL Server 用の ODBC ドライバー11を更新して、TLS 1.2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)) のサポートを追加します。
    1. [ODBC Driver 11 FOR SQL Server (Windows) を](https://www.microsoft.com/download/confirmation.aspx?id=36434)ダウンロードします。
    2. フロントエンドサーバーで Skype for Business Server 2015 サービスが停止していることを確認します。
        - 例 (標準エディション):```Stop-CsWindowsService```
        - 例 (Enterprise Edition):```Invoke-CsComputerFailover```
    3. 更新をインストールします。
6. 必須のレジストリキーを展開します。

### <a name="pre-requisite-registry-keys"></a>前提条件のレジストリキー

次のテストをメモ帳にコピーして貼り付け、TLSPreReq または任意の名前を変更して、インポートします。

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

Enterprise Edition プールの SQL バックエンドの場合、前提条件と TLS の無効化は、SQL または OS のすべての更新として処理する必要があります。参照先:[https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)

必須アプリケーションと TLS を無効にする手順は両方とも組み合わせることができますが、オペレーティングシステムレベルで TLS 1.0 および1.1 を無効にする前に、すべての前提条件を適用することを強くお勧めします。 ベストプラクティスのアプローチとしては、すべての前提条件を展開し、ワークロードが正常に機能していることを検証し、後で TLS 1.0/1.1 を有効にすることによって環境を準備します。

### <a name="disable-tls-10-and-11-via-registry-import"></a>レジストリのインポートを使用して TLS 1.0 および1.1 を無効にする

次の手順に進む前に、*すべての前提条件を完了していることを確認し、Skype For business のすべてのサーバーを更新*していることを確認します。

メモ帳のファイルに次のテキストをコピーして、TLSDisable 名前を変更し**ます。**

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

TLS 1.0 および1.1 を無効にする各サーバーに、.reg ファイルをインポートします。 サーバーを再起動します。 サービスがオンラインに戻ったら、次のサーバーに移動します。 Enterprise Edition のプールのアプローチは、OS の更新に使用するのと同じです。

ここでは、TLS 1.0 および1.1 を無効にするだけではありません。 ここでは、Cipher Suite の順序付け (上記を参照) をサポートしており、一部の古い強度の暗号を無効にする方法についても説明します。 これは、Skype for Business Server での SCHANNEL および Crypto API への変更を正式に正式にサポートしていることを意味しています。この変更は、現時点でサポートおよびテストされたものだけであることに注意してください。 今後、追加の構成を検討することもありますが、現時点では、実装のレジストリインポートファイルを変更しないようにしてください。

### <a name="validate-that-workloads-are-functioning-as-expected"></a>ワークロードが期待どおりに機能していることを検証する

お客様の環境で TLS 1.0 と1.1 を無効にした後は、IM & プレゼンス、P2P 通話、エンタープライズボイスなどのメインワークロードがすべて正常に機能していることを確認してください。

**TLS 1.2 のみが使用されていることを確認する**

セキュリティチームが Skype for Business トラフィックの新しい監査を実行して、古いプロトコル TLS 1.0 および1.1 が使用されなくなったことを確認します。

または、Internet Explorer を使用して、TLS 1.0 と TLS 1.1 を無効にした後で、Skype for Business Server 2015 から web サービスへの TLS 接続をテストすることもできます。

1. Internet Explorer を起動します。
2. [**ツール** > ] の [**インターネットオプション**] を選びます。
3. [**詳細設定**] タブを選択します。
4. [**設定**] で、下にスクロールします。
5. TLS 1.0、TLS 1.1、および TLS 1.2 が有効になっていることを確認します。
6. SfB 2015 プールの内部 Web サービスの URL を参照します (正常に接続されている必要があります)。
7. Internet Explorer に戻り、 **TLS 1.2**のみを使うオプションを無効にします。
8. SfB 2015 プールの内部 Web サービスの URL をもう一度参照します (接続に失敗する必要があります)。

![インターネットオプション](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a>高度な展開シナリオ

Skype for Business Ser 2015 で TLS 1.2 をサポートするには、一部の依存関係の前提条件が必要であるため、TLS 1.0 と1.1 が無効になっているシステムでは、RTM メディアからのインストールは失敗します。

**お客様の環境で TLS 1.0 および1.1 が無効になった後、新しい Standard Edition サーバーまたは Enterprise Edition プールを展開します。**

**オプション 1:**[Smartsetup](../../deploy/install/install-skype-for-business-server.md)を使用します。 今後の CU で更新された SQL バイナリに対応するように SmartSetup を更新しており、今後この記事が更新されることにご注意ください。

**オプション 2:** インストール前のローカル SQL インスタンス (RTCLOCAL と LYNCLOCAL)

1. SQL Express 2014 SP2 (SQLEXPR_x64) を、FE のローカルフォルダーにダウンロードしてコピーします。 フォルダーパス <SQL_FOLDER_PATH> と言うことができます。
2. PowerShell またはコマンドプロンプトを起動し、<SQL_FOLDER_PATH> に移動します。
3. 以下のコマンドを実行して、RTCLOCAL SQL インスタンスを作成します。 続行する前に SQLEXPR_x64 .exe が終了するまで待ちます。

    SQLEXPR_x64 .exe/Q/IACCEPTSQLSERVERLICENSETERMS/updateenabled = 0/hidecon/ACTION = インストール/機能 = SQLEngine、Tools/INSTANCENAME = RTCLOCAL/tcpenabled = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin\Administrators"/BROWSERSVCSTARTUPTYPE = ""/AGTSVCACCOUNT = "NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = "Automati" =
1. 以下のコマンドを実行して、LYNCLOCAL SQL インスタンスを作成します。 次の手順に進む前に SQLEXPR_x64 .exe が終了するまで待ちます。

    SQLEXPR_x64 .exe/Q/IACCEPTSQLSERVERLICENSETERMS/updateenabled = 0/hidecon/ACTION = インストール/機能 = SQLEngine、Tools/INSTANCENAME = LYNCLOCAL/tcpenabled = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin\Administrators"/BROWSERSVCSTARTUPTYPE = "自動"/AGTSVCACCOUNT = "NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = "" = 自動
1. Skype for Business Server 2015 RTM セットアップを実行します。
2. 上記の「前提条件」セクションの残りの手順に従います。

**オプション 3:** また、次のようにして、ローカルインストールメディアディレクトリのバイナリを手動で置き換えることもできます。

1. [Skype for Business Server の前提条件をインストールする](../../deploy/install/install-prerequisites.md)  
2. .NET 4.7 をインストールします。 
      - **注:** 最初に、Skype for Business Server 2015 CU5 以降 (6.0.9319.281) での .NET 4.7 のサポートについて説明しました。 そのため、次の手順では、メインインストールの前にコアコンポーネントを更新する予定です。
      - ダウンロード: https://www.microsoft.com/download/details.aspx?id=55167。 
      - リファレンス: [Skype For Business Server 2015 の展開前にインストールする必要があるソフトウェア](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)
3. ISO ファイル/フォルダーをコピーします。 
    - Skype for Business Server 2015 ISO が添付されている場合、ファイルが添付されているドライブのルートディレクトリ (\)例: D: エクスプローラーで) を開きます。
    - すべてのフォルダーとファイルをローカルディスク上のフォルダー (例: c skypeforbusiness2015iso) にコピーします。
    - **注:** コンポーネントをインストールする前に、TLS 1.2 をサポートするために一部のファイルを更新する必要があります。
4. MSI/EXE パッケージを置き換える: 
    - ローカルコンピューター上のインストールメディアの/Setup/Amd64/フォルダーにある既存の MSI パッケージと EXE パッケージを置き換えます。
    - SQL 2014 SP2 Express:https://www.microsoft.com/en-us/download/details.aspx?id=53167 
        - ローカルコンピューター上の SQLEXPR_x64 に名前を変更し、インストールメディアの Setup/amd64/フォルダーで既存のファイルを置き換えます。
    - SQL Native Client:https://www.microsoft.com/en-us/download/details.aspx?id=50402 
        - **注:** 必要に応じて、sqlncli に名前を変更して、インストールメディアの Setup/amd64/フォルダーに存在する既存のファイルを置き換えます。
    - SQL 管理オブジェクト:https://www.microsoft.com/en-us/download/details.aspx?id=53164 
        - **注:** 機能パックには、ダウンロードできる多くのアイテムが含まれています。 SharedManagementObjects をダウンロードする場合に選択します。
        - **注:** インストールメディアの Setup/amd64/フォルダーに存在する既存のファイルを置き換えます。
    - SQL CLR 型:https://www.microsoft.com/en-us/download/details.aspx?id=53164 
        - **注:** 機能パックには、ダウンロードできる多くのアイテムが含まれています。 CQLSysClrTypes をダウンロードする場合に選択します。
        - **注**: インストールメディアの Setup/amd64/フォルダーに存在する既存のファイルを置き換えます。
5. コアコンポーネントをインストールします。 
    - インストールメディアの Setup/amd64/フォルダーから Setup.exe を実行します。 指示に従ってコアコンポーネントをインストールする
    - コアコンポーネントを閉じます。
6. 主要コンポーネントの更新: 
    - Skype for Business 更新プログラムインストーラーをダウンロードします。
    - インストーラーを実行してコアコンポーネントを更新し、パフォーマンスカウンターをインストールします。
    - **注:** CU6HF2 のリリース時点では、現時点で自動更新機能をインストールできるのは、CU6 までです。 そのため、アップデーターは、コアコンポーネントを6.0.9319.516 に更新するために個別に実行する必要があります。
    - 文献https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015
7. 管理ツールをインストールする (オプション): 
    - この操作を行うと、更新されたファイルを使用して、Microsoft SQL Server 2012 Native Client、SQL Server 2014 Management Objects (x64)、および Microsoft System CLR の各種類の SQL Server 2014 (x64) がインストールされます。 さらに、Skype for Business Server 2015 のトポロジビルダーとコントロールパネルは、ローカルコンピューターでも使用できます。
8. ローカル構成ストア (手順 1) をインストールします。 
     - 展開ウィザードを開き、[Skype for Business Server システムのインストールまたは更新] をクリックし、手順1で [**実行**] をクリックします。ローカル構成ストアをインストールします。
     - [**ローカル構成ストアのインストール**] ダイアログボックスで [**次へ**] をクリックします。
     ![[ローカル構成ストアのインストール] ダイアログボックス](../../media/local-configuration-store.png)
     - 結果を確認して、タスクの進捗状況が完了していることを確認します。 [**ログの表示**] をクリックして、結果のログファイルを確認します。
     ![タスクの状態が完了として表示される](../../media/local-configuration-task-completed.png)
     - [**完了**] をクリックします。
9. Skype for Business Server コンポーネントのセットアップまたは削除 (手順 2):
    - 展開ウィザードを開き、[ **skype For Business Server System をインストールまたは更新**する] をクリックして、手順 2: Skype For Business server**コンポーネントのセットアップ**または削除を行う
    - [Skype for Business Server コンポーネントのセットアップ] ダイアログボックスで [**次へ**] をクリックします。
    ![[Skype for Business Server コンポーネントのセットアップ] ウィンドウ](../../media/set-up-skype-for-business-server-components-window.png)
    - ビューログを使用してログを確認し、問題なくセットアップが完了したことを確認します。 
    - [**完了**] をクリックします。
10. 必要に応じて、追加のインストールと構成を続行します (この時点で通常のインストール手順を再開できます)。
