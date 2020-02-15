---
title: Skype for Business Server 2015 で TLS 1.0/1.1 を無効にする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: '概要: お使いの環境で TLS 1.0 および1.1 を無効にするための準備と実装を行います。'
ms.openlocfilehash: 0a25060463ed3b67db8ca523171c2bc48660293d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42012750"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 で TLS 1.0/1.1 を無効にする

この記事の目的は、お客様の環境で TLS 1.0 および1.1 を無効にするための準備と実装に必要なガイダンスを提供することです。 このプロセスには、広範な計画と準備が必要です。 お客様の組織で TLS 1.0 および1.1 を無効にすることを計画している場合は、この記事に記載されているすべての情報を慎重に確認してください。 TLS 1.0/1.1 を無効にすることによって影響を受ける可能性がある、多くの外部依存関係と接続条件があることに注意してください。詳細な計画とテストが保証されています。

## <a name="in-this-article"></a>この記事の内容

- [背景と範囲](#background)
- [前提条件とプロセス](#prerequisites-and-process)
- [高度な展開シナリオ](#advanced-deployment-scenarios)

## <a name="background"></a>背景

TLS 1.0 および1.1 のサポートを無効にするための主なドライバーは、オンプレミスの Skype for Business Server のサポートを無効にすることです。 PCI 要件の詳細については、[こちら](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls)を参照してください。  Microsoft は、組織がこれらの要件に従う必要があるかどうかについてのガイダンスを提供することはできません。 ご使用の環境で TLS 1.0 または1.1 を無効にする必要があるかどうかを判断する必要があります。

Microsoft は、[ここ](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)で使用可能な TLS に関するホワイトペーパーを作成しました。また、この[Exchange ブログ](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)では背景の読み取りも推奨されています。

## <a name="supportability-scope"></a>サポートの範囲

*範囲*は、サポートの境界を参照します。 *完全にテストおよびサポート*されているということは、リストされている製品バージョンに対して TLS 1.0 および1.1 の無効化を完全にサポートしていることを意味します。 現時点では、*調査中*であることを意味します。これらの製品を TLS 無効化サポートの対象にすることについて、積極的に調査しています。 *スコープが不足*している場合は、これらの製品バージョンは TLS 1.0 または1.1 の無効化をサポートしておらず、例外が報告されます。

### <a name="fully-tested-and-supported-servers"></a>完全にテストおよびサポートされているサーバー

- Skype for Business Server 2019 CU1 17.0.2046.123 (2019 年6月) 以降
- Skype for Business Server 2015 CU9 6.0.9319.548 (2019 年5月) または Windows Server 2012 (KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in)または優先する更新プログラム)、2012 R2 または2016。
- Windows Server 2008 R2、2012 (KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in)または優先される更新プログラム)、または 2012 R2 で、CU9 6.0.9319.548 (2019) またはそれ以上のインプレースアップグレードされた Skype For business Server 2015。
- Exchange 接続と Outlook Web App と Exchange Server 2010 SP3 RU19 以降[のガイダンス](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)
- 存続可能 Branch Appliance (SBA) (Skype for Business Server 2015 CU6 HF2 以降) (ベンダーによって、適切な更新プログラムがパッケージ化され、アプライアンスで利用可能になっていることをご確認ください)
- 存続可能 Branch Server (SBS)、Skype for Business Server 2015 CU6 HF2 以降
- Lync Server 2013**エッジの役割のみ**。これはエッジの役割が Windows Fabric 1.0 に依存していないためです。

### <a name="fully-tested-and-supported-clients"></a>完全にテストおよびサポートされているクライアント

- Lync 2013 (Skype for Business) デスクトップクライアント、MSI、C2R (基本的な[15.0.5023.1000 またはそれ以降](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334))
- Skype for Business 2016 デスクトップクライアント、MSI [16.0.4678.1000 またはそれ](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323)以上 (Basic を含む)
- Skype for Business 2016 クリックして実行します。 [2018 年4月](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus)の更新プログラムが必要です。 
    - 月間および半期の対象、16\.0\.9126\.2152 以降
    - 半期チャネルと繰延チャネル、16\.0\.8431\.2242 以降
- Mac 16.15 以降の Skype for Business
- IOS および Android 用の Skype for Business 6.19 以降
- Microsoft Teams ルーム (以前の Skype Room System V2 SRS V2) の 4.0.64.0 (12 月 2018) 以上
- KB4499162 に基づく Team edition の Surface Hub 更新プログラム (2019 年5月、OS ビルド 15063.1835) 以降
- Skype Web App 2015 CU6 HF2 またはそれ以上 (サーバーに付属)

### <a name="currently-being-investigated"></a>現在調査中

- 通話品質ダッシュボード (TLS 1.0 の後に新規インストールされます。1.1 は無効になっています。次を参照) *
 
### <a name="out-of-scope"></a>対象外

記載されている場合を除き、次の製品は TLS 1.0/1.1 の無効化をサポートしていません。また、TLS 1.0 および1.1 が無効になっている環境では機能しません。 その意味: スコープ外のサーバーまたはクライアントを引き続き使用している場合、Skype for Business Server のオンプレミス展開で TLS 1.0/1.1 を無効にする必要がある場合は、これらを更新または削除する必要があります。

- Lync Server 2013
- Lync Server 2010
- Windows Server 2008 またはそれ以降
- Lync for Mac 2011
- Lync 2013 for Mobile-iOS、iPad、Android、または Windows Phone
- Lync "MX" Windows ストアクライアント
- Lync Room System (別名 SRSv1). LRS は、2018年10月9日にサポートの最後に達したため、TLS 1.2 をサポートするように更新されません。
- すべての Lync 2010 クライアント
- Lync Phone Edition-[ここで](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035)更新されたガイダンス。
- 2013ベースの存続可能 Branch Appliance (SBA) または存続可能 Branch Server (SBS)
- Cloud Connector Edition (CCE)
- Windows Phone 版 Skype for Business

### <a name="exceptions"></a>Exceptions

#### <a name="lync-server-2013"></a>Lync Server 2013

Lync Server 2013 は、Windows Fabric バージョン1.0 に依存しています。  Lync Server 2013 の設計フェーズでは、レプリケーション、高可用性、フォールトトレランスを提供するために、魅力的で新しい分散アーキテクチャに Windows Fabric 1.0 が選択されました。  時間の経過とともに、Skype for Business Server と Windows Fabric の両方が、今後のバージョンでの大幅な再設計により、この共同アーキテクチャを大幅に改善しました。  現在の Skype for Business 2015 Server は、Windows Fabric 3.0 を使用しています (例:)。

残念ながら、Windows Fabric 1.0**は TLS 1.2 をサポートしていません。 ただし、Lync Server 2013 を TLS 1.2 と連携するように更新**します。 これは、Lync Server 2013 の次の累積的な更新プログラムで提供されます。  マイクロソフトは、共存、移行、フェデレーション、およびハイブリッドシナリオを可能にするために TLS 1.2 サポートを提供しています。

組織で TLS 1.0 および1.1 を無効にする必要があり、現在 Lync Server 2013 を使用している場合は、計画プロセスを開始することをお勧めします。これにより、一括アップグレードまたは並行移行 (新しいプール、ユーザーの移動) が Skype for Business で必要になる可能性があります。Business Server 2015 以降。  または、Skype for Business Online への移行を高速化する必要がある場合があります。

#### <a name="call-quality-dashboard"></a>通話品質ダッシュボード

現在、オンプレミスの通話品質ダッシュボードは、新しいインストール時に TLS 1.0 に依存しています (オンプレミス環境への初めてのインストール)。  現在、この問題について調査しており、近い将来、修正プログラムのリリースを計画しています。  CQD のインストールと TLS 1.0 の無効化を計画している場合は、CQD のインストールを最初に完了してから、TLS 1.0 無効化を続行することをお勧めします。

#### <a name="third-party-devices"></a>サードパーティ製デバイス

3PIP 電話、ビデオ会議、リバースプロキシ、ロードバランサーなどのサードパーティ製デバイスでは、TLS 1.2 のサポートを検証し、必要に応じて、ベンダーに問い合わせてください。

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a>エッジサーバーで TLS 1.0/1.1 を無効にするときのフェデレーションに関する考慮事項

エッジサーバーで TLS 1.0/1.1 を無効にすることによる影響を慎重に計画し、検討する必要があります。  TLS 1.0 および1.1 を無効にすると、他の組織が組織とフェデレーションできなくなることがあります。

エッジサーバー上で TLS 1.0/1.1 を有効にしたままにして、適用されていない (SfB 2015、Lync 2013) または古い (2010) 外部システムとの下位互換性を維持することができます。

Microsoft は、エッジネットワーク (またはネットワーク) が PCI standard の下にあるかどうかに関するアドバイスや推奨事項を提供することはできません。これは、個々の会社によって決定される必要があります。

Skype for Business Online は現在、TLS 1.2 をサポートしているため、オンラインとのハイブリッド/フェデレーションへの影響は期待できません。

PIC (パブリック IM 接続) から Skype コンシューマサービスへ: [Skype 接続](../../deploy/deploy-skype-connectivity.md)に影響を与えるために TLS 1.0/1.1 を無効にすることは想定されていません。Microsoft PIC ゲートウェイは、既に TLS 1.2 に対応しています。

## <a name="prerequisites-and-process"></a>前提条件とプロセス

上記の場合を除き、TLS 1.0 および1.1 がスコープ外のサーバーを無効にすると、クライアントとデバイスは正常に機能しなくなります。 これは、更新されたガイダンスを Microsoft から一時停止して待つ必要があることを意味します。 すべての要件を満たしていて、ギャップに対処するための計画を立てることができれば、次の手順を実行します。

詳細については、「skype for business Server 2019 をインストール時に準備する」の手順を実行する必要があります。 Skype for business Server 2015 では、CU9 をインストールし、前提条件の更新プログラムを .NET および SQL に適用して、必要なレジストリキーを展開し、最終的に別のオペレーティングシステム構成の更新 (レジストリファイルのインポートによる TLS 1.0 および1.1 の無効化) 環境内のすべてのサーバーで TLS 1.0 および1.1 を無効にする前に、Skype for Business Server 2015 CU6 HF2 などのすべての必須コンポーネントのインストールを完了することが非常に重要です。 エッジの役割と SQL バックエンドを含む、すべての Skype for Business server は更新を必要とします。 また、サポートされている (スコープ内の) すべてのクライアントが必要な最小バージョンに更新されていることを確認してください。 管理ワークステーションも更新することを忘れないでください。

Skype for Business サーバーをアップグレードする場合、"インサイド out" の通常の操作順序に従ってください。 通常と同じ方法で、ディレクタープール、常設チャット、およびペアプールを処理します。 [ここ](topology.md)では、アップグレードの順序と方法に[ついて説明します。](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)

### <a name="high-level-process"></a>高レベルのプロセス

1. 運用サーバーを構成する前に、ラボのすべての手順をテストします。
2. 更新する個々のサーバーごとに、エクスポートされたレジストリのコピーをバックアップして保持します。 サーバー間でレジストリを共有することはできません。これには、マシンベースの一意のキーが含まれています。
3. すべての Skype for Business 2015 サーバーを CU9 以降にアップグレードします。 Skype for Business Server 2019 の場合は、CU1 以降にアップグレードします。
4. すべての必須コンポーネントをすべてのサーバーにインストールします。
5. 前提条件となるレジストリキーを展開します。
6. 範囲内のすべてのクライアントが更新されるようにします。
7. レジストリインポート経由で TLS 1.0 および1.1 を無効にします。
8. ワークロードが予想どおりに機能していることを検証します。
    - 問題が発生した場合、トラブルシューティングと解決、または
    - 手順2のレジストリを復元して、TLS 1.0 および1.1 を再度有効にする
9. TLS 1.2 のみが使用されていることを検証します。

### <a name="install-prerequisites-to-all-servers"></a>必須コンポーネントをすべてのサーバーにインストールする

Skype for Business Server の2015展開で、オペレーティングシステムレベルで TLS 1.0 および1.1 の無効化を開始する前に、広範な依存関係の更新を行う必要があります。 TLS 1.2 をサポートできる最小バージョンは次のとおりです。 TLS 1.0 および1.1 の無効化を開始する前に、前提条件となるすべての更新プログラムを環境内のすべての Skype for Business サーバーに展開します。

- Skype for Business Server 2015 CU9 6.0.9319.548 (2019 年5月) 以降
- レジストリで SchUseStrongCrypto が有効になっている[.Net Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167)またはそれ以降 (以下に提供)
- すべての Skype for Business 2015 サーバーおよびバックエンドで、SQL を更新する必要があります。 最初に Enterprise Edition プールの SQL バックエンドを更新し、次にそれぞれの FEs を更新します。 
    - [Sql server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926)、またはそれ以降の sql SERVER 2012 SP2 + CU16 または sql SERVER [2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014)、またはそれ以降の/sql server 2014 SP2
     - [Sql Server の sql server Native Client 2012](https://www.microsoft.com/download/details.aspx?id=50402)
     - [SQL Server 以降の MICROSOFT ODBC Driver 11](https://www.microsoft.com/download/details.aspx?id=36434)
     - [SQL Server 2014 SP2 の共有管理オブジェクト](https://www.microsoft.com/download/details.aspx?id=53164)
     - [SQL server 2014 SP2 の SQLSysClrTypes](https://www.microsoft.com/download/details.aspx?id=42295)

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a>推奨される操作順序で必要な前提条件をインストールするための基本的な手順

1. Skype for Business Server CU9 の更新プログラムをすべてのサーバーにインストールします。 
    1. アップデーターを使用して、コンポーネントの更新プログラムをインストールします。
    2. ドキュメントに記載されている手順に従ってデータベースを更新します。 Skype for Business Server 2015 については、「KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)」を参照してください。
    3. 他の変更を加えて前に進む前に、展開の製品機能を検証します。
2. .NET 4.7 オフラインインストーラーをダウンロードします。 
    1. 参考[https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)
    2. フロントエンドサーバーで、Skype for Business Server 2015 サービスが停止していることを確認します。
    3. 参考[https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)
    4. Ex (Standard Edition):```Stop-CsWindowsService```
    5. Ex (Enterprise Edition):```Invoke-CsComputerFailover```
    6. インストーラパッケージを実行します。
    7. サーバーを再起動します。
3. すべてのサーバーで SQL Express 2014 を更新します。 
    1. 参考[https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)
    2. SQL 2014 SP2 をダウンロードする 
        - 参考[https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)
    3. インストールメディアをサーバー上のフォルダー (例: C:\ 01_2014SqlSp2) にコピーします。
    4. フロントエンドサーバーで Skype for Business Server 2015 サービスが停止していることを確認する 
        - Ex (Standard Edition):```Stop-CsWindowsService```
        - Ex (Enterprise Edition):```Invoke-CsComputerFailover```
    5. 管理者コマンドプロンプトを開き、インストールされているすべてのコンポーネントとインスタンスをアップグレードする 
        - 例: C:\ 01_2014SqlSp2 \SQLServer2014SP2-KB3171021-x64-ENU.exe/qs/IAcceptSQLServerLicenseTerms/Action = Patch/allinstances
4. SQL ネイティブクライアントを更新します。 
    1. リファレンス: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)。
    2. ダウンロード元[https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)
    3. フロントエンドサーバーで Skype for Business Server 2015 サービスが停止していることを確認します。 
        - Ex (Standard Edition):```Stop-CsWindowsServices```
        - Ex (Enterprise Edition):```Invoke-CsComputerFailover```
    4. 実行時にインストールされた SQL インスタンスを停止する 
        - 渡し```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```
        - 渡し```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```
        - Ex (Standard Edition のみ):```Get-Service 'MSSQL$RTC' | Stop-Service```
    5. 更新プログラムをインストールします。
5. SQL Server 用の ODBC Driver 11 を更新して、TLS 1.2 のサポートを含めます (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server))。
    1. [SQL Server の ODBC Driver 11 をダウンロードしてください-Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434)。
    2. フロントエンドサーバーで、Skype for Business Server 2015 サービスが停止していることを確認します。
        - 例 (Standard Edition):```Stop-CsWindowsService```
        - 例 (Enterprise Edition):```Invoke-CsComputerFailover```
    3. 更新プログラムをインストールします。
6. 前提条件となるレジストリキーを展開します。

### <a name="pre-requisite-registry-keys"></a>前提条件となるレジストリキー

次のテストをコピーしてメモ帳に貼り付け、TLSPreReq または任意の名前を変更してから、インポートします。

```console
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

Enterprise Edition プールの SQL バックエンドの場合、前提条件と TLS の無効化は、SQL または OS の更新と同様に処理する必要があります。以下を参照してください。[https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)

前提条件となるアプリケーションと TLS の無効化手順の両方を組み合わせることができますが、オペレーティングシステムレベルで TLS 1.0 および1.1 を無効にする前に、すべての前提条件を適用することを強くお勧めします。 ベストプラクティスの方法は、すべての前提条件を展開して環境を準備し、ワークロードがすべて正常に機能していることを検証して、後で TLS 1.0/1.1 を無効にすることです。

### <a name="disable-tls-10-and-11-via-registry-import"></a>レジストリインポートによる TLS 1.0 および1.1 の無効化

次の手順に進む前に、*すべての前提条件と更新された Skype For Business サーバーを完了*していることを確認してください。

次のテキストをメモ帳ファイルにコピーして、 **TLSDisable**の名前を変更します。

```console
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

TLS 1.0 および1.1 を無効にする各サーバーに .reg ファイルをインポートします。 サーバーを再起動します。 サービスがオンラインに戻ったら、次のサーバーに移動します。 Enterprise Edition プールのアプローチは、すべての OS 更新に対して実行するのと同じです。

ここでは、TLS 1.0 および1.1 を無効にするだけではありません。 (前述のように) 暗号スイートの再オーダーをサポートしており、一部の古い弱い暗号を無効にしています。 この変更は、Skype for Business Server での SCHANNEL および Crypto API への初めての変更を正式にサポートしています。これらの変更は、現時点でサポートおよびテストしたものだけであることに注意することが重要です。 今後、追加の構成を検討する場合がありますが、現時点では、実装でレジストリインポートファイルを変更しないでください。

### <a name="validate-that-workloads-are-functioning-as-expected"></a>ワークロードが予想どおりに機能していることを検証する

ご使用の環境で TLS 1.0 および1.1 が無効になったら、IM & プレゼンス、P2P 呼び出し、エンタープライズ Voip など、すべての主要なワークロードが想定どおりに機能していることを確認してください。

**TLS 1.2 のみが使用されていることを確認する**

セキュリティチームが Skype for Business トラフィックの新しい監査を実行して、古いプロトコルの TLS 1.0 および1.1 が使用されなくなっていることを確認します。

または、Internet Explorer を使用して、TLS 1.0 および TLS 1.1 を無効にした後、Skype for Business Server 2015 から web サービスへの TLS 接続をテストすることもできます。

1. Internet Explorer を起動します。
2. [**ツール** > ] [**インターネットオプション**] を選択します。
3. [**詳細設定**] タブを選択します。
4. [**設定**] で、一番下までスクロールします。
5. TLS 1.0、TLS 1.1、および TLS 1.2 が有効になっていることを確認します。
6. SfB 2015 プールの内部 Web サービス URL を参照します (正常に接続されている必要があります)。
7. Internet Explorer に戻り、 **TLS 1.2**のみを使用するオプションを無効にします。
8. SfB 2015 プールの内部 Web サービス URL をもう一度参照してください (接続に失敗する必要があります)。

![インターネットオプション](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a>高度な展開シナリオ

Skype for Business Ser 2015 で TLS 1.2 をサポートするには、いくつかの依存関係の前提条件が必要になるため、TLS 1.0 および1.1 が無効になっているシステムでは、RTM メディアからのインストールは失敗します。

**TLS 1.0 および1.1 が環境で無効になっている場合、新しい Standard Edition サーバーまたは Enterprise Edition プールを展開します。**

**オプション 1:**[Smartsetup](../../deploy/install/install-skype-for-business-server.md)を使用します。 今後の CU では、更新された SQL バイナリに対応するように SmartSetup を更新しています。今後、この記事を更新します。

**オプション 2:** ローカル SQL インスタンスのインストール前 (RTCLOCAL および LYNCLOCAL)

1. SQL Express 2014 SP2 (SQLEXPR_x64) を FE のローカルフォルダーにダウンロードしてコピーします。 フォルダーのパス <SQL_FOLDER_PATH> について説明します。
2. PowerShell またはコマンドプロンプトを起動し、<SQL_FOLDER_PATH> に移動します。
3. 次のコマンドを実行して、RTCLOCAL SQL インスタンスを作成します。 続行する前に SQLEXPR_x64 exe が終了するまで待機します。

    SQLEXPR_x64/IACCEPTSQLSERVERLICENSETERMS/Q/updateenabled = 0/hideconall/ACTION = Install/FEATURES = SQLEngine, Tools/INSTANCENAME = RTCLOCAL/tcpenabled = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin\Administrators"/BROWSERSVCSTARTUPTYPE = "Automatic"/AGTSVCACCOUNT = "NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = Automati
1. 次のコマンドを実行して、LYNCLOCAL SQL インスタンスを作成します。 SQLEXPR_x64 .exe が終了するまで待ってから、次の手順に進みます。

    SQLEXPR_x64. .exe/Q/IACCEPTSQLSERVERLICENSETERMS/updateenabled = 0/HIDECON/ACTION = Install/FEATURES = SQLEngine, Tools/INSTANCENAME = LYNCLOCAL/tcpenabled = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin\Administrators"/BROWSERSVCSTARTUPTYPE = "Automatic"/AGTSVCACCOUNT = "NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = [自動]
1. Skype for Business Server 2015 RTM セットアップを実行します。
2. 上記の前提条件のセクションにある残りの手順に従います。

**オプション 3:** また、次のようにして、ローカルインストールメディアディレクトリのバイナリを手動で置き換えることもできます。

1. [Skype for Business Server の必須コンポーネントをインストールする](../../deploy/install/install-prerequisites.md)  
2. .NET 4.7 をインストールします。 
      - **注:** 最初に、Skype for Business Server 2015 CU5 (6.0.9319.281) での .NET 4.7 のサポートを導入しました。 そのため、次の手順では、主要なコンポーネントを更新してから、メインインストールの前に実行します。
      - ダウンロード: https://www.microsoft.com/download/details.aspx?id=55167。 
      - リファレンス: [Skype For Business Server 2015 の展開前にインストールする必要があるソフトウェア](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)
3. ISO ファイル/フォルダーをコピーします。 
    - Skype for Business Server 2015 ISO が接続されている場合は、ファイルエクスプローラーで、接続されているドライブの\)ルートディレクトリ (Ex: D:) を開きます。
    - すべてのフォルダーとファイルをローカルディスク上のフォルダー (例: C:\ skypeforbusiness2015iso) にコピーします。
    - **注:** コンポーネントをインストールする前に、TLS 1.2 のサポートのためにいくつかのファイルを更新する必要があります。
4. MSI/EXE パッケージを置換する: 
    - ローカルコンピューターのインストールメディアの/Setup/Amd64/フォルダー内の既存の MSI および EXE パッケージを置換します。
    - SQL 2014 SP2 Express:https://www.microsoft.com/download/details.aspx?id=53167 
        - ローカルコンピューター上の SQLEXPR_x64 の名前に変更し、インストールメディアの Setup/amd64/フォルダーにある既存のファイルを置き換えます。
    - SQL Native Client:https://www.microsoft.com/download/details.aspx?id=50402 
        - **注:** 必要に応じて、この名前を sqlncli.msi に変更し、インストールメディアの Setup/amd64/フォルダーに存在する既存のファイルを置き換えます。
    - SQL 管理オブジェクト:https://www.microsoft.com/download/details.aspx?id=53164 
        - **注:** 機能パックには、ダウンロード可能な多くのアイテムがあります。 SharedManagementObjects をダウンロードする場合は、このチェックボックスをオンにします。
        - **注:** インストールメディアの Setup/amd64/フォルダーに存在する既存のファイルを置換します。
    - SQL CLR の種類:https://www.microsoft.com/download/details.aspx?id=53164 
        - **注:** 機能パックには、ダウンロード可能な多くのアイテムがあります。 CQLSysClrTypes のダウンロードのみを選択する
        - **注**: インストールメディアの Setup/amd64/フォルダーに存在する既存のファイルを置き換えます。
5. コアコンポーネントをインストールします。 
    - インストールメディアの Setup/amd64/フォルダーから Setup.exe を実行します。 手順に従ってコアコンポーネントをインストールする
    - コアコンポーネントを閉じます。
6. コアコンポーネントを更新します。 
    - Skype for Business 更新プログラムインストーラーをダウンロードします。
    - インストーラーを実行してコアコンポーネントを更新し、パフォーマンスカウンターをインストールします。
    - **注:** CU6HF2 のリリースの時点で、自動更新機能は現在、CU6 にのみインストールされます。 したがって、コアコンポーネントを6.0.9319.516 に更新するには、updater を個別に実行する必要があります。
    - 参考https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015
7. 管理ツールをインストールする (オプション): 
    - これにより、更新されたファイルを使用して、Microsoft SQL Server 2012 Native Client、SQL Server 2014 Management Objects (x64)、および Microsoft System CLR Types for SQL Server 2014 (x64) がインストールされます。 また、Skype for Business Server 2015 トポロジビルダーとコントロールパネルは、ローカルコンピューターで利用できます。
8. ローカル構成ストアのインストール (手順 1): 
     - 展開ウィザードを開き、[Skype for Business Server システムのインストールまたは更新] をクリックし、[ステップ 1: ローカル構成ストアのインストール] で [**実行**] をクリックします。
     - [**ローカル構成ストアのインストール**] ダイアログボックスで [**次へ**] をクリックします。
     ![[ローカル構成ストアのインストール] ダイアログボックス](../../media/local-configuration-store.png)
     - 結果を確認し、タスクの状態が [完了] になっていることを確認します。 [**ログの表示**] をクリックして、結果のログファイルを確認します。
     ![タスクの進捗状況が完了と表示される](../../media/local-configuration-task-completed.png)
     - [**完了**] をクリックします。
9. Skype for Business Server コンポーネントのセットアップまたは削除 (手順 2):
    - 展開ウィザードを開き、[ **skype for Business Server システムのインストールまたは更新**] をクリックし **、[手順**2: Skype for Business server コンポーネントのセットアップまたは削除] をクリックします。
    - [Skype for Business Server コンポーネントのセットアップ] ダイアログボックスで、[**次へ**] をクリックします。
    ![[Skype for Business Server コンポーネントのセットアップ] ウィンドウ](../../media/set-up-skype-for-business-server-components-window.png)
    - View ログを使用してログを確認し、問題なくセットアップが完了したことを確認します。 
    - [**完了**] をクリックします。
10. 必要に応じて、追加のインストールと構成を続行します (この時点では、通常のインストール手順を再開できます)。
