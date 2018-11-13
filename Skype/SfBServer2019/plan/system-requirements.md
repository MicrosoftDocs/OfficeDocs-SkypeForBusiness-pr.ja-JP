---
title: ビジネス サーバー 2019 Skype のシステム要件
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: '概要: ビジネス サーバー 2019 サーバーおよびドメイン インフラストラクチャをこのトピックでは、Skype を準備します。 ハードウェア、OS、データベース、ソフトウェア、すべてのシステム要件と推奨事項は、DNS の証明書と、ファイル共有、および Active Directory については、ここでは正常にインストールし、サーバー ファームの展開を行うには。'
ms.openlocfilehash: c7064f4d1c8136cf714d784fd1985efd0f21c979
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2018
ms.locfileid: "26296156"
---
# <a name="system-requirements-for-skype-for-business-server-2019"></a>ビジネス サーバー 2019 Skype のシステム要件
 
**の概要:** ビジネス サーバー 2019 のこのトピックに Skype をインストールする準備をします。 ハードウェア、OS、ソフトウェア、データベース、証明書、作業中のディレクトリ、DNS、および fileshares は、ここで説明されます。 すべてのシステム要件と推奨事項は、ここで正常にインストールし、サーバー ファームの展開を確実にします。
  
ご想像のとおり、Skype をビジネス サーバー 2019 の展開を開始する前にいくつかの準備があります。 この記事では次の計画について、順を追って説明します。
  
