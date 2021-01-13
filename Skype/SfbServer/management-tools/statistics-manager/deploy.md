---
title: Skype for Business Server の統計情報マネージャーの展開
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
ms.collection: IT_Skype16
ms.assetid: 37b2bb9c-c5d4-4fb0-a976-670b7594b82f
description: '概要: このトピックでは、Skype for Business Server の Statistics Manager を展開する方法について説明します。'
ms.openlocfilehash: 79e07c29a5df4a5da239687708a9bb52e995d191
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814817"
---
# <a name="deploy-statistics-manager-for-skype-for-business-server"></a>Skype for Business Server の統計情報マネージャーの展開
 
**概要:** このトピックでは、Skype for Business Server の Statistics Manager を展開する方法について説明します。
  
 Skype for Business Server の Statistics Manager は、Skype for Business Server の正常性とパフォーマンスのデータをリアルタイムで表示できる強力なツールです。 数秒ごとに数百のサーバーでパフォーマンス データをポーリングし、統計情報マネージャー Web サイトで即座に結果を表示できます。
  
Statistics Manager をインストールする前に、ソフトウェア、ネットワーク、およびハードウェアの要件を理解していることを確認してください。 詳細については [、「Plan for Statistics Manager for Skype for Business Server」を参照してください](plan.md)。
  
> [!NOTE]
> 以前のバージョンの Statistics Manager からアップグレードする場合は [、「Upgrade Statistics Manager for Skype for Business Server」を参照してください](upgrade.md)。 
  
> [!NOTE]
> 統計情報マネージャーの Web サイトは、Internet Explorer 11 以上、Edge 20.10240+ 、および Chrome 46+ (現在のバージョンの常緑バージョン) でテストされ、正しく動作します。 
  
統計情報マネージャーは、以下からダウンロードできます [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload) 。 
  
このトピックは、以下のセクションで構成されています。
  
