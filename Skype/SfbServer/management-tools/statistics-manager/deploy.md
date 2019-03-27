---
title: Skype for Business Server の Statistics Manager の展開
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 37b2bb9c-c5d4-4fb0-a976-670b7594b82f
description: '概要: は、Skype のビジネス サーバーの統計情報マネージャーを展開する方法の詳細については、このトピックを読みます。'
ms.openlocfilehash: 901720f87cf1c0bf78f558ed0d031bd41377799a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898259"
---
# <a name="deploy-statistics-manager-for-skype-for-business-server"></a>Skype for Business Server の Statistics Manager の展開
 
**の概要:** Skype のビジネス サーバーの統計情報マネージャーを展開する方法の詳細については、このトピックを参照してください。
  
 Skype ビジネス サーバーの統計情報マネージャーとは、Skype をビジネスのサーバーの稼働状態とパフォーマンスのデータをリアルタイムに表示できるようにする強力なツールです。 数秒ごとに数百のサーバー間でのパフォーマンス データをポーリングし、統計マネージャーの web サイトですぐに結果を表示できます。
  
統計マネージャーをインストールしようとすると、前に、ソフトウェア、ネットワーク、およびハードウェア要件を熟知していることを確認してください。 詳細については、 [Skype ビジネス サーバーの統計情報マネージャーの計画](plan.md)を参照してください。
  
> [!NOTE]
> 統計マネージャーの以前のバージョンからアップグレードする場合は、 [Skype のビジネス サーバーの統計マネージャーのアップグレード](upgrade.md)を参照してください。 
  
> [!NOTE]
> Statistics Manager の Web サイトはテスト済みで Internet Explorer 11 以降、Edge 20.10240 以降、Chrome 46 以降 (現在広く使用されているバージョン) で正常に動作します。 
  
ダウンロード可能な統計マネージャーを見つけることができます[https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload)。 
  
このトピックには次のセクションが含まれます。
  
