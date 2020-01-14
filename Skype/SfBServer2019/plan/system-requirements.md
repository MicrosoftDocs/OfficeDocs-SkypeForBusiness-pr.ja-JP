---
title: Skype for Business Server 2019 のシステム要件
ms.reviewer: ''
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: '概要: このトピックを使用して、Skype for Business Server 2019 サーバーとドメインインフラストラクチャを準備します。 ハードウェア、OS、データベース、ソフトウェア、すべてのシステム要件と推奨事項、証明書の DNS、ファイル共有、Active Directory の情報と共に、サーバーファームのインストールと展開が正常に行われるようにするために、ここに記載されています。'
ms.openlocfilehash: ea4ae18a3714058e0df4f42a0190046ce7006ef8
ms.sourcegitcommit: 0119af282f53f49c4ab6e01c3319d01bc6fdad2c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/14/2020
ms.locfileid: "41111381"
---
# <a name="system-requirements-for-skype-for-business-server-2019"></a>Skype for Business Server 2019 のシステム要件
 
**概要:** このトピックを使用して、Skype for Business Server 2019 をインストールするための準備を行います。 ハードウェア、OS、ソフトウェア、データベース、証明書、Active Diretory、DNS、および fileshares について説明します。 システム要件と推奨事項はすべて、サーバーファームのインストールと展開を成功させるのに役立ちます。
  
Skype for Business Server 2019 の展開を開始する前に、いくつかの準備を行う必要があります。 この記事では次の計画について、順を追って説明します。
  
