---
title: クラウド コネクタの展開のトラブルシューティング
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/5/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e6cf58cc-dbd9-4f35-a51a-3e2fea71b5a5
description: クラウド コネクタ エディションの展開のトラブルシューティングを行います。
ms.openlocfilehash: 9da10f1b3e8dd800e57b46f6a56eb6a82c29e22c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094825"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a>クラウド コネクタの展開のトラブルシューティング

> [!Important]
> Cloud Connector Edition は、Skype for Business Online と共に 2021 年 7 月 31 日に廃止されます。 組織が Teams にアップグレードしたら、直接ルーティングを使用してオンプレミスのテレフォニー ネットワークを Teams に接続する方法 [について説明します](/MicrosoftTeams/direct-routing-landing-page)。
 
クラウド コネクタ エディションの展開のトラブルシューティングを行います。
  
このトピックでは、Cloud Connector Edition 展開に関する一般的な問題に対する解決策について説明します。 公衆交換電話網 (PSTN) との間で通話に問題が発生している場合は、このトピックで説明するソリューションに従って調査できます。
  
クラウド コネクタは、いくつかの問題を自動的に解決するための組み込みのメカニズムを提供します。 自動検出プロセスは、クラウド コネクタ アプライアンスに関する潜在的な問題を探し、可能であれば、管理者の介入を必要とせずに、それらの問題を解決するための修正措置を実行します。 検出プロセスは次のように動作します。
  
- **検出シーケンス:** クラウド コネクタ管理サービスは、アプライアンスがダウンしたかどうかを検出するために 60 秒ごとにプロセスを実行します。 クラウド コネクタ バージョン 2.0 以降では、検出プロセスは Skype for Business Corpnet スイッチを使用して、クラウド コネクタ コンピューターへの PowerShell 接続を行います。2.0 より前のバージョンの場合、検出プロセスは Cloud Connector 管理スイッチを使用します。
    
    > [!NOTE]
    > 自動回復を成功するには、ホスト ネットワーク スイッチを使用してホストと仮想マシンの間にネットワーク接続が必要です。 ネットワーク接続を確認して、自動検出と回復が成功する可能性を確認してください。 
  
- **監視:** クラウド コネクタ バージョン 2.0 以降では、次のサービスが監視されます。
    
  - 仮想マシンがクラウド コネクタ企業またはインターネット仮想スイッチに接続されていない
    
  - 仮想マシンが保存済みまたは停止中の状態
    
  - サーバーの全体管理サービス: REPLICA、MASTER
    
  - 仲介サーバー サービス: REPLICA、RTCSRV、MEDSVC
    
  - エッジ サーバー サービス: REPLICA、RTCSRV、RTCDATAPROXY、RTCMRAUTH、RTCMEDIARELAY
    
  - エッジ サーバー上の CS RTCSRV、仲介サーバー上の CS RTCMEDSRV に対して受信ファイアウォールルールが無効になっている
    
    クラウド コネクタ バージョン 1.4.2 では、次のサービスだけが監視されます。
    
  - 仲介サーバー サービス: RTCSRV および MEDSVC
    
  - エッジ サーバー サービス: RTCSRV
    
- **回復プロセス:** 監視対象のサービスがダウンしている場合、アプライアンスはマークダウンされ、すべての問題を解決するまでサービスは停止され、手動でマークされます。 これにより、呼び出しが失敗する可能性があるアプライアンスへのルーティングが防止されます。
    
    クラウド コネクタ管理サービスは、次のように自動回復を再試行します。
    
  - 最初の再試行間隔は 10 秒ごとに、最大間隔は 1 時間です。
    
  - 最初の 3 回の回復試行では、間隔は 10 秒です。 4 回目の再試行から開始すると、間隔時間は前の間隔時間の 2 倍増加します。 たとえば、4 回目の再試行は 20 秒、5 回目は 40 秒で発生します。 
    
  - 1 時間の最大間隔に達すると、再試行は 1 時間に 1 回続きます。
    
  - 回復が成功すると、間隔と再試行回数が初期値に設定されます。
    
  - 管理サービスが再起動された場合、間隔と再試行回数は初期値にリセットされます。
    
## <a name="troubleshooting"></a>トラブルシューティング

一般的に発生する問題の解決策を次に示します。
  