- [Statistics Manager を展開する](deploy.md#BKMK_Deploy)
    
- [展開のトラブルシューティング](deploy.md#BKMK_Troubleshoot)
    
- [自己署名証明書を作成する](deploy.md#BKMK_SelfCert)
    
## <a name="deploy-statistics-manager"></a>Statistics Manager を展開する
<a name="BKMK_Deploy"> </a>

Statistics Manager を展開するには、次の手順を実行します。
  
1. Redis のメモリ内キャッシュ システムをインストールし、適切な証明書がインストールされていることを確認して、リスナーのホスト コンピューターを準備します。
    
2. リスナー サービスをホスト コンピューターにインストールします。 
    
3. ホスト コンピューターに Web サイトをインストールします。
    
4. 監視する各 Skype for Business Server コンピューターにエージェントをインストールします。
    
5. 監視するサーバーのトポロジをインポートします。
    
> [!NOTE]
> Redis、リスナー サービス、および Web サイトはすべて、同じホスト コンピューターにインストールする必要があります。 ホスト コンピューターに Skype for Business Server がインストールされていないか確認します。 
  
### <a name="prepare-the-listener-host-machine"></a>リスナーのホスト コンピューターを準備する

ホスト コンピューターを準備するには、Redis のメモリ内キャッシュ システムをインストールし、有効な証明書がコンピューター上にインストールされている必要があります。 Microsoft では、Redis 3.0 の最新の安定したビルドをインストールしてください。 Statistics Manager バージョン 2.0 は Redis 3.2.100 でテストされました。 
  
1. Redis を次のサイトからダウンロードします [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis) 。 
    
    署名されていないインストーラーは、次の場所からダウンロードできます。 [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)
    
    必要に応じて、署名されたバイナリは、一般的なパッケージ マネージャー [(Nuget](https://www.nuget.org/packages/Redis-64/) と数え切り取り) [を通じて利用できます](https://chocolatey.org/packages/redis-64)。
    
   - 指定された msi を実行し、プロンプトに従います。
    
   - ファイアウォール 規則を追加する場合は、このチェック ボックスをオンにしてください。
    
2. リスナー サービスには証明書が必要です。 Microsoft では、信頼できる証明機関によって署名された証明書を使用してください。 
    
    ラボでテスト目的で自己署名証明書を使用する場合は、「自己署名証明書を作成する」を [参照してください](deploy.md#BKMK_SelfCert)。
    
    エージェントは(チェーン検証ではなく) 証明書の拇印検証を使用します。 自己署名証明書を使用する可能性が高いので、証明書の完全な検証は実行しません。
    
### <a name="install-the-listener-service"></a>リスナー サービスをインストールする

リスナー サービスをホスト コンピューターにインストールするには、次のコマンドStatsManPerfAgentListener.msi指定します。
  
1. 使用許諾契約書を確認し、同意する場合は、[使用許諾契約書に同意します] を選択し、[次へ] をクリック **します**。 
    
2. 次のページで、次の情報を指定します。
    
   - **サービス パスワード:** これは、リモート エージェントがリスナー サービスへの認証に使用するパスワードです。
    
   - **サービス ポート:** これは、リスナーがエージェントと通信するために使用する HTTPS ポート番号です。 インストール時に、このポートはローカル ファイアウォール経由で許可され、URL ACL が作成され、SSL 証明書はこのポートにバインドされます。 既定値は 8443 です。
    
   - **証明書の拇印:** これは、リスナーが HTTPS プロトコルを暗号化するために使用する証明書の拇印です。 ネットワーク サービスには、プライベート キーへの読み取りアクセス権が必要です。
    
     **[Select...]** ボタンをクリックして拇印を選択します。
    
     証明書の拇印は、証明書マネージャーを使用するか、次の PowerShell コマンドを使用して確認できます。
    
       ```PowerShell
       Get-ChildItem -path cert:\LocalMachine\My
       ```

   - **インストール ディレクトリ:** これは、バイナリがインストールされるディレクトリです。 [参照...] ボタンを使用して、既定 **の設定から変更** できます。
    
   - **AppData ディレクトリ:** これは、Logs フォルダーと他のデータが格納されるディレクトリです。 既定から変更できます。 アンインストール時に削除されません。
    
3. **[インストール]** をクリックします。
    
インストールを検証するには、次の手順を実行します。
  
1. ブラウザーを開き https://localhost: \<service-port\> 、/healthcheck/ に移動します。
    
    既定では、サービス ポートは 8443 です (別のポートを指定した場合を含む)。
    
2. リスナーが正しくインストールされていることを確認するには、次の情報を探します。
    
   - 正常性チェックページが表示された場合、リスナーのインストールは成功しました。
    
   - KnownServerCount が 1 以上の場合、Redis への接続が確立されます。
    
   - 数分待ち、少なくとも 1 つのエージェントがインストールされた後、ValuesWritten カウンターがインクリメントされていることを確認します。
    
### <a name="install-the-website"></a>Web サイトをインストールする

StatsManWebSite.msi [(Skype for Business Server、Real-Time Statistics Manager (64](https://www.microsoft.com/en-in/download/details.aspx?id=57518)ビット) に付属) を実行し、以下を指定して、ホスト コンピューターに Web サイトをインストールします。
  
1. 使用許諾契約書を確認し、同意する場合は、[使用許諾契約書に同意します] を選択し、[次へ] をクリック **します**。 
    
2. 次のページで、次の情報を指定します。
    
   - **サービス ポート:** これは、Web サイトがリッスンするポート番号です。 後で IIS マネージャー バインドを使用して変更できます。 インストール時に、このポートはローカル ファイアウォール経由で許可されます。
    
   - **インストール ディレクトリ:** これは、バイナリがインストールされるディレクトリです。 [参照...] ボタンを使用して、既定 **の設定から変更** できます。
    
   - **AppData ディレクトリ:** これは、Logs フォルダーと他のデータが格納されるディレクトリです。 既定から変更できます。 アンインストール時に削除されません。
    
3. **[インストール]** をクリックします。
    
Web サイトを表示するには、ブラウザーを開き http://localhost 、[,webport \> /] に移動します。
  
正常性情報のみを表示するには、ブラウザーを開き http://localhost: \<webport\> 、/healthcheck/ に移動します。
  
既定では、Web ポート番号は 8080 です。 IIS マネージャーを使用して、Web サイトのポート バインドを変更できます。
  
Web インストーラーは、StatsManWebSiteUsers というローカル セキュリティ グループを追加します。 このセキュリティ グループにアカウントを追加して、Web サイトへのアクセスを許可できます。 
  
### <a name="install-the-agents"></a>エージェントをインストールする

監視する各 Skype for Business Server にエージェントをインストールするには、次のコマンドStatsManPerfAgent.msi指定します。
  
1. 使用許諾契約書を確認し、同意する場合は、[使用許諾契約書に同意します] を選択し、[次へ] をクリック **します**。 
    
2. 次のページで、次の情報を指定します。
    
   - **サービス パスワード:** これは、リモート エージェントがリスナー サービスへの認証に使用するパスワードです。
    
   - **サービス URI:** これはリスナーが存在する URI です。 形式を使用 https://name:port する必要があります。
    
     NETBIOS 名または FQDN を使用できます。 リスナー サービスの証明書のサブジェクトまたはサブジェクトの代替名として指定されている名前も使用できますが、これは要件ではありません。
    
   - **サービスの拇印:** これは、リスナーが使用している SSL 証明書の拇印です。 エージェントは、この拇印を使用してリスナーに対する認証を行います。 (自己署名証明書を使用する可能性が高いので、完全な証明書検証は行う必要があります)。
    
   - **インストール ディレクトリ:** これは、バイナリがインストールされるディレクトリです。 [参照...] ボタンを使用して、既定 **の設定から変更** できます。
    
   - **AppData ディレクトリ:** これは、Logs フォルダーと暗号化されたファイルが保存password.txtディレクトリです。 既定から変更して下さい。 アンインストール時に削除されません。
    
3. **[インストール]** をクリックします。
    
多数のコンピューターにエージェントをインストールする場合は、無人モードでインストールする必要があります。 例: 
  
```console
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_  STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a>トポロジをインポートする
<a name="BKMK_ImportTopology"> </a>

Statistics Manager をインストールして実行したら、Statistics Manager が各サーバーのサイト、プール、および役割を知る Skype for Business Server トポロジをインポートする必要があります。 Skype for Business Server トポロジをインポートするには [、Get-CsPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) コマンドレットを使用して組織で使用されている各プールに関する情報を取得し、この情報を Statistics Manager にインポートします。
  
Skype for Business Server トポロジをインポートするには、次の手順を実行します。
  
1. Skype for Business Server PowerShell コマンドレットを持つホストの場合:
    
    a.  次のコマンドを実行します。 
    
   ```PowerShell
   Get-CsPool | Export-Clixml -Path mypoolinfo.xml
   ```
    b. "mypoolinfo.xml" ファイルをリスナーを実行するサーバーにコピーします。
    
2. リスナーを実行するホストで、次のコマンドを実行します。
    
   a.  PowerShell を実行します。
    
   b. リスナーがインストールされているディレクトリに移動します。 既定値は次の値です。 
    
   ```console
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

3. 追加および更新されるサーバーを確認するには、次のコマンドを実行します。
    
   ```console
    .\Update-StatsManServerInfo.ps1 -CsPoolFile  <path to mypoolinfo.xml>
   ```

次のコマンドを使用すると、すべてのオプションを表示できます。
  
```powershell
Get-Help .\Update-StatsManServerInfo.ps1 -Detailed 
```

現在インポートされているサーバー情報を表示するには、次のスクリプトを実行します。 
  
```powershell
.\Get-StatsManServerInfo.ps1
```

たとえば、Skype for Business Server トポロジ (Exchange Server) にはないサーバーを監視する場合は、リスナーを実行するホストで単一サーバーのインポートを実行できます。 単一サーバーのインポートを実行するには、次の手順を実行します。
  
1. リスナーがインストールされているディレクトリに移動します。 既定値は次の値です。 
    
   ```console
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

2. 次のコマンドを実行します。
    
   ```powershell
    .\Update-StatsManServerInfo.ps1 -HostName <hostname> -SiteName <name of site> -PoolName <poolName> -Roles <role1>[,<role2>,<roleN>]
   ```

## <a name="troubleshoot-your-deployment"></a>展開のトラブルシューティング
<a name="BKMK_Troubleshoot"> </a>

エージェントの開始に失敗した場合は、次の情報を確認します。 
  
- エージェントは統計情報マネージャーに登録されていますか?
    
    1. トポロジをインポートする手順に従ってください。 「 [トポロジのインポート」を参照してください](deploy.md#BKMK_ImportTopology)。
        
    2. エージェントがトポロジにリストされていないサーバー上にある場合 (たとえば、SQL AlwaysOn クラスター内のノード)、トポロジのインポートの手順に従って手動でエージェントを追加する必要[があります。](deploy.md#BKMK_ImportTopology)
    
- エージェントはリスナーに連絡できますか?
    
    1. リスナー サービスが実行されている必要があります。 
        
        実行されていない場合は、Redis が実行中で、リスナーの再起動を試みる必要があります。
        
    2. ポートがリスナー サービスに対して開いていて、エージェント コンピューターがポートと通信可能なポートを確認します。
    
- 統計情報マネージャーがデータを収集するために、CSV ファイルを次のように確認できます。 
    
    次のコマンドは、カウンターストレージ名を取得します。 
    
  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    次のコマンドは、指定したカウンターの値を取得します。 
    
  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

アプリケーション イベント ログに表示される可能性があるすべてのイベントの詳細については、「Skype for Business Server の Statistics Manager のトラブルシューティング [」を参照してください](troubleshoot.md)。
  
## <a name="create-a-self-signed-certificate"></a>自己署名証明書を作成する
<a name="BKMK_SelfCert"> </a>

Microsoft では、信頼できる証明機関によって署名された証明書の使用を強く推奨しています。 ただし、テスト目的で自己署名証明書を使用する場合は、次の手順を実行します。 
  
1. 管理者としてログオンしている間に PowerShell コンソールから、次のように入力します。
    
   ```powershell
   New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
   ```

2. 型  `certlm.msc` 。 これにより、ローカル コンピューターの証明書マネージャーが開きます。
    
3. [個人] **に移動** し、[証明書] **を開きます**。
    
4. **StatsManListener - [ \> すべてのタスク] - [プライベート キー \> の管理] を右クリックします。**
    
5. **[追加]** をクリックします。
    
6. [選択 **するオブジェクト名を入力してください]** ボックスに、「ネットワーク サービス」と入力します。
    
7. [**OK**] をクリックします。
    
8. [ **フル コントロール] の**[許可] チェック **ボックスを** オフにします。 (読み取りアクセスのみ必要です。
    
9. [**OK**] をクリックします。
    
## <a name="for-more-information"></a>関連情報
<a name="BKMK_SelfCert"> </a>

詳細については、次のトピックを参照してください。
  
- [Skype for Business Server の Statistics Manager の計画](plan.md)
    
- [Skype for Business Server の Statistics Manager のアップグレード](upgrade.md)
    
- Skype for Business Server の[Statistics Manager のトラブルシューティング](troubleshoot.md)
