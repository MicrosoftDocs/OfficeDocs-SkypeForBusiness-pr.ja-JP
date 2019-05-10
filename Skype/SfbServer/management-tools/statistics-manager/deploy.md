---
title: Skype for Business Server の統計情報マネージャーの展開
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
description: '概要: このトピックでは、Skype for Business Server の統計情報マネージャーを展開する方法について説明します。'
ms.openlocfilehash: c70bb596914142fb03e87ccd7e2f1df606aac31f
ms.sourcegitcommit: b2acf18ba6487154ebb4ee46938e96dc56cb2c9a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2019
ms.locfileid: "33864905"
---
# <a name="deploy-statistics-manager-for-skype-for-business-server"></a>Skype for Business Server の統計情報マネージャーの展開
 
**概要:** このトピックでは、Skype for Business Server の 統計情報マネージャーを展開する方法について説明します。
  
 Skype for Business Server 統計情報マネージャーは、リアルタイムでビジネス サーバーの状態とパフォーマンス データを Skype で表示する事ができる強力なツールです。   数秒ごとに数百のサーバーのパフォーマンス データをポーリングでき、その結果をすぐに統計情報 マネージャーのウェブ サイト上に表示することができます。
  
統計情報マネージャーをインストールする前に、ソフトウェア、ネットワーク、ハードウェアの要件について理解しておいてください。 詳細については、[Skype for Business Server の統計情報マネージャーの計画](plan.md)を参照ください。
  
> [!NOTE]
> 統計情報マネージャーを以前のバージョンからアップグレードする場合は、[Skype for Business Server の統計情報マネージャーのアップグレード](upgrade.md)を参照してください。 
  
> [!NOTE]
> 統計情報マネージャーのウェブ サイトはテスト済みで Internet Explorer 11 以降、Edge 20.10240 以降、Chrome 46 以降 (現在広く使用されているバージョン) で正常に動作します。 
  
下記のリンクで統計情報マネージャーをダウンロードできます。[https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload) 
  
このトピックには次のセクションが含まれます。
  
