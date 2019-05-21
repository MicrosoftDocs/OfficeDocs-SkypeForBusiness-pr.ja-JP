---
title: Cloud Connector 展開をトラブルシューティングする
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/5/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e6cf58cc-dbd9-4f35-a51a-3e2fea71b5a5
description: クラウドコネクタエディションの展開のトラブルシューティングを行います。
ms.openlocfilehash: 1049ec2f8f3b85c71c7b9203916b79764e9be161
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286724"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a>Cloud Connector 展開をトラブルシューティングする
 
クラウドコネクタエディションの展開のトラブルシューティングを行います。
  
このトピックでは、Cloud Connector Edition の展開に関する一般的な問題の解決策について説明します。公衆交換電話網 (PSTN) による通話で問題が発生する場合は、このトピックで説明する手順に従って調査することができます。
  
クラウドコネクタには、一部の問題を自動的に解決するための組み込みメカニズムが用意されています。 自動検出プロセスでは、クラウドコネクタのアプライアンスで発生する可能性のある問題を探し、可能であれば、管理者の介入なしでそれらの問題を解決するための修正措置をとることができます。 検出プロセスは次のように機能します。
  
- **検出シーケンス:** クラウドコネクタ管理サービスは、60秒ごとに、アプライアンスがダウンしているかどうかを検出するためのプロセスを実行します。 クラウドコネクタバージョン2.0 以降では、検出プロセスでは、クラウドコネクタマシンへの PowerShell 接続を実現するために、Skype for Business ネットワークのスイッチを使用します。2.0 より前のバージョンでは、検出プロセスではクラウドコネクタ管理スイッチを使用します。
    
    > [!NOTE]
    > 自動回復を正常に実行するには、ホストと仮想マシン間のネットワーク接続がホストネットワークスイッチを経由している必要があります。 自動検出と回復が正常に機能することを確認するため、ネットワーク接続を確認してください。 
  
- **監視:** クラウドコネクタバージョン2.0 以降では、次のサービスが監視されています。
    
  - 仮想マシンがクラウドコネクタの企業またはインターネット仮想スイッチに接続されていない
    
  - 仮想マシンが保存済みまたは停止状態である
    
  - サーバーの全体管理サーバーサービス: REPLICA、MASTER
    
  - 仲介サーバーサービス: REPLICA、RTCSRV、MEDSVC
    
  - Edge Server services: REPLICA、RTCSRV、RTCDATAPROXY、RTCMRAUTH、RTCDATAPROXY
    
  - エッジサーバー上の CS RTCSRV の受信ファイアウォールルールが無効になっている (仲介サーバー上の CS RTCMEDSRV)
    
    Cloud Connector バージョン1.4.2 では、次のサービスのみが監視されます。
    
  - 仲介サーバーサービス: RTCSRV と MEDSVC
    
  - エッジサーバーサービス: RTCSRV
    
- **回復プロセス:** 監視されているサービスがダウンしている場合は、アプライアンスがダウンしていて、すべての問題を解決するまで、サービスが停止され、手動でマークされます。 これにより、通話の失敗の原因となる可能性があるアプライアンスへのルーティングからの通話ができなくなります。
    
    クラウドコネクタ管理サービスは、次のように自動回復を再試行します。
    
  - 最初の再試行間隔は、最長で1時間の時間間隔で10秒ごとに指定します。
    
  - 最初の3回の回復試行の場合、間隔は10秒です。 4回目の再試行から開始します。間隔は、前の間隔の2倍で増加します。 たとえば、4回目の再試行は20秒、5分40秒で行われます。 
    
  - 1時間の最大間隔の時間に達すると、再試行は1時間に1回続行されます。
    
  - 回復が成功すると、間隔と再試行回数が初期値に設定されます。
    
  - 管理サービスが再開されると、間隔と再試行カウントは初期値にリセットされます。
    
## <a name="troubleshooting"></a>トラブルシューティング

一般的に発生する問題の解決策を次に示します。
  
- **問題: 展開スクリプトを実行すると、展開が失敗するか、応答しなくなる。各 VM にログインすると、管理/内部/外部 NIC の IP アドレスがないか、正しくない。**
    
    **解像度:** この問題は自動的に解決することはできません。 Nic は、実行中に Vm に追加することはできません。 Hyper-v manager でこれらの Vm をシャットダウンして削除してから、次のコマンドレットを実行してください。
    
  ```
  Uninstall-CcAppliance
  ```

  ```
  Install-CcAppliance
  ```

