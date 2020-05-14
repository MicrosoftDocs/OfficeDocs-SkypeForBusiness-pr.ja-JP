---
title: Cloud Connector 展開のトラブルシューティング
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
description: Cloud Connector エディションの展開のトラブルシューティングを行います。
ms.openlocfilehash: 97ece0ee1bcc11c22fd55709d025169ed95b16ff
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220227"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a>Cloud Connector 展開のトラブルシューティング
 
Cloud Connector エディションの展開のトラブルシューティングを行います。
  
このトピックでは、Cloud Connector Edition の展開に関する一般的な問題の解決方法について説明します。 公衆交換電話網 (PSTN) の呼び出しで問題が発生している場合は、このトピックで説明するソリューションに従って調査できます。
  
Cloud Connector には、いくつかの問題を自動的に解決するための組み込みのメカニズムが用意されています。 自動検出プロセスでは、Cloud Connector アプライアンスの潜在的な問題を検索し、可能であれば、管理者の介入なしにこれらの問題を解決するための是正措置を行います。 検出プロセスは次のように動作します。
  
- **検出シーケンス:** Cloud Connector Management service は、アプライアンスがダウンしているかどうかを検出するために60秒ごとに処理を実行します。 Cloud Connector バージョン2.0 以降では、検出プロセスでは、クラウドコネクタマシンへの PowerShell 接続を行うために Skype for Business の社内ネットワークスイッチを使用しています。2.0 より前のバージョンでは、検出プロセスは Cloud Connector management スイッチを使用します。
    
    > [!NOTE]
    > 自動回復を正常に行うには、ホストと仮想マシンの間のネットワーク接続がホストネットワークスイッチを経由する必要があります。 自動検出と回復が成功することを確認するために、必ずネットワーク接続を確認してください。 
  
- **監視:** Cloud Connector バージョン2.0 以降では、次のサービスが監視されます。
    
  - 仮想マシンが Cloud Connector の企業またはインターネット仮想スイッチに接続されていない
    
  - 仮想マシンが保存済みまたは停止状態になっている
    
  - 中央管理サーバーサービス: レプリカ、マスター
    
  - 仲介サーバーサービス: REPLICA、RTCSRV、MEDSVC
    
  - エッジサーバーサービス: REPLICA、RTCSRV、RTCDATAPROXY、RTCMRAUTH、RTCDATAPROXY
    
  - エッジサーバー上の CS RTCSRV で、受信ファイアウォールルールが無効になっている。仲介サーバー上の CS RTCMEDSRV
    
    Cloud Connector バージョン1.4.2 では、次のサービスのみが監視されます。
    
  - 仲介サーバーサービス: RTCSRV および MEDSVC
    
  - エッジサーバーサービス: RTCSRV
    
- **回復プロセス:** 監視対象のサービスがダウンしている場合は、アプライアンスが停止し、すべての問題を解決できるように、サービスが停止して、手動でマーク付けされます。 これにより、通話エラーが発生する可能性があるアプライアンスへのルーティングからの呼び出しを防ぐことができます。
    
    Cloud Connector Management service では、次のように自動回復が再試行されます。
    
  - 最初の再試行間隔は、最大間隔が1時間の10秒ごとになります。
    
  - 最初の3回の回復試行では、間隔は10秒です。 4回目の再試行から、間隔は前の間隔の2倍の時間になります。 たとえば、4回目の再試行は20秒で、5秒間に40秒間実行されます。 
    
  - 最大間隔の時間が1時間に達すると、再試行は1時間に1回続行されます。
    
  - 回復に成功すると、間隔と再試行回数は初期値に設定されます。
    
  - 管理サービスを再起動すると、間隔と再試行回数が初期値にリセットされます。
    
## <a name="troubleshooting"></a>トラブルシューティング

一般的に発生する問題の解決策を次に示します。
  
