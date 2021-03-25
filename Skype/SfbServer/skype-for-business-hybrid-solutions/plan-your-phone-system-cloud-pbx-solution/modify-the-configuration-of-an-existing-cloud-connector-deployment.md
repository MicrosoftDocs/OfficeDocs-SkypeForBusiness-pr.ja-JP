---
title: 既存のクラウド コネクタの展開構成の変更
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 90490c65-0e40-4e85-96e1-751f27897e25
description: このトピックの手順に従って、既存の Skype for Business Cloud Connector Edition 1.4.1 以降の展開の構成を変更します。
ms.openlocfilehash: 7fdfdd5ac5a76ebbc3ac58e12a69e2e3af1330cd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109173"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a>既存のクラウド コネクタの展開構成の変更

> [!Important]
> Cloud Connector Edition は、Skype for Business Online と共に 2021 年 7 月 31 日に廃止されます。 組織が Teams にアップグレードしたら、直接ルーティングを使用してオンプレミスのテレフォニー ネットワークを Teams に接続する方法 [について説明します](/MicrosoftTeams/direct-routing-landing-page)。

このトピックの手順に従って、既存の Skype for Business Cloud Connector Edition 1.4.1 以降の展開の構成を変更します。 
  
## <a name="modify-the-configuration-of-a-single-site"></a>1 つのサイトの構成を変更する
<a name="BKMK_SIngleSite"> </a>

サイト内にアプライアンスが 1 つしかない場合、アプライアンスの展開後に構成設定を変更する場合は、CloudConnector.ini ファイルを変更して展開を再度開始できます。
  
1. 次のコマンドレットを実行して、ホスト サーバー上のすべての既存の仮想マシンをアンインストールします。 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. 次のコマンドレットを実行して、アプライアンスの登録を解除します。
    
   ```powershell
   Unregister-CcAppliance
   ```

3. アプライアンス ディレクトリCloudConnector.iniファイルを更新します。
    
4. 構成を更新するには、次のコマンドレットを実行します (この手順はバージョン 2 にのみ適用されます。以前のバージョンの場合は、次の手順に進みます)。
    
   ```powershell
   Import-CcConfiguration 
   ```

5. 次のコマンドレットを実行して、アプライアンスを再度登録します。
    
   ```powershell
   Register-CcAppliance
   ```

6. Skype for Business Cloud Connector Edition をインストールするには、次のコマンドレットを実行します。
    
   ```powershell
   Install-CcAppliance
   ```

サイトに複数のアプライアンスがある場合は、次の手順に従い、CloudConnector.ini ファイルを変更し、アプライアンスを 1 つ 1 つ再展開する必要があります。
  
1. 次のコマンドレットを実行して、現在のアプライアンス上のすべての既存の仮想マシンをアンインストールします。 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. 次のコマンドレットを実行して、アプライアンスの登録を解除します。
    
   ```powershell
   Unregister-CcAppliance
   ```

3. アプライアンス ディレクトリCloudConnector.iniファイルを更新します。
    
4. 構成を更新するには、次のコマンドレットを実行します (この手順はバージョン 2 にのみ適用されます。以前のバージョンの場合は、次の手順に進みます)。
    
   ```powershell
   Import-CcConfiguration 
   ```

5. 次のコマンドレットを実行して、アプライアンスを再度登録します。
    
   ```powershell
   Register-CcAppliance
   ```

6. サイト内の他のすべてのアプライアンスで次のコマンドレットを実行して、最新の構成を取得します。
    
   ```powershell
   Publish-CcAppliance
   ```

7. 次のコマンドレットを実行して、現在のアプライアンスにクラウド コネクタを再展開します。
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a>複数のサイトの構成を変更する
<a name="BKMK_MultipleSites"> </a>

展開内の複数のサイトの構成を変更するには、1 つのサイトの手順に従って、一度に 1 つのサイトを更新します。
  
## <a name="modify-the-configuration-of-your-microsoft-365-or-office-365-organization-to-enable-automatic-updates"></a>自動更新を有効にするには、Microsoft 365 または Office 365 組織の構成を変更する
<a name="BKMK_MultipleSites"> </a>

