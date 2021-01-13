---
title: Skype for Business Server 2015 で TLS 1.0/1.1 を無効にする
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: '概要: 環境での TLS 1.0 および 1.1 の無効化を準備して実装します。'
ms.openlocfilehash: da76280540f9d18435ed929aace6cf6fc439a4cf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826397"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 で TLS 1.0/1.1 を無効にする

この記事の目的は、環境で TLS 1.0 および 1.1 の無効化を準備および実装するために必要なガイダンスを提供します。 このプロセスでは、広範な計画と準備が必要です。 組織で TLS 1.0 と 1.1 を無効にする計画を立て、この記事のすべての情報を慎重に確認してください。 TLS 1.0/1.1 を無効にすることで影響を受け得る多くの外部依存関係と接続条件があります。そのため、広範囲の計画とテストが必要です。

## <a name="in-this-article"></a>この記事の内容

- [バックグラウンドとスコープ](#background)
- [前提条件とプロセス](#prerequisites-and-process)
- [高度な展開シナリオ](#advanced-deployment-scenarios)

## <a name="background"></a>背景

TLS 1.0 および 1.1 を提供するための主要なドライバーは、Skype for Business Server On-Premises のサポートを無効にするための主要なドライバーは、Payment Card Industry (PCI) Security Standards Council および Federal Information Processing Standards の要件です。 PCI 要件の詳細については、こちらを参照 [してください](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls)。  Microsoft は、お客様の組織がこれらの要件または他の要件に従う必要があるかどうかに関するガイダンスを提供できません。 環境で TLS 1.0 または 1.1 を無効にする必要があるかどうかを判断する必要があります。

Microsoft では、TLS に関する[](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)ホワイト ペーパーをここで作成しました。また、この Exchange ブログで利用できるバックグラウンドの閲覧をお[勧めします](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)。

## <a name="supportability-scope"></a>サポートスコープ

*スコープとは* 、サポートの境界を指します。 *完全にテストされ、* サポートされているということは、リストされている製品バージョンに対して TLS 1.0 と 1.1 の無効化を完全にサポートし、テスト済みです。 *現在調査中の場合* は、次の意味が必要です。これらの製品を TLS 無効化サポートの範囲に含め、積極的に調査中です。 *スコープ外の* 場合、これらの製品バージョンは TLS 1.0 または 1.1 の無効化をサポートしていないので、示されている例外を除き機能しません。

### <a name="fully-tested-and-supported-servers"></a>完全にテストされ、サポートされているサーバー

- Skype for Business Server 2019 CU1 17.0.2046.123 (2019 年 6 月) 以上
- Skype for Business Server 2015 CU9 6.0.9319.548 (2019 年 5 月)、Windows Server 2012 (KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) 以上の更新プログラムを適用)、2012 R2 または 2016 以上。
- Windows Server 2008 R2、2012 年 (KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) または更新プログラムの代用)、または 2012 R2 の CU9 6.0.9319.548 (2019 年 5 月) 以上を使用する、一時アップグレードされた Skype for Business Server 2015。
- Exchange Connectivity and Outlook Web App with Exchange Server 2010 SP3 RU19 or higher, guidance [here](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)
- Skype for Business Server 2015 CU6 HF2 以上の存続可能ブランチ アプライアンス (SBA) (適切な更新プログラムがパッケージ化され、アプライアンスで利用可能にされたベンダーに確認してください)
- Skype for Business Server 2015 CU6 HF2 以上の存続可能ブランチ サーバー (SBS)
- Lync Server 2013 エッジの役割 **のみ**。これは、エッジの役割が Windows Fabric 1.0 に依存していないためです。

### <a name="fully-tested-and-supported-clients"></a>完全にテストされ、サポートされているクライアント

- Lync 2013 (Skype for Business) デスクトップ クライアント、MSI、C2R (Basic [15.0.5023.1000 以上を含む](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334))
- Skype for Business 2016 デスクトップ クライアント、MSI [16.0.4678.1000](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323)以上 (基本を含む)
- Skype for Business 2016 Click to Run Require the [April 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) Updates: 
    - 月次およびSemi-Annual対象、16 \. \. 0 9126 \. 2152 以上
    - Semi-Annualおよび Deferred Channel、16 \. 0 \. 8431 \. 2242 以上
- Mac 16.15 以上の Skype for Business
- Skype for Business for iOS および Android 6.19 以上
- Microsoft Teams Rooms (以前の Skype Room System V2 SRS V2) 4.0.64.0 (2018 年 12 月) 以上
- KB4499162 (2019 年 5 月、OS ビルド 15063.1835) 以上に基づく Team エディションの Surface Hub 更新プログラム
- Skype Web App 2015 CU6 HF2 以上 (サーバーに含む)

### <a name="currently-being-investigated"></a>現在調査中

- 通話品質ダッシュボード (TLS 1.0、1.1 が無効にされた後の新しいインストール(下記を参照)*
 
### <a name="out-of-scope"></a>対象外

特に示されている場合を除き、次の製品は TLS 1.0/1.1 のサポートの対象ではなく、TLS 1.0 と 1.1 が無効になっている環境では機能しません。 つまり、スコープ外のサーバーまたはクライアントをまだ利用している場合は、Skype for Business Server のオンプレミス展開の任意の場所で TLS 1.0/1.1 を無効にする必要がある場合は、これらを更新または削除する必要があります。

- Lync Server 2013
- Lync Server 2010
- Windows Server 2008 以下
- Lync for Mac 2011
- Lync 2013 for Mobile - iOS、iPad、Android、または Windows Phone
- Lync "MX" Windows ストア クライアント
- Lync Room System (a.k.a. SRSv1)。 LRS は 2018 年 10 月 9 日にサポート終了に達し、TLS 1.2 をサポートするために更新されません。
- すべての Lync 2010 クライアント
- Lync Phone Edition - ここで更新された [ガイダンス](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035)。
- 2013 ベースの存続可能ブランチ アプライアンス (SBA) または存続可能ブランチ サーバー (SBS)
- Cloud Connector エディション (CCE)
- Skype for Business for Windows Phone

### <a name="exceptions"></a>例外

#### <a name="lync-server-2013"></a>Lync Server 2013

Lync Server 2013 は Windows Fabric バージョン 1.0 に依存します。  Lync Server 2013 の設計フェーズでは、レプリケーション、高可用性、およびフォールト トレランスを実現するために、Windows Fabric 1.0 が魅力的で新しい分散アーキテクチャとして選択されました。  Skype for Business Server と Windows Fabric の両方で、この共同アーキテクチャは、後のバージョンで大幅に再設計され、時間のとともに大幅に改善されています。  現在の Skype for Business 2015 Server では、たとえば Windows Fabric 3.0 を使用します。

残念ながら、Windows Fabric 1.0 **では TLS 1.2 はサポートされていません。 ただし、TLS 1.2 で動作するために Lync Server 2013 を更新します**。 これは、Lync Server 2013 の次の累積的な更新プログラムで提供される予定です。  TLS 1.2 のサポートを提供して、共同存在、移行、フェデレーション、およびハイブリッドのシナリオを有効にします。

組織で TLS 1.0 と 1.1 を無効にする必要がある場合に、現在 Lync Server 2013 を使用している場合は、計画プロセスを開始することをお勧めします。計画プロセスは、Skype for Business Server 2015 以上への一時アップグレードまたはサイド バイ サイド移行 (新しいプール、ユーザーの移動) が必要になる可能性があります。  または、Skype for Business Online への移行を加速したい場合があります。

#### <a name="call-quality-dashboard"></a>通話品質ダッシュボード

現在、オンプレミス通話品質ダッシュボードは、新しいインストール時 (オンプレミス環境への初回インストール時) に TLS 1.0 に依存しています。  We are currently investigating this issue and plan to release a fix in the near future.  CQD のインストールと TLS 1.0 の無効化を計画している場合は、まず CQD インストールを完了してから、TLS 1.0 の無効化に進みます。

#### <a name="skype-for-business-sdn-manager"></a>Skype for Business SDN Manager

新しいインストール時にデータベースSQL使用する Skype for Business SDN Manager は TLS 1.0 に依存します。 SQL データベースを使用して Skype for Business SDN Manager をインストールし、TLS 1.0 も無効にする予定の場合は、最初に Skype for Business SDN Manager を完了してから、TLS 1.0 の無効化に進みます。 インストール前に TLS 1.0 が無効にされた場合は、Skype for Business SDN Manager SQL データベースをホストするために使用される SQL Server バックエンド サーバーで TLS 1.0 を一時的に有効に戻す必要があります。

#### <a name="third-party-devices"></a>サード パーティ製デバイス

3PIP 電話、ビデオ会議、リバース プロキシ、ロード バランサーなどのサード パーティ製デバイスでは、TLS 1.2 のサポート可能性を検証し、慎重にテストし、必要に応じてベンダーに問い合わせてください。

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a>エッジ サーバーで TLS 1.0/1.1 を無効にする場合のフェデレーションに関する考慮事項

エッジ サーバーで TLS 1.0/1.1 を無効にした場合の影響を慎重に計画し、検討する必要があります。  TLS 1.0 および 1.1 を無効にすると、他の組織が組織とのフェデレーションを行えなくなる可能性があります。

修正プログラムが適用されていない (SfB 2015、Lync 2013) 以前の (2010) 外部システムとの下位互換性を維持するために、エッジ サーバーで TLS 1.0/1.1 を有効にすることもできます。

Microsoft は、お客様のエッジ ネットワーク (またはネットワーク) が PCI 標準に準拠するかどうかに関するアドバイスや推奨事項を提供できません。個別の会社によって決定される必要があります。

Skype for Business Online は現在 TLS 1.2 に対応しています。そのため、ハイブリッド/オンラインとのフェデレーションへの影響は期待されません。

PIC (Public IM Connectivity) to Skype Consumer service: We do not expecting TLS 1.0/1.1 to impact [Skype Connectivity](../../deploy/deploy-skype-connectivity.md);Microsoft PIC ゲートウェイは既に TLS 1.2 に対応しています。

## <a name="prerequisites-and-process"></a>前提条件とプロセス

上記で説明した場合を除き、TLS 1.0 および 1.1 がスコープ外のサーバーで無効にされた場合、クライアントとデバイスは正常に機能するか、またはすべて機能します。 これは、Microsoft からの更新されたガイダンスを一時停止して待つ必要がある場合があります。 すべての要件を満たしていることを確認し、ギャップに対処する計画を立てしたら、次に進みます。

大きなレベルでは、Skype for Business Server 2019 をインストールする準備が整っている間、Skype for Business Server 2015 では CU9 のインストール、.NET と SQL への前提条件の更新プログラムの適用、前提条件となるレジストリ キーの展開、最後に別の OS 構成更新のラウンド (つまり、レジストリ ファイルのインポートによる TLS 1.0 と 1.1 の無効化) が必要です。 環境内の任意のサーバーで TLS 1.0 と 1.1 を無効にする前に、Skype for Business Server 2015 CU6 HF2 を含むすべての前提条件のインストールを完了することが非常に重要です。 エッジの役割やバックエンドの管理を含むすべての Skype for Business サーバー SQL更新プログラムが必要です。 また、サポート対象 (範囲内) のすべてのクライアントが必要な最小バージョンに更新されている必要があります。 管理ワークステーションも忘れずに更新してください。

Skype for Business サーバーをアップグレードする場合は、"インサイド アウト" の通常の運用順序に従う必要があります。 ディレクター プール、常設チャット、ペアリングされたプールは、通常と同じ方法で扱います。 アップグレードの順序と方法については、ここ [とここを](topology.md) 参照 [してください](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)。

### <a name="high-level-process"></a>プロセスのレベルが高い

1. 実稼働サーバーを構成する前に、ラボのすべての手順をテストします。
2. 更新する個々のサーバーごとに、エクスポートされたレジストリのコピーをバックアップして保持します。 サーバー間でレジストリを共有することはできません。コンピューターベースの一意のキーが含まれている。
3. すべての Skype for Business 2015 サーバーを CU9 以上にアップグレードします。 Skype for Business Server 2019 の場合は、CU1 以上にアップグレードします。
4. すべての必須コンポーネントをすべてのサーバーにインストールします。
5. 前提条件となるレジストリ キーを展開します。
6. スコープ内のすべてのクライアントが更新されます。
7. レジストリ のインポートを使用して TLS 1.0 および 1.1 を無効にします。
8. ワークロードが期待通り機能しているのを検証します。
    - 問題が発生した場合は、トラブルシューティングと解決、または
    - 手順 2 からレジストリを復元して TLS 1.0 と 1.1 を再び有効にする
9. TLS 1.2 だけが使用されているのを検証します。

### <a name="install-prerequisites-to-all-servers"></a>すべてのサーバーに必須コンポーネントをインストールする

Skype for Business Server 2015 展開のオペレーティング システム レベルで TLS 1.0 および 1.1 の無効化を開始する前に、広範な依存関係の更新が必要です。 TLS 1.2 をサポートできる最小バージョンを次に示します。 TLS 1.0 と 1.1 の無効化を開始する前に、環境内のすべての Skype for Business サーバーに前提条件の更新プログラムを展開します。

- Skype for Business Server 2015 CU9 6.0.9319.548 (2019 年 5 月) 以上
- レジストリで SchUseStrongCrypto を有効にした[.NET Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167)以上 (下記参照)
- SQL Skype for Business 2015 サーバーとバックエンドで更新する必要があります。 最初に Enterprise Edition プールSQLバックエンドを更新し、次にそれぞれの FEs を更新します。 
    - [SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926)以上 / SQL Server 2012 SP2 + CU16 以上 / [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014)以上 / SQL Server 2014 SP2
     - [SQL Server 2012 SQL Server Native Client](https://www.microsoft.com/download/details.aspx?id=50402)
     - [Microsoft ODBC Driver 11 for SQL Server](https://www.microsoft.com/download/details.aspx?id=36434)or higher
     - [SQL Server 2014 SP2 の共有管理オブジェクト](https://www.microsoft.com/download/details.aspx?id=53164)
     - [SQLSysClrTypes for SQL server 2014 SP2](https://www.microsoft.com/download/details.aspx?id=42295)

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a>前提条件をインストールするための基本的な手順 (推奨される操作順)

1. Skype for Business Server CU9 更新プログラムをすべてのサーバーにインストールします。 
    1. アップデータツールを使用してコンポーネントに更新プログラムをインストールします。
    2. 文書化されている手順に従ってデータベースを更新します。 Skype for Business Server 2015 の場合は、KB [3061064 を参照してください](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)。
    3. 他の変更を進む前に、展開の製品機能を検証します。
2. .NET 4.7 オフライン インストーラーをダウンロードします。 
    1. リファレンス: [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)
    2. フロント エンド サーバーで Skype for Business Server 2015 サービスが停止している必要があります。
    3. リファレンス: [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)
    4. Ex (Standard Edition): ```Stop-CsWindowsService```
    5. 例 (Enterprise Edition): ```Invoke-CsComputerFailover```
    6. インストーラー パッケージを実行します。
    7. サーバーを再起動します。
3. すべてのSQL Express 2014 を更新します。 
    1. リファレンス: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)
    2. 2014 SP2 SQLダウンロード 
        - リファレンス: [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)
    3. インストール メディアをサーバー上のフォルダーにコピーします (例: C:\01_2014SqlSp2)
    4. フロント エンド サーバーで Skype for Business Server 2015 サービスが停止している 
        - Ex (Standard Edition): ```Stop-CsWindowsService```
        - 例 (Enterprise Edition): ```Invoke-CsComputerFailover```
    5. 管理者コマンド プロンプトを開き、インストール済みのすべてのコンポーネントとインスタンスをアップグレードする 
        - 例: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances
4. ネイティブ SQL更新します。 
    1. リファレンス: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server) .
    2. ダウンロード [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)
    3. フロント エンド サーバーで Skype for Business Server 2015 サービスが停止します。 
        - Ex (Standard Edition): ```Stop-CsWindowsServices```
        - 例 (Enterprise Edition): ```Invoke-CsComputerFailover```
    4. インストールされたSQLインスタンスの実行を停止する 
        - 例: ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```
        - 例: ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```
        - Ex (Standard Edition のみ): ```Get-Service 'MSSQL$RTC' | Stop-Service```
    5. 更新プログラムをインストールします。
5. ODBC Driver 11 for SQL Server TLS 1.2 (KB [3135244)](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)のサポートを含める。
    1. ODBC [Driver 11 for SQL Server - Windows をダウンロードします](https://www.microsoft.com/download/confirmation.aspx?id=36434)。
    2. フロント エンド サーバーで Skype for Business Server 2015 サービスが停止している必要があります。
        - 例 (Standard Edition): ```Stop-CsWindowsService```
        - 例 (Enterprise Edition): ```Invoke-CsComputerFailover```
    3. 更新プログラムをインストールします。
6. 前提条件となるレジストリ キーを展開します。

### <a name="pre-requisite-registry-keys"></a>前提条件のレジストリ キー

次のテストをコピー/貼り付けしてメモ帳に貼り付け、TLSPreReq.reg または選択した名前の名前を変更してから、インポートします。

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

Enterprise Edition SQLのバック エンドの場合、前提条件と TLS の無効化は、次に示す任意SQLまたは OS の更新プログラムとして扱う必要があります。参照: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)

前提条件となるアプリケーションと TLS の両方の無効化手順を組み合わせることができますが、オペレーティング システム レベルでの TLS 1.0 と 1.1 の無効化に進む前に、すべての前提条件を適用することを強く推奨します。 ベスト プラクティスのアプローチは、すべての前提条件を展開し、すべてのワークロードが正常に正常に機能していることを検証し、後で TLS 1.0/1.1 を無効にすることで環境を準備する方法です。

### <a name="disable-tls-10-and-11-via-registry-import"></a>レジストリ インポートによる TLS 1.0 および 1.1 の無効化

次の手順に進む前に、すべての前提条件と更新された Skype for Business Servers が完了 *していることを確認してください*。

次のテキストをメモ帳ファイルにコピーし **、TLSDisable.reg という名前に変更します**。

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

TLS 1.0 と 1.1 を無効にする各サーバーに .reg ファイルをインポートします。 サーバーを再起動します。 サービスがオンラインに戻った後、次のサーバーに移動します。 Enterprise Edition プールのアプローチは、すべての OS 更新プログラムで使用する方法と同じです。

ここで TLS 1.0 と 1.1 を無効にしている以上のことを行っていることに気付いた可能性があります。 暗号スイートの再順序付け (上記のように) と、いくつかの古い弱暗号の無効化をサポートしています。 Skype for Business Server で SCHANNEL と Crypto API に対するこれらの変更を正式にサポートするのは今回が初めてであり、現時点でサポートおよびテストした変更は、これらの変更のみである点に注意することが重要です。 今後、追加の構成を検討する場合がありますが、現在のところ、実装内のレジストリ インポート ファイルは変更してください。

### <a name="validate-that-workloads-are-functioning-as-expected"></a>ワークロードが期待通り機能しているのを検証する

環境で TLS 1.0 と 1.1 が無効にされた後は、IM & プレゼンス、P2P 通話、エンタープライズ VoIP など、すべての主要なワークロードが期待通り機能している必要があります。

**TLS 1.2 のみを使用している検証**

セキュリティ チームに Skype for Business トラフィックの新しい監査を実行して、古いプロトコル TLS 1.0 と 1.1 が使用されなくなったか確認します。

または、Internet Explorer を使用して、TLS 1.0 と TLS 1.1 が無効にされた後に、Skype for Business Server 2015 から Web サービスへの TLS 接続をテストできます。

1. 起動Internet Explorer。
2. [**ツールインターネット オプション**  >  **] を選択します**。
3. [詳細設定] **タブを選択** します。
4. [ **設定] で**、一番下までスクロールします。
5. TLS 1.0、TLS 1.1、および TLS 1.2 が有効になっているか確認します。
6. SfB 2015 プールの内部 Web サービス URL を参照します (正常に接続する必要があります)。
7. サーバーに戻りInternet Explorer **TLS 1.2** のみを使用するオプションを無効にします。
8. SfB 2015 プールの内部 Web サービス URL を再び参照します (接続に失敗する必要があります)。

![インターネット オプション](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a>高度な展開シナリオ

Skype for Business Server 2015 で TLS 1.2 をサポートするには依存関係の前提条件がいくつか必要なので、TLS 1.0 と 1.1 が無効になっているシステムでは RTM メディアからのインストールが失敗します。

**環境内で TLS 1.0 および 1.1 を使用した場合の新しい Standard Edition サーバーまたは Enterprise Edition プールの展開は無効になっています。**

**オプション 1:**[SmartSetup を使用します](../../deploy/install/install-skype-for-business-server.md)。 SmartSetup は今後の CU で更新された SQL バイナリに対応するように更新中であり、この記事は今後更新される予定です。

**オプション 2:** ローカル サーバー インスタンスのSQL (RTCLOCAL および LYNCLOCAL)

1. Express 2014 SP2 (SQL) をダウンロードし、FE SQLEXPR_x64.exeフォルダーにコピーします。 たとえば、フォルダー パス <SQL_FOLDER_PATH>。
2. PowerShell またはコマンド プロンプトを起動し、<SQL_FOLDER_PATH ファイルに>。
3. 次のコマンドを実行して、SQL RTCLOCAL インスタンスを作成します。 処理が完了SQLEXPR_x64.exe、次の処理に進みます。

    SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati
1. 以下のコマンドを実行SQL LYNCLOCAL サービス インスタンスを作成します。 次の手順SQLEXPR_x64.exeに進む前に、次の手順が完了するまで待ちます。

    SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic
1. Skype for Business Server 2015 RTM セットアッププログラムを実行します。
2. 上記の前提条件セクションの残りの手順に従います。

**オプション 3:** 次のように、ローカル インストール メディア ディレクトリ内のバイナリを手動で置き換える場合があります。

1. [Skype for Business Server の前提条件のインストール](../../deploy/install/install-prerequisites.md)  
2. .NET 4.7 をインストールします。 
      - **注:** Skype for Business Server 2015 CU5 (6.0.9319.281) で .NET 4.7 のサポートを初めて導入しました。 したがって、次の手順では、メイン インストールの前にコア コンポーネントを更新します。
      - ダウンロード: https://www.microsoft.com/download/details.aspx?id=55167 . 
      - リファレンス: [Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)の展開前にインストールする必要があるソフトウェア
3. ISO ファイル/フォルダーをコピーする: 
    - Skype for Business Server 2015 ISO が接続されている場合は、添付されているドライブのルート ディレクトリを開きます (例: D: \) エクスプローラーで)。
    - すべてのフォルダーとファイルをローカル ディスク上のフォルダー (例: C:\SkypeForBusiness2015ISO) にコピーします。
    - **注:** コンポーネントをインストールする前に、TLS 1.2 のサポートのために一部のファイルを更新する必要があります。
4. MSI/EXE パッケージを置き換える: 
    - ローカル コンピューター上のインストール メディアの /Setup/amd64/ フォルダーにある既存の MSI パッケージと EXE パッケージを置き換える。
    - SQL 2014 SP2 Express: https://www.microsoft.com/download/details.aspx?id=53167 
        - ローカル コンピューター SQLEXPR_x64名前を変更し、インストール メディアの Setup/amd64/ フォルダーにある既存のファイルを置き換える。
    - SQL クライアント: https://www.microsoft.com/download/details.aspx?id=50402 
        - **注:** 必要に応じて名前を変更してsqlncli.msiし、インストール メディアの Setup/amd64/ フォルダーに存在する既存のファイルを置き換える必要があります。
    - SQL管理オブジェクト: https://www.microsoft.com/download/details.aspx?id=53164 
        - **注:** フィーチャー パックには、ダウンロードできるアイテムが多く含まれています。 ダウンロードのみを選択SharedManagementObjects.msiします。
        - **注:** インストール メディアの Setup/amd64/ フォルダーに存在する既存のファイルを置き換える。
    - SQL CLR 型: https://www.microsoft.com/download/details.aspx?id=53164 
        - **注:** フィーチャー パックには、ダウンロードできるアイテムが多く含まれています。 Select to download CQLSysClrTypes.msi only
        - **注**: インストール メディアの Setup/amd64/ フォルダーに存在する既存のファイルを置き換える。
5. コア コンポーネントをインストールします。 
    - インストール Setup.exe Setup/amd64/ フォルダーからこのコマンドを実行します。 指示に従ってコア コンポーネントをインストールする
    - コア コンポーネントを閉じます。
6. コア コンポーネントの更新: 
    - Skype for Business Update インストーラーをダウンロードします。
    - インストーラーを実行してコア コンポーネントを更新し、パフォーマンス カウンターをインストールします。
    - **注:** CU6HF2 のリリースの現在、自動更新機能は CU6 までしかインストールされなに。 したがって、コア コンポーネントを 6.0.9319.516 に更新するには、アップデータツールを個別に実行する必要があります。
    - リファレンス: https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015
7. 管理ツールをインストールする (オプション): 
    - これにより、更新されたファイルを使用して Microsoft SQL Server 2012 Native Client、SQL Server 2014 Management Objects (x64)、および Microsoft System CLR Types for SQL Server 2014 (x64) がインストールされます。 また、Skype for Business Server 2015 トポロジ ビルダーとコントロール パネルは、ローカル コンピューターで使用できます。
8. ローカル構成ストアのインストール (手順 1): 
     - 展開ウィザードを開き、[Skype for Business Server システムのインストールまたは更新] をクリックし、[ステップ 1: ローカル構成ストアのインストール] で [実行] をクリックします。
     - [ローカル **構成ストア** の **インストール] ダイアログ ボックスで [次へ** ] をクリックします。
     ![[ローカル構成ストアのインストール] ダイアログ ボックス](../../media/local-configuration-store.png)
     - 結果を確認し、タスクの状態が完了した状態を確認します。 [ログの表示] をクリックして、結果のログ ファイル **を確認します**。
     ![タスクの状態が完了として表示される](../../media/local-configuration-task-completed.png)
     - **[完了]** をクリックします。
9. Skype for Business Server コンポーネントをセットアップまたは削除する (手順 2):
    - 展開ウィザードを開き **、[Skype for Business Server システム** のインストールまたは更新] をクリックし、[ステップ 2: Skype for Business Server コンポーネントのセットアップまたは削除] で [実行] をクリックします。
    - **[Skype** for Business Server コンポーネントのセットアップ] ダイアログ ボックスで [次へ] をクリックします。
    ![[Skype for Business Server コンポーネントのセットアップ] ウィンドウ](../../media/set-up-skype-for-business-server-components-window.png)
    - ログの表示を使用してログを確認し、セットアップが問題なく完了したと確認します。 
    - **[完了]** をクリックします。
10. 必要に応じて追加のインストールと構成を続行します (この時点で通常のインストール手順を再開できます)。