- 
    
    **問題: Active Directory とフォレストをインストールした後、CMS サーバーや仲介サーバーがドメインに正しく参加しない。**
    
    **解決策:** この問題を解決するには、次の手順を実行します。
    
  - Active Directory サーバーにログオンし、ドメインが正しく作成されていることを確認します。
    
  - CMS/仲介サーバーにログオンし、Corpnet NIC で有効な IP アドレスが割り当てられていることと、AD サーバーの IP アドレスとして有効な固定 IP アドレスと DNS が構成されていることを確認します。
    
  - CMS/仲介サーバーにログオンし、コマンドプロンプトを開きます。 Active Directory サーバーの FQDN と IP アドレスに対して ping を実行できることを確かめます。 実行できない場合は、IP アドレスの競合が考えられます。 Active Directory に新しい IP を割り当てて、CMS/仲介サーバーで DNS を更新することを試してください。
    
- **問題: "仮想イーサネットスイッチの削除中にエラーが発生しました。" というエラーメッセージが表示されます。仮想スイッチ ' Cloud Connector 管理スイッチ ' は、仮想マシンを実行しているか、子プールに割り当てられているため、削除できません。 "**
    
    **解像度:** 展開後、"クラウドコネクタ管理スイッチ" は削除されませんでした。 このエラーが発生した場合は、Hyper-v マネージャーに移動して、仮想マシンがまだ接続されていないことを確認してください。 仮想マシンがまだ接続されている場合は、切断し、管理スイッチを削除します。 それでも管理スイッチを削除できない場合は、ホストサーバーを再起動して、もう一度やり直してください。
    
- **問題: 次のエラーメッセージが表示されました。 "サービス RTCMRAUTH を開始できませんでした。サービスが無効になっていないことを確認してください。 "**
    
    > [!NOTE]
    > この問題は、Cloud Connector バージョン1.4.2 より前のバージョンにのみ適用されます。 
  
    開始できない原因としては、このフロントエンド サーバーが (コンピューターのフェイルオーバーを使用して) 以前も失敗してやり直したことも考えられます。その場合は、(コンピューターのフェールバックアップを使用して) フェールバックを呼び出してください。
    
    **解決策:** この問題は、ルート CA 証明書または中間 CA 証明書がエッジ サーバーで信頼されていない場合に、エッジ サーバーで発生します。外部証明書をインポートできるとしても、証明書チェーンが破損しています。この状況では、RTCMRAUTH か RTCSRV、またはその両方のサービスが開始できません。
    
    ルート CA 証明書と、外部証明書の中間 CA 証明書をすべて手動でエッジ サーバーにをインポートしてから、エッジ サーバーを再起動します。エッジ サーバーで RTCMRAUTH サービスと RTCSRV サービスが開始したことを確認したら、ホスト サーバーに戻り、管理者として PowerShell コンソールを起動し、次のコマンドレットを実行して新しい展開に切り替えます。
    
  ```
  Switch-CcVersion
  ```

- 
    
    **問題: Windows Update の適用中にホスト サーバーが再起動され、サーバーによる呼び出しに失敗する。**
    
    **解決策:** 高可用性環境を展開した場合は、Windows Update を手動で確認およびインストールするときに、1 台のホスト マシン (展開インスタンス) を現在のトポロジに移動するか、またはそこから移動するのに役立つコマンドレットが用意されています。これを行うには、次の手順を実行します。
    
1. ホスト サーバーで、管理者として PowerShell コンソールを起動して、次を実行します。
    
   ```
   Enter-CcUpdate
   ```

2. 利用可能な更新をチェックしてインストールします。
    
3. PowerShell コンソールで、次のコマンドレットを実行します。
    
   ```
   Exit-CcUpdate
   ```

- 
    
    **問題: PSTN 番号を使って Skype for Business クライアントから通話を発信するとき、別の PSTN 番号を招待することで電話会議に通話をエスカレートできない。**
    
    **解像度:** この問題を解決するには、「[オンラインハイブリッド仲介サーバーの設定を構成](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer)する」を参照してください。
    