- [ハードウェア](system-requirements.md#Hardware)
  
- [オペレーティング ・ システム](system-requirements.md#OS)
  
- [ソフトウェア](system-requirements.md#Software)

- [バックエンド SQL データベース](system-requirements.md#DBs)
  
- [Active Directory](system-requirements.md#AD)
  
- [ドメイン ネーム システム (DNS)](system-requirements.md#DNS)
  
- [証明書](system-requirements.md#Certs)
  
- [ファイル共有](system-requirements.md#Fileshare)

  
## <a name="hardware-for-skype-for-business-server-2019"></a>ビジネス サーバー 2019 の Skype のハードウェア
<a name="Hardware"> </a>

ダウン、トポロジがある場合、ない場合は、[トポロジの基本的な](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md)ビジネス サーバー 2019 の Skype のトピックを確認できます) した後は、サーバーについて考える時間が。 Skype ビジネス サーバー 2019 サーバーは、64 ビットのハードウェアを必要とします。 推奨されるハードウェアをこの後に示します。 これらの要件、操作は、最適なパフォーマンスのために必要な要件を反映します。 状況に応じて、これを超えるものが必要であるかどうかの判断に役立つ、処理能力の計画に関するドキュメントも用意されています。
  
Standard Edition サーバーのハードウェアをお勧めします。

|**ハードウェア コンポーネント**|**推奨**|
|:-----|:-----|
|CPU  <br/> |インテル Xeon E5-2673 v3 のデュアル プロセッサ、6 コア、2.4 ghz (ギガヘルツ) またはそれ以上です。  <br/> サーバー 2019 のビジネス ロールの Skype は、Intel Itanium プロセッサがサポートされていません。  <br/> |
|メモリ  <br/> |32 ギガバイト (GB)  <br/> |
|ディスク  <br/> |次のいずれか:  <br/> •	10,000 RPM のハード ディスク ドライブで 72 GB 以上の空きディスク領域があるものを 8 台以上 (RAID 1 を使用する 2 台のディスクと、RAID 10 を使用する 6 台のディスク)。  <br/> または  <br/> •	10000 RPM の機械的ディスク ドライブ 8 台と同じ空き領域および同等のパフォーマンスを持つソリッド ステート ドライブ (SSD)。  <br/> |
|ネットワーク  <br/> |1 Gbps 以上のデュアルポート ネットワーク アダプター 1 つ (2 つのネットワーク アダプターを使用できるが、その場合は 1 つの MAC アドレスと 1 つの IP アドレスのチーミングが必要)。  <br/> デュアルまたはマルチホーム構成では、サーバーをフロント エンド サーバーやバック エンド サーバー、Standard Edition でサポートされて**いません**。 <br/> オペレーティング システムに公開されていない、監視し、サーバー ハードウェアの管理に使用されている限り、帯域外の管理システムでは、DRAC、または ILO などを持つことができます。 このシナリオは、マルチ ホーム サーバーの構成要素ではなく、サポートされています。  <br/> |


フロント エンド サーバーおよびバック エンド サーバーのハードウェアを推奨します。
  
|**ハードウェア コンポーネント**|**推奨**|
|:-----|:-----|
|CPU  <br/> |インテル Xeon E5-2673 v3 のデュアル プロセッサ、6 コア、2.4 ghz (ギガヘルツ) またはそれ以上です。 <br/> サーバー 2019 のビジネス ロールの Skype は、Intel Itanium プロセッサがサポートされていません。  <br/> |
|メモリ  <br/> |64 ギガバイト (GB)。  <br/> |
|ディスク  <br/> |次のいずれか:  <br/> •	10,000 RPM のハード ディスク ドライブで 72 GB 以上の空きディスク領域があるものを 8 台以上 (RAID 1 を使用する 2 台のディスクと、RAID 10 を使用する 6 台のディスク)。  <br/> または  <br/> •	10000 RPM の機械的ディスク ドライブ 8 台と同じ空き領域および同等のパフォーマンスを持つソリッド ステート ドライブ (SSD)。  <br/> |
|ネットワーク  <br/> |1 Gbps 以上のデュアルポート ネットワーク アダプター 1 つ (2 つのネットワーク アダプターを使用できるが、その場合は 1 つの MAC アドレスと 1 つの IP アドレスのチーミングが必要)。  <br/> デュアルまたはマルチホーム構成では、サーバーをフロント エンド サーバーやバック エンド サーバー、Standard Edition でサポートされて**いません**。 <br/> オペレーティング システムに公開されていない、監視し、サーバー ハードウェアの管理に使用されている限り、帯域外の管理システムでは、DRAC、または ILO などを持つことができます。 このシナリオは、マルチ ホーム サーバーの構成要素ではなく、サポートされています。  <br/> |
   
エッジ トランスポート サーバー、スタンドアロンの仲介サーバー、およびディレクターのハードウェアを推奨します。
  
|**ハードウェア コンポーネント**|**推奨**|
|:-----|:-----|
|CPU  <br/> |インテル Xeon E5-2673 v3 のデュアル プロセッサ、6 コア、2.4 ghz (ギガヘルツ) またはそれ以上です。  <br/> サーバー 2019 のビジネス ロールの Skype は、Intel Itanium プロセッサがサポートされていません。  <br/> |
|メモリ  <br/> |32 ギガバイトです。  <br/> |
|ディスク  <br/> |次のいずれか:  <br/> •	10,000 RPM のハード ディスク ドライブで 72 GB 以上の空きディスク領域があるものを 4 台以上 (ディスクは 2 x RAID 1 構成である必要がある)。  <br/> または  <br/> •	10000 RPM の機械的ディスク ドライブ 4 台と同じ空き領域および同等のパフォーマンスを持つソリッド ステート ドライブ (SSD)。  <br/> |
|ネットワーク  <br/> |1 Gbps 以上のデュアルポート ネットワーク アダプター 1 つ (2 つのネットワーク アダプターを使用できるが、その場合は 1 つの MAC アドレスと 1 つの IP アドレスのチーミングが必要)。  <br/> デュアルまたはマルチホームの構成は、ビデオの相互運用機能のサーバーやディレクターではサポート**されません**。 <br/> エッジ サーバーには、1 Gbps 以上のデュアルポート ネットワーク アダプターである 2 つのネットワーク インターフェイス (つまり 2 ペア (合計 4 つ) のネットワーク アダプター。この合計 2 つのペアでは、各ペアが 1 つの MAC アドレスと 1 つの IP アドレスでチームになっている) が必要です。  <br/> スタンドアロンの仲介サーバーでは、追加のネットワーク インターフェイス カード (Nic) が特定の PSTN の IP アドレスの構成を許可するのインストールがサポートされています。  <br/> |


> [!NOTE]
> サーバーの役割とは無関係にもお勧めビジネス サーバー 2019 の Skype の次のハードウェア設定 (ハードウェアを購入した、そのためのブランドによって異なる場合がありますこれについては製造元のマニュアルを参照してください)。
> - BIOS 設定は NUMA からフラット設定してください。
> - ハイパー スレッドを有効にします。
> - RSS キューの設定は、キューを 8 に設定してください。

   
## <a name="operating-systems-for-skype-for-business-server-2019"></a>ビジネス サーバー 2019 の Skype のオペレーティング ・ システム
<a name="OS"> </a>

ハードウェアである場合をインストールして正常にビジネス サーバー 2019 の Skype を使用することがあるインストールのオペレーティング システム (OS) にする必要があります。
  
|||
|:-----|:-----|
|Windows Server 2019 <br/> |
|Windows Server 2016 <br/> ||
||
   
ここで記載されているオペレーティング システム以外の場合は正しく機能しないもの再試行してくださいしない Skype のインストールの場合のビジネス サーバー 2019。

> [!NOTE]
> 
> Windows 管理センター 2019年を Windows Server 2019 マシンにインストールする場合が要求をリッスンするポート。 確率、443 番ポートを選択することがありますが、そのマシンのビジネス サーバー 2019 がインストールされて、Skype には Skype をビジネス サーバー 2019 のインストールに必要になるか、またはを選択してください別のポート番号。
> 
>なぜこれに大文字と小文字ですか。 Windows 管理センター 2019年がポート 443 上で実行している、ビジネス コントロール パネルでは、Skype を使用してサーバーに接続することができなくことができません (アドレス帳 Web サービスのサーバーで実行されているすべての内部の web サービスに接続することができます。、自動検出サービス、WebTicket サービスなど)。  実際には、任意の内部の Web サービス URL に接続することはできません。 必要がある場合、またはビジネス サーバー 2019 の Skype のサーバーで Windows 管理センター 2019年を配置する場合は、別のポートを選択してください。
> 

  
## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2019-deployment"></a>サーバー 2019 のビジネスを展開するため、Skype の前にインストールされるソフトウェア
<a name="Software"> </a>

インストールまたはビジネス サーバー 2019 の Skype を実行するサーバーを構成する必要がありますしようとしているものがあります。 これら次のとおり、特定のサーバーの役割の追加の要件を後にします。
  
 **すべてのサーバー。**
  
|**ソフトウェア/役割**|**詳細**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |これらのサーバーのすべての Skype では、Windows PowerShell 3.0 がインストールされている必要があります。  <br/> • はデフォルトでは Windows Server 2016 これをインストールする必要があります。<br/> |
|Microsoft .NET Framework  <br/> |WCF サービスは、インストールした**サーバー マネージャー**で、[Windows 機能としてないダウンロードのために必要な**機能**です。 <br/> • をする必要があります、 **HTTP アクティブ化**のオプションのもがチェックされ、インストールされて、それをチェックする場合は既にインストールされている場合や、この機能をインストールすると、次のようにします。 <br/> ![.NET Framework 4.5 機能の下に [HTTP アクティブ化] オプションが表示されたスクリーンショット](../../SfbServer/media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png) <br/> HTTP アクティブ化をインストールするには、その他のインストールが必要であるという追加のメッセージが表示されても問題はありません。 正常であります。[ok] をクリックし、先に進みします。 得られない場合このポップアップ、これらの要素を既にインストールされているし、先に進みを想定することができます。  <br/> 通常、Microsoft.NET Framework をインストールするは、Windows Server 2016 がインストールされている場合。 Skype ビジネス サーバーは、次の Microsoft.NET Framework のバージョンで動作します。  <br/> • .NET 3.5  <br/> • .NET 4.5  <br/> • .NET 4.6.x  <br/> • .NET 4.7 <br/> |
|メディア ファンデーション  <br/> |Windows サーバーの 2016 の Microsoft メディア Foundation と Windows Media フォーマット ランタイムをインストールします。  <br/> 会議のために使用される、すべてのフロント エンド サーバーと Standard Edition サーバーでは、アナウンスや音楽のコール パーク、アナウンス、および応答グループ アプリケーションを再生する Windows Media オーディオ (.wma) ファイルを実行する、Windows Media フォーマット ランタイムが必要です。  <br/> |
|Windows Identity Foundation  <br/> |ビジネス サーバー 2019 の Skype のサーバーからサーバーへの認証シナリオをサポートするために Windows アイデンティティ基盤の 3.5 が必要です。  <br/> • Windows サーバーの 2016 の物をダウンロードする必要はありません。 **サーバー マネージャー**を開いて、[**役割と機能の追加ウィザード**] に進みます。 [**機能**] セクションの一覧に [**Windows Identity Foundation 3.5**] が表示されています。 オンになっている場合は完了です。 それ以外の場合を選択し、[**次へ**[**インストール**] ボタンに到達します。 <br/> |
|リモート サーバー管理ツール  <br/> |役割管理ツール: AD DS および AD LDS ツール  <br/> |
   
 **フロント エンド サーバーと Standard Edition サーバーも必要があります。**
  
|**ソフトウェア/役割**|**詳細**|
|:-----|:-----|
|インターネット インフォメーション サービス (IIS)  <br/> |選択されている次のモジュールとは、すべてのフロント エンド サーバーとすべての Standard Edition サーバーでは、IIS が必要です。  <br/> • 一般的な HTTP 機能: 既定のドキュメントでは、HTTP エラーの場合は、静的なコンテンツ  <br/> • 状態と診断: HTTP のログ、トレース ログ ツール  <br/> • パフォーマンス: コンテンツの圧縮は静的、動的コンテンツの圧縮  <br/> • セキュリティ: 要求のフィルタ リング、クライアント証明書マッピング認証、Windows 認証  <br/> • アプリケーションの開発: .NET 3.5 の機能拡張、.NET 4.5 の機能拡張、ASP.NET 3.5 ASP.NET 4.5 では、ISAPI 拡張機能、ISAPI フィルター  <br/> • 管理ツール: IIS 管理コンソール、IIS 管理スクリプトおよびツール  <br/> 匿名アクセスが必要なもですが、一覧で選択する場所がないため、IIS をインストールするときに得ることに注意してください。  <br/> |
|Windows Media フォーマット ランタイム  <br/> | Windows サーバーの 2016 の**サーバー マネージャー**で、**メディア ファンデーション**機能をインストールする必要があります。 実際にビジネス サーバー 2019 のインストールには、これは、Skype を起動できますが、インストールを求められることが、ビジネス サーバー 2019 の Skype の前に、サーバーのインストールの再起動を続行し、 事前に行うことをお勧めします。 <br/> |
|Silverlight  <br/> |最新バージョンの Silverlight をインストールすることができます[ここ](https://www.microsoft.com/silverlight/)。  <br/> |
   
作業の簡素化のために、この処理を自動化するサンプル PowerShell スクリプトを次に示します。
  
```
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, Telnet-Client
```

 **ダイレクタが必要もあります。**
  
次のモジュールを選択した IIS:
  
- HTTP 共通機能
    
  - 既定のドキュメント
    
  - HTTP エラー
    
  - 静的コンテンツ
    
- 状態と診断
    
  - HTTP ログ
    
  - ログ ツール
    
  - 追跡
    
- パフォーマンス
    
  - 静的コンテンツ圧縮
    
- セキュリティ
    
  - 要求のフィルタリング
    
  - クライアント証明書マッピング認証
    
  - Windows 認証
    
- アプリケーション開発
    
  - .NET 拡張機能 3.5
    
  - .NET 拡張機能 4.5
    
  - ASP.NET 3.5
    
  - ASP.NET 4.5
    
  - ISAPI 拡張機能
    
  - ISAPI フィルター
    
(ご参考までに場合は、同じモジュールが動的コンテンツの圧縮を使用して、フロント エンド サーバーと Standard Edition サーバーとして設定し、管理ツールは省略)
  
また、同様に役立つ PowerShell コードを次に示します。
  
```
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, Telnet-Client
```

## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2019"></a>ビジネス サーバー 2019 の Skype で動作するバック エンド データベース
<a name="DBs"> </a>

Skype のビジネス サーバー 2019 Standard Edition をインストールすると、SQL Server 2016 Express (64 ビット版) する必要があります。

ビジネス サーバー 2019 のエンタープライズ版の Skype が必要になりますすべての SQL Server では、以下に示す (唯一の 64 ビット エディションの 32 ビット エディションを使用しないでください)。
  
||||
|:-----|:-----|:-----|
|2016年/2017 エンタープライズ (64 ビット版) の Microsoft SQL Server とは、最新の更新プログラム、および AlwaysOn 可用性グループで実行する必要があります。  <br/> ||
 |
   
ここで使用する SQL Server のエディションが表示されない場合は使用できません。
  
> [!NOTE]
> SQL Server レポート サービス サーバーの監視の役割をインストールする必要があります。 
  
### <a name="sql-clustering-and-sql-always-on"></a>SQL のクラスタ リング、および SQL は常にオン

ビジネス サーバー 2019 の Skype で SQL がクラスター化がサポートされているとします。 SQL クラスターを設定する場合は、SQL Server でそれを行います。
  
SQL クラスタ リングはサポートされているアクティブ/パッシブ構成があることを確認します。 他の任意の SQL インスタンスには、パッシブ ノードを共有しません。
  
フェールオーバー クラスタリングでは、次の OS を使用できます。
  
2 ノードの場合:
  
- Microsoft SQL Server 2016年/2017 標準 (64 ビット版) で最新のサービス パックの実行をお勧めします。
    
16 ノードの場合:
  
- 2016年/2017 エンタープライズ (64 ビット版) の Microsoft SQL Server とは、最新のサービス パックの実行をお勧めします。
    
記事、ビジネス サーバー 2019、準備にクラスタ リングを取得するための手順があるため、Skype のクラスタ リングを構成する SQL Server の必要があります。
 
SQL 常にではサポートされており、詳細を読み取ることができます[ビジネス サーバー 2019 の Skype のバック エンド サーバー](../../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md)の高可用性についてです。
  

###  <a name="additional-server-installation-recommendations"></a>追加のサーバーのインストールに関する推奨事項:
  
インストールしてください Microsoft インターネット セキュリティとアクセラレータ (ISA) Server クライアント ソフトウェア、または他の Winsock 複数層サービス プロバイダー (LSP) ソフトウェア (すべてのサードパーティ製のファイアウォールまたはネットワークのアンチ ウイルス検査ソフトウェアはここで指定)フロント エンド サーバーまたはスタンドアロンの仲介サーバーのいずれかです。 不適切なメディアのトラフィックのパフォーマンスは、そのソフトウェアがインストールされているとを確認されています。
  

## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

サーバーおよびサービスの構成データの多くは、ビジネス サーバー 2019 中央管理ストアの Skype に格納されますが、Active Directory にまだ保存されているものがあります。
  
|**Active Directory オブジェクト**|**オブジェクトの種類**|
|:-----|:-----|
|スキーマ拡張  <br/> |ユーザー オブジェクトの拡張  <br/> |
||ビジネス サーバー 2015 と前との下位互換性を維持するために Lync Server 2013 では、Skype の拡張機能がサポートされているバージョン  <br/> |
|データ  <br/> |ユーザーの SIP URI と他のユーザー設定  <br/> |
||(応答グループ アプリケーションや会議アテンダント アプリケーション) などのアプリケーションの連絡先オブジェクト  <br/> |
||下位互換性のために発行されたデータ  <br/> |
||サービス コントロール ポイント (SCP) を中央管理ストアの  <br/> |
||Kerberos 認証アカウント (オプションのコンピューター オブジェクト)  <br/> |
   
### <a name="os-for-domain-controllers"></a>ドメイン コントローラー用の OS

次のドメイン コント ローラー オペレーティング システムを使用することができます。
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
Skype を配置するには、ビジネスのサーバー 2019 の任意のドメインのドメインの機能レベルと Skype を配置するには、ビジネスのサーバー 2019 の任意のフォレストのフォレストの機能レベルは、次のいずれかである必要があります。
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
これらの環境で読み取り専用ドメイン コント ローラーを持つことができますか。 確かに、そこである限りは、書き込み可能なドメイン コント ローラー利用。
  
Skype ビジネス サーバー 2019 の単一ラベルのドメインをサポートしていないことを知っているが重要です。 単一ラベルのドメインがどのようなものかを把握しておいてください。 Contoso.local というラベルの付いたルート ドメインがあれば、十分にそうです。 ルート ドメイン ローカルという名前だけがあれば、作業をすることはしませんし、結果としてサポートされていません。 詳細については、[こちらのサポート技術情報の記事](https://support.microsoft.com/kb/300684/en-us)を参照してください。
  
ビジネス サーバー 2019 の Skype は、ドメイン名の変更もサポートしていません。 本当にした場合、ドメインの名前を変更するのが必要がありますのビジネス サーバー 2019、Skype をアンインストールするのにはドメインの名前変更の操作を行いますしてビジネス サーバー 2019 の Skype を再インストールします。
  
最後に、ロックされた AD DS 環境では、ドメインを扱うことがあり、ここまでです。 Skype ビジネス サーバー 2019 の展開に関するドキュメントのロック ダウンの AD DS 環境に展開する方法の詳細があります。
  
### <a name="ad-topologies"></a>Active Directory トポロジ

ビジネス サーバー 2019 の Skype でサポートされているトポロジは次のとおりです。
  
- 単一のドメインを含む単一のフォレスト
    
- 単一のツリーと複数のドメインを含む単一のフォレスト
    
- 複数のツリーと不整合の名前空間を含む単一のフォレスト
    
- 中央フォレスト トポロジの複数のフォレスト
    
- リソース フォレスト トポロジの複数のフォレスト
    
- Exchange Online を使用する Skype for Business リソース フォレスト トポロジの複数フォレスト
    
- Skype for Business Online および Azure Active Directory Connect を使用するリソース フォレスト トポロジの複数フォレスト
    
図と、環境、またはビジネス サーバー 2019 の Skype をインストールする前に設定する必要がありますが、どのようなトポロジを決定するための説明があります。 保つには、単純なキーも含めています。
  
![Skype for Business トポロジ図に使用される主なアイコン](../../SfbServer/media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>単一のドメインを含む単一のフォレスト

![ドメインが 1 つである Active Directory の単一フォレストの図](../../SfbServer/media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
この処理をより簡単に取得します。単一ドメインのフォレストでは、一般的なトポロジです。
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>単一のツリーと複数のドメインを含む単一のフォレスト

![単一のフォレスト、単一のツリー、複数のドメインがある図](../../SfbServer/media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
この図は、単一のフォレストを示していますが、1 つまたは複数の子ドメインにも (ある特定の例ではこの 3 つ) があります。 ユーザーがで作成されたドメインは、ビジネス サーバー 2019 を配置するの Skype のドメインとは異なる可能性があります。 これに関する心配は無用でしょうか。 Skype のビジネス サーバーのフロント エンド プールを展開する際の点に注意することが重要、そのプール内のすべてのサーバーが 1 つのドメインにインストールする必要があります。 ドメイン間 Skype 経由でサーバーの管理業務の Windows 管理者のユニバーサル グループをサポートすることができます。
  
上記の図では、1 つのドメインからのユーザーがビジネス サーバーのプール同じドメインからまたは別のドメインからの Skype にアクセスできない場合でも、子ドメインでは、それらのユーザーを確認できます。
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>複数のツリーと不整合の名前空間を含む単一のフォレスト

![単一のフォレスト、複数のツリー、不整合の名前空間がある図](../../SfbServer/media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
場所が 1 つのフォレストにあり、そのフォレスト内で別の AD の名前空間を持つ複数のドメインは、次の図のようなトポロジを使用するがあります。 この例では、この図は、ビジネス サーバー 2019 の Skype にアクセスする 3 つの異なるドメインにユーザーが含まれているため、理解するのに役立ちます。 純色の線は、破線にしようとしているプールを別のツリー全体をことを自身のドメイン内のビジネス サーバー プールの Skype にアクセスしているを示します。
  
ご覧のように、ユーザーが同じドメイン、同じツリーで、または別のツリーもプールにアクセスできます正常にします。
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>中央フォレスト トポロジの複数のフォレスト

![中央フォレスト トポロジの複数のフォレストの図](../../SfbServer/media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
ビジネス サーバー 2019 の Skype では、中央フォレスト トポロジで構成されている複数のフォレストをサポートします。 何があることを確認していない場合は、中央フォレスト トポロジでは、オブジェクトを使用することで、他のフォレスト、およびフォレスト内のユーザーのユーザー アカウントをホストのユーザーを表します。
  
これがどのように動作しているでしょうか。 (Forefront ユーザー マネージャーでは、FIM など) のディレクトリ同期製品では、全体の存在で、組織のユーザーのアカウントを管理します。 アカウントが作成または削除されたとき、フォレストから中央フォレスト内の対応する連絡先に変更が同期されること。
  
明らかに、AD インフラストラクチャが配置の場合は、このトポロジに移行できない場合があります、簡単ですが、されて場合、または計画が、フォレストのインフラストラクチャをこの、適切な選択ができます。 ユーザーは、検索、通信、および任意のフォレスト内の他のユーザーのプレゼンスを表示中に、1 つのフォレスト内のビジネス サーバー 2019 展開するため、Skype を集中管理できます。 すべてのユーザーの連絡先の更新は、同期ソフトウェアで自動的に処理されます。
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Skype for Business リソース フォレスト トポロジの複数のフォレスト
<a name="BKMK_multipleforestopology"> </a>

![リソース フォレスト トポロジ内に複数のフォレストがある図](../../SfbServer/media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
リソース フォレストのトポロジもサポートされています。フォレストは Microsoft Exchange Server およびビジネス サーバー 2019 の Skype のように、サーバー アプリケーションを実行するのには専用の場所をお勧めします。 このリソース フォレストでは、アクティブなユーザー オブジェクトの同期表現ですがないログオンが有効なユーザー アカウントもホストします。 リソース フォレストとは、共有サービス環境の他のフォレストのユーザー オブジェクトが存在し、リソース フォレストのフォレスト レベルの信頼関係があるのです。
  
Skype ビジネス サーバーと同じリソース フォレストまたは別のフォレストの Exchange Server を展開することに注意してください。
  
ユーザー フォレスト内のユーザー アカウントごとに、リソース フォレストで 1 つの無効なユーザー オブジェクトを作成するこの種類のトポロジでのビジネス サーバー 2019 の Skype を展開する (Microsoft Exchange Server が既に環境にいる場合は、これが自動的に行われます)。 ライフ サイクルを使用してユーザー アカウントを管理するためにディレクトリ同期ツール (Forefront ユーザー マネージャーでは、FIM など) する必要があります。
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Exchange Online を使用する Skype for Business リソース フォレスト トポロジの複数フォレスト
<a name="BKMK_multipleforestopology"> </a>

このトポロジは「[Skype for Business リソース フォレスト トポロジの複数フォレスト](system-requirements.md#BKMK_multipleforestopology)」で説明されるトポロジと同様のものです。
  
このトポロジでは、1 つまたは複数のユーザーのフォレストがあるし、Skype ビジネス サーバーの専用リソース フォレストに展開します。 Exchange Server を選択し、展開したオンプレミス リソース フォレストを同じまたは別のフォレストでは、Exchange online では、ハイブリッド用に構成されたまたは設置型のアカウントの Exchange のオンラインでのみ電子メール サービスを提供することがあります。 このトポロジの図はありません。
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>Skype for Business Online および Azure Active Directory Connect を使用するリソース フォレスト トポロジの複数フォレスト
<a name="BKMK_multipleforestopology"> </a>

![2 つの AD フォレスト (ユーザー フォレストとリソース フォレスト) があります。これらの 2 つのフォレストの間には、信頼関係が確立されています。これらの 2 つのフォレストは、Azure AD Connect を使用して Office 365 と同期されます。すべてのユーザーは、Office 365 経由で Skype for Business を利用できます。](../../SfbServer/media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
このシナリオでは、リソース フォレスト トポロジを使用するオンプレミスの複数のフォレストが存在し、Active Directory フォレスト間には完全な信頼関係がある場合を考えます。オンプレミス ユーザー フォレストと Office 365 との間のアカウントを同期するために、Azure Active Directory Connect ツールが使用されます。
  
 この組織は Office 365 も備えており、[Azure Active Directory Connect](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect) を使用してオンプレミス アカウントを Office 365 と同期します。 Office 365 と Skype では、オンライン ビジネスのビジネス用の Skype は、有効になっているユーザーが有効です。 ビジネス サーバー用の Skype は、オンプレミスで導入ではありません。
  
シングル サインオン認証は、ユーザーのフォレストにある、Active Directory フェデレーション サービス ファームによって提供されます。
  
このシナリオでは Exchange の設置型、Exchange Online では、ハイブリッドの Exchange ソリューションを展開するか、しないに展開される Exchange サポートします。 (図のみ交換設置を示していますが、他の Exchange ソリューションが完全にサポートされている)。
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>ハイブリッド Skype for Business を使用するリソース フォレスト トポロジの複数フォレスト
<a name="BKMK_multipleforestopology"> </a>

このシナリオでは、1 つを使用する必要がある以上、オンプレミス ユーザーのフォレスト、ビジネスの Skype 専用のリソース フォレストに展開し、ビジネス オンラインの Skype でハイブリッド モードの構成 Exchange Server は、展開したオンプレミス リソース フォレストを同じまたは別のフォレストし、Exchange online のハイブリッド用に構成することがあります。 または、電子メール サービスを Exchange Online でのみ設置型のアカウントの提供できます。
  
詳細については、[ハイブリッド ビジネスの Skype の複数のフォレスト環境の構成](../../SfbServer/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md)を参照してください。
  
## <a name="domain-name-system-dns"></a>ドメイン ネーム システム (DNS)
<a name="DNS"> </a>

ビジネス サーバー 2019 の Skype では、次の理由により、DNS が必要です。
  
- DNS は、サーバーからサーバーへの通信を許可する内部サーバーまたはプールを検出するのには、ビジネス サーバー 2019 の Skype を使用できます。
    
- DNS では、クライアント マシンのフロント エンド プールまたは Standard Edition サーバーの SIP トランザクションの使用を検出します。
    
- 会議用の簡易 URL と、これらの会議をホストするサーバーが関連付けられます。
    
- DNS は、エッジ サーバー、HTTP 用リバース プロキシ、インスタント メッセージング (IM) または会議に接続するには、外部のユーザーやクライアント コンピューターです。
    
- 統合コミュニケーション (UC) を使用してフロント エンド プールまたは Standard Edition サーバーの更新プログラムを取得し、ログを送信するデバイス更新 web サービスを実行しているデバイスにログインしていないことを検出します。
    
- DNS を使用すると、モバイル クライアントでは、デバイス設定で URL を手動入力しなくても Web サービス リソースを自動的に検出できます。
    
- それは、DNS の負荷分散で使用しています。
    
Skype ビジネス サーバー 2019 の国際化ドメイン名 (Idn) をサポートしていないことに注意する必要があります。
  
覚えておくことは非常に重要と DNS 内の任意の名前のビジネス サーバー 2019、Skype で使用されている任意のサーバーで構成されているコンピューター名と同一であります。 具体的には、環境内の任意の短い名前を持つことはできませんし、トポロジ ビルダーの Fqdn を指定する必要があります。
  
これは、ドメインに既に参加している任意のコンピューターの論理が、短い形式の名前、ドメイン サフィックスなしの既定値を必要がある場合は、ドメインに参加していないエッジ サーバーがある場合は、ように思われます。 しない場合は、dns、またはエッジ サーバー、またはビジネス サーバー 2019 サーバーまたはプール、さらに言えば、Skype では、あることを確認します。
  
Unicode 文字またはアンダー スコアが確実に行われて使用しないでください。 標準的な文字が文字 (A-Z、a-z、0-9、およびハイフン) は、外部 DNS およびパブリック証明機関でサポートされている (Fqdn を証明書の SN に割り当てする必要があります注意することが重要) したが予備の自分で問題の多くに名前を付ける場合があるので、この開始点にします。
  
ネットワークの DNS 要件に関するその他の情報については、「計画」ドキュメントの「[Networking](../../SfbServer/plan-your-deployment/network-requirements/network-requirements.md)」を参照してください。
  
## <a name="certificates"></a>証明書
<a name="Certs"> </a>

展開の前の最も重要な作業の 1 つは、証明書を用意することです。 ビジネス サーバー 2019 の Skype では、トランスポートの公開キー基盤 (PKI) が必要なレイヤーのセキュリティ (TLS) と相互トランスポート層セキュリティ (MTLS) 接続します。 基本的には、標準化された方法で安全に通信をする Skype のビジネス サーバーは証明機関 (Ca) によって発行された証明書を使用します。
  
ビジネス サーバー 2019 の Skype 用の証明書を使用しているものがあります。
  
- クライアントとサーバー間の TLS 接続
    
- サーバー間の MTLS 接続
    
- パートナーの自動 DNS 検出を使用してフェデレーション
    
- インスタント メッセージング (IM) 用のリモート ユーザー アクセス
    
- 音声/ビデオ (AV) セッション、アプリケーション共有、および会議への外部ユーザー アクセス
    
- Web アプリケーションと Outlook Web Access (OWA) を話す
    
証明書の計画をする必要があります。 ここで、証明書を要求するときに留意すべき事項のいくつかのリストを見てみましょう。
  
- すべてのサーバー証明書がサーバーの承認 (サーバー EKU) をサポートしている必要がある。
    
- すべてのサーバー証明書に CRL 配布ポイント (CDP) を含める必要がある。
    
- すべての証明書が、オペレーティング システムでサポートされている署名アルゴリズムによって署名されている必要がある。 ビジネス サーバー 2019 の Skype は、SHA-1 をサポートし、ダイジェスト群の SHA 2 (224 256、384、512 ビット) のサイズとを満たしているか、オペレーティング システムの要件を超えています。
    
- ビジネス サーバー 2019 の Skype を実行している内部のサーバーの自動登録がサポートされています。
    
- ビジネス サーバー 2019 エッジ サーバー用の Skype、自動登録がサポートされていません。
    
> [!NOTE]
> RSASSA-PSS 署名アルゴリズムの使用はサポートされておらず、数ある問題の中でも、ログイン時のエラーや着信転送時の問題につながる可能性があります。 
  
- 暗証キーの長さとして 1024、2048、4096 がサポートされます。2048 以上のキーの長さはお勧めしません。
    
- 既定のダイジェストまたはハッシュ アルゴリズムは RSA です。ECDH_P256、ECDH_P384、ECDH_P521 のハッシュ アルゴリズムもサポートされます。
    
、について考えることはたくさんあるし、は、さまざまな CA から証明書を要求すると快適さのレベルがあります。 紹介の下にいくつか詳しく計画をできるだけ楽に作成します。
  
### <a name="certificates-for-your-internal-servers"></a>内部サーバー用の証明書

証明書を内部のサーバーのほとんどする必要があり、ほとんどの場合、内部 CA (つまり、ドメイン内にある CA) から入手できますがします。 する場合は、外部 CA (1 つはインターネット上にある) から、これらの証明書を要求できます。 参考までにどのような公共の CA の場合に進んでください、[ユニファイド コミュニケーション パートナーを証明書](https://support.microsoft.com/kb/929395/en-us)のリストをチェックすることができます。
  
しようとしているビジネス サーバー 2019 の Skype は、他のアプリケーションや Microsoft Exchange Server などのサーバーと通信するときに証明書を必要があります。 これは、言うまでもなく、必要がありますこれら他のアプリケーションおよびサーバーがサポートされている方法で使用できる証明書。 Skype ビジネス サーバー 2019 およびその他のマイクロソフト製品には、サーバーからサーバーへの認証と承認のためオープン認証 (OAuth) プロトコルをサポートします。 これに興味があるなら、ビジネス サーバー 2019 の OAuth と Skype の他の計画の資料があります。
  
ビジネス サーバー 2019 の Skype を使用せず) のサポートも含まれます、sha-256 暗号ハッシュ関数を使用して署名された証明書です。 SHA-256 を使用する外部アクセスをサポートするには、SHA-256 を使用するパブリック CA が外部証明書を発行する必要があります。
  
するために簡単ですをご用意しました Standard Edition サーバー、フロント エンド プール、およびその他のロールでは、証明書の要件を次のテーブルでは、(おそらく使用する他の例で使用されている架空の contoso.com の環境)。 これらは、すべて標準的な web サーバー証明書、秘密キーをエクスポートできないのです。 いくつか追加の点に注意してください。
  
- サーバーの拡張キー使用法 (EKU) は、証明書ウィザードを使って証明書を要求するときに自動的に構成されます。
    
- 各証明書のフレンドリ名は、コンピューター ストアで一意である必要があります。
    
- 以下のサンプル名が DNS に sipinternal.contoso.com または sipexternal.contoso.com を構成した場合は証明書のサブジェクト代替名 (SAN) を追加する必要が。 あります
    
Standard Edition サーバーの証明書:
  
|**証明書**|**サブジェクト名/共通名**|**サブジェクトの別名**|**例**|**コメント**|
|:-----|:-----|:-----|:-----|:-----|
|Default  <br/> |プールの FQDN  <br/> |プールの FQDN およびサーバーの FQDN  <br/> SIP ドメインが複数あり、自動クライアント構成が有効な場合は、証明書ウィザードによって、サポートされている各 SIP ドメインの FQDN が検出され、追加されます。  <br/> このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密なドメイン ネーム システム (DNS) マッチングが必要な場合は、sip.sipdomain のエントリ (所有する各 SIP ドメイン用) も必要となります。  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com  <br/> このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS マッチングが必要な場合は、SAN=sip.contoso.com、SAN=sip.fabrikam.com も必要です。  <br/> |Standard Edition サーバーは、サーバーの FQDN とは、プールの FQDN と同じです。  <br/> このウィザードでは、セットアップ時に指定した SIP ドメインが検出され、サブジェクトの別名に自動的に追加されます。  <br/> また、この証明書はサーバー間認証でも使用できます。  <br/> |
|内部 Web  <br/> |サーバーの FQDN  <br/> |次のうちのすべて:  <br/> • 内部 web FQDN は、サーバーの FQDN と同じ)  <br/> および  <br/> • 対応の簡単な Url  <br/> ・ ダイヤルで簡単な URL  <br/> • 管理の簡単な URL  <br/> または  <br/> • 簡単な Url のワイルドカード エントリ  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> ワイルドカード証明書使用時:  <br/> SN=se01.contoso.com です。SAN=se01.contoso.com です。SAN =\*. contoso.com  <br/> |内部 web トポロジ ビルダー内の FQDN を無効にすることはできません。  <br/> 対応の複数の単純な Url を使っている場合、それらのすべてを含める必要がありますと San です。  <br/> 簡易 URL エントリではワイルドカード エントリがサポートされます。  <br/> |
|外部 Web  <br/> |サーバーの FQDN  <br/> |次のうちのすべて:  <br/> • 外部 web FQDN  <br/> および  <br/> ・ ダイヤルで簡単な URL  <br/> • SIP ドメインごと対応の簡単な Url。  <br/> または  <br/> • 簡単な Url のワイルドカード エントリ  <br/> |SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> ワイルドカード証明書使用時:  <br/> SN=se01.contoso.com です。SAN=webcon01.contoso.com です。SAN =\*. contoso.com  <br/> |対応の複数の簡単な Url の場合は、サブジェクト代替名としては、それらのすべてを含める必要があります。  <br/> 簡易 URL エントリではワイルドカード エントリがサポートされます。  <br/> |
   
フロント エンド プール内のフロント エンド サーバーの証明書:
  
|**証明書**|**サブジェクト名/共通名**|**サブジェクトの別名**|**例**|**コメント**|
|:-----|:-----|:-----|:-----|:-----|
|Default  <br/> |プールの FQDN  <br/> |プールの FQDN およびサーバーの FQDN  <br/> SIP ドメインが複数あり、自動クライアント構成が有効な場合は、証明書ウィザードによって、サポートされている各 SIP ドメインの FQDN が検出され、追加されます。  <br/> このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密なドメイン ネーム システム (DNS) マッチングが必要な場合は、sip.sipdomain のエントリ (所有する各 SIP ドメイン用) も必要となります。  <br/> |SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com   <br/> このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS マッチングが必要な場合は、SAN=sip.contoso.com、SAN=sip.fabrikam.com も必要です。  <br/> |このウィザードでは、セットアップ時に指定した SIP ドメインが検出され、サブジェクトの別名に自動的に追加されます。  <br/> また、この証明書はサーバー間認証でも使用できます。  <br/> |
|内部 Web  <br/> |プールの FQDN  <br/> |次のうちのすべて:  <br/> • 内部 web FQDN (これは、サーバーの FQDN と同じ)  <br/> • サーバーの FQDN  <br/> • Skype ビジネス プールの FQDN  <br/> および  <br/> • 対応の簡単な Url  <br/> ・ ダイヤルで簡単な URL  <br/> • 管理の簡単な URL  <br/> または  <br/> • 簡単な Url のワイルドカード エントリ  <br/> |SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> ワイルドカード証明書使用時:  <br/> SN=ee01.contoso.com です。SAN=ee01.contoso.com です。SAN =\*. contoso.com  <br/> |対応の複数の簡単な Url の場合は、サブジェクト代替名としては、それらのすべてを含める必要があります。  <br/> 簡易 URL エントリではワイルドカード エントリがサポートされます。  <br/> |
|外部 Web  <br/> |プールの FQDN  <br/> |次のうちのすべて:  <br/> • 外部 web FQDN  <br/> および  <br/> ・ ダイヤルで簡単な URL  <br/> • 管理の簡単な URL  <br/> または  <br/> • 簡単な Url のワイルドカード エントリ  <br/> |SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> ワイルドカード証明書使用時:  <br/> SN=ee01.contoso.com です。SAN=webcon01.contoso.com です。SAN =\*. contoso.com  <br/> |対応の複数の簡単な Url の場合は、サブジェクト代替名としては、それらのすべてを含める必要があります。  <br/> 簡易 URL エントリではワイルドカード エントリがサポートされます。  <br/> |
   
ディレクターの証明書:
  
|**証明書**|**サブジェクト名/共通名**|**サブジェクトの別名**|**例**|
|:-----|:-----|:-----|:-----|
|Default  <br/> |ディレクター プール  <br/> |ディレクター、ディレクター プールの FQDN の FQDN です。  <br/> このプールがクライアント、および厳密な自動ログオン サーバーである場合は、グループ ポリシーで必要な DNS に一致する、(各 SIP ドメイン) の sip.sipdomain のエントリも必要があります。  <br/> |pool.contoso.com; SAN=dir01.contoso.com   <br/> このダイレクタ ・ プールは、クライアントの自動ログオン サーバーと、グループ ポリシーで厳密な DNS マッチングが必要なする必要も SAN=sip.contoso.com。SAN=sip.fabrikam.com  <br/> |
|内部 Web  <br/> |サーバーの FQDN  <br/> |次のうちのすべて:  <br/> • 内部 web FQDN は、サーバーの FQDN と同じ)  <br/> • サーバーの FQDN  <br/> • Skype ビジネス プールの FQDN  <br/> および  <br/> • 対応の簡単な Url  <br/> ・ ダイヤルで簡単な URL  <br/> • 管理の簡単な URL  <br/> または  <br/> • 簡単な Url のワイルドカード エントリ  <br/> |SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> ワイルドカード証明書使用時:  <br/> SN=dir01.contoso.com です。SAN の SAN=dir01.contoso.com =\*. contoso.com  <br/> |
|外部 Web  <br/> |サーバーの FQDN  <br/> |次のうちのすべて:  <br/> • 外部 web FQDN  <br/> および  <br/> • SIP ドメインごと対応の簡単な Url。  <br/> ・ ダイヤルで簡単な URL  <br/> または  <br/> • 簡単な Url のワイルドカード エントリ  <br/> |ディレクターの外部 web FQDN は、フロント エンド プールまたはフロント エンド サーバーとは異なるである必要があります。  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> ワイルドカード証明書使用時:  <br/> SN=dir01.contoso.com です。SAN の SAN=directorwebcon01.contoso.com =\*. contoso.com  <br/> |
   
スタンドアロンの仲介サーバーの証明書:
  
|**証明書**|**サブジェクト名/共通名**|**サブジェクトの別名**|**例**|
|:-----|:-----|:-----|:-----|
|Default  <br/> |プールの FQDN  <br/> |プールの FQDN  <br/> プール メンバー サーバーの FQDN  <br/> |SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net  <br/> |
   
リカバリ性に優れたブランチ アプライアンス (具体的には、リカバリ性に優れた分岐 2015 用アプライアンス ビジネス サーバー 2019 の Skype) の証明書:
  
|**証明書**|**サブジェクト名/共通名**|**サブジェクトの別名**|**例**|
|:-----|:-----|:-----|:-----|
|Default  <br/> |アプライアンスの FQDN  <br/> |SIP。\<sipdomain\> (SIP ドメインごとに 1 つだけのエントリが必要)  <br/> |SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
   
### <a name="certificates-for-external-user-access-edge"></a>外部ユーザー アクセス (エッジ) 用の証明書

ビジネス サーバー 2019 の Skype は、アクセスおよび web 会議エッジ外部インターフェイスに加えて、A の**1 つのパブリック証明書**の使用をサポートしている/V 認証サービスは、エッジ サーバー経由で提供されています。 エッジの内部インターフェイスは、通常、内部 CA によって発行されるプライベート証明書を使用する場合、使用することがパブリック証明書この同様に、信頼された CA からである場合。
  
またリバース プロキシ (RP) でも、パブリック証明書を使用して、RP からクライアントへの通信と RP から内部サーバーへの通信を、HTTP (厳密には TLS over HTTP) を使用して暗号化します。
  
### <a name="certificates-for-mobility"></a>モビリティ用の証明書

モビリティを展開しているモバイル クライアントの自動検出をサポートしている場合は、しようとしているモバイル クライアントからセキュリティで保護された接続をサポートする証明書のいくつかの追加のサブジェクト代替名エントリを含める必要があります。
  
次の証明書の自動検出機能を SAN の名前が必要です。
  
- ディレクター プール
    
- フロントエンド プール
    
- リバース プロキシ
    
詳細については、次の表に表示されます。
  
これは、ちょっとした事前の計画に問題ですが、場合によって展開した Skype ビジネス サーバー 2019 のモビリティを展開する必要のないは後で証明書を環境内に既に存在する場合。 通常、内部 CA を介した証明書の再発行は簡単ですが、パブリック CA のパブリック証明書を使用する場合は、多少コストが上がる可能性があります。
  
(これは既定では HTTPS を使用する代わりに、最初の自動検出サービス要求の HTTP を使用するのにはリバース プロキシを構成するには何を探して、これは、(これは加えることがより高価な SAN) の SIP ドメインの多くがある場合は、構成)。 [モビリティの計画](../../SfbServer/plan-your-deployment/mobility.md)の資料の詳細については、これがあります。
  
ディレクター プールとフロント エンド プールは、要件を証明書します。
  
|**説明**|**SAN エントリ**|
|:-----|:-----|
|内部自動検出サービス URL  <br/> |SAN lyncdiscoverinternal を = します。\<sipdomain\>  <br/> |
|外部自動検出サービス URL  <br/> |SAN lyncdiscover を = します。\<sipdomain\>  <br/> |
   
または SAN を使用することができます =\*。\<sipdomain\>
  
リバース プロキシ (パブリック CA) の証明書の要件:
  
|**説明**|**SAN エントリ**|
|:-----|:-----|
|外部自動検出サービス URL  <br/> |SAN lyncdiscover を = します。\<sipdomain\>  <br/> |
   
この SAN を、リバース プロキシ上の SSL リスナーに割り当てられる証明書に割り当てる必要があります。
  
> [!NOTE]
> リスナーがリバース プロキシが、外部 Web サービス個の URL の San があるしようとしています。 あります SAN=skypewebextpool01.contoso.com と dirwebexternal.contoso.com、(これはオプションです)、ディレクターを展開した場合です。 
  
## <a name="file-share"></a>ファイル共有
<a name="Fileshare"> </a>

ビジネス サーバー 2019 の Skype では、すべてのファイル ・ ストレージの同じファイル共有を使用できます。 以下の点を考慮する必要があります。
  
- ファイル共有は、直接取り付け記憶域 (DAS) と記憶域ネットワーク (SAN) のいずれかに配置する必要があり、またファイル共有には、分散ファイル システム (DFS) だけでなくファイル ストア用の RAID (Redundant Array of Independent Disks) も含まれます。 Windows Server 2012 用の DFS の詳細については、[こちらの DFS に関するページ](https://technet.microsoft.com/en-us/library/jj127250.aspx)を参照してください。
    
- 共有クラスター ファイル共有に対応することをお勧めします。 いずれかを使用している場合は、Windows Server 2012 または Windows Server 2012 R2 をクラスターする必要があります。 なぜ最新の Windows でしょうか。 以前のバージョンは、すべての機能を有効にする適切なアクセス許可をいない可能性があります。 クラスター アドミニストレーターを使用するには、ファイル共有を作成して、この KB[のクラスターを作成する](https://support.microsoft.com/en-us/help/224967)資料に役立つ詳細を記載しました。
    
> [!CAUTION]
> ファイル共有にネットワーク接続ストレージ (NAS) は使用できません。ファイル共有には、上記のいずれかの選択肢を利用してください。 
  