- [ハードウェア](system-requirements.md#Hardware)
  
- [オペレーティング システム](system-requirements.md#OS)
  
- [ソフトウェア](system-requirements.md#Software)

- [バックエンド SQL データベース](system-requirements.md#DBs)
  
- [Active Directory](system-requirements.md#AD)
  
- [ドメイン ネーム システム (DNS)](system-requirements.md#DNS)
  
- [証明書](system-requirements.md#Certs)
  
- [ファイル共有](system-requirements.md#Fileshare)

  
## <a name="hardware-for-skype-for-business-server-2019"></a>Skype for Business Server 2019 のハードウェア
<a name="Hardware"> </a>

トポロジをダウンしたら ( [Skype For Business Server 2019 トピックのトポロジの基礎](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md)を確認できます)、サーバーについて考えてみましょう。 Skype for Business Server 2019 サーバーには、64ビットのハードウェアが必要です。 推奨されるハードウェアをこの後に示します。 これらは必須ではありませんが、最適なパフォーマンスを得るために必要な要件を反映しています。 状況に応じて、これを超えるものが必要であるかどうかの判断に役立つ、処理能力の計画に関するドキュメントも用意されています。
  
Standard Edition サーバーに推奨されるハードウェア:

|**ハードウェア コンポーネント**|**推奨**|
|:-----|:-----|
|CPU  <br/> |Intel Xeon E5-2673 v3 デュアルプロセッサ、6コア、2.4 ghz (GHz) 以上。  <br/> Skype for Business Server 2019 ロールでは、Intel Itanium プロセッサはサポートされていません。  <br/> |
|メモリ  <br/> |32 ギガバイト (GB)  <br/> |
|ディスク  <br/> |次のいずれか:  <br/> • 1万 RPM 以上のハードディスクドライブ (少なくとも 72 GB のディスク空き容量 (RAID 10 を使用している2台のディスクと、RAID 10 を使用した6個のディスク)  <br/> または  <br/> •ソリッドステートドライブ (Ssd) では、8 1万 RPM 機械的ディスクドライブと同じ空き領域と同様のパフォーマンスを提供できます。  <br/> |
|ネットワーク  <br/> |1 Gbps 以上のデュアルポート ネットワーク アダプター 1 つ (2 つのネットワーク アダプターを使用できるが、その場合は 1 つの MAC アドレスと 1 つの IP アドレスのチーミングが必要)。  <br/> フロントエンドサーバー、バックエンドサーバー、標準エディションサーバーでは、デュアルホーム構成またはマルチホーム構成はサポートされ**ません**。 <br/> オペレーティングシステムに公開されておらず、サーバーハードウェアを監視および管理するために使用されている限り、DRAC や ILO などの帯域外管理システムを使うことができます。 このシナリオは、マルチ ホーム サーバーの構成要素ではなく、サポートされています。  <br/> |


フロントエンドサーバーとバックエンドサーバーに推奨されるハードウェア:
  
|**ハードウェア コンポーネント**|**推奨**|
|:-----|:-----|
|CPU  <br/> |Intel Xeon E5-2673 v3 デュアルプロセッサ、6コア、2.4 ghz (GHz) 以上。 <br/> Skype for Business Server 2019 ロールでは、Intel Itanium プロセッサはサポートされていません。  <br/> |
|メモリ  <br/> |64ギガバイト (GB)。  <br/> |
|ディスク  <br/> |次のいずれか:  <br/> • 1万 RPM 以上のハードディスクドライブ (少なくとも 72 GB のディスク空き容量 (RAID 10 を使用している2台のディスクと、RAID 10 を使用した6個のディスク)  <br/> または  <br/> •ソリッドステートドライブ (Ssd) では、8 1万 RPM 機械的ディスクドライブと同じ空き領域と同様のパフォーマンスを提供できます。  <br/> |
|ネットワーク  <br/> |1 Gbps 以上のデュアルポート ネットワーク アダプター 1 つ (2 つのネットワーク アダプターを使用できるが、その場合は 1 つの MAC アドレスと 1 つの IP アドレスのチーミングが必要)。  <br/> フロントエンドサーバー、バックエンドサーバー、標準エディションサーバーでは、デュアルホーム構成またはマルチホーム構成はサポートされ**ません**。 <br/> オペレーティングシステムに公開されておらず、サーバーハードウェアを監視および管理するために使用されている限り、DRAC や ILO などの帯域外管理システムを使うことができます。 このシナリオは、マルチ ホーム サーバーの構成要素ではなく、サポートされています。  <br/> |
   
エッジサーバー、スタンドアロン仲介サーバー、およびディレクターに推奨されるハードウェア:
  
|**ハードウェア コンポーネント**|**推奨**|
|:-----|:-----|
|CPU  <br/> |Intel Xeon E5-2673 v3 デュアルプロセッサ、6コア、2.4 ghz (GHz) 以上。  <br/> Skype for Business Server 2019 ロールでは、Intel Itanium プロセッサはサポートされていません。  <br/> |
|メモリ  <br/> |32ギガバイト。  <br/> |
|ディスク  <br/> |次のいずれか:  <br/> • 4 GB 以上の 1万 RPM ハードディスクドライブ (少なくとも 72 GB の空きディスク領域が必要です (ディスクは2倍の RAID 1 構成にする必要があります)。  <br/> または  <br/> •ソリッドステートドライブ (Ssd) では、4 1万 RPM 機械的ディスクドライブと同じ空き領域と同様のパフォーマンスを提供できます。  <br/> |
|ネットワーク  <br/> |1 Gbps 以上のデュアルポート ネットワーク アダプター 1 つ (2 つのネットワーク アダプターを使用できるが、その場合は 1 つの MAC アドレスと 1 つの IP アドレスのチーミングが必要)。  <br/> ビデオ相互運用サーバーとディレクターでは、デュアルホーム構成またはマルチホーム構成はサポートされ**ません**。 <br/> エッジ サーバーには、1 Gbps 以上のデュアルポート ネットワーク アダプターである 2 つのネットワーク インターフェイス (つまり 2 ペア (合計 4 つ) のネットワーク アダプター。この合計 2 つのペアでは、各ペアが 1 つの MAC アドレスと 1 つの IP アドレスでチームになっている) が必要です。  <br/> スタンドアロンの仲介サーバーでは、特定の PSTN IP アドレスの構成を許可するために、追加のネットワークインターフェイスカード (Nic) のインストールがサポートされています。  <br/> |


> [!NOTE]
> サーバーの役割にかかわらず、Skype for Business Server 2019 の場合は、次のハードウェア設定もお勧めします (これは購入したハードウェアのブランドによって異なる場合がありますので、詳細については製造元のマニュアルを参照してください)。
> - BIOS 構成-NUMA から FLAT に設定する必要があります。
> - ハイパースレッディングを有効にします。
> - RSS キューの設定は8つのキューに設定する必要があります。

   
## <a name="operating-systems-for-skype-for-business-server-2019"></a>Skype for Business Server 2019 のオペレーティングシステム
<a name="OS"> </a>

ハードウェアを用意したら、Skype for Business Server 2019 をインストールして正常に使用できるようにするインストールオペレーティングシステム (OS) が必要になります。
  
|||
|:-----|:-----|
|Windows Server 2019 <br/> |
|Windows Server 2016 <br/> ||
||
   
ここに記載されているオペレーティングシステム以外のものは正しく機能しません。Skype for Business Server 2019 のインストールをお試しください。 たとえば、Server Core オプションは表示されません。そのため、サポートされません。  注: OS のインプレースアップグレードは、Lync Server 2013 ではサポートされていません。  OS が異なる場合は、別のプールを展開して、新しいプールにユーザーを移行する必要があります。

> [!NOTE]
> 
> Windows Server 2019 コンピューターに Windows 管理センター2019をインストールしている場合、リッスンするポートを入力するように求められます。 Liklihood は、ポート443を選ぶこともありますが、そのコンピューターに Skype for business Server 2019 がインストールされている場合、または Skype for business Server 2019 がインストールされている場合は、別のポート番号を選択する必要があります。
> 
>なぜですか? Windows 管理センター2019がポート443で実行されている場合、Skype for Business コントロールパネルを使用してサーバーに接続することはできません。また、サーバー上で実行されている内部 web サービス (アドレス帳 Web サービス) に接続することもできません。、自動検出サービス、WebTicket サービスなど) があります。  実際には、内部の Web サービスの URL に接続することはできません。 Skype for Business Server 2019 のサーバーに Windows 管理センター2019を配置する必要がある場合は、別のポートを選択してください。
> 

  
## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2019-deployment"></a>Skype for Business Server 2019 の展開前にインストールする必要があるソフトウェア
<a name="Software"> </a>

Skype for Business Server 2019 を実行しているサーバーについては、いくつかの方法でインストールまたは構成する必要があります。 以下に、特定のサーバーの役割の追加要件を示します。

> [!IMPORTANT]
> Skype For Business 2019 は .Net Framework 4.8 をサポートしています。 
  
 **すべてのサーバー:**
  
|**ソフトウェア/役割**|**詳細**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |すべての Skype for Business Server サーバーには、Windows PowerShell 3.0 がインストールされている必要があります。  <br/> • Windows Server 2016 には、既定でインストールされている必要があります。<br/> |
|Microsoft .NET Framework  <br/> |WCF サービスは、Windows 機能としてインストールされている**機能**です。**サーバーマネージャー**では、最初にダウンロードする必要はありません。 <br/> •この機能がインストールされているかどうかを確認する必要がある場合、または既にインストールされていて確認している場合は、次のように**HTTP アクティブ化**オプションがオンになっていることを確認する必要があります。 <br/> ![.NET Framework 4.5 機能の下に [HTTP アクティブ化] オプションが表示されたスクリーンショット](../../SfbServer/media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png) <br/> HTTP アクティブ化をインストールするには、その他のインストールが必要であるという追加のメッセージが表示されても問題はありません。 これは正常です。[OK] をクリックして、進みます。 このポップアップが表示されない場合は、既にインストールされているものと想定してください。  <br/> Microsoft .NET Framework は、通常、Windows Server 2016 がインストールされたときにインストールされます。 Skype for Business Server を使用するには、Microsoft .NET Framework 4.7 または4.8 が必要です。その場合は、おそらく更新が必要です。 更新プログラムは次の[ページで](https://support.microsoft.com/help/3186497/the-net-framework-4-7-offline-installer-for-windows/)参照できます。<br/> |
|メディア ファンデーション  <br/> |Windows Server 2016 の場合、Windows Media 形式ランタイムは、Microsoft メディアファンデーションにインストールされます。  <br/> 会議に使われるすべてのフロントエンドサーバーおよび標準エディションのサーバーでは、Windows Media Format Runtime を使用して、コールパーク、お知らせ、および応答グループアプリケーションがお知らせや音楽を再生するための Windows media Audio (.wma) ファイルを実行する必要があります。  <br/> |
|Windows Identity Foundation  <br/> |Skype for Business Server 2019 のサーバー間認証シナリオをサポートするには、Windows Id ファンデーション3.5 が必要です。  <br/> • Windows Server 2016 の場合は、何もダウンロードする必要はありません。 **サーバー マネージャー**を開いて、[**役割と機能の追加ウィザード**] に進みます。 [**機能**] セクションの一覧に [**Windows Identity Foundation 3.5**] が表示されています。 選択されている場合は、問題ありません。 それ以外の場合は、選択して「**次へ**」をクリックし、「**インストール**」ボタンをクリックします。 <br/> |
|リモート サーバー管理ツール  <br/> |役割管理ツール: AD DS および AD LDS ツール  <br/> |
   
 **フロントエンドサーバーと Standard Edition サーバーにも次のものが必要です。**
  
|**ソフトウェア/役割**|**詳細**|
|:-----|:-----|
|インターネット インフォメーション サービス (IIS)  <br/> |IIS は、すべてのフロントエンドサーバー、およびすべての標準エディションのサーバーで、次のモジュールが選択されている必要があります。  <br/> •一般的な HTTP 機能: 既定のドキュメント、HTTP エラー、静的コンテンツ  <br/> •正常性と診断: HTTP ログ、ログツール、トレース  <br/> •パフォーマンス: 静的なコンテンツの圧縮、動的なコンテンツの圧縮  <br/> •セキュリティ: フィルターの要求、クライアント証明書のマッピング認証、Windows 認証  <br/> •アプリケーション開発: .NET 機能拡張3.5、.NET 機能拡張4.5、ASP.NET 3.5、ASP.NET 4.5、ISAPI 拡張、ISAPI フィルター  <br/> •管理ツール: IIS 管理コンソール、IIS 管理スクリプト、ツール  <br/> また、匿名アクセスも必要であることに注意してください。ただし、IIS のインストール時には、リストから選択する場所がありません。  <br/> |
|Windows Media フォーマット ランタイム  <br/> | Windows Server 2016 の場合は、**メディアファンデーション**機能を**サーバーマネージャー**にインストールする必要があります。 Skype for business Server 2019 のインストールは、実際にはできませんが、skype for Business Server 2019 のインストールが続行される前に、インストールしてサーバーを再起動するように求められます。 前もってお勧めします。 <br/> |
|Silverlight  <br/> |[ここで](https://www.microsoft.com/silverlight/)は、最新バージョンの Silverlight をインストールできます。  <br/> |
   
作業の簡素化のために、この処理を自動化するサンプル PowerShell スクリプトを次に示します。
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, Telnet-Client, BITS, ManagementOData, Web-Mgmt-Console, Web-Metabase, Web-Lgcy-Mgmt-Console, Web-Lgcy-Scripting, Web-WMI, Web-Scripting-Tools, Web-Mgmt-Service
```

 **ディレクターも次のことを行う必要があります。**
  
次のモジュールを選択した IIS:
  
- HTTP 共通機能
    
  - 既定のドキュメント
    
  - HTTP エラー
    
  - 静的コンテンツ
    
- 状態と診断
    
  - HTTP ログ
    
  - ログ ツール
    
  - トレース
    
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
    
(ご不明な点がある場合は、動的なコンテンツ圧縮と管理ツールが表示された状態で、フロントエンドサーバーと標準エディションサーバーと同じモジュールセットになります)。
  
また、同様に役立つ PowerShell コードを次に示します。
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, Telnet-Client
```

## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2019"></a>Skype for Business Server 2019 で動作するバックエンドデータベース
<a name="DBs"> </a>

Skype for Business Server 2019 Standard Edition をインストールすると、SQL Server 2016 Express (64 ビット版) がインストールされます。

Skype for Business Server 2019 Enterprise Edition には、以下に示すように完全な SQL Server が必要です (64 ビット版のみ)。32ビットエディションは使用しないでください。
  
||||
|:-----|:-----|:-----|
|Microsoft SQL Server 2019 (64 ビット版)、最新の更新プログラムを使用して実行する必要があります。  <br/> |Microsoft SQL Server 2017 (64 ビット版)、最新の更新プログラムを使用して実行する必要があります。  <br/> |
Microsoft SQL Server 2016 (64 ビット版)、最新の更新プログラムを使用して実行する必要があります。|
 |

使用したい SQL Server エディションがここに表示されていない場合は、使用できません。
  
> [!NOTE]
> また、監視サーバーの役割の SQL Server Reporting Services もインストールする必要があります。 
  
### <a name="sql-clustering-and-sql-always-on"></a>SQL クラスタリング、SQL は常にオン

Skype for Business Server 2019 での SQL クラスタリングはサポートされています。 SQL クラスタリングをセットアップする場合は、SQL Server で行います。
  
サポートされている SQL クラスタリング用のアクティブ/パッシブ構成があることを確認してください。 パッシブノードを他の SQL インスタンスと共有しないでください。
  
フェールオーバー クラスタリングでは、次の OS を使用できます。
  
2 ノードの場合:
  
- Microsoft SQL Server 2019 Standard (64 ビット版)、最新のサービスパックを使用して実行することをお勧めします。
- Microsoft SQL Server 2017 Standard (64 ビット版)、最新のサービスパックを使用して実行することをお勧めします。
- Microsoft SQL Server 2016 Standard (64 ビット版)、最新のサービスパックを使用して実行することをお勧めします。

16 ノードの場合:
  
- Microsoft SQL Server 2019 Enterprise (64 ビット版)、最新の service pack を使用して実行することをお勧めします。
- Microsoft SQL Server 2017 Enterprise (64 ビット版)、最新の service pack を使用して実行することをお勧めします。
- Microsoft SQL Server 2016 Enterprise (64 ビット版)、最新の service pack を使用して実行することをお勧めします。

SQL Always On がサポートされていますが、 [Skype For Business Server 2019 のバックエンドサーバーの高可用性](../../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md)機能で、その詳細を確認できます。
  

###  <a name="additional-server-installation-recommendations"></a>その他のサーバーインストールの推奨事項:
  
Microsoft インターネットセキュリティとアクセラレータ (ISA) サーバークライアントソフトウェア、またはその他の Winsock レイヤードサービスプロバイダ (LSP) ソフトウェア (サードパーティ製のファイアウォールまたはウイルス対策ネットワーク検査ソフトウェア) をインストールしないでください。任意のフロントエンドサーバーまたはスタンドアロンの仲介サーバー。 ソフトウェアがインストールされているときに低品質のメディアトラフィックのパフォーマンスが表示される。
  

## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

サーバーおよびサービスの構成データの大部分は、Skype for Business Server 2019 中央管理ストアに保存されていますが、まだ Active Directory に保存されているものもあります。
  
|**Active Directory オブジェクト**|**オブジェクトの種類**|
|:-----|:-----|
|スキーマ拡張  <br/> |ユーザー オブジェクトの拡張  <br/> |
||Skype for Business Server 2015 および Lync Server 2013 の拡張機能、以前サポートされているバージョンとの下位互換性を維持するためのものです。  <br/> |
|データ  <br/> |ユーザーの SIP URI と他のユーザー設定  <br/> |
||アプリケーションの連絡先オブジェクト (返信グループアプリケーション、会議アテンダントアプリケーションなど)  <br/> |
||下位互換性のために公開されたデータ  <br/> |
||中央管理ストアのサービス制御ポイント (SCP)  <br/> |
||Kerberos 認証アカウント (オプションのコンピューターオブジェクト)  <br/> |
   
### <a name="os-for-domain-controllers"></a>ドメイン コントローラー用の OS

次のドメインコントローラーオペレーティングシステムを使用できます。
  
- Windows Server 2019

- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
Skype for business Server 2019 に展開した任意のドメインのドメイン機能レベル、および Skype for Business Server 2019 を展開したフォレストの機能レベルは、次のいずれかである必要があります。
  
- Windows Server 2019

- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
これらの環境には読み取り専用ドメインコントローラーがありますか? 確かに、書き込み可能なドメインコントローラーも利用できる限り、
  
Skype for Business Server 2019 では、単一のラベルが付いたドメインをサポートしていないことを知っておくことが重要です。 単一ラベルのドメインがどのようなものかを把握しておいてください。 Contoso. .local というラベルの付いたルートドメインを持っている場合、これは問題ありません。 ローカルという名前のルートドメインがあり、それが機能していない場合、結果としてサポートされません。 詳細については、[このサポート技術情報の記事で](https://support.microsoft.com/kb/300684/)記載されています。
  
Skype for Business Server 2019 では、ドメイン名の変更もサポートされていません。 ドメイン名を変更する必要がある場合は、Skype for Business Server 2019 をアンインストールし、ドメイン名の変更を行ってから、Skype for Business Server 2019 を再インストールする必要があります。
  
最後に、ロックダウンされた AD DS 環境でドメインを処理している可能性があります。 Skype for Business Server 2019 をロックダウンされた AD DS 環境に展開する方法については、展開ドキュメントを参照してください。
  
### <a name="ad-topologies"></a>Active Directory トポロジ

Skype for Business Server 2019 でサポートされているトポロジは次のとおりです。
  
- 単一のドメインを含む単一のフォレスト
    
- 単一のツリーと複数のドメインを含む単一のフォレスト
    
- 複数のツリーと不整合の名前空間を含む単一のフォレスト
    
- 中央フォレスト トポロジの複数のフォレスト
    
- リソース フォレスト トポロジの複数のフォレスト
    
- Exchange Online を使用する Skype for Business リソース フォレスト トポロジの複数フォレスト
    
- Skype for Business Online および Azure Active Directory Connect を使用するリソース フォレスト トポロジの複数フォレスト
    
使用している環境にどのようなトポロジがあるかを判断するのに役立つ図と説明、および Skype for Business Server 2019 をインストールする前にセットアップする必要があることについて説明します。 シンプルな状態を維持するために、キーも含めています。
  
![Skype for Business トポロジ図に使用される主なアイコン](../../SfbServer/media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>単一のドメインを含む単一のフォレスト

![ドメインが 1 つである Active Directory の単一フォレストの図](../../SfbServer/media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
これよりも簡単に表示されません。これは単一のドメインフォレストであり、一般的なトポロジです。
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>単一のツリーと複数のドメインを含む単一のフォレスト

![単一のフォレスト、単一のツリー、複数のドメインがある図](../../SfbServer/media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
この図は、1つのフォレストを示していますが、1つ以上の子ドメインも含まれています (この例では3つあります)。 そのため、ユーザーが作成されるドメインは、Skype for Business Server 2019 の展開先のドメインとは異なる場合があります。 どうしたらよいのでしょうか。 Skype for Business Server フロントエンドプールを展開するときに、そのプール内のすべてのサーバーが単一のドメインに存在している必要があることに注意してください。 Windows ユニバーサル管理者グループの Skype for Business Server サポートでは、ドメイン間管理を行うことができます。
  
上の図では、ユーザーが子ドメインにいる場合でも、あるドメインのユーザーが同じドメインまたは異なるドメインから Skype for Business Server プールにアクセスできることを確認できます。
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>複数のツリーと不整合の名前空間を含む単一のフォレスト

![単一のフォレスト、複数のツリー、不整合の名前空間がある図](../../SfbServer/media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
この図のようなトポロジは、1つのフォレストがあり、そのフォレスト内に複数のドメインがあり、別々の AD 名前空間を使用している場合があります。 この図は、3つの異なるドメインに Skype for Business Server 2019 にアクセスするユーザーが含まれているため、この図をお勧めします。 実線は、自分のドメインで Skype for Business サーバープールにアクセスしていることを示しますが、破線は、他のツリーでプールに移動していることを示します。
  
ご覧のとおり、同じドメイン内のユーザー、同じツリー、または別のツリーでも、プールに正常にアクセスできます。
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>中央フォレスト トポロジの複数のフォレスト

![中央フォレスト トポロジの複数のフォレストの図](../../SfbServer/media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
Skype for Business Server 2019 は、中央フォレストトポロジで構成されている複数のフォレストをサポートしています。 自分が持っていることがわからない場合、トポロジの中央のフォレストでは、他のフォレストのユーザーを表すためのオブジェクトを使用し、フォレスト内のユーザーのユーザーアカウントをホストします。
  
動作のしくみ ディレクトリ同期製品 (Forefront Identity Manager、FIM など) では、組織のユーザーアカウントがその存在を通じて管理されます。 フォレストからアカウントが作成または削除されると、その変更はセントラルフォレスト内の対応する連絡先に同期されます。
  
お客様の広告インフラストラクチャが適切に設定されている場合は、このトポロジに移行するのは簡単ではありませんが、既に存在している場合、またはフォレストインフラストラクチャを計画している場合は、この方法が適しています。 Skype for Business Server 2019 の展開を1つのフォレストにまとめることができます。ユーザーは、任意のフォレストの他のユーザーの検索、通信、表示を行うことができます。 すべてのユーザーの連絡先の更新は、同期ソフトウェアで自動的に処理されます。
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Skype for Business リソース フォレスト トポロジの複数のフォレスト
<a name="BKMK_multipleforestopology"> </a>

![リソース フォレスト トポロジ内に複数のフォレストがある図](../../SfbServer/media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
リソースフォレストのトポロジもサポートされています。ここでは、Microsoft Exchange Server や Skype for Business Server 2019 など、サーバーアプリケーションの実行専用のフォレストがあります。 このリソースフォレストは、アクティブなユーザーオブジェクトの同期表現もホストしますが、ログオン可能なユーザーアカウントはホストしません。 そのため、リソースフォレストは、ユーザーオブジェクトが存在する他のフォレストの共有サービス環境であり、リソースフォレストとのフォレストレベルの信頼関係があります。
  
Exchange Server は、Skype for Business Server と同じリソースフォレスト、または別のフォレストに展開できることに注意してください。
  
この種類のトポロジで Skype for Business Server 2019 を展開するには、ユーザーフォレスト内の各ユーザーアカウントのリソースフォレストに無効なユーザーオブジェクトを1つ作成します (Microsoft Exchange Server が既に環境に存在している場合は、これが自動的に実行されることがあります)。 その後、ユーザーアカウントをライフサイクルを通じて管理するディレクトリ同期ツール (Forefront Identity Manager、FIM など) が必要になります。
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Exchange Online を使用する Skype for Business リソース フォレスト トポロジの複数フォレスト
<a name="BKMK_multipleforestopology"> </a>

このトポロジは「[Skype for Business リソース フォレスト トポロジの複数フォレスト](system-requirements.md#BKMK_multipleforestopology)」で説明されるトポロジと同様のものです。
  
このトポロジには、1つ以上のユーザーフォレストがあり、Skype for Business Server は専用リソースフォレストに展開されます。 Exchange Server は、同じリソースフォレストまたは別のフォレストに展開して、Exchange Online とのハイブリッド用に構成することができます。また、メールサービスは、オンプレミスアカウントの Exchange Online でのみ提供されます。 このトポロジで利用できる図はありません。
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>Skype for Business Online および Azure Active Directory Connect を使用するリソース フォレスト トポロジの複数フォレスト
<a name="BKMK_multipleforestopology"> </a>

![2 つの AD フォレスト (ユーザー フォレストとリソース フォレスト) があります。これらの 2 つのフォレストの間には、信頼関係が確立されています。これらの 2 つのフォレストは、Azure AD Connect を使用して Office 365 と同期されます。すべてのユーザーは、Office 365 経由で Skype for Business を利用できます。](../../SfbServer/media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
このシナリオでは、リソース フォレスト トポロジを使用するオンプレミスの複数のフォレストが存在し、Active Directory フォレスト間には完全な信頼関係がある場合を考えます。オンプレミス ユーザー フォレストと Office 365 との間のアカウントを同期するために、Azure Active Directory Connect ツールが使用されます。
  
 組織にも Office 365 があり、 [Azure Active Directory Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)を使用して、オンプレミスアカウントを office 365 と同期します。 Skype for Business が有効になっているユーザーは、Office 365 および Skype for Business Online によって有効にされています。 Skype for Business Server はオンプレミスでは展開されません。
  
シングルサインオン認証は、ユーザーフォレストにある Active Directory フェデレーションサービスファームによって提供されます。
  
このシナリオでは、exchange をオンプレミス、Exchange Online、ハイブリッド Exchange ソリューション、または Exchange が展開されていない状態で展開することがサポートされています。 (図面には Exchange のオンプレミスのみが表示されますが、その他の Exchange ソリューションも完全にサポートされています)。
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>ハイブリッド Skype for Business を使用するリソース フォレスト トポロジの複数フォレスト
<a name="BKMK_multipleforestopology"> </a>

このシナリオでは、1つ以上のオンプレミスのユーザーフォレストがあり、Skype for Business は専用のリソースフォレストに展開され、skype for business Online とのハイブリッドモード用に構成されています。 Exchange Server は、同じリソースフォレストまたは別のフォレストに展開することができます。また、exchange Online とのハイブリッド用に構成することもできます。 または、社内アカウントの Exchange Online によってのみ、メールサービスが提供されることがあります。
  
詳細については、「[ハイブリッド Skype For business 用にマルチフォレスト環境を構成](../../SfbServer/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md)する」を参照してください。
  
## <a name="domain-name-system-dns"></a>ドメイン ネーム システム (DNS)
<a name="DNS"> </a>

Skype for Business Server 2019 には DNS が必要です。次の理由が考えられます。
  
- DNS によって、Skype for Business Server 2019 は内部サーバーまたはプールを検出できるため、サーバー間の通信が可能になります。
    
- DNS により、クライアントコンピューターは SIP トランザクションに使用されているフロントエンドプールまたは Standard Edition サーバーを検出できます。
    
- 会議用の簡易 URL と、これらの会議をホストするサーバーが関連付けられます。
    
- DNS を使うと、外部ユーザーとクライアントコンピューターが、インスタントメッセージング (IM) または会議のために、エッジサーバーまたは HTTP リバースプロキシに接続できます。
    
- ログインしていないユニファイドコミュニケーション (UC) デバイスでは、デバイス更新 web サービスが実行されているフロントエンドプールまたは Standard Edition サーバーで、更新プログラムを取得してログを送信できます。
    
- DNS を使用すると、モバイル クライアントでは、デバイス設定で URL を手動入力しなくても Web サービス リソースを自動的に検出できます。
    
- これは DNS の負荷分散で使われます。
    
Skype for Business Server 2019 は、国際化ドメイン名 (Idn) をサポートしていないことに注意してください。
  
また、DNS の名前は、Skype for Business Server 2019 で使用されているサーバー上で構成されているコンピューター名と同じであることを覚えておくことが非常に重要です。 具体的には、環境内に短い名前を設定することはできません。また、トポロジビルダーの Fqdn が必要です。
  
これは、既にドメインに参加しているコンピューターには関係ありませんが、ドメインに参加していないエッジサーバーがある場合は、既定値としてドメインサフィックスが含まれていない可能性があります。 この問題について、DNS、またはエッジサーバー、または Skype for Business Server 2019 サーバーまたはプールのどちらでも、そうしないようにしてください。
  
必ず Unicode 文字またはアンダースコアは使用しないでください。 標準文字 (A-z、a-z、0-9、ハイフン) は、外部 DNS と公共の証明機関によってサポートされています (証明書の SN に Fqdn を割り当てる必要があるため、覚えておくことが重要です)。名前を付けると、問題が発生しやすくなります。これについては、最初にご注意ください。
  
ネットワークの DNS 要件に関するその他の情報については、「計画」ドキュメントの「[Networking](../../SfbServer/plan-your-deployment/network-requirements/network-requirements.md)」を参照してください。
  
## <a name="certificates"></a>証明書
<a name="Certs"> </a>

展開の前の最も重要な作業の 1 つは、証明書を用意することです。 Skype for Business Server 2019 には、トランスポート層セキュリティ (TLS) および相互トランスポート層セキュリティ (MTLS) 接続用の公開キー基盤 (PKI) が必要です。 基本的に、標準化された方法で安全に通信するために、Skype for Business Server は証明機関 (Ca) によって発行された証明書を使用します。
  
Skype for Business Server 2019 では、次のような用途で証明書が使用されます。
  
- クライアントとサーバー間の TLS 接続
    
- サーバー間の MTLS 接続
    
- パートナーの自動 DNS 検出を使ったフェデレーション
    
- インスタント メッセージング (IM) 用のリモート ユーザー アクセス
    
- 音声/ビデオ (AV) セッション、アプリケーション共有、および会議への外部ユーザー アクセス
    
- Web アプリケーションと Outlook Web Access (OWA) との会話
    
したがって、証明書の計画は必須です。 次に、証明書を要求するときに考慮しておく必要がある事項の一覧を見てみましょう。
  
- すべてのサーバー証明書がサーバーの承認 (サーバー EKU) をサポートしている必要がある。
    
- すべてのサーバー証明書に CRL 配布ポイント (CDP) を含める必要がある。
    
- すべての証明書が、オペレーティング システムでサポートされている署名アルゴリズムによって署名されている必要がある。 Skype for Business Server 2019 は、ダイジェストのサイズ (224、256、384、512ビット) の SHA-1 および SHA-1 スイートをサポートしており、オペレーティングシステムの要件を満たしているか、超えています。
    
- 自動登録は、Skype for Business Server 2019 を実行している内部サーバーでサポートされています。
    
- 自動登録は、Skype for Business Server 2019 Edge サーバーではサポートされていません。
    
> [!NOTE]
> RSASSA-PSS 署名アルゴリズムの使用はサポートされておらず、数ある問題の中でも、ログイン時のエラーや着信転送時の問題につながる可能性があります。 
  
- 暗証キーの長さとして 1024、2048、4096 がサポートされます。2048 以上のキーの長さはお勧めしません。
    
- 既定のダイジェストまたはハッシュ アルゴリズムは RSA です。ECDH_P256、ECDH_P384、ECDH_P521 のハッシュ アルゴリズムもサポートされます。
    
これは非常に重要であり、CA から証明書を要求することによって、さまざまなレベルの快適さがあります。 お客様の計画をできるだけ簡単にするために、以下のガイダンスをさらに紹介します。
  
### <a name="certificates-for-your-internal-servers"></a>内部サーバー用の証明書

ほとんどの内部サーバーには証明書が必要ですが、ほとんどの場合、内部 CA (ドメインにある CA) から証明書を取得します。 必要に応じて、外部 CA (インターネット上にある CA) からこれらの証明書を要求することができます。 どのパブリック CA にアクセスすればよいか迷っている場合は、[ユニファイドコミュニケーション証明書パートナー](/SkypeForBusiness/certification/services-ssl)の一覧を確認できます。
  
また、Skype for Business Server 2019 が他のアプリケーションやサーバー (Microsoft Exchange Server など) と通信する場合は、証明書が必要になります。 これは明らかに、他のアプリやサーバーでサポートされている方法で使用できる証明書である必要があります。 Skype for Business Server 2019 およびその他の Microsoft 製品は、サーバー間の認証と承認のための Open Authorization (OAuth) プロトコルをサポートしています。 この項目に興味をお持ちの場合は、OAuth および Skype for Business Server 2019 のその他の計画記事をご覧ください。
  
Skype for Business Server 2019 には、(必要256とせずに) SHA-1 暗号化ハッシュ関数を使って署名された証明書のサポートも含まれています。 SHA-256 を使用する外部アクセスをサポートするには、SHA-256 を使用するパブリック CA が外部証明書を発行する必要があります。
  
わかりやすくするために、標準エディションサーバー、フロントエンドプール、その他の役割の証明書要件を、例として使用されている架空の contoso.com を使用して、次の表に示します (これについては別の方法を使用している可能性があります)。お客様の環境)。 これらはすべて、標準の web サーバー証明書であり、エクスポートできない秘密キーが含まれています。 その他の注意事項:
  
- サーバーの拡張キー使用法 (EKU) は、証明書ウィザードを使って証明書を要求するときに自動的に構成されます。
    
- 各証明書のフレンドリ名は、コンピューター ストアで一意である必要があります。
    
- 以下のサンプル名に従って、DNS で sipinternal.contoso.com または sipexternal.contoso.com を構成している場合は、証明書のサブジェクト代替名 (SAN) に追加する必要があります。
    
Standard Edition サーバーの証明書:
  
|**証明書**|**サブジェクト名/共通名**|**サブジェクトの別名**|**例**|**コメント**|
|:-----|:-----|:-----|:-----|:-----|
|Default  <br/> |プールの FQDN  <br/> |プールの FQDN およびサーバーの FQDN  <br/> SIP ドメインが複数あり、自動クライアント構成が有効な場合は、証明書ウィザードによって、サポートされている各 SIP ドメインの FQDN が検出され、追加されます。  <br/> このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密なドメイン ネーム システム (DNS) マッチングが必要な場合は、sip.sipdomain のエントリ (所有する各 SIP ドメイン用) も必要となります。  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com  <br/> このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS マッチングが必要な場合は、SAN=sip.contoso.com、SAN=sip.fabrikam.com も必要です。  <br/> |Standard Edition サーバーでは、サーバーの FQDN はプールの FQDN と同じです。  <br/> このウィザードでは、セットアップ時に指定した SIP ドメインが検出され、サブジェクトの別名に自動的に追加されます。  <br/> また、この証明書はサーバー間認証でも使用できます。  <br/> |
|内部 Web  <br/> |サーバーの FQDN  <br/> |次のうちのすべて:  <br/> •内部 web FQDN (サーバーの FQDN と同じ)  <br/> および  <br/> •単純な Url を満たす  <br/> •ダイヤルインの簡単な URL  <br/> •管理者 simple URL  <br/> または  <br/> •単純な Url のワイルドカードエントリ  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> ワイルドカード証明書使用時:  <br/> SN = se01;SAN = se01;SAN =\*contoso.com  <br/> |トポロジビルダーでは、内部 web FQDN を上書きすることはできません。  <br/> 複数の会議の単純な Url がある場合は、それらをすべて San として含める必要があります。  <br/> 簡易 URL エントリではワイルドカード エントリがサポートされます。  <br/> |
|外部 Web  <br/> |サーバーの FQDN  <br/> |次のうちのすべて:  <br/> •外部 web FQDN  <br/> および  <br/> •ダイヤルインの簡単な URL  <br/> • SIP ドメインあたりの単純な Url を満たす  <br/> または  <br/> •単純な Url のワイルドカードエントリ  <br/> |SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> ワイルドカード証明書使用時:  <br/> SN = se01;SAN = webcon01;SAN =\*contoso.com  <br/> |複数の条件を満たす単純な Url がある場合は、それらのすべてを対象の代替名として含める必要があります。  <br/> 簡易 URL エントリではワイルドカード エントリがサポートされます。  <br/> |
   
フロントエンドプールのフロントエンドサーバー用の証明書:
  
|**証明書**|**サブジェクト名/共通名**|**サブジェクトの別名**|**例**|**コメント**|
|:-----|:-----|:-----|:-----|:-----|
|既定  <br/> |プールの FQDN  <br/> |プールの FQDN およびサーバーの FQDN  <br/> SIP ドメインが複数あり、自動クライアント構成が有効な場合は、証明書ウィザードによって、サポートされている各 SIP ドメインの FQDN が検出され、追加されます。  <br/> このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密なドメイン ネーム システム (DNS) マッチングが必要な場合は、sip.sipdomain のエントリ (所有する各 SIP ドメイン用) も必要となります。  <br/> |SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com   <br/> このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS マッチングが必要な場合は、SAN=sip.contoso.com、SAN=sip.fabrikam.com も必要です。  <br/> |このウィザードでは、セットアップ時に指定した SIP ドメインが検出され、サブジェクトの別名に自動的に追加されます。  <br/> また、この証明書はサーバー間認証でも使用できます。  <br/> |
|内部 Web  <br/> |プールの FQDN  <br/> |次のうちのすべて:  <br/> •内部 web FQDN (サーバーの FQDN とは異なります)  <br/> •サーバー FQDN  <br/> • Skype for Business プールの FQDN  <br/> および  <br/> •単純な Url を満たす  <br/> •ダイヤルインの簡単な URL  <br/> •管理者 simple URL  <br/> または  <br/> •単純な Url のワイルドカードエントリ  <br/> |SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> ワイルドカード証明書使用時:  <br/> SN = ee01;SAN = ee01;SAN =\*contoso.com  <br/> |複数の条件を満たす単純な Url がある場合は、それらのすべてを対象の代替名として含める必要があります。  <br/> 簡易 URL エントリではワイルドカード エントリがサポートされます。  <br/> |
|外部 Web  <br/> |プールの FQDN  <br/> |次のうちのすべて:  <br/> •外部 web FQDN  <br/> および  <br/> •ダイヤルインの簡単な URL  <br/> •管理者 simple URL  <br/> または  <br/> •単純な Url のワイルドカードエントリ  <br/> |SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> ワイルドカード証明書使用時:  <br/> SN = ee01;SAN = webcon01;SAN =\*contoso.com  <br/> |複数の条件を満たす単純な Url がある場合は、それらのすべてを対象の代替名として含める必要があります。  <br/> 簡易 URL エントリではワイルドカード エントリがサポートされます。  <br/> |
   
ディレクター用の証明書:
  
|**証明書**|**サブジェクト名/共通名**|**サブジェクトの別名**|**例**|
|:-----|:-----|:-----|:-----|
|既定  <br/> |ディレクター プール  <br/> |ディレクタープールの FQDN の fqdn。  <br/> このプールがクライアント用の自動ログオンサーバーであり、かつ厳密な DNS 一致がグループポリシーで必要となる場合は、sipdomain (SIP ドメインごとに) を入力する必要もあります。  <br/> |pool.contoso.com; SAN=dir01.contoso.com   <br/> このディレクタープールがクライアント用の自動ログオンサーバーであり、かつ厳密な DNS 一致がグループポリシーで必要な場合は、SAN = sip-pstn を使用する必要もあります。サン = sip-pstn  <br/> |
|内部 Web  <br/> |サーバーの FQDN  <br/> |次のうちのすべて:  <br/> •内部 web FQDN (サーバーの FQDN と同じ)  <br/> •サーバー FQDN  <br/> • Skype for Business プールの FQDN  <br/> および  <br/> •単純な Url を満たす  <br/> •ダイヤルインの簡単な URL  <br/> •管理者 simple URL  <br/> または  <br/> •単純な Url のワイルドカードエントリ  <br/> |SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> ワイルドカード証明書使用時:  <br/> SN = dir01;SAN = dir01 サン =\*. contoso.com  <br/> |
|外部 Web  <br/> |サーバーの FQDN  <br/> |次のうちのすべて:  <br/> •外部 web FQDN  <br/> および  <br/> • SIP ドメインあたりの単純な Url を満たす  <br/> •ダイヤルインの簡単な URL  <br/> または  <br/> •単純な Url のワイルドカードエントリ  <br/> |ディレクターの外部 web FQDN は、フロントエンドプールまたはフロントエンドサーバーと異なっている必要があります。  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> ワイルドカード証明書使用時:  <br/> SN = dir01;SAN = directorwebcon01 サン =\*. contoso.com  <br/> |
   
スタンドアロンの仲介サーバーの証明書:
  
|**証明書**|**サブジェクト名/共通名**|**サブジェクトの別名**|**例**|
|:-----|:-----|:-----|:-----|
|既定  <br/> |プールの FQDN  <br/> |プールの FQDN  <br/> プール メンバー サーバーの FQDN  <br/> |SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net  <br/> |
   
Survivable Branch Appliance 用の証明書 (特に、Skype for Business Server 2019 の Survivable Branch Appliance 2015):
  
|**証明書**|**サブジェクト名/共通名**|**サブジェクトの別名**|**例**|
|:-----|:-----|:-----|:-----|
|Default  <br/> |アプライアンスの FQDN  <br/> |フェデレーション.\<SIPDOMAIN\> (SIP ドメインごとに1つのエントリしか必要ありません)  <br/> |SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
   
### <a name="certificates-for-external-user-access-edge"></a>外部ユーザー アクセス (エッジ) 用の証明書

Skype for Business Server 2019 では、access および web 会議エッジの外部インターフェイスに対する**1 つの公開証明書**と、エッジサーバー経由で提供される a/V 認証サービスをサポートしています。 通常、Edge 内部インターフェイスでは、内部 CA から発行されたプライベート証明書を使用しますが、必要に応じて、信頼できる CA から発行された公開証明書を使用することもできます。
  
またリバース プロキシ (RP) でも、パブリック証明書を使用して、RP からクライアントへの通信と RP から内部サーバーへの通信を、HTTP (厳密には TLS over HTTP) を使用して暗号化します。
  
### <a name="certificates-for-mobility"></a>モビリティ用の証明書

モバイルクライアントの自動検出をサポートしている場合、モバイルクライアントの自動検出をサポートするには、モバイルクライアントからのセキュリティで保護された接続をサポートするために、追加のサブジェクト代替名のエントリを追加する必要があります。
  
次の証明書では、自動検出には SAN 名が必要です。
  
- ディレクター プール
    
- フロントエンド プール
    
- リバース プロキシ
    
詳細は以下の表に記載されています。
  
ここでは、いくつかの事前計画を行うことができますが、モビリティを導入するのではなく、Skype for Business Server 2019 を展開したことがあります。これは、環境内に既に証明書がある場合に発生します。 通常、内部 CA を介した証明書の再発行は簡単ですが、パブリック CA のパブリック証明書を使用する場合は、多少コストが上がる可能性があります。
  
この情報が表示されていて、SIP ドメインが多数ある場合 (つまり、SAN をさらに追加するため)、HTTPS (既定値) ではなく、HTTP を使用するようにリバースプロキシを構成できます。構成)。 [モビリティ計画](../../SfbServer/plan-your-deployment/mobility.md)の記事については、こちらを参照してください。
  
ディレクタープールとフロントエンドプールの証明書の要件:
  
|**説明**|**SAN エントリ**|
|:-----|:-----|
|内部自動検出サービス URL  <br/> |SAN = lyncdiscoverinternal。\<sipdomain\>  <br/> |
|外部自動検出サービス URL  <br/> |SAN = lyncdiscover。\<sipdomain\>  <br/> |
   
また、SAN =\*を使うこともできます。\<sipdomain\>
  
リバース プロキシ (パブリック CA) の証明書の要件:
  
|**説明**|**SAN エントリ**|
|:-----|:-----|
|外部自動検出サービス URL  <br/> |SAN = lyncdiscover。\<sipdomain\>  <br/> |
   
この SAN を、リバース プロキシ上の SSL リスナーに割り当てられる証明書に割り当てる必要があります。
  
> [!NOTE]
> リバースプロキシリスナーは、外部 Web サービスの URL に対して San を使用する予定です。 ディレクターを展開した場合の例としては、「SAN = skypewebextpool01 and dirwebexternal.contoso.com」などがあります (これはオプションです)。 
  
## <a name="file-share"></a>ファイル共有
<a name="Fileshare"> </a>

Skype for Business Server 2019 では、すべてのファイルストレージに同じファイル共有を使用できます。 以下の点を考慮する必要があります。
  
- ファイル共有は、直接取り付け記憶域 (DAS) と記憶域ネットワーク (SAN) のいずれかに配置する必要があり、またファイル共有には、分散ファイル システム (DFS) だけでなくファイル ストア用の RAID (Redundant Array of Independent Disks) も含まれます。 Windows Server 2012 向け DFS について詳しくは、[この dfs のページ](https://technet.microsoft.com/library/jj127250.aspx)をご覧ください。
    
- ファイル共有の共有クラスターをお勧めします。 既にいずれかのバージョンを使用している場合は、Windows Server 2012 以降のバージョンをクラスター化する必要があります。

> [!Note]
> **最新の Windows の理由** 以前のバージョンには、すべての機能を有効にするための適切な権限がない場合があります。 クラスターアドミニストレーターを使用して、ファイル共有を作成できます。 詳細について[は、](https://support.microsoft.com/help/224967)このサポート記事の記事を参照してください。
    
> [!CAUTION]
> ファイル共有にネットワーク接続ストレージ (NAS) は使用できません。ファイル共有には、上記のいずれかの選択肢を利用してください。 このサポートの制限は、デバイスの共有ファイルシステムにアクセスする Windows Server ベースのコンピューターにファイルシステムの適応性を提供する必要がある、NAS デバイスの可変設計によって発生します。
  








