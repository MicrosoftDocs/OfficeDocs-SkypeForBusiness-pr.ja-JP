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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 90490c65-0e40-4e85-96e1-751f27897e25
description: 既存の Skype for Business Cloud Connector エディション1.4.1 以降の展開の構成を変更するには、このトピックの手順に従います。
ms.openlocfilehash: 4b551d7cd7a61a1113b4b2bb05e2c0f5ca4f3288
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220297"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a>既存の Cloud Connector の展開構成の変更
 
既存の Skype for Business Cloud Connector エディション1.4.1 以降の展開の構成を変更するには、このトピックの手順に従います。 
  
## <a name="modify-the-configuration-of-a-single-site"></a>1つのサイトの構成を変更する
<a name="BKMK_SIngleSite"> </a>

サイト内にアプライアンスが1つしかない場合は、アプライアンスの展開後に構成設定を変更するときに、CloudConnector の .ini ファイルを変更して展開を再度開始することができます。
  
1. 次のコマンドレットを実行して、ホストサーバー上の既存の仮想マシンをすべてアンインストールします。 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. 次のコマンドレットを実行してアプライアンスの登録を解除します。
    
   ```powershell
   Unregister-CcAppliance
   ```

3. アプライアンスディレクトリで CloudConnector .ini ファイルを更新します。
    
4. 次のコマンドレットを実行して構成を更新します。 (この手順はバージョン2にのみ適用されます。以前のバージョンでは、次の手順に進んでください。)
    
   ```powershell
   Import-CcConfiguration 
   ```

5. 次のコマンドレットを実行して、アプライアンスを再度登録します。
    
   ```powershell
   Register-CcAppliance
   ```

6. Skype for Business Cloud Connector エディションをインストールするには、次のコマンドレットを実行します。
    
   ```powershell
   Install-CcAppliance
   ```

サイト内に複数のアプライアンスがある場合は、次の手順に従って、CloudConnector の .ini ファイルを変更し、各アプライアンスを1つずつ再展開する必要があります。
  
1. 次のコマンドレットを実行して、現在のアプライアンス上にある既存の仮想マシンをすべてアンインストールします。 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. 次のコマンドレットを実行してアプライアンスの登録を解除します。
    
   ```powershell
   Unregister-CcAppliance
   ```

3. アプライアンスディレクトリで CloudConnector .ini ファイルを更新します。
    
4. 次のコマンドレットを実行して構成を更新します。 (この手順はバージョン2にのみ適用されます。以前のバージョンでは、次の手順に進んでください。)
    
   ```powershell
   Import-CcConfiguration 
   ```

5. 次のコマンドレットを実行して、アプライアンスを再度登録します。
    
   ```powershell
   Register-CcAppliance
   ```

6. サイト内の他のすべてのアプライアンスで次のコマンドレットを実行して、最新の構成を選択します。
    
   ```powershell
   Publish-CcAppliance
   ```

7. 次のコマンドレットを実行して、現在のアプライアンスで Cloud Connector を再展開します。
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a>複数のサイトの構成を変更する
<a name="BKMK_MultipleSites"> </a>

展開内の複数のサイトの構成を変更するには、1つのサイトの手順に従って、一度に1つのサイトを更新します。
  
## <a name="modify-the-configuration-of-your-microsoft-365-or-office-365-organization-to-enable-automatic-updates"></a>Microsoft 365 または Office 365 組織の構成を変更して自動更新を有効にする
<a name="BKMK_MultipleSites"> </a>

オペレーティングシステムの自動更新と Bits の自動更新を有効にするには、オンライン管理用の Skype for Business テナント管理者アカウントを使用し、テナントのリモート PowerShell を次のように使用する必要があります。
  
オペレーティングシステムの自動更新または Bits 自動更新を無効にした場合、ホストと仮想マシンで重要な Windows 更新プログラムが使用できなくなり、Cloud Connector が新しいバージョンに自動的にアップグレードされることはありません。 自動更新を有効にすることを強くお勧めします。
  
