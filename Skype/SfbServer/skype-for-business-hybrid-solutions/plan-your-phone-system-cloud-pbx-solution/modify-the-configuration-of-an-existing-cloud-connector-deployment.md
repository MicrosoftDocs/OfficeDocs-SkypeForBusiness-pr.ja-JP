---
title: 既存の Cloud Connector の展開構成の変更
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 90490c65-0e40-4e85-96e1-751f27897e25
description: このトピックの手順に従って、既存の Skype for Business Cloud Connector エディション1.4.1 以降の展開の構成を変更します。
ms.openlocfilehash: ead952c0ba567a8e5d81c52144de597e50d24014
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002287"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a>Modify the configuration of an existing Cloud Connector deployment
 
このトピックの手順に従って、既存の Skype for Business Cloud Connector エディション1.4.1 以降の展開の構成を変更します。 
  
## <a name="modify-the-configuration-of-a-single-site"></a>1 つのサイトの構成を変更する
<a name="BKMK_SIngleSite"> </a>

サイトに 1 つのアプライアンスしかなく、アプライアンスを展開した後で構成設定を変更する必要がある場合は、CloudConnector.ini ファイルを変更して、もう一度展開を開始することができます。
  
1. 次のコマンドレットを実行して、ホスト サーバー上にあるすべての既存の仮想マシンをアンインストールします。 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. アプライアンスを登録解除するには、次のコマンドレットを実行します。
    
   ```powershell
   Unregister-CcAppliance
   ```

3. アプライアンス ディレクトリ の CloudConnector.ini ファイルを更新します。
    
4. 次のコマンドレットを実行して構成を更新します: (この手順はバージョン2にのみ適用されます。以前のバージョンでは、次の手順に進みます)。
    
   ```powershell
   Import-CcConfiguration 
   ```

5. アプライアンスをもう一度登録するには、次のコマンドレットを実行します。
    
   ```powershell
   Register-CcAppliance
   ```

6. Skype for Business Cloud Connector エディションをインストールするには、次のコマンドレットを実行します。
    
   ```powershell
   Install-CcAppliance
   ```

サイトに複数のアプライアンスがある場合は、次の手順に従って、CloudConnector.ini ファイルを変更し、アプライアンスを 1 つずつ再展開する必要があります。
  
1. 現在のアプライアンス上にある既存の仮想マシンをすべてアンインストールするには、次のコマンドレットを実行します。  
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. アプライアンスを登録解除するには、次のコマンドレットを実行します。
    
   ```powershell
   Unregister-CcAppliance
   ```

3. アプライアンス ディレクトリ の CloudConnector.ini ファイルを更新します。
    
4. 次のコマンドレットを実行して構成を更新します: (この手順はバージョン2にのみ適用されます。以前のバージョンでは、次の手順に進みます)。
    
   ```powershell
   Import-CcConfiguration 
   ```

5. アプライアンスをもう一度登録するには、次のコマンドレットを実行します。
    
   ```powershell
   Register-CcAppliance
   ```

6. 最新の構成を取得するには、サイトにあるその他すべてのアプライアンスで次のコマンドレットを実行します。
    
   ```powershell
   Publish-CcAppliance
   ```

7. 次のコマンドレットを実行して、現在のアプライアンスのクラウドコネクタを再展開します。
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a>複数のサイトの構成を変更する
<a name="BKMK_MultipleSites"> </a>

展開内の複数のサイトの構成を変更するには、1つのサイトの手順に従って、一度に1つのサイトを更新します。
  
## <a name="modify-the-configuration-of-your-office-365-tenant-to-enable-automatic-updates"></a>自動更新を有効にするために Office 365 テナントの構成を変更する
<a name="BKMK_MultipleSites"> </a>

オペレーティングシステムの自動更新と Bits の自動更新を有効にするには、Skype for Business テナント管理者アカウントを使用してオンライン管理を行ってから、次のようにテナントのリモート PowerShell を使用する必要があります。
  
オペレーティングシステムの自動更新または Bits の自動更新を無効にした場合、ホストと仮想マシンで重要な Windows の更新プログラムが失われることがあります。クラウドコネクタは、新しいバージョンに自動的にアップグレードされることはありません。 自動更新を有効にすることを強くお勧めします。
  