オペレーティング システムの自動更新と Bits 自動更新を有効にするには、Skype for Business テナント管理者アカウントをオンライン管理に使用し、次のようにテナント リモート PowerShell を使用する必要があります。
  
オペレーティング システムの自動更新または Bits 自動更新を無効にした場合、ホストと仮想マシンは重要な Windows 更新プログラムを見逃す可能性があります。クラウド コネクタは新しいバージョンに自動的にアップグレードしません。 自動更新を有効にすることを強くお勧めします。
  
1. サイトの EnableAutoUpdate プロパティを true (既定値) に設定する必要があります。 EnableAutoUpdate が true に設定されている場合は、次のコマンドレットを実行します。
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. テナントの自動更新タイム ウィンドウを作成します。
    
    タイム ウィンドウは、日単位、週単位、月単位で指定できます。 すべてのタイム ウィンドウには、開始時刻と期間が必要です。
    
   - 1 日のタイム ウィンドウでは、開始時刻と期間だけが必要です。 
    
   - 週単位のタイム ウィンドウでは、1 日または複数の日を指定できる週の日数が必要です。
    
   - 月次のタイム ウィンドウには、2 つの種類があります。 最初の種類は、月の日を指定します。これは 1 日にできます。 2 番目の種類は、月の週と、1 つのアイテムまたは複数のアイテムの両方を指定できる週の日数を指定します。
    
   - 各テナントには、20 のタイム ウィンドウを定義できます。 新しいテナントの既定のタイム ウィンドウは、オペレーティング システムの更新とビット更新の既定のタイム ウィンドウとして作成されます。 次のコマンドレットを実行して、毎日、毎週、または毎月のタイム ウィンドウを設定します。
    
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

   - 更新時間ウィンドウをサイトに割り当てる。 
    
     ビット更新時刻と OS 更新時刻ウィンドウは個別に構成されます。 両方とも、1 つのタイム ウィンドウまたは複数のタイム ウィンドウを割り当てることができます。 各タイム ウィンドウは、異なるサイトと異なる目的 (ビット更新プログラムと OS 更新プログラム) に割り当てることができます。 サイトのタイム ウィンドウを設定するには、次のコマンドレットを実行します。 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a>専用テナント管理者の資格情報を更新する
<a name="BKMK_MultipleSites"> </a>

Microsoft 365 または Office 365 組織の管理上の変更は、必要なアクセス許可を持つアカウントから行います。 2.0 より前の Cloud Connector バージョンでは、そのアカウントは専用のグローバル テナント管理者アカウントです。 Cloud Connector バージョン 2.0 以降では、そのアカウントには、Skype for Business 管理者権限を持つ Microsoft 365 または Office 365 アカウントを使用できます。
  
Microsoft 365 または Office 365 で管理者アカウントの資格情報が変更された場合は、展開した各クラウド コネクタ アプライアンスで次の Administrator PowerShell コマンドを実行して、クラウド コネクタでローカルにキャッシュされた資格情報も更新する必要があります。
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a>ホスト サーバーのパスワードを更新する
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> このセクションは、Cloud Connector バージョン 2.0 以降に適用されます。 
  
すべてのクラウド コネクタ資格情報は、"%SystemDrive%\Programdata\Cloudconnector\credentials" というファイルに格納されます \<CurrentUser\> 。xml」 ホスト サーバーのパスワードが変更された場合は、ローカルに保存されている資格情報を更新する必要があります。
  
クラウド コネクタ アプライアンスでローカルに保存されている資格情報を更新するには [、Get-CcCredential](get-cccredential.md) コマンドレットと [Set-CcCredential](set-cccredential.md) コマンドレットを使用し、次の手順を実行します。
  
1. 後で必要なパスワードを取得するには、次のコマンドを実行します。 
    
   - Get-CcCredential -AccountType DomainAdmin -DisplayPassword
    
   - Get-CcCredential -AccountType VMAdmin -DisplayPassword
    
   - Get-CcCredential -AccountType CceService -DisplayPassword
    
2. ホスト サーバー上のアカウントのパスワードを変更します。
    
3. ホスト サーバーを再起動します。
    
4. "%SystemDrive%\Programdata\Cloudconnector\credentials" というファイルを削除します \<CurrentUser\> 。xml」
    