- **問題: Active Directory サーバーのインストール中に、「Windows 自動更新が有効になっていません。新しくインストールした役割または機能が自動的に更新されるようにするには、[Windows Update] を有効にしてください」という Windows Update に関する警告メッセージが表示される。**
    
    **解像度:** Skype for Business テナント管理者の資格情報を使用してテナントリモート PowerShell セッションを開始し、次のコマンドレットを実行して、サイトの_Enableautoupdate_構成を確認します。
    
  ```
  Get-CsHybridPSTNSite
  ```

    _Enableautoupdate_が**True**に設定されている場合、CCEManagement サービスは仮想マシンとホストサーバーの両方の Windows 更新プログラムのダウンロードとインストールを処理するため、この警告メッセージは安全に無視できます。 _Enableautoupdate_が**False**に設定されている場合は、次のコマンドレットを実行して**True**に設定します。
    
  ```
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    または、更新プログラムを手動で確認してインストールすることができます。 次のセクションを参照してください。
    
- **問題: エラーメッセージが表示さ\<れる: 現在の入力/構成サイト\>名また\<\> \<\> \<はコンピューター名または仲介サーバーの IP アドレスが原因で、アプライアンスを登録できません\>既存のアプライアンスと競合しています。コンフリクト製品を削除するか、入力/構成情報を更新して、もう一度登録します。' Register-CcAppliance を実行して、現在のアプライアンスをオンラインに登録します。**
    
    **解像度:** アプライアンスのドメイン\<\>名、 \<仲介サーバーの FQDN\> 、 \<仲介サーバーの IP アドレス\>の値は、一意であり、1つのアプライアンス登録でのみ使用されている必要があります。 既定では\<、ホスト名\>から取得されます。 \<構成 ini ファイル\>で\<定義されて\>いる仲介サーバーの FQDN と仲介サーバーの IP アドレス。
    
    たとえば、(ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) を使用して SiteName=MySite に登録しても、登録済みアプライアンス (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) があると、競合が発生します。
    
    まず、ApplianceRoot ディレクトリ セクションで CloudConnector.ini ファイルを確認します。 ファイルには\<、\>SiteName \<、仲介サーバー\>の\<FQDN、および仲介\>サーバーの IP アドレスの値が表示されます。 \<アプライアンス名\>は、ホストサーバー名です。
    
    次に、Skype for Business テナント管理者の資格情報を使用してテナントリモート PowerShell を起動し、次のコマンドレットを実行して登録済みのアプライアンスを確認します。
    
  ```
  Get-CsHybridPSTNAppliance
  ```

    競合を特定したら、登録済みアプライアンスと一致する情報を CloudConnector.ini ファイルで更新するか、既存のアプライアンスを登録解除して、競合を解決します。
    
  ```
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- **問題: ホストで実行されている展開済みのアプライアンスがある場合、Get-CcRunningVersion コマンドレットは空の値を返します。**
    
  **解像度:** これは、1.3.4 または1.3.8 から1.4.1 にアップグレードした場合に発生する可能性があります。 .Msi を使ってバージョン1.4.1 をインストールした後、他`Register-CcAppliance`のコマンドレットを実行する前に実行する必要があります。 `Register-CcAppliance`%UserProfile%\CloudConnector から%ProgramData%\CloudConnector. にモジュール .ini ファイルを移行します 見逃した場合は、%ProgramData%\CloudConnector フォルダーに新しい system.ini が作成され、1.3.4 または1.3.8 の実行/バックアップバージョンの情報が置き換えられます。
    
  %UserProfile%\CloudConnector と %ProgramData%\CloudConnector フォルダーにある module.ini ファイルを比較します。 相違点がある場合は、%ProgramData%\CloudConnector でそのモジュールの .ini ファイルを`Register-CcAppliance`削除して再実行します。 また、ファイルを手動で実行およびバックアップバージョンに変更することもできます。
    
- **問題: スイッチ-CcVersion コマンドレットを実行して、現在のスクリプトのバージョンとは異なる古いバージョンに切り替えると、この古いバージョンでは高可用性のサポートはありません。**
    
    **解像度:** たとえば、1.4.1 から1.4.2 にアップグレードしたとします。 現在のスクリプトのバージョンは、実行`Get-CcVersion`によって決定され、実行中のバージョン`Get-CcRunningVersion`はどちらも1.4.2 であることが確認できます。 現時点では、実行され`Switch-CcVersion`ているバージョンを1.4.1 に戻す場合、この古いバージョンについては高可用性のサポートはありません。
    
    高可用性を完全にサポートするには、1.4.2 に切り替えて、実行中のバージョンとスクリプト バージョンが同じになるようにします。1.4.2 展開で問題が発生している場合は、できるだけ早くアンインストールして、再インストールしてください。
    