1. サイトの EnableAutoUpdate プロパティは、true (既定値) に設定されている必要があります。 EnableAutoUpdate が True に設定されていることを確認するには、次のコマンドレットを実行します。
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. テナントの自動更新の時間枠を作成します。
    
    時間枠は、日単位、週単位、月単位で設定できます。すべての時間枠には、開始時刻と期間が必要です。
    
   - 日単位の時間枠の場合は、開始時刻と期間のみが必要です。 
    
   - 週単位の時間枠の場合は、1 つまたは複数の曜日が必要です。
    
   - 月単位の時間枠の場合は、2 種類あります。1 番目の種類では、日付を 1 つ指定します。2 番目の方法では、第何週の何曜日かを (それぞれ 1 つでも複数でも可) 指定します。
    
   - 各テナントに定義できる時間枠は 20 件です。新しいテナントには、オペレーティング システムの更新と BITS の更新用の既定の時間枠が作成されます。日単位、週単位、月単位の時間枠を設定するには、次のコマンドレットを実行します。
    
   ```powershell
   New-CsTenantUpdateTimeWindow -Identity Night -Daily -StartTime 22:00 -Duration 6:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity WeekdayNight -Weekly -DaysOfWeek Monday,Tuesday,Wednesday,Thursday,Friday -StartTime 22:00 -Duration 4:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity FirstAndLastWeekend -Monthly -WeeksOfMonth First,Last -DaysOfWeek Sunday,Saturday -StartTime 0:00 -Duration 10:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity MidDayOfMonth -Monthly -DayOfMonth 15 -StartTime 0:00 -Duration 1.00:00
   ```

   - 更新時間枠をサイトに割り当てます。  
    
     BITS の更新時間枠と OS の更新時間枠は、個別に構成します。 どちらにも、1 つまたは複数の時間枠を割り当てることができます。 各時間枠は、異なるサイトや異なる用途 (BITS の更新と OS の更新) に割り当てることができます。 次のコマンドレットを実行して時間枠をサイトに設定します。  
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a>専用のテナント管理者の資格情報を更新する
<a name="BKMK_MultipleSites"> </a>

クラウドコネクタの Office 365 テナントの管理上の変更は、必要なアクセス許可を持つアカウントから行われます。 2.0 より前のクラウドコネクタのバージョンでは、そのアカウントはグローバルテナント管理者専用のアカウントです。 クラウドコネクタバージョン2.0 以降では、そのアカウントは、Skype for Business の管理者権限を持つ Office 365 アカウントになることができます。
  
Office 365 で管理者アカウントの資格情報を変更した場合は、展開した各クラウドコネクタのアプライアンスで次の管理者 PowerShell コマンドを実行して、クラウドコネクタのローカルにキャッシュされた資格情報を更新する必要があります。
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a>ホスト サーバーのパスワードを更新する
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> このセクションは Cloud Connector バージョン 2.0 以降のみを対象としています。 
  
すべてのクラウドコネクタの資格情報は、次のファイルに格納されます。 "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>. ホスト サーバーのパスワードを変更するときには、ローカルで格納されている資格情報を更新する必要があります。
  
クラウドコネクタアプライアンスでローカルに保存されている資格情報を更新するには、 [cccredential](get-cccredential.md)と[cccredential](set-cccredential.md)コマンドレットを使用して、次の手順を実行します。
  
1. 次のコマンドを実行して、後で必要になるパスワードを取得します。 
    
   - Get-CcCredential -AccountType DomainAdmin -DisplayPassword
    
   - Get-CcCredential -AccountType VMAdmin -DisplayPassword
    
   - Get-CcCredential -AccountType CceService -DisplayPassword
    
2. ホスト サーバー上でお使いのアカウントのパスワードを変更します。
    
3. ホスト サーバーを再起動します。
    
4. 次のファイルを削除します: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.
    