- [Statistics Manager の展開](deploy.md#BKMK_Deploy)
    
- [展開のトラブルシューティング](deploy.md#BKMK_Troubleshoot)
    
- [自己署名証明書の作成](deploy.md#BKMK_SelfCert)
    
## <a name="deploy-statistics-manager"></a>Statistics Manager の展開
<a name="BKMK_Deploy"> </a>

統計情報マネージャーを展開するには、次の手順を実行します。
  
1. リスナーのホスト コンピューターを準備します。その際は、Redis メモリ内キャッシュ システムをインストールすることと、適切な証明書をインストールしたことを確認することが必要です。
    
2. リスナー サービスをホスト コンピューターにインストールします。 
    
3. Web サイトをホスト コンピューターにインストールします。
    
4. 監視したい各 Skype for Business Server にエージェントをインストールします。
    
5. 監視しているサーバーのトポロジをインポートします。
    
> [!NOTE]
> Redis、リスナー サービス、Web サイトは同一のホスト コンピューターにインストールされる必要があります。 ホスト コンピューターに Skype for Business Server がインストールされていないことを確認してください。 
  
### <a name="prepare-the-listener-host-machine"></a>リスナーのホスト コンピューターの準備

ホスト コンピューターを準備するには、Redis メモリ内キャッシュ システムをインストールして、有効な証明書がコンピューター上にあることを確認する必要があります。 Microsoft は Redis 3.0 の最新の安定したビルドをインストールすることを推奨します。 統計情報マネージャー バージョン 2.0 は Redis 3.2.100でテストされました。 
  
1. 下記のサイトから Redis をダウンロードしてください。[https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis) 
    
    下記のサイトから符号なしのインストーラーをダウンロードできます。[https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)
    
    必要な場合には、下記のサイトから符号付きのバイナリを、有名なパッケージ マネージャー経由で入手できます。[Nuget](https://www.nuget.org/packages/Redis-64/) と [Choclatey](https://chocolatey.org/packages/redis-64)
    
   - 提供された msi を実行してプロンプトに従います。
    
   - ファイアウォールのルールを追加するチェック ボックスをオフにします。
    
2. リスナー サービスは証明書を必要とします。 Microsoft は、信用のある認証機関によって署名された証明書を使用することを強く推奨します。 
    
    ラボでのテスト目的で自己署名証明書を使用するような場合には、「[自己署名証明書の作成](deploy.md#BKMK_SelfCert)」を参照してください。
    
    エージェントが (チェーンの検証ではなく) 証明書の拇印の検証を使用することに注意してください。自己署名証明書を使用することが可能なため、証明書の完全な検証は行いません。
    
### <a name="install-the-listener-service"></a>リスナー サービスのインストール

StatsManPerfAgentListener.msi を実行し、以下を指定することによって、ホスト コンピューターにリスナー サービスをインストールします。
  
1. 使用許諾契約書の内容を確認して、同意する場合は [**使用許諾契約書に同意します**] を選択して、[**次へ**] をクリックします。 
    
2. 次のページで、以下の情報を指定します。
    
   - **サービス パスワード:** これはリモート エージェントがリスナー サービスを認証するために使用するパスワードです。
    
   - **Service Port:** これはリスナーがエージェントと通信するために使用する HTTPS ポート番号です。 インストール時に、このポートはローカル ファイアウォールによって許可され、URL ACL が作成され、SSL 証明書がこのポートに適用されます。 デフォルトは 8443 です。
    
   - **証明書の拇印:** これはリスナーが HTTPS プロトコルを暗号化するために使用する証明書の拇印です。 ネットワーク サービスは、秘密キーへの読み取りアクセスが必要です。
    
     [**選択...**] をクリックして拇印を選びます。
    
     証明書マネージャーを使用するか、次の PowerShell コマンドを使用して証明書の拇印を見つけることができます。
    
   ```
   Get-ChildItem -path cert:\LocalMachine\My
   ```

   - **インストール ディレクトリ:** これはバイナリがインストールされるディレクトリです。 **ブラウズ...** ボタンを使用することによって、デフォルトを変更できます。
    
   - **AppData ディレクトリ:** これはログ フォルダーとその他のデータが保存されるディレクトリです。 デフォルトを変更できます。 アンインストールしても、削除されません。
    
3. **[インストール]** をクリックします。
    
インストールを検証するには、次の手順を実行します。
  
1. ブラウザーを開き、https://localhost:\<service-port\>/healthcheck/ に移動します。
    
    既定では、(別のポートを指定済みでない限り) サービス ポートは 8443 です。
    
2. リスナーが適切にインストールされていることを確認するには、次について調べます。
    
   - 正常性チェックのページが表示される場合は、リスナーのインストールは正常に完了しています。
    
   - KnownServerCount が 1 以上の場合は、Redis への接続が確立されます。
    
   - 数秒間経過してから、および少なくとも 1 つのエージェントがインストールされてから、ValuesWritten カウンターの数値が増えていることを確認します。
    
### <a name="install-the-website"></a>Web サイトのインストール

([Skype for Business Server、リアルタイム 統計情報マネージャー (64-bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)に含まれる) StatsManWebSite.msi を実行し、ホスト コンピューターにウェブサイトをインストールし、以下の指定をします。
  
1. 使用許諾契約書の内容を確認して、同意する場合は [**使用許諾契約書に同意します**] を選択して、[**次へ**] をクリックします。 
    
2. 次のページで、以下の情報を指定します。
    
   - **サービス ポート:** これはウェブサイトがリッスンするポート番号です。 この番号は後で IIS マネージャーのバインドを使用して変更できます。 インストール時に、このポートはローカル ファイアウォールによって許可されます。
    
   - **インストール ディレクトリ:** これはバイナリがインストールされるディレクトリです。 **ブラウズ...** ボタンを使用することによって、デフォルトを変更できます。
    
   - **AppData ディレクトリ:** これはログ フォルダーとその他のデータが保存されるディレクトリです。 デフォルトを変更できます。 アンインストールしても、削除されません。
    
3. **[インストール]** をクリックします。
    
ウェブサイトを表示するには、ブラウザーを開いてhttp://localhost、ウェブ ポート\>/ に移動します。
  
状態の情報のみを表示するには、ブラウザーを開いてhttp://localhost:\<webport\>/healthcheck/に移動します。
  
既定では、Web ポート番号は 8080 です。 IIS マネージャーを使用して Web サイトのポートのバインドを変更できます。
  
Web インストーラーは StatsManWebSiteUsers というローカル セキュリティ グループを追加します。 アカウントをこのセキュリティ グループに追加して Web サイトへのアクセスを付与することができます。 
  
### <a name="install-the-agents"></a>エージェントのインストール

StatsManPerfAgent.msi を実行して以下を指定することによって、監視したい各 Skype for Business Server にエージェントをインストールします。
  
1. 使用許諾契約書の内容を確認して、同意する場合は [**使用許諾契約書に同意します**] を選択して、[**次へ**] をクリックします。 
    
2. 次のページで、以下の情報を指定します。
    
   - **サービス パスワード:** これはリモート エージェントがリスナー サービスを認証するために使用するパスワードです。
    
   - **サービス URI:** これはリスナーが存在する URI です。 https://name:portのフォーマットを使う必要があります。
    
     NETBIOS の名前または FQDN を使用できます。 リスナー サービスの証明書の**Subject** または **Subject Alternative Names** としても指定されている名前を使用できますが、これは必須ではありません。
    
   - **サービス 拇印:** これはリスナーが使用している SSL 証明書の拇印です。 エージェントはリスナーを認証するためにこの拇印を使用します。 (自己署名証明書を使用することが可能なため、証明書の完全な検証は行いません。)
    
   - **インストール ディレクトリ:** これはバイナリがインストールされるディレクトリです。 **ブラウズ...** ボタンを使用することによって、デフォルトを変更できます。
    
   - **AppData ディレクトリ:** これはログ フォルダーと暗号化された password.txt ファイルが保存されるディレクトリです。 ディフォルトから変更することができます。 アンインストールしても、削除されません。
    
3. **[インストール]** をクリックします。
    
エージェントを多数のコンピューターにインストールしている場合、その操作を無人モードで実行する方が望ましい場合が考えられます。例: 
  
```
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_  STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a>トポロジのインポート
<a name="BKMK_ImportTopology"> </a>

統計情報マネージャーがインストールされ起動した後で、統計情報マネージャーが、各サーバーのサイト、プール、ロールを認識できるようにするため、Skype for Business Server トポロジをインポートする必要があります。 Skype for Business Server トポロジをインポートするには、[Get-CsPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) コマンドレットを使用して、組織で使用中の各プールについての情報を検索し、その情報を統計情報マネージャーにインポートします。
  
Skype for Business Server トポロジをインポートするには、以下の手順を実行します。
  
1. Skype for Business Server PowerShell コマンドレットのあるホスト：
    
    a. 次のコマンドを実行します。 
    
   ```
   Get-CsPool | Export-Clixml -Path mypoolinfo.xml
   ```
    b. "mypoolinfo.xml" ファイルを、リスナーを実行するサーバーにコピーします。
    
2. リスナーを実行するホスト：
    
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

現在のインポート済みのサーバー情報を表示するには、次のスクリプトを実行します。 
  
```
.\Get-StatsManServerInfo.ps1
```

Skype for Business Server トポロジにないサーバー (例えば Exchange Server) を監視する場合には、リスナーを実行するホスト上で単一サーバーのインポートができます。 単一サーバーのインポートを実行するには、次の手順を実行します。
  
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

エージェントを開始できない場合は、以下のことを確認します。 
  
- 統計情報 マネージャーにエージェントが登録されているか？
    
1. 	トポロジのインポートの手順に従っていることを確認します。「[Import the topology (英語)](deploy.md#BKMK_ImportTopology)」を参照してください。  
    
2. このトポロジ内のリストに記述されていないサーバーにエージェントがある場合 (たとえば、SQL AlwaysOn クラスタ内のノード)、「[トポロジのインポート](deploy.md#BKMK_ImportTopology)」にある手順に従ってエージェントを手動で追加する必要があります。
    
- エージェントがリスナーと連絡することができるか
    
1. リスナー サービスが実行中であることを確認します。 
    
    実行中でない場合は、Redis が実行していることを確認して、リスナーの再起動を試行します。
    
2. ポートがリスナー サービスに対して開いていて、エージェントのコンピューターがポートと通信できることを確認します。
    
- 統計情報 マネージャーがデータを収集していることを確認するには、以下のように CSV ファイルを調べます。 
    
    次のコマンドで、カウンターのストレージ名を取得します。 
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    次のコマンドで指定したカウンターの値を取得します。 
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

アプリケーション イベント ログで確認できるすべてのイベントについての情報は、[Skype for Business Server の統計情報マネージャーの トラブルシューティング ](troubleshoot.md)を参照してください。
  
## <a name="create-a-self-signed-certificate"></a>自己署名証明書の作成
<a name="BKMK_SelfCert"> </a>

Microsoft は、必ず信頼済みの認証局によって署名された証明書を使用することを推奨します。 ただし、自己署名証明書をテストの目的で使用する場合は、次の手順を実行してください。 
  
1. PowerShell コンソールから、管理者としてログ オンしている状態で、次を入力します。
    
   ```
   New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
   ```

2. `certlm.msc` と入力します。 これにより、ローカル コンピューターの証明書マネージャーが開きます。
    
3. **個人** に移動して、 **証明書**を開きます。
    
4. **StatsManListener-\>を右クリックして、すべてのタスク-\>秘密キーの管理…** の順に選択します。
    
5. [**追加**] をクリックします。
    
6. [**選択するオブジェクト名を入力してください**] ボックスに、「Network Service」と入力します。
    
7. **[OK]** をクリックします。
    
8. [**フル コントロール**] で、[**許可**] チェック ボックスをオフにします。(読み取りアクセス権のみが必要です。)
    
9. **[OK]** をクリックします。
    
## <a name="for-more-information"></a>関連情報
<a name="BKMK_SelfCert"> </a>

詳細については、以下を参照してください。
  
- [Skype for Business Server の統計情報マネージャーの計画](plan.md)
    
- [Skype for Business Server の統計情報マネージャーのアップグレード](upgrade.md)
    
- [Skype for Business Server の統計情報マネージャーのトラブルシューティング](troubleshoot.md) ß