- **問題: 証明機関の証明書、または中央管理ストア、仲介サーバー、エッジ サーバーに対して発行された内部証明書の有効期限が近づいているか、侵害された。**
    
    **解決策:** Skype for Business 証明機関の証明書は 5 年間有効です。中央管理ストア、仲介サーバー、エッジ サーバーに対して発行された内部証明書は 2 年間有効です。
    
    > [!NOTE]
    > クラウドコネクタバージョン2.0 以降では、更新-CcServerCertificate コマンドレットが更新-CcServerCertificate に変更され、CcCACertificate コマンドレットが更新-CcCACertificate に変更されました。 
  
    中央管理ストア、仲介サーバー、エッジサーバーに対して発行された内部証明書の有効期限が近づいている場合は、CcServerCertificate または Update-CcServerCertificate コマンドレットを実行して、証明書を更新します。
    
    証明機関証明書の有効期限が近づいている場合は、CcCACertificate または CcCACertificate コマンドレットを実行して証明書を更新します。
    
    **証明機関の証明書が侵害され、サイトに1つのアプライアンスしか存在しない場合は、** 次の手順を実行します。
    
1. Enter-CcUpdate コマンドレットを実行して、サービスをドレインし、アプライアンスをメンテナンス モードにします。
   
   ```
   Enter-CcUpdate
   ```
   
2. 次のコマンドレットを実行して、リセットし、新しい証明機関の証明書とすべての内部サーバー証明書を作成します。
    
    2.0 より前のクラウドコネクタリリースの場合:
    
    ```
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    または、クラウドコネクタのリリース2.0 以降:
    
    ```
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. ゲートウェイと仲介サーバーの間で TLS が使用されている場合は、アプライアンスから CcRootCertificate コマンドレットを実行してから、エクスポートされた証明書を PSTN ゲートウェイにインストールします。 また、ゲートウェイで証明書を再発行する必要がある場合もあります。

   ```
   Export-CcRootCertificate
   ```

4. 終了-CcUpdate コマンドレットを実行してサービスを開始し、メンテナンスモードを終了します。

   ```
   Exit-CcUpdate
   ```


    **証明機関の証明書が侵害され、サイトに複数のアプライアンスがある場合は、** サイト内の各アプライアンスで次の一連の手順を実行します。
    
    この手順は、ピーク時以外の時間帯に実行することをお勧めします。
    
1. 最初のアプライアンスで、CcCertificationAuthorityFile コマンドレットを実行して、 \<siteroot\>ディレクトリにある CA バックアップファイルをクリーンアップします。

     ```
     Remove-CcCertificationAuthorityFile
     ```
    
2. 「CcUpdate」コマンドレットを実行してサービスをドレインし、各アプライアンスをメンテナンスモードにします。

     ```
     Enter-CcUpdate
     ```
    
3. 最初のアプライアンスで、次のコマンドレットを実行して、新しい証明機関証明書とすべての内部サーバー証明書をリセットして作成します。
    
     2.0 より前のクラウドコネクタリリースの場合:
    
     ```
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     または、クラウドコネクタのリリース2.0 以降:
    
     ```
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. 最初のアプライアンスで、次のコマンドレットを実行して、CA ファイルを\<siteroot\>フォルダにバックアップします。
    
     ```
     Backup-CcCertificationAuthority
     ```
   