- **問題: 展開スクリプトを実行すると、展開に失敗するか、応答が停止します。各 VM にログオンした後、管理/内部/外部 NIC に対して IP アドレスが見つからないか、または正しくありません。**
    
    **解決策:** この問題を自動的に解決することはできません。 Nic は、実行中に Vm に追加することはできません。 Hyper-v マネージャーでこれらの Vm をシャットダウンし、削除してから、次のコマンドレットを実行してください。
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    **問題: Active Directory サーバーとフォレストがインストールされた後、CMS サーバーや仲介サーバーがドメインに正しく参加しませんでした。**
    
    **解決策:** この問題を解決するには、次の手順を実行します。
    
  - Active Directory サーバーにログオンし、ドメインが正しく作成されたことを確認します。
    
  - CMS/仲介サーバーにログオンし、社内の NIC で有効な IP アドレスが割り当てられていること、および有効な静的 IP と DNS が AD サーバーの IP アドレスとして構成されていることを確認します。
    
  - CMS/仲介サーバーにログオンし、コマンドプロンプトを開きます。 Active Directory サーバーの FQDN と IP アドレスに ping を実行できることを確認してください。 できない場合は、IP アドレスの競合が発生している可能性があります。 Active Directory の新しい IP を割り当てて、CMS/仲介サーバーで DNS を更新してみてください。
    
- **問題: "削除-VMSwitch: 仮想イーサネットスイッチの削除中にエラーが発生しました。" というエラーメッセージが表示される。仮想スイッチ ' Cloud Connector Management スイッチ ' は、実行中の仮想マシンによって使用されているか、子プールに割り当てられているため、削除できません。 "**
    
    **解決策:** 展開後に "Cloud Connector Management スイッチ" が削除されていません。 このエラーが発生した場合は、Hyper-v マネージャーに移動して、仮想マシンがまだ接続されていないことを確認してください。 まだ接続されている仮想マシンがある場合は、それらを切断して管理スイッチを削除します。 引き続き管理スイッチを削除できない場合は、ホストサーバーを再起動し、もう一度実行してください。
    
- **問題: 次のエラーメッセージが表示されます。 "サービス RTCMRAUTH を開始できませんでした。サービスが無効になっていないことを確認してください。 "**
    
    > [!NOTE]
    > この問題は、1.4.2 より前の Cloud Connector バージョンにのみ適用されます。 
  
    また、このフロントエンドサーバーが以前にフェールオーバーされた (コンピューターのフェールオーバーを使用した) ために、開始に失敗することもあります。 その場合は、フェールバックを呼び出してください (コンピューターのフェールバックを使用)。
    
    **解決策:** この問題は、ルート CA 証明書または中間 CA 証明書がエッジサーバーによって信頼されていない場合に、エッジサーバーで発生します。 外部証明書をインポートできるが、証明書チェーンが破損している場合でも、 この条件下では、RTCMRAUTH または RTCSRV サービスを開始できません。
    
    ルート CA 証明書と外部証明書のすべての中間 CA 証明書をエッジサーバーに手動でインポートし、エッジサーバーを再起動してください。 エッジサーバー上で RTCMRAUTH サービスおよび RTCSRV サービスが開始されたことを確認した後、ホストサーバーに戻り、管理者として PowerShell コンソールを起動し、次のコマンドレットを実行して新しい展開に切り替えます。
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    **問題: Windows 更新プログラムの適用中にホストサーバーが再起動され、サーバーによって処理された呼び出しが失敗する。**
    
    **解決策:** 高可用性環境を展開した場合、Microsoft は、Windows update を手動で確認してインストールするときに、現在のトポロジから1つのホストマシン (展開インスタンス) を移行するためのコマンドレットを提供します。 これを行うには、次の手順を使用します。
    
1. ホストサーバーで、管理者として PowerShell コンソールを起動し、次のように実行します。
    
   ```powershell
   Enter-CcUpdate
   ```

2. 更新プログラムを確認し、利用可能なものをインストールします。
    
3. PowerShell コンソールで、次のコマンドレットを実行します。
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    **問題: PSTN 番号を使用して Skype for Business クライアントから通話を発信したときに、別の PSTN 番号を招待することで、その通話を会議にエスカレートすることはできません。**
    
    **解決策:** この問題を解決するには、「 [Configure online Hybrid 仲介サーバーの設定](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer)」を参照してください。
    