5. 管理者として PowerShell コンソールを起動し、"Register-CcAppliance -Local" を実行して、説明に従ってパスワードを再入力します。 クラウド コネクタの展開に対して、前に入力したパスワードと同じパスワードを入力してください。
    
既定では、VmAdmin と DomainAdmin は CceService と同じパスワードを使用します。 手順 1 で返される DomainAdmin、VMAdmin、および CceService のパスワードが異なる場合は、次の手順を実行する必要があります。
  
1. 次Set-CcCredential -AccountType DomainAdmin を実行します。
    
1. 古いアカウント資格情報の入力を求めるメッセージが表示されたら、CceService パスワードに使用した資格情報を入力します。
    
2. 新しいアカウント資格情報の入力を求めるメッセージが表示されたら、手順 1 で返される DomainAdmin パスワードのパスワードを入力します。
    
2. 次Set-CcCredential -AccountType VmAdmin を実行します。
    
1. 古いアカウント資格情報の入力を求めるメッセージが表示されたら、CceService パスワードに使用した資格情報を入力します。
    
2. 新しいアカウント資格情報の入力を求めるメッセージが表示されたら、手順 1 で返される VmAdmin パスワードのパスワードを入力します。 
    
## <a name="update-the-password-for-the-cceservice-account"></a>CceService アカウントのパスワードを更新する
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> このセクションは、Cloud Connector バージョン 2.0.1 以降に適用されます。 
  
クラウド コネクタ サービスは、クラウド コネクタ管理サービスを実行します。 CceService アカウントは、Cloud Connector Edition の展開中に作成され、"%SystemDrive%\Programdata\Cloudconnector\credentials" に格納されます \<CurrentUser\> 。xml" と "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml"
  
すべてのアプライアンスがサイト ディレクトリ共有にアクセスするには、サイト内に展開されているすべてのアプライアンスで CceService アカウントのパスワードが同じである必要があります。 以下の点にご注意ください。
  
- 既定では、CceService アカウントは "Password never expires" として構成されます。 パスワードを更新する場合は、この構成を維持してください。
    
- ピーク時以外の使用期間中、およびビットまたは Windows 更新プログラムの自動更新タイム ウィンドウ以外の場合は、パスワードを更新する必要があります。 パスワードを更新する場合、アプライアンスをドレインして再起動する必要があります。時間がかかる場合があります。 アプライアンスを再起動すると、自動更新操作が中断されます。 
    
- CceService アカウントのパスワードを変更する場合は、すべての資格情報を指定し、ローカルに保存されたファイルで更新する必要があります。 
    
同じ PSTN サイトに属するアプライアンスごとに、次の項目を指定する必要があります。 
  
1. 次のコマンドを実行して、後で使用するアカウント名とパスワードを取得します。
    
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

2. このコマンドレットEnter-CcUpdate実行して、アプライアンスをドレインし、手動メンテナンス モードに移行します。
    
3. ホスト サーバー上の CceService アカウントのパスワードを更新します。
    
4. ホスト サーバーを再起動します。
    
5. 説明にRestore-CcCredentialsパスワードを再入力するには、次のコマンドレットを実行します。 
    
    CceService アカウントを除くクラウド コネクタの展開に対して、前に入力したパスワードと同じパスワードを入力してください。 CceService アカウントに新しいパスワードを入力します。 CceService アカウントの新しいパスワードが PSTN サイトのすべてのアプライアンスで同じことを確認します。
    
6. 既定では、VmAdmin と DomainAdmin は CceService と同じパスワードを使用します。 手順 1 で返される DomainAdmin、VMAdmin、および CceService のパスワードが異なる場合は、次の手順を実行する必要があります。
    
7. 次Set-CcCredential -AccountType DomainAdmin を実行します。
    
   - 古いアカウント資格情報の入力を求めるメッセージが表示されたら、CceService パスワードに使用した資格情報を入力します。
    
   - 新しいアカウント資格情報の入力を求めるメッセージが表示されたら、手順 1 で返される DomainAdmin パスワードのパスワードを入力します。
    
8. 次Set-CcCredential -AccountType VmAdmin を実行します。
    
   - 古いアカウント資格情報の入力を求めるメッセージが表示されたら、CceService パスワードに使用した資格情報を入力します。
    
   - 新しいアカウント資格情報の入力を求めるメッセージが表示されたら、手順 1 で返される VmAdmin パスワードのパスワードを入力します。 
    