1. サイトの EnableAutoUpdate プロパティを true (既定値) に設定する必要があります。 次のコマンドレットを実行して、EnableAutoUpdate が true に設定されていることを確認します。
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. テナントの自動更新時間ウィンドウを作成します。
    
    時間枠は、日単位、週単位、月単位で指定できます。 すべての時間帯に、開始時刻と期間が必要です。
    
   - 日単位の時間枠の場合は、開始時刻と期間のみが必要です。 
    
   - 週単位の時間枠の場合、曜日が必要です。これは、1日または複数の日数でなければなりません。
    
   - 月単位の時間枠の場合は、2つの種類があります。 最初の種類は、月の日付を指定することで、1日にすることができます。 2番目の種類は、月の週と曜日を指定することです。1つまたは複数のアイテムでもかまいません。
    
   - 各テナントでは、20時間のウィンドウを定義できます。 新しいテナントの既定の時間枠は、オペレーティングシステムの更新および Bits 更新の既定の時間枠として作成されます。 次のコマンドレットを実行して、日単位、週単位、または月単位の時間枠を設定します。
    
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

   - 更新時刻ウィンドウをサイトに割り当てます。 
    
     Bits 更新時間および OS 更新時間ウィンドウは個別に構成されます。 これらの両方には、1つまたは複数の時間帯を割り当てることができます。 各時間枠は、さまざまなサイトに割り当てることができ、さまざまな目的 (Bits 更新および OS 更新) に割り当てることができます。 サイトの時間枠を設定するには、次のコマンドレットを実行します。 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a>専用のテナント管理者の資格情報を更新する
<a name="BKMK_MultipleSites"> </a>

クラウドコネクタの Microsoft 365 または Office 365 組織の管理上の変更は、必要なアクセス許可を持つアカウントから作成されます。 2.0 より前の Cloud Connector のバージョンでは、このアカウントは専用のグローバルテナント管理者アカウントです。 Cloud Connector バージョン2.0 以降では、このアカウントは、Skype for Business 管理者権限を持つ Microsoft 365 または Office 365 アカウントにすることができます。
  
Microsoft 365 または Office 365 で管理者アカウントの資格情報が変更された場合は、展開した各 Cloud Connector アプライアンス上で次の管理者 PowerShell コマンドを実行して、ローカルにキャッシュされた資格情報を Cloud Connector で更新する必要があります。
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a>ホストサーバーのパスワードを更新する
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> このセクションは、Cloud Connector バージョン2.0 以降に適用されます。 
  
すべての Cloud Connector 資格情報は、次のファイルに格納されます。 "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser \> ホストサーバーのパスワードが変更された場合は、ローカルに格納されている資格情報を更新する必要があります。
  
Cloud Connector アプライアンスでローカルに格納されている資格情報を更新するには、 [Get](get-cccredential.md) [と cccredential の各コマンドレット](set-cccredential.md)を使用して、次の手順を実行します。
  
1. 後で必要になるパスワードを取得するには、次のコマンドを実行します。 
    
   - 取得-CcCredential-AccountType DomainAdmin-DisplayPassword
    
   - 取得-CcCredential-AccountType VMAdmin-DisplayPassword
    
   - 取得-CcCredential-AccountType CceService-DisplayPassword
    
2. ホストサーバー上のアカウントのパスワードを変更します。
    
3. ホストサーバーを再起動します。
    
4. 次のファイルを削除します。 "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser \>
    
5. 管理者として PowerShell コンソールを起動してから、説明に従ってパスワードを再入力するには、「Register-CcAppliance-Local」を実行します。 Cloud Connector の展開の前に入力したのと同じパスワードを入力してください。
    
既定では、VmAdmin と DomainAdmin は CceService と同じパスワードを使用します。 手順1で返された DomainAdmin、VMAdmin、および CceService のパスワードが異なる場合は、次の手順を実行する必要があります。
  