5. 同じサイト内の他のすべてのアプライアンスで、次のコマンドを実行して CA バックアップファイルを使用すると、すべてのアプライアンスで同じルート証明書が使用され、新しい証明書が要求されます。 
   
     ```
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. ゲートウェイと仲介サーバーの間で TLS が使用されている場合は、サイト内の任意のアプライアンスから CcRootCertificate コマンドレットを実行し、エクスポートされた証明書を PSTN ゲートウェイにインストールします。 また、ゲートウェイで証明書を再発行する必要がある場合もあります。
  
     ```
     Export-CcRootCertificate
     ```
     
7. 終了-CcUpdate コマンドレットを実行してサービスを開始し、メンテナンスモードを終了します。 

     ```
     Exit-CcUpdate
     ```
    
    
- **問題: クラウドコネクタ管理サービスログ "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService Error: 0: 予期しない例外が発生したときに、次のエラーメッセージが表示される状態をオンラインに報告: CmdletInvocationException: ユーザー \<グローバルテナント管理者\>のログオンに失敗しました。新しい credential オブジェクトを作成して、正しいユーザー名とパスワードを使用したことを確認してください。---\>**
    
    **解像度:** クラウドコネクタのアプライアンスが登録されてから、Office 365 グローバルテナント管理者の資格情報が変更されました。 クラウドコネクタアプライアンスでローカルに保存されている資格情報を更新するには、ホストアプライアンスで、管理者 PowerShell から次の操作を実行します。
    
  ```
  Set-CcCredential -AccountType TenantAdmin
  ```

- **問題: 展開に使用した host server アカウントのパスワードを変更すると、次のエラーメッセージが表示されます: "Convertto-json-「: 指定された状態で使用するためのキーが無効です。"%ProgramFiles%\Skype for Business Cloud Connector の場合Edition\ManagementService\CceManagementService.log または Get-CcCredential コマンドレットを実行中です。**
    
    **解像度:** すべてのクラウドコネクタの資格情報は、次のファイルに格納されます。 "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>. ホスト サーバーのパスワードを変更するときには、ローカルで格納されている資格情報を更新する必要があります。
    
    **Cloud Connector バージョン 1.4.2 を実行している場合は、** 次の手順を実行してすべての Cloud Connector パスワードを再生成します。
    
  1. ホスト サーバーを再起動します。
    
  2. 次のファイルを削除します: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.
    
  3. 管理者として PowerShell コンソールを起動し、[この説明に従ってパスワードを再入力するには、"Register Appliance-Local]" を実行します。 Cloud Connector の展開で前回使用したパスワードと同じパスワードを入力します。
    
     **クラウドコネクタバージョン2.0 以降を実行**している場合は、次の手順に従って、すべてのクラウドコネクタのパスワードを再生成します。
    
  4. ホスト サーバーを再起動します。
    
  5. 次のファイルを削除します: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.
    
  6. 管理者として PowerShell コンソールを起動し、[この説明に従ってパスワードを再入力するには、"Register Appliance-Local]" を実行します。 
    
     キャッシュされているファイルが Cloud Connector バージョン 1.4.2 で生成されたファイルである場合は、パスワードを求められたときに CceService パスワードの VMAdmin パスワードを使用します。その他すべてのアカウントについては、Cloud Connector の展開で前回使用したパスワードと同じパスワードを入力します。
    
     キャッシュされているパスワード ファイルが Cloud Connector バージョン 1.4.2 で生成されたファイルであり、DomainAdmin と VMAdmin のパスワードが異なる場合は、次の手順を実行する必要があります。
    
  7. Set-CcCredential -AccountType DomainAdmin を次のように実行します。
    
  8. 以前のアカウントの資格情報を求められた場合は、CceService パスワードに使用した資格情報を入力します。
    
  9. 新しいアカウントの資格情報を求められた場合は、以前使用していた DomainAdmin パスワードを入力します。
    
     キャッシュされたパスワードファイルがクラウドコネクタバージョン2.0 以降で生成された場合、既定では、VmAdmin と DomainAdmin は CceService と同じパスワードを使用します。 DomainAdmin と VMAdmin のパスワードを変更した場合は、次の手順を実行する必要があります。
    
  10. Set-CcCredential -AccountType DomainAdmin を次のように実行します。
    
       1. 以前のアカウントの資格情報を求められた場合は、CceService パスワードに使用した資格情報を入力します。
    
       2. 新しいアカウントの資格情報を求められた場合は、以前使用していた DomainAdmin パスワードを入力します。
    
  11. Set-CcCredential -AccountType VmAdmin を次のように実行します。
    
       1. 以前のアカウントの資格情報を求められた場合は、CceService パスワードに使用した資格情報を入力します。
    
       2. 新しいアカウントの資格情報を求められた場合は、以前使用していた VmAdmin パスワードを入力します。 
    
- **問題: Cloud Connector バージョン2.1 以降で、Register-CcAppliance またはアプライアンス上のその他のコマンドレットを実行すると、次のようなエラーメッセージが表示されます。このオブジェクトには、プロパティ ' Common ' が見つかりません。プロパティが存在することを確認します。C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1: 681 char:14 "**
    
    **解像度:** Cloud Connector 2.1 以降には、.NET Framework 4.6.1 以降が必要です。 アプライアンスの .NET Framework をバージョン4.6.1 以降に更新して、もう一度コマンドレットを実行してください。

- **問題: Cloud Connector エディション2.1 で、インストール-CcAppliance を実行しているときに、"新しいインスタンスをインストールできませんでした。" というエラーメッセージが表示されることがあります。これは、XmlNode のプロパティを設定するために文字列のみを値として使うことができるためです。**

   **解像度:** Cloudconnector の [Common] セクションで、以下のように "状態" の構成を追加してください: CountryCode = US 州 = WA City = レドモンド

   "状態" 行に値を設定することは必須ではありませんが、Cloudconnector の .ini ファイルから "状態" 行を削除することはできません。

- **問題: 次のエラーメッセージが表示されます。 "WindowsImage: WindowsImage に失敗しました。エラーコード = 0xc1550115 "は、クラウドコネクタエディションをインストールまたはアップグレードするときに発生します。**
    
    **解像度:** 管理者として PowerShell コンソールを起動し、"DISM.EXE-Cleanup-Wim" を実行します。 Troubled のすべての画像がクリーンアップされます。 インストール-CcAppliance をもう一度実行するか、bits が自動的にアップグレードされるのを待ちます。
    
- **問題: HA 環境での第1のクラウドコネクタのアプライアンスの展開に失敗する**
    
    **解像度:** 実行する手順は、展開の失敗の理由によって異なります。
    
  - 最初の Cloud Connector アプライアンスに障害が発生し、その原因を特定できない場合は、展開が成功するまでもう一度アプライアンスをインストールしてから、他のアプライアンスをインストールする必要があります。
    
  - 最初のクラウドコネクタのアプライアンスで、外部証明書の問題などの軽微な問題が発生した場合は、アプライアンスを再インストールしなくても問題を解決できる可能性があります。 次に、テナントのリモート PowerShell を使用して、次のように展開を成功としてマークできます。 (最初の展開が成功した場合に、次の手順を使用することもできますが、何らかの理由により、クラウドコネクタが成功として展開を報告できない場合もあります)。
    
  - 最初の Cloud Connector アプライアンスの Id (GUID) を取得するには、CsHybridPSTNAppliance コマンドレットを実行します。
    
  - アプライアンスが正常に展開されたことを示すには、次のように CsCceApplianceDeploymentStatus を実行します。
    
  ```
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- **問題: ホスト サーバーまたは仮想マシン上で Windows Update を手動で確認してインストールする必要がある。**
    
   **解決策:** Skype for Business Cloud Connector エディションが備える自動 OS 更新プログラムを活用することをお勧めします。アプライアンスをオンライン管理に登録して、自動 OS 更新を有効にすると、ホスト サーバーと仮想マシンが自動的に Windows Update を確認して、OS 更新の時間枠設定に従ってインストールします。
    
   Windows Update を手動で確認してインストールする必要がある場合は、展開の種類に該当する、このセクションに記載されている手順に従ってください。更新に必要なダウン タイムを最小限にするため、ホスト サーバーと、そこで動作する仮想マシンの両方の更新を計画する必要があります。
    
   また、Windows Server Update Services (WSUS) サーバーを使用して、Cloud Connector サーバーに更新プログラムを提供することもできます。Windows Update が自動的にインストール**されない**ように構成してください。
    
   Cloud Connector 展開を手動で更新する方法については、次のセクションを参照してください。
    