5. 管理者として PowerShell コンソールを起動し、[この説明に従ってパスワードを再入力するには、"Register Appliance-Local]" を実行します。 Cloud Connector の展開で前回使用したパスワードと同じパスワードを入力します。
    
既定では、VmAdmin および DomainAdmin では CceService と同じパスワードが使用されます。手順 1 で返された DomainAdmin、VMAdmin および CceService のパスワードが異なる場合は、次の手順を実行する必要があります。
  
1. Set-CcCredential -AccountType DomainAdmin を次のように実行します。
    
1. 以前のアカウントの資格情報を求められた場合は、CceService パスワードに使用した資格情報を入力します。
    
2. 新しいアカウントの資格情報を求められた場合は、手順 1 で返された DomainAdmin パスワードを入力します。
    
2. Set-CcCredential -AccountType VmAdmin を次のように実行します。
    
1. 以前のアカウントの資格情報を求められた場合は、CceService パスワードに使用した資格情報を入力します。
    
2. 新しいアカウントの資格情報を求められた場合は、手順 1 で返された VmAdmin パスワードを入力します。 
    
## <a name="update-the-password-for-the-cceservice-account"></a>CceService アカウントのパスワードを更新する
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> このセクションは、Cloud Connector バージョン2.0.1 以降に適用されます。 
  
クラウドコネクタサービスは、クラウドコネクタ管理サービスを実行します。 CceService アカウントは、クラウドコネクタエディションの展開中に作成され、次のファイルに保存されます。 "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>"と"%SystemDrive%\Programdata\Cloudconnector\credentials..CceService "。
  
すべてのアプライアンスがサイトディレクトリ共有にアクセスできるようにするには、CceService アカウントのパスワードが、サイト内に展開されているすべてのアプライアンスで同じである必要があります。 以下の点について留意してください。
  
- 既定では、CceService アカウントは "パスワードを無期限にする" として構成されています。 パスワードを更新する場合は、この設定を維持することをお勧めします。
    
- パスワードは、非ピーク時の使用期間内、および bits または Windows の更新プログラムの自動更新の時間帯外で更新する必要があります。 パスワードを更新する際には、アプライアンスをドレインして再起動する必要があります。これには時間がかかります。 アプライアンスを再起動すると、自動更新操作が中断されます。 
    
- CceService アカウントのパスワードを変更する場合は、すべての資格情報を指定して、ローカルに保存されているファイルで更新する必要があります。 
    
同じ PSTN サイトに属している各アプライアンスについて、次の情報を指定する必要があります。 
  
1. 後で使用するアカウント名とパスワードを取得するには、次のコマンドを実行します。
    
   ```powershell
   Get-CcCredential -AccountType TenantAdmin -DisplayPassword
   Get-CcCredential -AccountType TenantAdmin
   Get-CcCredential -AccountType OMSWorkspace -DisplayPassword
   Get-CcCredential -AccountType OMSWorkspace 
   Get-CcCredential -AccountType ExternalCert -DisplayPassword
   Get-CcCredential -AccountType CABackupFile -DisplayPassword
   Get-CcCredential -AccountType CceService -DisplayPassword
   Get-CcCredential -AccountType VMAdmin -DisplayPassword
   Get-CcCredential -AccountType DomainAdmin -DisplayPassword
   ```

2. 「CcUpdate」コマンドレットを実行してアプライアンスをドレインし、手動メンテナンスモードに移行します。
    
3. ホストサーバー上の CceService アカウントのパスワードを更新します。
    
4. ホスト サーバーを再起動します。
    
5. Restore-CcCredentials コマンドレットを実行して、説明に従ってパスワードを再入力します。 
    
    CceService アカウントを除き、クラウドコネクタの展開前に入力したパスワードと同じパスワードを入力してください。 CceService アカウントの場合は、新しいパスワードを入力します。 CceService アカウントの新しいパスワードが、PSTN サイト内のすべてのアプライアンスで同じであることを確認してください。
    
6. 既定では、VmAdmin および DomainAdmin では CceService と同じパスワードが使用されます。手順 1 で返された DomainAdmin、VMAdmin および CceService のパスワードが異なる場合は、次の手順を実行する必要があります。
    
7. Set-CcCredential -AccountType DomainAdmin を次のように実行します。
    
   - 以前のアカウントの資格情報を求められた場合は、CceService パスワードに使用した資格情報を入力します。
    
   - 新しいアカウントの資格情報を求められた場合は、手順 1 で返された DomainAdmin パスワードを入力します。
    
8. Set-CcCredential -AccountType VmAdmin を次のように実行します。
    
   - 以前のアカウントの資格情報を求められた場合は、CceService パスワードに使用した資格情報を入力します。
    
   - 新しいアカウントの資格情報を求められた場合は、手順 1 で返された VmAdmin パスワードを入力します。 
    
9. 終了-CcUpdate コマンドレットを実行して、手動メンテナンスモードからアプライアンスを移動します。
    
10. 同じ PSTN サイト内のすべてのアプライアンスでこれらの手順を完了したら、サイトルートディレクトリ内の次のファイルを削除します。
    
    - CcLockFile
    
    - Site_\<Edge の外部 Sip プール fqdn\>
    
    - Tenant_\<Edge の外部 Sip プール fqdn\>
    
    - TenantConfigLock_\<Edge の外部 Sip プール fqdn\>
    
## <a name="add-a-new-sip-domain"></a>新しい SIP ドメインを追加する 
<a name="BKMK_UpdatePassword"> </a>

新しい SIP ドメイン (または複数の SIP ドメイン) を既存のクラウドコネクタ展開に追加するには、次の操作を行います。
  
1. Office 365 でドメインを更新する手順を完了し、DNS レコードを追加できることを確認します。 Office 365 でドメインをセットアップする方法の詳細については、「 [office 365 にドメインを追加](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)する」を参照してください。
    
2. 新しい SIP ドメインでクラウドコネクタ構成ファイルを更新します。
    
3. クラウドコネクタ構成で定義されている SIP ドメインごとに、追加の SAN 名を使用して、新しいエッジ外部証明書を要求します。 
    
4. 新しい Microsoft Edge 外部証明書のパスを次のように設定します。
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    「[1 つのサイトの構成を変更する](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite)」または「[複数のサイトの構成を変更する](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites)」の手順を実行します。
    
## <a name="modify-the-primary-sip-domain"></a>プライマリ SIP ドメインを変更する
<a name="BKMK_UpdatePassword"> </a>

クラウドコネクタの展開でプライマリ SIP ドメインを変更する必要がある場合は、次の操作を行います。
  
1. Office 365 でドメインを更新する手順を完了し、DNS レコードを追加できることを確認します。 Office 365 でドメインをセットアップする方法の詳細については、「 [office 365 にドメインを追加](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)する」を参照してください。
    
2. 新しい SIP ドメインでクラウドコネクタ構成ファイルを更新します。
    
3. クラウドコネクタ構成で定義されている SIP ドメインごとに、追加の SAN 名を使用して、新しいエッジ外部証明書を要求します。 
    
4. 新しい Microsoft Edge 外部証明書のパスを次のように設定します。
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    クラウドコネクタの管理者 PowerShell で次のコマンドレットを実行して、サイト内の各アプライアンスのテナント登録を削除します。
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    Skype for Business Online の PowerShell で次のコマンドを実行して、各サイトのサイト登録を削除します。
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    Cloud Connector 上の管理者 PowerShell で次のコマンドレットを実行して、各アプライアンスをアンインストールします。
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     各アプライアンスを登録するには、Cloud Connector の管理者 PowerShell で次のコマンドレットを実行します。
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     各アプライアンスを1つずつインストールします。そのためには、Cloud Connector 上の管理者 PowerShell で次のコマンドレットを実行します。
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a>外部境界の証明書を新しい証明書に置き換える
<a name="BKMK_UpdatePassword"> </a>

クラウドコネクタのアプライアンスで外部エッジ証明書を置き換える必要がある場合は、新しいエッジ証明書を取得し、秘密キーと完全な証明書チェーンを含む PFX ファイルを準備してから、各アプライアンスで次の操作を行います。
  
1. 「CcUpdate の入力」コマンドレットを使用して、アプライアンスをメンテナンスモードにします。
    
2. 次のコマンドを実行します。 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    新しい証明書のパスワードが古いものと同じである場合は、インポートは成功します。 パスワードが異なる場合は、パスワードが間違っていることを示すエラーが表示され、-Local パラメーターを使用して CcAppliance コマンドレットを実行して、手順2を繰り返して、パスワードを再設定する必要があります。 
    
4. 終了-CcUpdate コマンドレットを使用して、アプライアンスのメンテナンスモードを終了します。
    