- [Statistics Manager の展開](deploy.md#BKMK_Deploy)
    
- [展開のトラブルシューティング](deploy.md#BKMK_Troubleshoot)
    
- [自己署名証明書の作成](deploy.md#BKMK_SelfCert)
    
## <a name="deploy-statistics-manager"></a>Statistics Manager の展開
<a name="BKMK_Deploy"> </a>

統計マネージャーを展開するには、以下の手順を実行します。
  
1. リスナーのホスト コンピューターを準備します。その際は、Redis メモリ内キャッシュ システムをインストールすることと、適切な証明書をインストールしたことを確認することが必要です。
    
2. リスナー サービスをホスト コンピューターにインストールします。 
    
3. Web サイトをホスト コンピューターにインストールします。
    
4. 各 Skype をビジネスのサーバー コンピューターを監視するためにエージェントをインストールします。
    
5. 監視しているサーバーのトポロジをインポートします。
    
> [!NOTE]
> Redis、リスナー サービス、Web サイトは同一のホスト コンピューターにインストールされる必要があります。 ホスト ・ マシンが Skype のビジネス サーバーがインストールされていることを確認します。 
  
### <a name="prepare-the-listener-host-machine"></a>リスナーのホスト コンピューターの準備

ホスト コンピューターを準備するには、Redis メモリ内キャッシュ システムをインストールして、有効な証明書がコンピューター上にあることを確認する必要があります。 Microsoft は Redis 3.0 の最新の安定したビルドをインストールすることを推奨します。 統計マネージャーのバージョン 2.0 は、Redis 3.2.100 でテストされました。 
  
1. Redis の次のサイトからダウンロード: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis)。 
    
    符号なしのインストーラーをダウンロードできます。[https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)
    
    必要な場合、署名されたバイナリは、人気のあるパッケージ ・ マネージャー: [Nuget](https://www.nuget.org/packages/Redis-64/)と[Choclatey](https://chocolatey.org/packages/redis-64)。
    
   - 提供された msi を実行してプロンプトに従います。
    
   - ファイアウォールのルールを追加するチェック ボックスをオフにします。
    
2. リスナー サービスは証明書を必要とします。 信頼された証明機関によって署名された証明書があることを強くお勧めします。 
    
    ラボでのテスト目的で自己署名証明書を使用するような場合には、「[自己署名証明書の作成](deploy.md#BKMK_SelfCert)」を参照してください。
    
    エージェントが (チェーンの検証ではなく) 証明書の拇印の検証を使用することに注意してください。自己署名証明書を使用することが可能なため、証明書の完全な検証は行いません。
    
### <a name="install-the-listener-service"></a>リスナー サービスのインストール

StatsManPerfAgentListener.msi を実行し、次を指定するホスト ・ マシン上のリスナー サービスをインストールします。
  
1. 使用許諾契約書の内容を確認して、同意する場合は [**使用許諾契約書に同意します**] を選択して、[**次へ**] をクリックします。 
    
2. 次のページで、以下の情報を指定します。
    
   - **サービス パスワード:** これはリモート エージェントがリスナー サービスを認証するために使用するパスワードです。
    
   - **サービス ポート:** エージェントと通信するためにリスナーを使用する HTTPS ポート番号です。 インストール時に、このポート通過を許可するローカルのファイアウォールでは、URL の ACL が作成され、SSL 証明書は、このポートにバインドされます。 デフォルトは、8443 です。
    
   - **証明書の拇印:** これは、HTTPS プロトコルを暗号化するために、リスナーで使用する証明書の拇印です。 ネットワーク サービスには、秘密キーへの読み取りアクセスが必要です。
    
     [**選択...**] をクリックして拇印を選びます。
    
     証明書マネージャーを使用するか、次の PowerShell コマンドを使用して証明書の拇印を見つけることができます。
    
   ```
   Get-ChildItem -path cert:\LocalMachine\My
   ```

   - **インストール ディレクトリ:** これは、バイナリをインストールするディレクトリです。 既定値から、[**参照...** ] ボタンを使用して変更する場合があります。
    
   - **AppData ディレクトリ:** これは、ログ フォルダーとその他のデータを格納するディレクトリです。 既定値から変更することがあります。 それは削除されませんをアンインストールします。
    
3. [**インストール**] をクリックします。
    
インストールを検証するには、次の手順を実行します。
  
1. ブラウザーを開き、下に移動https://localhost:\<service-port\>/healthcheck/
    
    既定では、(別のポートを指定済みでない限り) サービス ポートは 8443 です。
    
2. リスナーが適切にインストールされていることを確認するには、次について調べます。
    
   - 正常性チェックのページが表示される場合は、リスナーのインストールは正常に完了しています。
    
   - KnownServersCount が 1 以上である場合は、Redis への接続が確立されます。
    
   - 数秒間経過してから、および少なくとも 1 つのエージェントがインストールされてから、ValuesWritten カウンターの数値が増えていることを確認します。
    
### <a name="install-the-website"></a>Web サイトのインストール

( [Skype ビジネス サーバーに、リアルタイムの統計情報マネージャー (64 ビット)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)に含まれている) StatsManWebSite.msi を実行して、ホスト ・ マシン上の web サイトをインストールし、次を指定します。
  
1. 使用許諾契約書の内容を確認して、同意する場合は [**使用許諾契約書に同意します**] を選択して、[**次へ**] をクリックします。 
    
2. 次のページで、以下の情報を指定します。
    
   - **サービス ポート:** Web サイト上でリッスンするポート番号です。 バインドの IIS マネージャーを使用して後で変更できます。 インストール時に、ローカル ファイアウォールによってこのポートが許可されます。
    
   - **インストール ディレクトリ:** これは、バイナリのインストール先となるディレクトリです。 既定値から、[**参照...** ] ボタンを使用して変更する場合があります。
    
   - **AppData ディレクトリ:** これは、ログ フォルダーとその他のデータを格納するディレクトリです。 既定値から変更することがあります。 それは削除されませんをアンインストールします。
    
3. [**インストール**] をクリックします。
    
Web サイトを表示するには、ブラウザーを開きに移動: http://localhost、webport\>とします。
  
状態情報のみを表示、ブラウザーを開きに移動する: http://localhost:\<webport\>/healthcheck/。
  
既定では、Web ポート番号は 8080 です。 IIS マネージャーを使用して Web サイトのポートのバインドを変更できます。
  
Web インストーラーは StatsManWebSiteUsers というローカル セキュリティ グループを追加します。 アカウントをこのセキュリティ グループに追加して Web サイトへのアクセスを付与することができます。 
  
### <a name="install-the-agents"></a>エージェントのインストール

各 Skype で、StatsManPerfAgent.msi を実行し、次を指定することによって、監視するビジネスのサーバーにエージェントをインストールします。
  
1. 使用許諾契約書の内容を確認して、同意する場合は [**使用許諾契約書に同意します**] を選択して、[**次へ**] をクリックします。 
    
2. 次のページで、以下の情報を指定します。
    
   - **サービス パスワード:** これはリモート エージェントがリスナー サービスを認証するために使用するパスワードです。
    
   - **サービスの URI:** これは、リスナーが存在する URI です。 それを使用する必要があります、https://name:portの形式です。
    
     NETBIOS 名または FQDN を使用できます。 **件名**またはリスナー サービスに証明書の**サブジェクト代替名**としても指定されている名前を使用することができますが、これは要件ではありません。
    
   - **サービスの拇印:** これは、リスナーを使用して SSL 証明書の拇印です。 (自己署名証明書を使用することが可能なため、証明書の完全な検証は行いません。 )
    
   - **インストール ディレクトリ:** これは、バイナリをインストールするディレクトリです。 既定値から、[**参照...** ] ボタンを使用して変更する場合があります。
    
   - **AppData ディレクトリ:** これは、ログ フォルダーと暗号化された password.txt ファイルを保存するディレクトリです。 ことがあります、ありがとうございます、デフォルトから変更します。 それは削除されませんをアンインストールします。
    
3. [**インストール**] をクリックします。
    
エージェントを多数のコンピューターにインストールしている場合、その操作を無人モードで実行する方が望ましい場合が考えられます。例:   
  
```
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_  STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a>トポロジのインポート
<a name="BKMK_ImportTopology"> </a>

統計マネージャーのインストールし、実行している場合、インポートする必要がビジネスのサーバー トポロジの Skype ある、その統計マネージャーを知っているサイト、プール、および各サーバーの役割です。 ビジネス サーバー トポロジの場合、Skype をインポートするには、 [Get CsPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps)コマンドレットを使用して、組織で使用されている各プールに関する情報を取得し、統計マネージャーにこの情報をインポートします。
  
ビジネス サーバー トポロジの Skype をインポートするのには以下の手順を実行します。
  
1. ビジネス サーバーの PowerShell コマンドレットの Skype のあるホスト。
    
    a. 次のコマンドを実行します。 
    
   ```
   Get-CsPool | Export-Clixml -Path mypoolinfo.xml
   ```
    b. リスナーを実行しているサーバーに"mypoolinfo.xml"ファイルをコピーします。
    
2. リスナーを実行するホストで、以下の操作を行います。
    
   a. PowerShell を実行します。
    
   b. リスナーがインストールされているディレクトリに移動します。 既定値は次のとおりです。 
    
   ```
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

3. どのサーバーが追加および更新されているかを確認するには、次のコマンドを実行します。
    
   ```
    .\Update-StatsManServerInfo.ps1 -CsPoolFile  <path to mypoolinfo.xml>
   ```

次のコマンドで、すべてのオプションを表示することができます。
  
```
Get-Help .\Update-StatsManServerInfo.ps1 -Detailed 
```

読み込まれた現在のサーバーの情報を表示するには、次のスクリプトを実行します。 
  
```
.\Get-StatsManServerInfo.ps1
```

--ビジネス サーバー トポロジを Exchange Server に、Skype ではないサーバーを監視したい場合たとえば--リスナーを実行しているホスト上の 1 台のサーバーのインポートを実行できます。 単一サーバーのインポートを実行するには、次の手順を実行します。
  
1. リスナーがインストールされているディレクトリに移動します。 既定値は次のとおりです。 
    
   ```
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

2. 次のコマンドを実行します。
    
   ```
    .\Update-StatsManServerInfo.ps1 -HostName <hostname> -SiteName <name of site> -PoolName <poolName> -Roles <role1>[,<role2>,<roleN>]
   ```

## <a name="troubleshoot-your-deployment"></a>展開のトラブルシューティング
<a name="BKMK_Troubleshoot"> </a>

エージェントを開始できない場合は、次について確認します。 
  
- エージェントが統計情報マネージャーでを登録されているでしょうか。
    
1. 	トポロジのインポートの手順に従っていることを確認します。「[Import the topology (英語)](deploy.md#BKMK_ImportTopology)」を参照してください。  
    
2. このトポロジ内のリストに記述されていないサーバーにエージェントがある場合 (たとえば、SQL AlwaysOn クラスタ内のノード)、「[トポロジのインポート](deploy.md#BKMK_ImportTopology)」にある手順に従ってエージェントを手動で追加する必要があります。
    
- エージェントがリスナーと連絡することができるか
    
1. リスナー サービスが実行中であることを確認します。 
    
    実行中でない場合は、Redis が実行していることを確認して、リスナーの再起動を試行します。
    
2. リスナー サービスには、ポートとポートと、エージェント コンピューターが通信できることを確認ください。
    
- 統計マネージャーがデータを収集していることを確認するには、次のように CSV ファイルを確認できます。 
    
    次のコマンドで、カウンターのストレージ名を取得します。 
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    次のコマンドで指定したカウンターの値を取得します。 
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

アプリケーション イベント ログに表示されるすべてのイベントに関する情報は、 [Skype のビジネス サーバーの統計マネージャーのトラブルシューティング](troubleshoot.md)を参照してください。
  
## <a name="create-a-self-signed-certificate"></a>自己署名証明書の作成
<a name="BKMK_SelfCert"> </a>

Microsoft は、必ず信頼済みの認証局によって署名された証明書を使用することを推奨します。 ただし、自己署名証明書をテストの目的で使用する場合は、次の手順を実行してください。 
  
1. PowerShell コンソールから、管理者としてログ オンしている状態で、次を入力します。
    
   ```
   New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
   ```

2. 型`certlm.msc`。 これにより、ローカル コンピューターの証明書マネージャーが開きます。
    
3. **個人**に移動して、**証明書**を開きます。
    
4. 右クリックして**StatsManListener -\>すべてのタスク -\>秘密キーの管理...**
    
5. [**追加**] をクリックします。
    
6. [**選択するオブジェクト名を入力してください**] ボックスに、「Network Service」と入力します。
    
7. [**OK**] をクリックします。
    
8. [**フル コントロール**] で、[**許可**] チェック ボックスをオフにします。(読み取りアクセス権のみが必要です。)
    
9. [**OK**] をクリックします。
    
## <a name="for-more-information"></a>関連情報
<a name="BKMK_SelfCert"> </a>

詳細については、以下を参照してください。
  
- [Skype for Business Server の Statistics Manager の計画](plan.md)
    
- [Skype for Business Server の Statistics Manager のアップグレード](upgrade.md)
    
- ß の[Skype ビジネス サーバーの統計マネージャーのトラブルシューティング](troubleshoot.md)