1. Set-CcCredential-AccountType DomainAdmin を次のように実行します。
    
1. 古いアカウントの資格情報の入力を求められたら、CceService パスワードに使用した資格情報を入力します。
    
2. 新しいアカウントの資格情報の入力を求められたら、手順1で返された DomainAdmin パスワードのパスワードを入力します。
    
2. Set-CcCredential-AccountType VmAdmin を次のように実行します。
    
1. 古いアカウントの資格情報の入力を求められたら、CceService パスワードに使用した資格情報を入力します。
    
2. 新しいアカウントの資格情報の入力を求められたら、手順1で返された VmAdmin パスワードのパスワードを入力します。 
    
## <a name="update-the-password-for-the-cceservice-account"></a>CceService アカウントのパスワードを更新する
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> このセクションは、Cloud Connector バージョン2.0.1 以降に適用されます。 
  
Cloud Connector service は、Cloud Connector Management service を実行します。 CceService アカウントは、Cloud Connector Edition の展開時に作成され、次のファイルに格納されます。 "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser \> "および"%SystemDrive%\Programdata\Cloudconnector\credentials..CceService "。
  
すべてのアプライアンスがサイトディレクトリ共有にアクセスできるようにするには、CceService アカウントのパスワードが、サイト内に展開されているすべてのアプライアンスで同じである必要があります。 以下の点にご注意ください。
  
- 既定では、CceService アカウントは、[パスワードを無期限にする] として構成されています。 パスワードを更新するときは、この構成を維持することをお勧めします。
    
- Bits または Windows update では、非ピーク時の使用時と自動更新時間帯の外部でパスワードを更新する必要があります。 パスワードを更新するときは、アプライアンスをドレインして再起動する必要があります。これにはしばらく時間がかかります。 アプライアンスを再起動すると、自動更新操作が中断されます。 
    
- CceService アカウントのパスワードを変更する場合は、すべての資格情報を指定して、ローカルに格納されているファイルで更新する必要があります。 
    
同じ PSTN サイトに属するアプライアンスごとに、次のものを指定する必要があります。 
  
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

2. コマンドレットを実行してアプライアンスをドレインし、手動メンテナンスモードに移行します。
    
3. ホストサーバー上の CceService アカウントのパスワードを更新します。
    
4. ホストサーバーを再起動します。
    
5. Restore-CcCredentials コマンドレットを実行して、説明に従ってパスワードを再入力します。 
    
    CceService アカウントを除き、Cloud Connector の展開の前に入力したのと同じパスワードを入力してください。 CceService アカウントには、新しいパスワードを入力します。 CceService アカウントの新しいパスワードが、PSTN サイト内のすべてのアプライアンスで同じであることを確認してください。
    
6. 既定では、VmAdmin と DomainAdmin は CceService と同じパスワードを使用します。 手順1で返された DomainAdmin、VMAdmin、および CceService のパスワードが異なる場合は、次の手順を実行する必要があります。
    
7. Set-CcCredential-AccountType DomainAdmin を次のように実行します。
    
   - 古いアカウントの資格情報の入力を求められたら、CceService パスワードに使用した資格情報を入力します。
    
   - 新しいアカウントの資格情報の入力を求められたら、手順1で返された DomainAdmin パスワードのパスワードを入力します。
    
8. Set-CcCredential-AccountType VmAdmin を次のように実行します。
    
   - 古いアカウントの資格情報の入力を求められたら、CceService パスワードに使用した資格情報を入力します。
    
   - 新しいアカウントの資格情報の入力を求められたら、手順1で返された VmAdmin パスワードのパスワードを入力します。 
    
9. 終了-CcUpdate コマンドレットを実行してアプライアンスを手動メンテナンスモードの外に移動します。
    