- **問題: Active Directory サーバーのインストール時に Windows Update に関する警告メッセージが表示されます。 "Windows 自動更新が有効になっていません。"新しくインストールした役割または機能が自動的に更新されるようにするには、[Windows Update] を有効にします。**
    
    **解決策:** Skype for Business テナント管理者の資格情報を使用してテナントのリモート PowerShell セッションを起動し、次のコマンドレットを実行して、サイトの_Enableautoupdate_の構成を確認します。
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    _Enableautoupdate_が**True**に設定されている場合、CCEManagement サービスは仮想マシンとホストサーバーの両方の Windows 更新プログラムのダウンロードとインストールを処理するため、この警告メッセージは無視しても問題ありません。 _Enableautoupdate_が**False**に設定されている場合は、次のコマンドレットを実行して**True**に設定します。
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    別の方法として、更新プログラムを手動で確認してインストールすることもできます。 次のセクションを参照してください。
    
- **問題: エラーメッセージ: 現在の入力/構成サイト名またはサーバー名または仲介サーバーの \< \> \< \> \< \> \< IP アドレスが \> 既存のアプライアンスと競合しているため、アプライアンスを登録できません。競合するアプライアンスを削除するか、入力/構成情報を更新してから、もう一度登録します。' Register → CcAppliance を実行して、現在のアプライアンスをオンラインに登録します。**
    
    **解決策:** この値は、 \< 一意で \> 、 \< \> \< \> 1 つのアプライアンス登録にのみ使用する必要があります。 既定では、 \< アプライアンス \> 名はホスト名によって決まります。 \<\> \< \> 構成 ini ファイルで定義されている仲介サーバーの FQDN と仲介サーバーの IP アドレス。
    
    たとえば、(アプライアンス名を使用している場合は) を使用します。 (ただし、登録されているアプライアンスがある場合には、登録済みのアプライアンス (アプライアンス名 Ename = Myserver、仲介サーバーの FQDN = マックス、仲介サーバーの IP アドレス = 10.10.10.10) がある場合は、この競合が発生します。
    
    最初に、ApplianceRoot directory セクションで CloudConnector .ini ファイルを確認してください。 この \< ファイルには、SiteName \> 、 \< 仲介サーバーの FQDN、 \> および \< 仲介サーバーの IP アドレス \> の値が表示されます。 \<この \> ホストサーバー名を指定します。
    
    2番目に、Skype for Business テナント管理者の資格情報を使用してテナントのリモート PowerShell を起動し、次のコマンドレットを実行して、登録されているアプライアンスを確認します。
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    競合を特定したら、登録済みのアプライアンスと一致する情報を使用して CloudConnector の .ini ファイルを更新するか、既存のアプライアンスの登録を解除して競合を解決することができます。
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- **問題: ホスト上で実行されている展開済みのアプライアンスがある場合、Get-CcRunningVersion コマンドレットは空の値を返します。**
    
  **解決策:** これは、1.3.4 または1.3.8 から1.4.1 にアップグレードしたときに発生する可能性があります。 バージョン1.4.1 を .msi と共にインストールした後、 `Register-CcAppliance` 他のコマンドレットを実行する前に、を実行する必要があります。 `Register-CcAppliance`%UserProfile%\CloudConnector から%ProgramData%\CloudConnector. にモジュール .ini ファイルを移行します。 不在の場合は、%ProgramData%\CloudConnector フォルダーに新しい system.ini が作成され、1.3.4 または1.3.8 の実行/バックアップバージョン情報が置き換えられます。
    
  %UserProfile%\CloudConnector および%ProgramData%\CloudConnector フォルダー内のモジュール .ini ファイルを比較します。 相違点がある場合は、%ProgramData%\CloudConnector でモジュール .ini ファイルを削除して、再度実行 `Register-CcAppliance` します。 また、適切な実行およびバックアップバージョンにファイルを手動で変更することもできます。
    
- **問題: スイッチ-CcVersion コマンドレットを実行して、現在のスクリプトバージョンとは異なる古いバージョンに切り替えた場合、古いバージョンでは高可用性がサポートされません。**
    
    **解決策:** たとえば、1.4.1 から1.4.2 にアップグレードしたとします。 現在のスクリプトバージョンは、を実行することによって決定され、実行中の `Get-CcVersion` バージョンは、両方が1.4.2 であることを確認でき `Get-CcRunningVersion` ます。 現時点で、実行 `Switch-CcVersion` 中のバージョンを1.4.1 に戻すために実行した場合、古いバージョンでは高可用性がサポートされません。
    
    完全な高可用性サポートを取得するには、1.4.2 に切り替えて、実行中のバージョンとスクリプトバージョンが同じであることを確認してください。 1.4.2 展開で問題が発生している場合は、できるだけ早くアンインストールして再インストールしてください。
    
- **問題: 中央管理ストア、仲介サーバー、エッジサーバーに対して発行された証明機関証明書または内部証明書の有効期限が近づいているか、侵害されています。**
    
    **解決策:** Skype for Business の証明機関証明書は5年間有効です。 中央管理ストア、仲介サーバー、エッジサーバーに対して発行された内部証明書は、2年間有効です。
    
    > [!NOTE]
    > Cloud Connector バージョン2.0 以降では、Renew-cccacertificate コマンドレットが更新-CcServerCertificate に変更され、コマンドレットが Renew-cccacertificate に変更されました。 
  
    中央管理ストア、仲介サーバー、エッジサーバーに対して発行された内部証明書の有効期限が近づいているか、または危険にさらされている場合は、更新-CcServerCertificate または Update-CcServerCertificate コマンドレットを実行して証明書を更新します。
    
    証明機関の証明書の有効期限が近づいている場合は、Renew-cccacertificate または Renew-cccacertificate コマンドレットを実行して証明書を更新します。
    
    **証明機関の証明書が侵害され、サイトにアプライアンスが1つしか存在しない場合は、** 次の手順を実行します。
    
1. コマンドレットを実行してサービスをドレインし、アプライアンスをメンテナンスモードにします。
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. 次のコマンドレットを実行してリセットし、新しい証明機関の証明書とすべての内部サーバー証明書を作成します。
    
    2.0 より前の Cloud Connector のリリースの場合:
    
    ```powershell
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    または、Cloud Connector リリース2.0 以降の場合:
    
    ```powershell
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. ゲートウェイと仲介サーバーの間で TLS が使用されている場合は、アプライアンスから Export-ccrootcertificate コマンドレットを実行して、エクスポートした証明書を PSTN ゲートウェイにインストールします。 また、ゲートウェイで証明書を再発行する必要がある場合もあります。

   ```powershell
   Export-CcRootCertificate
   ```

4. 終了-CcUpdate コマンドレットを実行して、サービスを開始し、メンテナンスモードを終了します。

   ```powershell
   Exit-CcUpdate
   ```


    **証明機関の証明書が侵害され、サイトに複数のアプライアンスが存在する場合**は、サイト内の各アプライアンスで次の順次手順を実行します。
    
    Microsoft では、ピーク時以外の時間帯にこれらの手順を実行することをお勧めします。
    
1. 最初のアプライアンスで、Remove-cccertificationauthorityfile コマンドレットを実行して、siteroot ディレクトリ内の CA バックアップファイルをクリーンアップし \< \> ます。

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. コマンドレットを実行してサービスをドレインし、各アプライアンスをメンテナンスモードにします。

     ```powershell
     Enter-CcUpdate
     ```
    
3. 最初のアプライアンスで、次のコマンドレットを実行してリセットし、新しい証明機関の証明書とすべての内部サーバー証明書を作成します。
    
     2.0 より前の Cloud Connector のリリースの場合:
    
     ```powershell
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     または、Cloud Connector リリース2.0 以降の場合:
    
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. 最初のアプライアンスで、次のコマンドレットを実行して、CA ファイルを \< siteroot フォルダーにバックアップし \> ます。
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. 同じサイト内の他のすべてのアプライアンスで、次のコマンドを実行して CA バックアップファイルを使用し、すべてのアプライアンスで同じルート証明書が使用されるようにして、新しい証明書を要求します。 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. ゲートウェイと仲介サーバーの間で TLS が使用されている場合は、サイト内の任意のアプライアンスから Export-ccrootcertificate コマンドレットを実行して、エクスポートした証明書を PSTN ゲートウェイにインストールします。 また、ゲートウェイで証明書を再発行する必要がある場合もあります。
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. 終了-CcUpdate コマンドレットを実行して、サービスを開始し、メンテナンスモードを終了します。 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- **問題: Cloud Connector Management Service のログに "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log" というエラーメッセージが表示されます。 CceService Error: 0: 状態をオンラインに報告しているときに、予期しない例外が発生しました。 CmdletInvocationException: ユーザーの \< グローバルテナント管理者にログオンできませんでした \> 。新しい資格情報オブジェクトを作成してください。正しいユーザー名とパスワードを使用していることを確認してください。---\>**
    
    **解決策:** Cloud Connector アプライアンスが登録されてから、Microsoft 365 または Office 365 グローバルテナント管理者の資格情報が変更されました。 Cloud Connector アプライアンスでローカルに格納されている資格情報を更新するには、ホストアプライアンスの管理者 PowerShell から次を実行します。
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- **問題: 展開に使用したホストサーバーアカウントのパスワードを変更すると、次のエラーメッセージが表示されます。 "Convertto-securestring-System.security.securestring: キーが指定した状態で使用できません。" というエラーメッセージが表示されます。%ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log または Get-CcCredential コマンドレットを実行しています。**
    
    **解決策:** すべての Cloud Connector 資格情報は、次のファイルに格納されます。 "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser \> ホストサーバーのパスワードが変更された場合は、ローカルに格納されている資格情報を更新する必要があります。
    
    **Cloud connector バージョン1.4.2 を実行**している場合は、次の手順に従って、すべての cloud connector パスワードを再生成します。
    
  1. ホストサーバーを再起動します。
    
  2. 次のファイルを削除します。 "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser \>
    
  3. 管理者として PowerShell コンソールを起動してから、説明に従ってパスワードを再入力するには、「Register-CcAppliance-Local」を実行します。 Cloud Connector を展開する前に入力したのと同じパスワードを入力します。
    
     **Cloud connector バージョン2.0 以降を実行**している場合は、次の手順に従って、すべての cloud connector パスワードを再生成します。
    
  4. ホストサーバーを再起動します。
    
  5. 次のファイルを削除します。 "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser \>
    
  6. 管理者として PowerShell コンソールを起動してから、説明に従ってパスワードを再入力するには、「Register-CcAppliance-Local」を実行します。 
    
     キャッシュされたパスワードファイルが Cloud Connector バージョン1.4.2 で生成されている場合は、CceService パスワードの入力を求められたときに、VMAdmin パスワードを使用します。 他のすべてのアカウントに対して、Cloud Connector の展開の前に入力したパスワードを入力します。
    
     キャッシュされたパスワードファイルが Cloud Connector バージョン1.4.2 を使用して生成され、DomainAdmin と VMAdmin のパスワードが異なる場合は、次の手順を実行する必要があります。
    
  7. Set-CcCredential-AccountType DomainAdmin を次のように実行します。
    
  8. 古いアカウントの資格情報の入力を求められたら、CceService パスワードに使用した資格情報を入力します。
    
  9. 新しいアカウントの資格情報の入力を求められたら、前に使用した DomainAdmin パスワードのパスワードを入力します。
    
     キャッシュされたパスワードファイルが Cloud Connector バージョン2.0 以降で生成された場合、既定では、VmAdmin と DomainAdmin は CceService と同じパスワードを使用します。 DomainAdmin および VMAdmin のパスワードを変更した場合は、次の手順を実行する必要があります。
    
  10. Set-CcCredential-AccountType DomainAdmin を次のように実行します。
    
       1. 古いアカウントの資格情報の入力を求められたら、CceService パスワードに使用した資格情報を入力します。
    
       2. 新しいアカウントの資格情報の入力を求められたら、前に使用した DomainAdmin パスワードのパスワードを入力します。
    
  11. Set-CcCredential-AccountType VmAdmin を次のように実行します。
    
       1. 古いアカウントの資格情報の入力を求められたら、CceService パスワードに使用した資格情報を入力します。
    
       2. 新しいアカウントの資格情報の入力を求められたら、以前使用した VmAdmin パスワードのパスワードを入力します。 
    
- **問題: Cloud Connector バージョン2.1 以降で、アプライアンスで Register-CcAppliance またはその他のコマンドレットを実行すると、次のようなエラーメッセージが表示されます。このオブジェクトには、プロパティ ' Common ' が見つかりません。プロパティが存在することを確認します。C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1: 681 char:14 "**
    
    **解決策:** Cloud Connector 2.1 以降では、.NET Framework 4.6.1 以降が必要です。 アプライアンスの .NET Framework をバージョン4.6.1 以降に更新して、コマンドレットを再度実行してください。

- **問題: Cloud Connector エディション2.1 で、インストール-CcAppliance を実行すると、"新しいインスタンスをインストールできませんでした:" というエラーメッセージが表示されます。これは、文字列のみを値として使用して XmlNode のプロパティを設定することができるため、"状態を設定できません" です。**

   **解決策:** Cloudconnector の [Common] セクションで、以下のように「State」 config を追加してください。 CountryCode = US State = WA City = Redmond

   "State" 行に値を設定することは必須ではありません。ただし、"State" 行を Cloudconnector の .ini ファイルから削除することはできません。

- **問題: "WindowsImage: WindowsImage に失敗しました" というエラーメッセージが表示されます。Cloud Connector エディションをインストールまたはアップグレードするときに、エラーコード = 0xc1550115 "が返されます。**
    
    **解決策:** 管理者として PowerShell コンソールを起動し、"DISM-Cleanup-Wim '" を実行します。 これにより、すべての troubled 画像がクリーンアップされます。 もう一度インストール-CcAppliance を実行するか、bits が自動的にアップグレードされるのを待ちます。
    
- **問題: HA 環境での最初の Cloud Connector アプライアンスの展開が失敗する**
    
    **解決策:** 実行する手順は、展開が失敗した理由によって異なります。
    
  - 最初の Cloud Connector アプライアンスに障害が発生し、障害の原因を特定できない場合は、展開が成功するまでアプライアンスを再度インストールして、他のアプライアンスをインストールする必要があります。
    
  - 最初の Cloud Connector アプライアンスが、外部証明書の問題などの軽微な問題で失敗した場合は、アプライアンスを再インストールしなくても問題を解決できる場合があります。 その後、テナントのリモート PowerShell を使用して、展開を次のようにマークできます。 (最初の展開が成功した場合は、次の手順を使用することもできますが、何らかの理由で、クラウドコネクタが成功として展開を報告できない場合もあります)。
    
  - 最初の Cloud Connector アプライアンスの Id (GUID) を取得するには、CsHybridPSTNAppliance コマンドレットを実行します。
    
  - 正常に展開された状態でアプライアンスをマークするには、次のように CsCceApplianceDeploymentStatus を実行します。
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- **問題: ホストサーバーまたは仮想マシンで Windows 更新プログラムを手動で確認してインストールする必要があります。**
    
   **解決策:** Skype for Business Cloud Connector エディションで提供される自動 OS 更新プログラムを利用することをお勧めします。 アプライアンスがオンライン管理用に登録され、自動 OS 更新が有効になると、ホストサーバーと仮想マシンは、OS 更新時間ウィンドウの設定に従って自動的に Windows 更新プログラムをチェックしてインストールします。
    
   Windows 更新プログラムを手動で確認してインストールする必要がある場合は、展開の種類に該当するこのセクションの手順を実行します。 更新に必要なダウンタイムを最小限に抑えるために、ホストサーバーと仮想マシンの両方を同時に更新することを計画する必要があります。
    
   必要に応じて、Windows Server Update Services (WSUS) サーバーを使用して、Cloud Connector サーバーに更新を提供することができます。 Windows Update を自動的にインストールし**ない**ように構成してください。
    
   Cloud Connector の展開を手動で更新する方法については、次のセクションを参照してください。
    
- **問題: Cloud Connector が新しいビルドに更新されても、Cloud Connector コマンドレットは更新されません。** これは、自動更新の実行時に PowerShell ウィンドウを開いたままになっている場合に発生することがあります。
    
  **解決策:** 更新されたコマンドレットを読み込むには、次のいずれかの手順を実行します。
    
   - Cloud Connector アプライアンスで PowerShell を閉じてから、PowerShell をもう一度開きます。
    
     - または、Import モジュール CloudConnector-Force を実行することもできます。 
 
-   **問題: "Stop-CsWindowsService ' という用語は、コマンドレット、関数、スクリプトファイル、または実行可能なプログラムの名前として認識されません。" というメッセージが返されます。**

    **解決策:**$HOME \AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache ファイルを削除します。
このファイルは、PowerShell によって検出されたモジュールのコマンドレットのキャッシュとして作成されるので、実際に処理が遅くなるように毎回すべてのモジュールを再分析する必要はありません。 多くの場合、キャッシュから戻ってきたときに、誤って PowerShell に結果を提供するファイルの破損が発生しました。

-   **問題: "インポート-モジュール CloudConnector" でエラー "Import-モジュールが生成されました" が、モジュールディレクトリに有効なモジュールファイルが見つからないため、読み込まれませんでした "**

    **解決方法:**
    - CloudConnector モジュールが c:\Program Files\WindowsPowerShell\Modules の下に存在することを確認します。
    
    - この位置の下に CloudConnector モジュールが存在することを検証した後、モジュールの場所へのパスを格納する PSModulePath 環境変数を変更できます。
    
     a. 一時的な変更: 管理者として Powershell を起動し、次のコマンドを実行します。 $env:P SModulePath = $env:P SModulePath + ";C:\Program Files\WindowsPowerShell\Modules\"
        
     b. 永続的な変更では、管理者として PowerShell を起動し、次のコマンドを1つずつ実行します。 $CurrentValue = [Environment]::: GetEnvironmentVariable ("PSModulePath", "Machine") SetEnvironmentVariable ("PSModulePath", $CurrentValue + ";C:\Program Files\WindowsPowerShell\Modules "," Machine ")

    
## <a name="install-windows-updates-manually"></a>Windows 更新プログラムを手動でインストールする

環境で自動更新を使用しない場合は、次の手順に従って、Windows 更新プログラムを手動で確認して適用します。 Windows 更新プログラムを確認してインストールするには、サーバーの再起動が必要になることがあります。 ホストサーバーを再起動すると、ユーザーはクラウドコネクタを使用して通話を発信または受信できなくなります。 更新プログラムが実行されるタイミングを制御する更新プログラムを手動で確認してインストールし、必要に応じて、サービスの中断を回避するためにコンピューターを再起動することができます。
  
更新プログラムを手動で確認するには、各ホストサーバーに接続し、[**コントロールパネル]** を開きます。 [**システムとセキュリティ] [ \> Windows Update**] を選択し、環境に合わせて更新プログラムとサーバーの再起動を管理します。
  
- サイトにアプライアンスが1つしかない場合は、各仮想マシンに接続して [**コントロールパネル]** を開きます。 [**システムとセキュリティ] [ \> Windows Update**] を選択し、必要に応じて更新プログラムとサーバーの再起動を構成します。
    
- サイト内に複数のアプライアンスが存在する場合、更新中に更新中または再起動されているインスタンスはユーザーがアクセスできません。 更新が完了した後、すべての仮想マシンとすべての Skype for Business サービスが仮想マシンで開始されるまで、ユーザーは展開内の他のインスタンスに接続します。 サービスの中断を回避するには、更新プログラムを適用している間に、そのインスタンスを HA から削除して、完了した時点で復元することができます。 これを行うには、以下のようにします:
    
1. 各ホストサーバーで、管理者として PowerShell コンソールを開きます。
    
2. 次のコマンドレットを使用して、HA からインスタンスを削除します。
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    単一インスタンスの手順に従って、更新プログラムを手動で適用し、仮想マシンを再起動します。
    
4. 次のコマンドレットを使用して、インスタンスを HA に戻します。
    
   ```powershell
   Exit-CcUpdate
   ```

複数サイト展開の場合は、展開内の各サイトに対して1つのサイトの手順を実行し、一度に1つのサイトに対して更新プログラムを適用します。
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a>Cloud Connector ホストコンピューターにウイルス対策ソフトウェアをインストールするときのヒント

Cloud Connector ホストコンピューターにウイルス対策ソフトウェアをインストールする必要がある場合は、次の除外を追加する必要があります。
  
- 各コンピューターのローカルアプライアンスディレクトリ。
    
- 各コンピューター上のリモートサイトディレクトリ。
    
- コンピューター上のローカルサイトディレクトリは、共有サイトのルートフォルダーをホストします。
    
- %ProgramFiles%\Skype for Business Cloud Connector エディション
    
- %ALLUSERSPROFILE%\CloudConnector
    
- %ProgramFiles%\WindowsPowerShell\Modules\CloudConnector
    
- プロセスの管理を実行します。
