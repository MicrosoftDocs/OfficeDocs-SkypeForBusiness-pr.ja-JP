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
description: 環境で TLS 1.0 と 1.1 を無効にする準備と実装を行います。
ms.openlocfilehash: b07b9b5319b858a20a8073de8c6a37dd4d3299ec
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103213"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 で TLS 1.0/1.1 を無効にする

この記事では、環境で TLS 1.0 と 1.1 を無効にする準備と実装に役立ちます。 このプロセスには、広範な計画と準備が必要です。 組織で TLS 1.0 と 1.1 を無効にする計画を立て、この記事のすべての情報を慎重に確認してください。 TLS 1.0/1.1 を無効にすることで影響を受けかねない多くの外部依存関係と接続条件があります。そのため、広範な計画とテストが保証されます。

- [背景とスコープ](#background-and-scope)
- [前提条件とプロセス](#prerequisites-and-process)
- [高度な展開シナリオ](#advanced-deployment-scenarios)

## <a name="background-and-scope"></a>背景とスコープ

TLS 1.0 および 1.1 を提供するための主要なドライバーは、Skype for Business Server オンプレミスのサポートを無効にしているのが、Payment Card Industry (PCI) セキュリティ標準評議会と連邦情報処理標準の要件です。 PCI 要件の詳細については、こちらを参照 [してください](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls)。  Microsoft は、組織がこれらの要件または他の要件を遵守する必要があるかどうかに関するガイダンスを提供できません。 環境で TLS 1.0 および/または 1.1 を無効にする必要があるかどうかを判断する必要があります。

Microsoft は、ここで利用できる TLS に関するホワイト ペーパーを作成 [しました](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)。また、この Exchange ブログで利用できる背景の読み取りも [推奨します](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)。

## <a name="supportability-scope"></a>サポートの範囲

*スコープ* は、サポートの境界を参照します。 *完全にテストされ* 、サポートされているということは、リストされている製品バージョンの TLS 1.0 と 1.1 の無効化を完全にサポートし、テスト済みです。 *現在調査中の場合は* 、その情報が必要です。これらの製品を TLS 無効化のサポートの範囲に含め、積極的に調査しています。 *スコープ外の場合* 、これらの製品バージョンは TLS 1.0 または 1.1 の無効化をサポートしていないので、機能しません。ただし、例外が示されています。

### <a name="fully-tested-and-supported-servers"></a>完全にテストされ、サポートされているサーバー

- Skype for Business Server 2019 CU1 17.0.2046.123 (2019 年 6 月) 以上
- Skype for Business Server 2015 CU9 6.0.9319.548 (2019 年 5 月) 以上の Windows Server 2012 (KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) 以上の更新プログラムを使用)、2012 R2 または 2016。
- 一方でアップグレードされた Skype for Business Server 2015(CU9 6.0.9319.548 (2019 年 5 月) 以上の Windows Server 2008 R2、2012 (KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) または更新プログラムの代用)、または 2012 R2。
- Exchange Connectivity and Outlook Web App 2010 SP3 RU19 Exchange Server 2010 SP3 RU19 以上の場合のガイダンス[](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)
- Skype for Business Server 2015 CU6 HF2 以上の存続可能ブランチ アプライアンス (SBA) (適切な更新プログラムがパッケージ化され、アプライアンスで使用可能にされたとベンダーに確認してください)
- Skype for Business Server 2015 CU6 HF2 以上の存続可能ブランチ サーバー (SBS)
- Lync Server 2013 **Edge Role Only**,これは、エッジ の役割が Windows Fabric 1.0 に依存していないためです。

### <a name="fully-tested-and-supported-clients"></a>完全にテストされ、サポートされているクライアント

- Lync 2013 (Skype for Business) デスクトップ クライアント、MSI、C2R (Basic [15.0.5023.1000 以上を含む](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334))
- Skype for Business 2016 デスクトップ クライアント、MSI [16.0.4678.1000](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323)以上 (Basic を含む)
- Skype for Business 2016 Click to Run Require the [April 2018](/officeupdates/release-notes-office365-proplus) Updates: 
    - 月次およびSemi-Annual対象、16 \. 0 \. 9126 \. 2152 以上
    - Semi-Annualおよび遅延チャネル、16 \. 0 \. 8431 \. 2242 以上
- Skype for Business on Mac 16.15 以上
- Skype for Business for iOS および Android 6.19 以上
- Microsoft Teams Rooms (以前は Skype Room System V2 SRS V2) 4.0.64.0 (2018 年 12 月) 以上
- KB4499162 (2019 年 5 月、OS ビルド 15063.1835) 以上に基づくチーム エディションの Surface Hub 更新プログラム
- Skype Web App 2015 CU6 HF2 以上 (サーバーに含む)

### <a name="currently-being-investigated"></a>現在調査中

- 通話品質ダッシュボード (TLS 1.0、1.1 が無効にされた後の新しいインストールは、以下を参照)*
 
### <a name="out-of-scope"></a>対象外

ただし、以下の製品は TLS 1.0/1.1 ではサポートを無効にし、TLS 1.0 と 1.1 が無効になっている環境では機能しません。 つまり、スコープ外のサーバーまたはクライアントを引き続き使用する場合は、Skype for Business Server オンプレミス展開の任意の場所で TLS 1.0/1.1 を無効にする必要がある場合は、これらを更新または削除する必要があります。

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
- クラウド コネクタ エディション (CCE)
- Skype for Business for Windows Phone

### <a name="exceptions"></a>例外

#### <a name="lync-server-2013"></a>Lync Server 2013

Lync Server 2013 は、Windows Fabric バージョン 1.0 に依存します。  Lync Server 2013 の設計フェーズでは、レプリケーション、高可用性、フォールト トレランスを実現するために、魅力的で新しい分散アーキテクチャとして Windows Fabric 1.0 が選択されました。  時間がたつ間に、Skype for Business Server と Windows Fabric の両方が、この共同アーキテクチャを大幅に改善し、以降のバージョンでは大幅に再設計されました。  現在の Skype for Business 2015 Server では、たとえば Windows Fabric 3.0 が使用されます。

残念ながら、Windows Fabric 1.0 **では TLS 1.2 はサポートされていません。 ただし、LYNC Server 2013 を更新して TLS 1.2** で動作します。 これは、Lync Server 2013 の次の累積的な更新プログラムに含まれる予定です。  TLS 1.2 のサポートを提供して、共存在、移行、フェデレーション、ハイブリッドのシナリオを有効にします。

組織で TLS 1.0 と 1.1 を無効にする必要がある場合に、現在 Lync Server 2013 を使用している場合は、計画プロセスを開始することをお勧めします。計画プロセスを開始すると、一時アップグレードまたはサイド バイ サイド移行 (新しいプール、ユーザーの移動) が Skype for Business Server 2015 以上になる可能性があります。  または、Skype for Business Online への移行を加速する必要がある場合があります。

#### <a name="call-quality-dashboard"></a>通話品質ダッシュボード

オンプレミス通話品質ダッシュボードは、現在、新しいインストール時 (オンプレミス環境への初回インストール) 中に TLS 1.0 に依存しています。  現在、この問題を調査中であり、近い将来に修正プログラムをリリースする予定です。  CQD のインストールと TLS 1.0 の無効化を計画している場合は、最初に CQD インストールを完了してから、TLS 1.0 の無効化を続行することをお勧めします。

#### <a name="skype-for-business-sdn-manager"></a>Skype for Business SDN Manager

データベースを使用する Skype for Business SDN Manager SQL、新しいインストール時に TLS 1.0 に依存します。 SQL データベースを使用して Skype for Business SDN Manager をインストールし、TLS 1.0 も無効にする場合は、まず Skype for Business SDN Manager を完了してから、TLS 1.0 の無効化を続行することをお勧めします。 インストール前に TLS 1.0 が無効になっている場合は、Skype for Business SDN Manager SQL データベースのホストに使用される SQL Server バックエンド サーバーで TLS 1.0 を一時的に有効にする必要があります。

#### <a name="third-party-devices"></a>サード パーティ製デバイス

3PIP 電話、ビデオ会議、リバース プロキシ、ロード バランサーなどのサード パーティ製デバイスでは、TLS 1.2 のサポートを検証し、慎重にテストし、必要に応じてベンダーに問い合わせてください。

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a>エッジ サーバーで TLS 1.0/1.1 を無効にする場合のフェデレーションに関する考慮事項

TLS 1.0/1.1 をエッジ サーバーで無効にした場合の影響を慎重に計画し、検討する必要があります。  TLS 1.0 と 1.1 が無効になったら、他の組織が組織とフェデレーションできなくなった場合があります。

パッチ適用されていない (SfB 2015、Lync 2013) 以前の (2010 年) 外部システムとの下位互換性を維持するために、エッジ サーバーで TLS 1.0/1.1 を有効に保つ場合があります。

Microsoft は、エッジ ネットワーク (または任意のネットワーク) が PCI 標準に該当するかどうかに関するアドバイスや推奨事項を提供できません。個々の会社によって決定される必要があります。

Skype for Business Online は現在 TLS 1.2 に対応しています。そのため、ハイブリッド/オンラインとのフェデレーションへの影響は期待されません。

PIC (パブリック IM Connectivity) から Skype コンシューマー サービスへ: TLS 1.0/1.1 を無効にして [Skype Connectivity](../../deploy/deploy-skype-connectivity.md)に影響を与える可能性はありません。Microsoft PIC ゲートウェイは既に TLS 1.2 に対応しています。

## <a name="prerequisites-and-process"></a>前提条件とプロセス

上記の場合を除き、TLS 1.0 と 1.1 が無効になった後は、スコープ外のサーバーが無効になり、クライアントとデバイスが正常に機能しなくなるか、または全く機能しなくなる。 これは、Microsoft からの更新されたガイダンスを一時停止して待つ必要がある場合があります。 すべての要件を満たしていることを確認し、ギャップに対処する計画を立てしたら、続行します。

高レベルでは、Skype for Business Server 2019 はインストール時に手順を実行する準備ができましたが、Skype for Business Server 2015 では CU9 のインストール、.NET および SQL への前提条件更新プログラムの適用、前提条件のレジストリ キーの展開、および最後に別の OS 構成更新プログラムの展開 (レジストリ ファイルのインポートによる TLS 1.0 と 1.1 の無効化) が必要になります。 環境内の任意のサーバーで TLS 1.0 と 1.1 を無効にする前に、Skype for Business Server 2015 CU6 HF2 を含むすべての前提条件のインストールを完了することが非常に重要です。 エッジの役割やバックエンドを含むすべての Skype for Business サーバー SQL更新プログラムが必要です。 また、サポートされている (スコープ内の) すべてのクライアントが必要な最小バージョンに更新されている必要があります。 管理ワークステーションも更新することを忘れないでください。

Skype for Business サーバーをアップグレードする場合は、「インサイド アウト」の通常の操作順序に従います。 ディレクター プール、常設チャット、ペアリングされたプールは、通常と同じ方法で処理します。 アップグレードの順序と方法については、ここで[説明](topology.md)[します](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)。

### <a name="high-level-process"></a>高レベルのプロセス

1. 実稼働サーバーを構成する前に、ラボのすべての手順をテストします。
2. 更新する個々のサーバーごとに、エクスポートされたレジストリのコピーをバックアップして保持します。 サーバー間でレジストリを共有することはできません。コンピューター ベースの一意のキーが含まれる。
3. すべての Skype for Business 2015 サーバーを CU9 以上にアップグレードします。 Skype for Business Server 2019 の場合は、CU1 以上にアップグレードします。
4. すべての前提条件をすべてのサーバーにインストールします。
5. 前提条件のレジストリ キーを展開します。
6. スコープ内のすべてのクライアントが更新されます。
7. レジストリ インポートを使用して TLS 1.0 と 1.1 を無効にします。
8. ワークロードが期待通り機能しているのを検証します。
    - 問題が発生した場合は、トラブルシューティングと解決、または
    - 手順 2 からレジストリを復元し、TLS 1.0 と 1.1 を再び有効にする
9. TLS 1.2 だけが使用されているのを検証します。

### <a name="install-prerequisites-to-all-servers"></a>すべてのサーバーに前提条件をインストールする

Skype for Business Server 2015 展開のオペレーティング システム レベルで TLS 1.0 と 1.1 を無効にする前に、広範な依存関係の更新が必要です。 TLS 1.2 をサポートできる最小バージョンを次に示します。 TLS 1.0 と 1.1 の無効化を開始する前に、環境内のすべての Skype for Business サーバーに前提条件の更新プログラムを展開します。

- Skype for Business Server 2015 CU9 6.0.9319.548 (2019 年 5 月) 以上
- .NET Frameworkで SchUseStrongCrypto が有効になっている[4.7](https://www.microsoft.com/download/details.aspx?id=55167)以上の場合 (以下に提供)
- SQL Skype for Business 2015 サーバーとバックエンドで更新する必要があります。 まず、Enterprise Edition Pool SQLバックエンド、次にそれぞれの FEs を更新します。 
    - [SQL Server 2014 SP1 + CU5、](https://support.microsoft.com/help/3130926)またはより高い / SQL Server 2012 SP2 + CU16 以上 / [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014)、またはより高い / SQL Server SP2
     - [SQL Server 2012 年のネイティブ SQL Server クライアント](https://www.microsoft.com/download/details.aspx?id=50402)
     - [Microsoft ODBC Driver 11 for SQL Server](https://www.microsoft.com/download/details.aspx?id=36434)以上
     - [2014 SP2 の共有管理オブジェクトSQL Server 2014 SP2](https://www.microsoft.com/download/details.aspx?id=53164)
     - [SQLSysClrTypes for SQL server 2014 SP2](https://www.microsoft.com/download/details.aspx?id=42295)

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a>運用の推奨順序で前提条件をインストールするための基本的な手順

1. Skype for Business Server CU9 更新プログラムをすべてのサーバーにインストールします。 
    1. アップデータを使用してコンポーネントに更新プログラムをインストールします。
    2. 文書化された手順に従ってデータベースを更新します。 Skype for Business Server 2015 の場合は、「KB [3061064」を参照してください](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)。
    3. 他の変更を進む前に、展開で製品の機能を検証します。
2. .NET 4.7 オフライン インストーラーをダウンロードします。 
    1. リファレンス: [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)
    2. フロント エンド サーバーで Skype for Business Server 2015 サービスが停止している必要があります。
    3. リファレンス: [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)
    4. Ex (Standard Edition): ```Stop-CsWindowsService```
    5. Ex (Enterprise Edition): ```Invoke-CsComputerFailover```
    6. インストーラー パッケージを実行します。
    7. サーバーを再起動します。
3. すべてのSQL Express 2014 を更新します。 
    1. リファレンス: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)
    2. ダウンロード SQL 2014 SP2 
        - リファレンス: [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)
    3. サーバー上のフォルダーにインストール メディアをコピーする (例: C:\01_2014SqlSp2)
    4. フロント エンド サーバーで Skype for Business Server 2015 サービスが停止する 
        - Ex (Standard Edition): ```Stop-CsWindowsService```
        - Ex (Enterprise Edition): ```Invoke-CsComputerFailover```
    5. 管理コマンド プロンプトを開き、インストール済みのすべてのコンポーネントとインスタンスをアップグレードする 
        - 例: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances
4. ネイティブ クライアントSQL更新します。 
    1. リファレンス: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server) .
    2. からダウンロードする [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)
    3. フロント エンド サーバーで Skype for Business Server 2015 サービスが停止している必要があります。 
        - Ex (Standard Edition): ```Stop-CsWindowsServices```
        - Ex (Enterprise Edition): ```Invoke-CsComputerFailover```
    4. インストールされているSQLの実行を停止する 
        - 例: ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```
        - 例: ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```
        - Ex (Standard Edition のみ): ```Get-Service 'MSSQL$RTC' | Stop-Service```
    5. 更新プログラムをインストールします。
5. TLS 1.2 (KB [3135244)](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)のサポートSQL Server ODBC Driver 11 を更新します。
    1. ODBC [Driver 11 for SQL Server - Windows をダウンロードします](https://www.microsoft.com/download/confirmation.aspx?id=36434)。
    2. フロント エンド サーバーで Skype for Business Server 2015 サービスが停止している必要があります。
        - 例 (Standard Edition): ```Stop-CsWindowsService```
        - 例 (Enterprise Edition): ```Invoke-CsComputerFailover```
    3. 更新プログラムをインストールします。
6. 前提条件のレジストリ キーを展開します。

### <a name="pre-requisite-registry-keys"></a>前提条件のレジストリ キー

次のテストをメモ帳にコピー/貼り付け、TLSPreReq.reg または選択した名前の名前を変更してからインポートします。

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

Enterprise Edition SQLバック エンドの場合、前提条件と TLS の無効化は、すべての更新プログラムまたは OS 更新プログラムSQL扱う必要があります。参照: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](./patch-or-update-a-back-end-or-standard-edition-server.md)

必須アプリケーションと TLS 無効化の両方の手順を組み合わせることができますが、すべての前提条件を適用してから、オペレーティング システム レベルで TLS 1.0 と 1.1 を無効にすることを強く推奨します。 ベスト プラクティスの方法は、すべての前提条件を展開し、すべてのワークロードが正しく正常に機能していることを検証し、後で TLS 1.0/1.1 を無効にすることで環境を準備します。

### <a name="disable-tls-10-and-11-via-registry-import"></a>レジストリ インポートを使用して TLS 1.0 および 1.1 を無効にする

次の手順に進む前に、すべての前提条件を完了し *、Skype for Business Servers を更新してください*。

次のテキストをメモ帳ファイルにコピーし **、TLSDisable.reg の名前を変更します**。

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

TLS 1.0 および 1.1 を無効にする各サーバーに .reg ファイルをインポートします。 サーバーを再起動します。 サービスがオンラインに戻ったら、次のサーバーに移動します。 Enterprise Edition プールのアプローチは、OS 更新プログラムと同じです。

ここでは、TLS 1.0 と 1.1 を無効にする以上の機能を行っていることに気付いた可能性があります。 上記のように、暗号スイートの再注文と、いくつかの古い弱暗号の無効化をサポートしています。 Skype for Business Server で SCHANNEL と Crypto API に対するこれらの変更を公式にサポートしたのはこれが初めてであり、この時点でサポートおよびテストした変更は、これらの変更のみである点に注意することが重要です。 今後、追加の構成を検討する場合がありますが、今のところ、実装内のレジストリ インポート ファイルは変更しない必要があります。

### <a name="validate-that-workloads-are-functioning-as-expected"></a>ワークロードが期待通り機能しているのを検証する

環境で TLS 1.0 と 1.1 を無効にしたら、IM & Presence、P2P 呼び出し、エンタープライズ VoIP など、すべての主要なワークロードが期待通り機能している必要があります。

**使用されている TLS 1.2 のみを検証する**

セキュリティ チームに Skype for Business トラフィックの新しい監査を実行して、古いプロトコル TLS 1.0 と 1.1 が使用されなくなったか確認します。

または、Internet Explorer を使用して、TLS 1.0 および TLS 1.1 が無効にされた後、Skype for Business Server 2015 から Web サービスへの TLS 接続をテストできます。

1. 起動Internet Explorer。
2. [ツール **インターネット**  >  **オプション] を選択します**。
3. [**詳細設定**] タブを選択します。
4. [設定 **] の** 下までスクロールします。
5. TLS 1.0、TLS 1.1、および TLS 1.2 が有効になっているか確認します。
6. SfB 2015 プールの内部 Web サービス URL を参照します (正常に接続する必要があります)。
7. [TLS **1.2** Internet Explorerを使用する] オプションを無効にします。
8. SfB 2015 プールの内部 Web サービス URL を再度参照します (接続に失敗する必要があります)。

![インターネット オプション](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a>高度な展開シナリオ

Skype for Business Server 2015 で TLS 1.2 をサポートするには、いくつかの依存関係の前提条件が必要なので、TLS 1.0 および 1.1 が無効になっているシステムでは RTM メディアからのインストールが失敗します。

**環境で TLS 1.0 と 1.1 が無効にされた後に、新しい Standard Edition サーバーまたは Enterprise Edition プールを展開します。**

**オプション 1:**[SmartSetup を使用します](../../deploy/install/install-skype-for-business-server.md)。 更新されたバイナリを将来の CU に対応SQL SmartSetup を更新中であり、今後この記事を更新する予定です。

**オプション 2:** ローカル インスタンスの事前インストールSQL (RTCLOCAL および LYNCLOCAL)

1. Express 2014 SP2 (SQL) を FE のローカル フォルダーにダウンロードSQLEXPR_x64.exeコピーします。 たとえば、フォルダー パスが<SQL_FOLDER_PATH>。
2. PowerShell またはコマンド プロンプトを起動し、<SQL_FOLDER_PATH ファイルに>。
3. 以下のコマンドを実行してSQL RTCLOCAL インスタンスを作成します。 次の処理がSQLEXPR_x64.exeするまで待ちます。

    SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati
1. 以下のコマンドを実行SQL LYNCLOCAL サーバー インスタンスを作成します。 次の手順SQLEXPR_x64.exe進む前に、次の手順が完了するまで待ちます。

    SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic
1. Skype for Business Server 2015 RTM セットアップを実行します。
2. 上記の前提条件セクションの残りの手順に従います。

**オプション 3:** 次のように、ローカル インストール メディア ディレクトリのバイナリを手動で置き換えすることもできます。

1. [Skype for Business Server の前提条件をインストールする](../../deploy/install/install-prerequisites.md)  
2. .NET 4.7 をインストールします。 
      - **注:** 最初に、Skype for Business Server 2015 CU5 (6.0.9319.281) で .NET 4.7 のサポートが導入されました。 したがって、以下の後の手順では、メイン インストールの前にコア コンポーネントを更新します。
      - ダウンロード: https://www.microsoft.com/download/details.aspx?id=55167 . 
      - リファレンス: [Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)展開の前にインストールする必要があるソフトウェア
3. ISO ファイル/フォルダーのコピー: 
    - Skype for Business Server 2015 ISO が接続されている場合は、添付されているドライブのルート ディレクトリ (エクスプローラーで Ex: D: ) を \) 開きます。
    - すべてのフォルダーとファイルをローカル ディスク上のフォルダーにコピーします (例: C:\SkypeForBusiness2015ISO)。
    - **注:** コンポーネントをインストールする前に、TLS 1.2 のサポートのために一部のファイルを更新する必要があります。
4. MSI/EXE パッケージを置き換える: 
    - ローカル コンピューター上のインストール メディアの /Setup/amd64/ フォルダーにある既存の MSI パッケージと EXE パッケージを置き換える。
    - SQL 2014 SP2 Express: https://www.microsoft.com/download/details.aspx?id=53167 
        - ローカル コンピューター SQLEXPR_x64に名前を変更し、インストール メディアの Setup/amd64/フォルダーにある既存のファイルを置き換える。
    - SQLネイティブ クライアント: https://www.microsoft.com/download/details.aspx?id=50402 
        - **注:** 必要に応じて、sqlncli.msi名前を変更し、インストール メディアの Setup/amd64/フォルダーに存在する既存のファイルを置き換える。
    - SQL管理オブジェクト: https://www.microsoft.com/download/details.aspx?id=53164 
        - **注:** フィーチャー パックには、ダウンロードできるアイテムが多く含まれます。 [ダウンロードのみ] をSharedManagementObjects.msiします。
        - **注:** インストール メディアの Setup/amd64/フォルダーに存在する既存のファイルを置き換える。
    - SQL CLR 型: https://www.microsoft.com/download/details.aspx?id=53164 
        - **注:** フィーチャー パックには、ダウンロードできるアイテムが多く含まれます。 [選択] をクリックしてCQLSysClrTypes.msiのみ
        - **注**: インストール メディアの Setup/amd64/フォルダーに存在する既存のファイルを置き換える。
5. コア コンポーネントのインストール: 
    - インストール メディアSetup.exeセットアップ/amd64/フォルダーからファイルを実行します。 手順に従ってコア コンポーネントをインストールする
    - コア コンポーネントを閉じます。
6. コア コンポーネントの更新: 
    - Skype for Business Update インストーラーをダウンロードします。
    - インストーラーを実行してコア コンポーネントを更新し、パフォーマンス カウンターをインストールします。
    - **注:** CU6HF2 のリリースの現在、自動更新機能は現在 CU6 までインストールされます。 したがって、コア コンポーネントを 6.0.9319.516 に更新するには、アップデータを個別に実行する必要があります。
    - リファレンス: https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015
7. 管理ツールのインストール (オプション): 
    - これにより、Microsoft SQL Server 2012 ネイティブ クライアント、SQL Server 2014 管理オブジェクト (x64)、および更新されたファイルを使用して microsoft System CLR Types for SQL Server 2014 (x64) がインストールされます。 さらに、Skype for Business Server 2015 トポロジ ビルダーとコントロール パネルは、ローカル コンピューターで使用できます。
8. ローカル構成ストアのインストール (手順 1): 
     - 展開ウィザードを開き、[Skype for Business Server System のインストールまたは更新] をクリックし、[手順 1: ローカル構成ストアのインストール] で [実行] をクリックします。
     - [ローカル **構成ストアの** インストール **] ダイアログ ボックスの [次へ** ] をクリックします。
     ![[ローカル構成ストアのインストール] ダイアログ ボックス](../../media/local-configuration-store.png)
     - 結果を確認し、[タスクの状態] が [完了] に設定されています。 [ログの表示] をクリックして、結果のログ ファイル **を確認します**。
     ![タスクの状態が [完了] と表示される](../../media/local-configuration-task-completed.png)
     - **[完了]** をクリックします。
9. Skype for Business Server コンポーネントのセットアップまたは削除 (手順 2):
    - 展開ウィザードを開き **、[Skype for Business Server** System のインストールまたは更新] をクリックし、[手順 2: Skype for Business Server コンポーネントのセットアップまたは削除] で [実行] をクリックします。
    - [Skype **for** Business Server コンポーネントのセットアップ] ダイアログ ボックスの [次へ] をクリックします。
    ![[Skype for Business Server コンポーネントのセットアップ] ウィンドウ](../../media/set-up-skype-for-business-server-components-window.png)
    - [ログの表示] を使用してログを確認し、問題なくセットアップが完了したと検証します。 
    - **[完了]** をクリックします。
10. 必要に応じて追加のインストールと構成を続行します (この時点で通常のインストール手順を再開できます)。