- **問題: 展開スクリプトの実行中に展開が失敗するか、応答を停止します。各 VM にログオンした後、管理/内部/外部 NIC の IP アドレスが見つからないか、正しくありません。**
    
    **解決策:** この問題は自動的に解決できません。 NIC は、実行中は VM に追加できません。 Hyper-v マネージャーでこれらの VM をシャットダウンして削除し、次のコマンドレットを実行してください。
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    **問題: Active Directory Server とフォレストがインストールされた後、CMS Server または仲介サーバーがドメインに正しく参加しなかった。**
    
    **解決策:** この問題を解決するには、次の手順を実行します。
    
  - Active Directory Server にログオンし、ドメインが正しく作成されていることを確認します。
    
  - CMS/Mediation Server にログオンし、corpnet NIC で有効な IP アドレスが割り当てられているか、有効な静的 IP と DNS が AD サーバーの IP アドレスとして構成されていることを確認します。
    
  - CMS/仲介サーバーにログオンし、コマンド プロンプトを開きます。 Active Directory Server の FQDN と IP アドレスに ping を実行できます。 できない場合は、IP アドレスの競合が発生する可能性があります。 Active Directory に新しい IP を割り当て、CMS/仲介サーバーで DNS を更新してください。
    
- **問題: 次のエラー メッセージが表示されます。"Remove-VMSwitch : 仮想イーサネット スイッチの削除中に失敗しました。仮想スイッチ 'Cloud Connector Management Switch' は、仮想マシンの実行によって使用されるか、または子プールに割り当てられているため、削除できません。**
    
    **解決策:** 展開後に "クラウド コネクタ管理スイッチ" が削除されません。 このエラーが発生した場合は、Hyper-v マネージャーに移動して、まだ仮想マシンがまだ接続されていないか確認してください。 仮想マシンがまだ接続されている場合は、それらを切断して管理スイッチを削除します。 管理スイッチを削除できない場合は、ホスト サーバーを再起動し、もう一度やり直してください。
    
- **問題: 次のエラー メッセージが表示されます。"Service RTCMRAUTH の開始に失敗しました。サービスが無効にされていないか確認してください。**
    
    > [!NOTE]
    > この問題は、1.4.2 より前の Cloud Connector バージョンにのみ適用されます。 
  
    このフロントエンド サーバーが以前に (コンピューターのフェール オーバーを使用して) 失敗したため、開始に失敗する可能性があります。 その場合は、(コンピューターのフェール バックを使用して) フェール バックを呼び出してください。
    
    **解決策:** この問題は、ルート CA 証明書または中間 CA 証明書がエッジ サーバーによって信頼されていない場合にエッジ サーバーで発生します。 外部証明書をインポートできますが、証明書チェーンが壊れている場合でも。 この条件では、RTCMRAUTH サービスまたは RTCSRV サービスを開始できない。
    
    外部証明書のルート CA 証明書とすべての中間 CA 証明書を手動でエッジ サーバーにインポートし、エッジ サーバーを再起動してください。 エッジ サーバーで RTCMRAUTH サービスと RTCSRV サービスが開始されたのを確認した後、ホスト サーバーに戻り、管理者として PowerShell コンソールを起動し、次のコマンドレットを実行して新しい展開に切り替えます。
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    **問題: Windows 更新プログラムが適用されるとホスト サーバーが再起動され、サーバーによってサービスされた呼び出しが失敗しています。**
    
    **解決策:** 高可用性環境を展開した場合、Microsoft は、Windows 更新プログラムを手動で確認してインストールするときに、1 つのホスト マシン (展開インスタンス) を現在のトポロジに移動または削除するためのコマンドレットを提供します。 これを実現するには、次の手順を実行します。
    
1. ホスト サーバーで、管理者として PowerShell コンソールを起動し、次のコマンドを実行します。
    
   ```powershell
   Enter-CcUpdate
   ```

2. 更新プログラムを確認し、利用可能な更新プログラムをインストールします。
    
3. PowerShell コンソールで、次のコマンドレットを実行します。
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    **問題: PSTN 番号を使用して Skype for Business クライアントから通話が行われた場合、別の PSTN 番号を招待して電話会議にエスカレートすることはできません。**
    
    **解決策:** この問題を解決するには [、「Configure online hybrid Mediation Server Settings」を参照してください](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer)。
    