10. 同じ PSTN サイト内のすべてのアプライアンスでこれらの手順を完了した後、サイトのルートディレクトリにある次のファイルを削除します。
    
    - CcLockFile
    
    - Site_ \< エッジ外部 Sip プールの fqdn\>
    
    - Tenant_ \< エッジ外部 Sip プールの fqdn\>
    
    - TenantConfigLock_ \< エッジ外部 Sip プールの fqdn\>
    
## <a name="add-a-new-sip-domain"></a>新しい SIP ドメインを追加する
<a name="BKMK_UpdatePassword"> </a>

既存の Cloud Connector 展開に新しい SIP ドメイン (または複数の SIP ドメイン) を追加するには、次の手順を実行します。
  
1. Microsoft 365 または Office 365 でドメインを更新する手順を完了しており、DNS レコードを追加できることを確認してください。 Microsoft 365 または Office 365 でドメインをセットアップする方法の詳細については、「 [Add a domain To microsoft 365」または「office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)」を参照してください。
    
2. 新しい SIP ドメインを使用して、Cloud Connector 構成ファイルを更新します。
    
3. Cloud Connector の構成で定義されている各 SIP ドメインについて、sip の追加の SAN 名を使用して新しいエッジの外部証明書を要求します。 
    
4. 新しいエッジの外部証明書のパスを次のように設定します。
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    指示に従って、 [1 つのサイトの構成を変更](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite)するか、[複数のサイトの構成を変更](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites)します。
    
## <a name="modify-the-primary-sip-domain"></a>プライマリ SIP ドメインを変更する
<a name="BKMK_UpdatePassword"> </a>

Cloud Connector の展開でプライマリ SIP ドメインを変更する必要がある場合は、次の手順を実行します。
  
1. Microsoft 365 または Office 365 でドメインを更新する手順を完了しており、DNS レコードを追加できることを確認してください。 Microsoft 365 または Office 365 でドメインをセットアップする方法の詳細については、「 [Add a domain To microsoft 365」または「office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)」を参照してください。
    
2. 新しい SIP ドメインを使用して、Cloud Connector 構成ファイルを更新します。
    
3. Cloud Connector の構成で定義されている各 SIP ドメインについて、sip の追加の SAN 名を使用して新しいエッジの外部証明書を要求します。 
    
4. 新しいエッジの外部証明書のパスを次のように設定します。
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    Cloud Connector 上の管理者 PowerShell で次のコマンドレットを実行して、サイト内の各アプライアンスのテナント登録を削除します。
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    Skype for Business Online PowerShell で次のコマンドレットを実行して、各サイトのサイト登録を削除します。
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    Cloud Connector 上の管理者 PowerShell で次のコマンドレットを実行して、各アプライアンスをアンインストールします。
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     Cloud Connector 上の管理者 PowerShell で次のコマンドレットを実行して、各アプライアンスを登録します。
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     Cloud Connector 上の管理者 PowerShell で次のコマンドレットを実行して、各アプライアンスを1つずつインストールします。
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a>外部エッジ証明書を新しい証明書に置き換える
<a name="BKMK_UpdatePassword"> </a>

Cloud Connector アプライアンスで外部エッジ証明書を置き換える必要がある場合は、新しいエッジ証明書を取得し、秘密キーと完全な証明書チェーンを含む PFX ファイルを準備してから、各アプライアンスで次の操作を実行する必要があります。
  
1. コマンドレットを使用して、アプライアンスをメンテナンスモードにします。
    
2. 次のコマンドを実行します。 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    新しい証明書のパスワードが old と同じ場合は、インポートが成功します。 パスワードが異なる場合は、パスワードが間違っているというエラーが表示されます。-Local パラメーターを指定して CcAppliance コマンドレットを実行し、手順2を繰り返して、パスワードをリセットする必要があります。 
    
4. 終了-CcUpdate コマンドレットを使用してアプライアンスのメンテナンスモードを停止します。
    