- **問題: Cloud Connector が新しいビルドに更新された場合、クラウドコネクタコマンドレットは更新されません。** これは、自動更新が行われたときに PowerShell ウィンドウを開いたままにした場合に発生することがあります。
    
  **解像度:** 更新されたコマンドレットを読み込むには、次のいずれかの手順を実行します。
    
   - クラウドコネクタのアプライアンスで PowerShell を閉じ、PowerShell をもう一度開きます。
    
     - または、Import-モジュール CloudConnector-Force を実行できます。 
 
-   **問題: "Stop-CsWindowsService" という用語は、コマンドレット、関数、スクリプトファイル、または操作可能なプログラムの名前として認識されません。 "入力-CcUpdate コマンドレットを実行しようとしたときにエラーが発生しました。"**

    **解像度:**$HOME \AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache ファイルを削除します。
PowerShell では、このファイルが検出されたモジュールのコマンドレットのキャッシュとして作成されるため、そのたびにすべてのモジュールを再分析する必要がなくなります。 多くの場合、そのキャッシュから読み戻されたときに、誤った結果を示すファイルが破損していました。

-   **問題: "インポート-モジュール CloudConnector" でエラー "Import-モジュールが発生しました。モジュールディレクトリで有効なモジュールファイルが見つからなかったため、指定されたモジュール" CloudConnector "は読み込まれませんでした"**

    **解決策:**
    - 実際に CloudConnector モジュールが c:\Program Files\WindowsPowerShell\Modules の下に存在することを確認します。
    
    - この場所に CloudConnector モジュールが存在することを検証した後、モジュールの場所へのパスを格納する PSModulePath 環境変数を変更できます。
    
     a. 一時的な変更: 管理者として Powershell を起動し、次のコマンドを実行します。 $env:P SModulePath = $env:P SModulePath + ";C:\Program Files\WindowsPowerShell\Modules\"
        
     b. 永続的な変更を行うには、管理者として PowerShell を起動し、次のコマンドを1つずつ実行します。 $CurrentValue = [環境]:: GetEnvironmentVariable ("PSModulePath", "Machine") SetEnvironmentVariable ("PSModulePath", "コンピューター") ("" $CurrentValue, "")C:\Program Files\WindowsPowerShell\Modules "," Machine ")

    