- **問題: Active Directory サーバーをインストールするときに、Windows Update に関する警告メッセージが表示されます。"Windows 自動更新が有効になっていません。新しくインストールされた役割または機能が自動的に更新されていることを確認するには、Windows Update を有効にします。**
    
    **解決策:** Skype for Business テナント管理者資格情報を使用してテナント リモート PowerShell セッションを起動し、次のコマンドレットを実行してサイトの _EnableAutoUpdate_ 構成を確認します。
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    _EnableAutoUpdate_ が **True** に設定されている場合は、CCEManagement サービスが仮想マシンとホスト サーバーの両方の Windows 更新プログラムのダウンロードとインストールを処理しますので、この警告メッセージを無視しても問題ない場合があります。 _EnableAutoUpdate が False_ に設定されている **場合** は、次のコマンドレットを実行して True に設定 **します**。
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    または、更新プログラムを手動で確認してインストールすることもできます。 次のセクションを参照してください。
    
- **問題: 現在の入力/構成、または既存のアプライアンスとの競合により、アプライアンスを登録できないというエラー メッセージが \<SiteName\> \<ApplianceName\> \<Mediation Server FQDN\> \<Mediation Server IP Address\> 表示されます。競合アプライアンスを削除するか、入力/構成情報を更新してから、もう一度登録します。' を実行すると、Register-CcApplianceアプライアンスをオンラインに登録できます。**
    
    **解決策:** の値は \<ApplianceName\> 、 \<Mediation Server FQDN\> 一 \<Mediation Server IP Address\> 意で、1 つのアプライアンス登録にのみ使用する必要があります。 既定では、 \<ApplianceName\> ホスト名から来ます。 \<Mediation Server FQDN\> 構成 \<Mediation Server IP Address\> ini ファイルで定義されます。
    
    たとえば、SiteName=MySite に登録する (ApplianceName= MyserverNew、仲介サーバー FQDN=ms.contoso.com、仲介サーバー IP アドレス=10.10.10.10) を使用しますが、登録アプライアンス (ApplianceName= Myserver、Mediation Server FQDN=ms.contoso.com、仲介サーバー IP アドレス=10.10.10.10)がある場合、競合が発生します。
    
    まず、[アプライアンスルート ディレクトリ] セクションCloudConnector.iniファイルを確認してください。 ファイル内の \<SiteName\> 、 \<Mediation Server FQDN\> および \<Mediation Server IP Address\> 値を取得します。 \<ApplianceName\> はホスト サーバー名です。
    
    次に、Skype for Business テナント管理者資格情報を使用してテナント リモート PowerShell を起動し、次のコマンドレットを実行して登録済みのアプライアンスを確認します。
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    競合を特定した後、CloudConnector.ini ファイルを登録されているアプライアンスに一致する情報で更新するか、既存のアプライアンスを登録解除して競合を解決できます。
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- **問題: ホストGet-CcRunningVersion展開されたアプライアンスが実行されている場合、このコマンドレットは空の値を返します。**
    
  **解決策:** これは、1.3.4 または 1.3.8 から 1.4.1 にアップグレードするときに発生する可能性があります。 バージョン 1.4.1 を .msi でインストールした後、他のコマンドレットを実行する前 `Register-CcAppliance` に実行する必要があります。 `Register-CcAppliance` %UserProfile%\CloudConnector module.ini%ProgramData%\CloudConnector に移行します。 見つからない場合は、%ProgramData%\CloudConnector フォルダーに新しい module.ini が作成され、1.3.4 または 1.3.8 の実行中/バックアップ バージョン情報が置き換されます。
    
  module.ini %UserProfile%\CloudConnector および %ProgramData%\CloudConnector フォルダー内のファイルを比較します。 違いがある場合は、%ProgramData%\CloudConnector module.iniファイルを削除して再実行します  `Register-CcAppliance` 。 また、ファイルを手動で正しい実行バージョンとバックアップ バージョンに変更することもできます。
    
- **問題: Switch-CcVersion コマンドレットを実行して、現在のスクリプトバージョンとは異なる古いバージョンに切り替えてから、この古いバージョンに対する高可用性のサポートはありません。**
    
    **解決策:** たとえば、1.4.1 から 1.4.2 にアップグレードしたとします。 現在のスクリプト バージョン (実行によって決定できます)と、実行中のバージョン (実行によって決定できるバージョン) は、両方とも `Get-CcVersion`  `Get-CcRunningVersion` 1.4.2 です。 この時点で、実行中のバージョンを 1.4.1 に切り替える場合、この古いバージョンに対する高可用性 `Switch-CcVersion` のサポートはありません。
    
    完全な高可用性のサポートを受け取る場合は、1.4.2 に切り替えて、実行中のバージョンとスクリプトのバージョンが同じにしてください。 1.4.2 の展開で問題が発生している場合は、できるだけ早くアンインストールして再インストールしてください。
    