9. 手動メンテナンス Exit-CcUpdateからアプライアンスを移動するには、このコマンドレットを実行します。
    
10. 同じ PSTN サイト内のすべてのアプライアンスでこれらの手順を完了したら、サイト ルート ディレクトリ内の次のファイルを削除します。
    
    - CcLockFile
    
    - Site_\<Edge External Sip Pool fqdn\>
    
    - Tenant_\<Edge External Sip Pool fqdn\>
    
    - TenantConfigLock_\<Edge External Sip Pool fqdn\>
    
## <a name="add-a-new-sip-domain"></a>新しい SIP ドメインを追加する
<a name="BKMK_UpdatePassword"> </a>

既存のクラウド コネクタ展開に新しい SIP ドメイン (または複数の SIP ドメイン) を追加するには、次の手順を実行します。
  
1. Microsoft 365 または Office 365 でドメインを更新する手順が完了し、DNS レコードを追加する機能を持っている必要があります。 Microsoft 365 または Office 365 でドメインをセットアップする方法の詳細については [、「Add a domain to Microsoft 365 or Office 365」を参照](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)してください。
    
2. クラウド コネクタ構成ファイルを新しい SIP ドメインまたはドメインで更新します。
    
3. クラウド コネクタ構成で定義されている SIP ドメインごとに sip.domain 用に追加の SAN 名を持つ新しいエッジ外部証明書を要求します。 
    
4. 新しいエッジ外部証明書のパスを次のように設定します。
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    「1 つのサイトの [構成を変更](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) する」または「複数のサイトの構成 [を変更する」の指示に従います](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites)。
    
## <a name="modify-the-primary-sip-domain"></a>プライマリ SIP ドメインの変更
<a name="BKMK_UpdatePassword"> </a>

クラウド コネクタ展開でプライマリ SIP ドメインを変更する必要がある場合は、次の操作を行います。
  
1. Microsoft 365 または Office 365 でドメインを更新する手順が完了し、DNS レコードを追加する機能を持っている必要があります。 Microsoft 365 または Office 365 でドメインをセットアップする方法の詳細については [、「Add a domain to Microsoft 365 or Office 365」を参照](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)してください。
    
2. 新しい SIP ドメインでクラウド コネクタ構成ファイルを更新します。
    
3. クラウド コネクタ構成で定義されている SIP ドメインごとに sip.domain 用に追加の SAN 名を持つ新しいエッジ外部証明書を要求します。 
    
4. 新しいエッジ外部証明書のパスを次のように設定します。
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    管理者 PowerShell on Cloud Connector で次のコマンドレットを実行して、サイト内の各アプライアンスのテナント登録を削除します。
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    Skype for Business Online PowerShell で次のコマンドレットを実行して、各サイトのサイト登録を削除します。
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    クラウド コネクタの管理者 PowerShell で次のコマンドレットを実行して、各アプライアンスをアンインストールします。
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     クラウド コネクタの管理者 PowerShell で次のコマンドレットを実行して、各アプライアンスを登録します。
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     クラウド コネクタの管理者 PowerShell で次のコマンドレットを実行して、各アプライアンスを 1 つ 1 つインストールします。
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a>外部エッジ証明書を新しい証明書に置き換える
<a name="BKMK_UpdatePassword"> </a>

クラウド コネクタ アプライアンスの外部エッジ証明書を置き換える必要がある場合は、新しいエッジ証明書を取得し、プライベート キーと完全な証明書チェーンを含む PFX ファイルを準備し、各アプライアンスで次の操作を行う必要があります。
  
1. このコマンドレットを使用して、アプライアンスをメンテナンス モードEnter-CcUpdateします。
    
2. 次のコマンドを実行します。 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    新しい証明書のパスワードが古い証明書と同じ場合、インポートは成功します。 パスワードが異なる場合は、パスワードが間違っているというエラーが表示され、Register-CcAppliance コマンドレットを -Local パラメーターで実行し、手順 2 を繰り返してパスワードをリセットする必要があります。 
    
4. Exit -CcUpdate コマンドレットを使用して、アプライアンスをメンテナンス モードから外します。