## <a name="install-windows-updates-manually"></a>Windows 更新プログラムを手動でインストールする

ご利用の環境で自動更新を使用しない場合は、次の手順に従って、Windows Update を手動で確認して適用します。 Windows Update の確認とインストールでは、サーバーの再起動が必要となる場合があります。 ホストサーバーが再起動すると、ユーザーはクラウドコネクタを使用して通話の発信や受信を行うことができなくなります。 更新プログラムを手動で確認してインストールすることにより更新の実行時期を制御してから、サービスの中断を回避するために選んだ期間中に必要に応じてコンピューターを再起動できます。
  
更新プログラムを手動で確認するには、各ホスト サーバーに接続し、[**コントロール パネル**] を開きます。 [**システムとセキュリティ\>の Windows Update**] を選択し、環境に合わせて更新とサーバーの再起動を管理します。
  
- サイトにアプライアンスが 1 台しかない場合は、各仮想マシンに接続し、[**コントロール パネル**] に接続します。 [**システムとセキュリティ\>の Windows Update**] を選び、必要に応じて、更新プログラムとサーバーの再起動を構成します。
    
- サイトに複数のアプライアンスがある場合、更新中、更新して再起動するインスタンスにはアクセスできません。更新が完了して、すべての仮想マシンと、仮想マシン上のすべての Skype for Business サービスが開始するまで、展開内の別のインスタンスに接続することになります。サービス中断の可能性を避けるため、更新プログラム適用中にインスタンスから HA を削除し、完了してから復元することができます。その手順は、次のとおりです。
    
1. ホスト サーバーごとに、管理者として PowerShell コンソールを開きます。
    
2. 次のコマンドレットを使用して、HA からインスタンスを削除します。
    
   ```
   Enter-CcUpdate
   ```

3. 
    
    単一インスタンスの手順に従い、更新を手動で適用し仮想マシンを再起動します。
    
4. 次のコマンドレットを使用して、HA にインスタンスを戻します。
    
   ```
   Exit-CcUpdate
   ```

マルチサイト展開の場合は、展開内の各サイトに対して 1 つのサイトの手順を実行し、一度に 1 つのサイトに対して更新プログラムを適用します。
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a>クラウドコネクタホストコンピューターにウイルス対策ソフトウェアをインストールするときのヒント

クラウドコネクタホストコンピューターにウイルス対策ソフトウェアをインストールする必要がある場合は、次の除外を追加する必要があります。
  
- 各マシンのローカルアプライアンスディレクトリ。
    
- 各コンピューター上のリモートサイトディレクトリ。
    
- コンピューター上のローカルサイトディレクトリは共有サイトルートフォルダーをホストします。
    
- %ProgramFiles%\Skype for Business Cloud Connector エディション
    
- %ALLUSERSPROFILE%\CloudConnector
    
- %ProgramFiles%\WindowsPowerShell\Modules\CloudConnector
    
- ManagementService のプロセスを実行します。