- **問題: サーバーの全体管理ストア、仲介サーバー、およびエッジ サーバーに発行された証明機関の証明書または内部証明書が有効期限が近いか、侵害されています。**
    
    **解決策:** Skype for Business 証明機関の証明書は 5 年間有効です。 中央管理ストア、仲介サーバー、エッジ サーバーに発行された内部証明書は、2 年間有効です。
    
    > [!NOTE]
    > クラウド コネクタ バージョン 2.0 以降では、Renew-CcServerCertificate コマンドレットが Update-CcServerCertificate に変更され、Renew-CcCACertificate コマンドレットが Update-CcCACertificate に変更されました。 
  
    中央管理ストア、仲介サーバー、エッジ サーバーに発行された内部証明書の有効期限が近い場合、または侵害されている場合は、Renew-CcServerCertificate または Update-CcServerCertificate コマンドレットを実行して証明書を更新します。
    
    証明機関の証明書の有効期限が近い場合は、Renew-CcCACertificateまたはUpdate-CcCACertificateコマンドレットを実行して証明書を更新します。
    
    **証明機関の証明書が侵害** され、サイトにアプライアンスが 1 つしかない場合は、次の手順を実行します。
    
1. サービスをEnter-CcUpdateし、アプライアンスをメンテナンス モードに設定するには、このコマンドレットを実行します。
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. 次のコマンドレットを実行して、新しい証明機関証明書とすべての内部サーバー証明書をリセットして作成します。
    
    2.0 より前のクラウド コネクタ リリースの場合:
    
    ```powershell
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    または、クラウド コネクタ リリース 2.0 以降の場合:
    
    ```powershell
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. ゲートウェイと仲介サーバーの間で TLS を使用する場合は、アプライアンスから Export-CcRootCertificate コマンドレットを実行し、エクスポートされた証明書を PSTN ゲートウェイにインストールします。 また、ゲートウェイで証明書を再発行する必要がある場合があります。

   ```powershell
   Export-CcRootCertificate
   ```

4. サービスを開始Exit-CcUpdateメンテナンス モードを終了するには、次のコマンドレットを実行します。

   ```powershell
   Exit-CcUpdate
   ```


    **証明機関の証明書が侵害** され、サイト内に複数のアプライアンスがある場合は、サイト内の各アプライアンスで次の順次手順を実行します。
    
    ピーク以外の使用時間の間にこれらの手順を実行してください。
    
1. 最初のアプライアンスで、Remove-CcCertificationAuthorityFile コマンドレットを実行して、ディレクトリ内の CA バックアップ ファイルをクリーンアップ \<SiteRoot\> します。

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. サービスをEnter-CcUpdateし、各アプライアンスをメンテナンス モードに設定するには、Enter-CcUpdate コマンドレットを実行します。

     ```powershell
     Enter-CcUpdate
     ```
    
3. 最初のアプライアンスで、次のコマンドレットを実行して、新しい証明機関証明書とすべての内部サーバー証明書をリセットして作成します。
    
     2.0 より前のクラウド コネクタ リリースの場合:
    
     ```powershell
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     または、クラウド コネクタ リリース 2.0 以降の場合:
    
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. 最初のアプライアンスで、次のコマンドレットを実行して CA ファイルをフォルダーにバックアップ \<SiteRoot\> します。
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. 同じサイト内の他のすべてのアプライアンスで、次のコマンドを実行して CA バックアップ ファイルを使用し、アプライアンスすべてが同じルート証明書を使用し、新しい証明書を要求します。 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. ゲートウェイと仲介サーバーの間で TLS を使用する場合は、サイト内の任意のアプライアンスから Export-CcRootCertificate コマンドレットを実行し、エクスポートされた証明書を PSTN ゲートウェイにインストールします。 また、ゲートウェイで証明書を再発行する必要がある場合があります。
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. サービスを開始Exit-CcUpdateメンテナンス モードを終了するには、次のコマンドレットを実行します。 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- **問題: クラウド コネクタ管理サービス ログに次のエラー メッセージが表示されます。"C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService エラー: 0 : オンラインに状態を報告するときに予期しない例外: System.Management.Automation.CmdletInvocationException: ユーザーのログオンに失敗しました。 \<Global Tenant Admin\>正しいユーザー名とパスワードを使用していることを確認して、新しい資格情報オブジェクトを作成してください。---\>**
    
    **解決策:** Microsoft 365 または Office 365 グローバル テナント管理者の資格情報は、クラウド コネクタ アプライアンスが登録された後に変更されています。 クラウド コネクタ アプライアンスでローカルに保存されている資格情報を更新するには、ホスト アプライアンスの Administrator PowerShell から次の手順を実行します。
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- **問題: 展開に使用したホスト サーバー アカウントのパスワードを変更した後、%ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log または Get-CcCredential コマンドレットの実行中に、次のエラー メッセージが表示されます。**
    
    **解決策:** すべてのクラウド コネクタ資格情報は、"%SystemDrive%\Programdata\Cloudconnector\credentials" というファイルに格納されます \<CurrentUser\> 。xml」 ホスト サーバーのパスワードが変更された場合は、ローカルに保存されている資格情報を更新する必要があります。
    
    **クラウド コネクタ バージョン 1.4.2** を実行している場合は、次の手順に従ってすべてのクラウド コネクタ のパスワードを再生成します。
    
  1. ホスト サーバーを再起動します。
    
  2. "%SystemDrive%\Programdata\Cloudconnector\credentials" というファイルを削除します \<CurrentUser\> 。xml」
    
  3. 管理者として PowerShell コンソールを起動し、"Register-CcAppliance -Local" を実行して、説明に従ってパスワードを再入力します。 クラウド コネクタの展開に前に入力したパスワードと同じパスワードを入力します。
    
     **クラウド コネクタ バージョン 2.0** 以降を実行している場合は、次の手順に従ってすべての Cloud Connector パスワードを再生成します。
    
  4. ホスト サーバーを再起動します。
    
  5. "%SystemDrive%\Programdata\Cloudconnector\credentials" というファイルを削除します \<CurrentUser\> 。xml" .
    
  6. 管理者として PowerShell コンソールを起動し、"Register-CcAppliance -Local" を実行して、説明に従ってパスワードを再入力します。 
    
     キャッシュされたパスワード ファイルが Cloud Connector バージョン 1.4.2 で生成された場合は、プロンプトが表示されたら、CceService パスワードの VMAdmin パスワードを使用します。 他のすべてのアカウントのクラウド コネクタ展開に対して前に入力したパスワードと同じパスワードを入力します。
    
     キャッシュされたパスワード ファイルが Cloud Connector バージョン 1.4.2 で生成され、DomainAdmin と VMAdmin のパスワードが異なる場合は、次の手順を実行する必要があります。
    
  7. 次Set-CcCredential -AccountType DomainAdmin を実行します。
    
  8. 古いアカウント資格情報の入力を求めるメッセージが表示されたら、CceService パスワードに使用した資格情報を入力します。
    
  9. 新しいアカウント資格情報の入力を求めるメッセージが表示されたら、前に使用した DomainAdmin パスワードのパスワードを入力します。
    
     キャッシュされたパスワード ファイルが Cloud Connector バージョン 2.0 以降で生成された場合、既定では VmAdmin と DomainAdmin は CceService と同じパスワードを使用します。 DomainAdmin パスワードと VMAdmin パスワードを変更した場合は、次の手順を実行する必要があります。
    
  10. 次Set-CcCredential -AccountType DomainAdmin を実行します。
    
       1. 古いアカウント資格情報の入力を求めるメッセージが表示されたら、CceService パスワードに使用した資格情報を入力します。
    
       2. 新しいアカウント資格情報の入力を求めるメッセージが表示されたら、前に使用した DomainAdmin パスワードのパスワードを入力します。
    
  11. 次Set-CcCredential -AccountType VmAdmin を実行します。
    
       1. 古いアカウント資格情報の入力を求めるメッセージが表示されたら、CceService パスワードに使用した資格情報を入力します。
    
       2. 新しいアカウント資格情報の入力を求めるメッセージが表示されたら、前に使用した VmAdmin パスワードのパスワードを入力します。 
    
- **問題: クラウド コネクタ バージョン 2.1 以降では、Register-CcAppliance または他のコマンドレットをアプライアンスで実行すると、次のようなエラー メッセージが表示されます。"Each-Object : プロパティ 'Common' はこのオブジェクトで見つかりません。プロパティが存在することを確認します。C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**
    
    **解決策:** クラウド コネクタ 2.1 以降では、.NET Framework 4.6.1 以降が必要です。 アプライアンスの.NET Frameworkバージョン 4.6.1 以降に更新し、コマンドレットを再度実行してください。

- **問題: Cloud Connector Edition 2.1 を使用して Install-CcAppliance を実行すると、次のようなエラー メッセージが表示されます。**

   **解決策:** [Cloudconnector.ini[Common] セクションで、次のように "State" 構成を追加してください。 CountryCode=US State=WA City=Redmond

   "State" 行に値を設定する必要は必須ではありませんが、"State" 行はファイルファイルからCloudconnector.iniできません。

- **問題: 次のエラー メッセージ "Dismount-WindowsImage : エラーが発生Dismount-WindowsImageされます。Cloud Connector Edition をインストール0xc1550115アップグレードする場合、エラー コード = 0xc1550115" が表示されます。**
    
    **解決策:** 管理者として PowerShell コンソールを起動し、「DISM -Cleanup-Wim」を実行します。 これにより、問題が発生した画像はすべてクリーンアップされます。 もうInstall-CcAppliance実行するか、ビットが自動的にアップグレードされるのを待ちます。
    
- **問題: HA 環境での最初のクラウド コネクタ アプライアンスの展開が失敗する**
    
    **解決策:** 実行する手順は、展開が失敗した理由によって異なる。
    
  - 最初のクラウド コネクタ アプライアンスが失敗し、障害の理由を特定できない場合は、展開が成功するまでアプライアンスを再度インストールしてから、他のアプライアンスをインストールする必要があります。
    
  - 外部証明書の問題など、軽微な問題で最初のクラウド コネクタ アプライアンスが失敗した場合は、アプライアンスを再インストールせずに問題を解決できる場合があります。 その後、テナント リモート PowerShell を使用して、展開を次のように成功としてマークできます。 (最初の展開が成功した場合でも、次の手順を使用できますが、何らかの理由で、クラウド コネクタは展開を成功として報告できません)。
    
  - 最初のクラウド コネクタ アプライアンスの ID (GUID) を取得するには、次のコマンドレットGet-CsHybridPSTNApplianceします。
    
  - アプライアンスを正常に展開済みとしてマークするには、次のようにSet-CsCceApplianceDeploymentStatusを実行します。
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- **問題: ホスト サーバーまたは仮想マシンで Windows 更新プログラムを手動で確認してインストールする必要があります。**
    
   **解決策:** Skype for Business Cloud Connector Edition が提供する自動 OS 更新プログラムを利用することをお勧めします。 アプライアンスがオンライン管理用に登録され、自動 OS 更新が有効になると、ホスト サーバーと仮想マシンは、OS の更新タイム ウィンドウの設定に従って Windows Update を自動的にチェックしてインストールします。
    
   Windows 更新プログラムを手動で確認してインストールする必要がある場合は、展開の種類に適用されるこのセクションの手順に従います。 更新に必要なダウンタイムを最小限に抑えるために、ホスト サーバーとホスト サーバー上で実行されている仮想マシンの両方を同時に更新する予定です。
    
   必要に応じて、WSUS (Windows Server Update Services) サーバーを使用して、クラウド コネクタ サーバーに更新プログラムを提供できます。 Windows Update が自動的にインストールされない構成 **にしてください** 。
    
   クラウド コネクタの展開を手動で更新する方法については、次のセクションを参照してください。
    
- **問題: クラウド コネクタが新しいビルドに更新された場合、Cloud Connector コマンドレットは更新されません。** これは、自動更新が発生した場合に PowerShell ウィンドウが開いた残っている場合に発生することがあります。
    
  **解決策:** 更新されたコマンドレットを読み込むには、次のいずれかの手順を実行できます。
    
   - クラウド コネクタ アプライアンスで PowerShell を閉じ、PowerShell を再度開きます。
    
     - または、CloudConnector -Force Import-Module実行できます。 
 
-   **問題: "Stop-CsWindowsService" という用語は、コマンドレット、関数、スクリプト ファイル、または操作可能なプログラムの名前として認識されません。Enter-CcUpdate コマンドレットを実行しようとするとエラーが発生します。**

    **解決策:** ファイルを$HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache ファイルを削除します。
PowerShell は、見つけたモジュールからコマンドレットのキャッシュとしてこのファイルを作成します。これにより、すべてのモジュールを再分析する必要が生じ、その結果、処理が非常に遅くなります。 ほとんどの場合、そのキャッシュから読み戻す際に、PowerShell に誤解を招く結果を提供するファイルの破損が発生した可能性があります。

-   **問題: "Import-Module CloudConnector" はエラー "Import-Module: 指定されたモジュール "CloudConnector" が読み込まれないので、有効なモジュール ファイルがモジュール ディレクトリに見つからなかったため生成されます。**

    **解決策:**
    - c:\Program Files\WindowsPowerShell\Modules の下に CloudConnector モジュールが存在することを確認する
    
    - CloudConnector モジュールがこの場所に存在することを検証した後、モジュールの場所へのパスを格納する PSModulePath 環境変数を変更できます。
    
     a. 一時的な変更: Powershell を管理者として起動し、$env:PSModulePath = $env:PSModulePath + ";C:\Program Files\WindowsPowerShell\Modules\"
        
     b. 永続的な変更を行う場合は、PowerShell を管理者として起動し、次のコマンドを 1 つ 1 つ実行します。$CurrentValue = [環境]::GetEnvironmentVariable("PSModulePath","Machine") SetEnvironmentVariable("PSModulePath",$CurrentValue + ";C:\Program Files\WindowsPowerShell\Modules", "Machine")

    
## <a name="install-windows-updates-manually"></a>Windows 更新プログラムを手動でインストールする

環境で自動更新を使用しない場合は、次の手順に従って Windows 更新プログラムを手動で確認して適用します。 Windows 更新プログラムを確認してインストールするには、サーバーの再起動が必要な場合があります。 ホスト サーバーが再起動すると、ユーザーはクラウド コネクタを使用して通話を送受信できません。 更新プログラムを手動で確認してインストールして、更新プログラムの実行を制御し、サービスの中断を避けるために選択した時間に必要に応じてコンピューターを再起動できます。
  
更新プログラムを手動で確認するには、各ホスト サーバーに接続し、コントロール パネルを **開きます**。 [ **システムとセキュリティ \> の Windows Update]** を選択し、環境に応じて更新プログラムとサーバーの再起動を管理します。
  
- サイトにアプライアンスが 1 つしかない場合は、各仮想マシンに接続し、コントロール パネルを **開きます**。 [ **システムとセキュリティ \> の Windows Update]** を選択し、必要に応じて更新プログラムとサーバーの再起動を構成します。
    
- サイト内に複数のアプライアンスがある場合、更新中および再起動中のインスタンスは、更新中にユーザーがアクセスできません。 更新が完了した後、すべての仮想マシンとすべての Skype for Business サービスが仮想マシンで開始されるまで、ユーザーは展開内の他のインスタンスに接続します。 サービスが中断される可能性を回避するために、更新プログラムの適用中に HA からインスタンスを削除し、完了したら復元できます。 これを行うには、以下のようにします。
    
1. 各ホスト サーバーで、管理者として PowerShell コンソールを開きます。
    
2. 次のコマンドレットを使用して HA からインスタンスを削除します。
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    1 つのインスタンスの手順に従って手動で更新プログラムを適用し、仮想マシンを再起動します。
    
4. 次のコマンドレットを使用して、インスタンスを HA に戻します。
    
   ```powershell
   Exit-CcUpdate
   ```

複数サイト展開の場合は、展開内の各サイトの 1 つのサイトの手順に従って、一度に 1 つのサイトに更新プログラムを適用します。
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a>クラウド コネクタ ホスト コンピューターにウイルス対策ソフトウェアをインストールする際のヒント

クラウド コネクタ ホスト コンピューターにウイルス対策ソフトウェアをインストールする必要がある場合は、次の除外を追加する必要があります。
  
- 各コンピューター上のローカル アプライアンス ディレクトリ。
    
- 各コンピューターのリモート サイト ディレクトリ。
    
- コンピューター上のローカル サイト ディレクトリは、共有サイト のルート フォルダーをホストします。
    
- %ProgramFiles%\Skype for Business Cloud Connector Edition
    
- %ALLUSERSPROFILE%\CloudConnector
    
- %ProgramFiles%\WindowsPowerShell\Modules\CloudConnector
    
- プロセスはMicrosoft.Rtc.CCE.ManagementService.exe。