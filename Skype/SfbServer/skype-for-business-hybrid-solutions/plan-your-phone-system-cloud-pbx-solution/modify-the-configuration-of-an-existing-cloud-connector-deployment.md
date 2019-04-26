---
title: 既存の Cloud Connector の展開構成の変更
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 90490c65-0e40-4e85-96e1-751f27897e25
description: ビジネス クラウド コネクタ エディション 1.4.1 またはそれ以降の展開は、既存の Skype の構成を変更するには、このトピックの手順を実行します。
ms.openlocfilehash: abe7d9be6ec0ae48ff8cbac09475c6a41bf2a49f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32237610"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a>Modify the configuration of an existing Cloud Connector deployment
 
ビジネス クラウド コネクタ エディション 1.4.1 またはそれ以降の展開は、既存の Skype の構成を変更するには、このトピックの手順を実行します。 
  
## <a name="modify-the-configuration-of-a-single-site"></a>1 つのサイトの構成を変更する
<a name="BKMK_SIngleSite"> </a>

サイトに 1 つのアプライアンスしかなく、アプライアンスを展開した後で構成設定を変更する必要がある場合は、CloudConnector.ini ファイルを変更して、もう一度展開を開始することができます。
  
1. 次のコマンドレットを実行して、ホスト サーバー上にあるすべての既存の仮想マシンをアンインストールします。 
    
   ```
   Uninstall-CcAppliance
   ```

2. アプライアンスを登録解除するには、次のコマンドレットを実行します。
    
   ```
   Unregister-CcAppliance
   ```

3. アプライアンス ディレクトリ の CloudConnector.ini ファイルを更新します。
    
4. 構成を更新するのには次のコマンドレットを実行する: (この手順は、バージョン 2; 以前のバージョンに該当する場合のみ、次の手順に進みます)。
    
   ```
   Import-CcConfiguration 
   ```

5. アプライアンスをもう一度登録するには、次のコマンドレットを実行します。
    
   ```
   Register-CcAppliance
   ```

6. Skype for Business Cloud Connector エディションをインストールするには、次のコマンドレットを実行します。
    
   ```
   Install-CcAppliance
   ```

サイトに複数のアプライアンスがある場合は、次の手順に従って、CloudConnector.ini ファイルを変更し、アプライアンスを 1 つずつ再展開する必要があります。
  
1. 現在のアプライアンス上にある既存の仮想マシンをすべてアンインストールするには、次のコマンドレットを実行します。  
    
   ```
   Uninstall-CcAppliance
   ```

2. アプライアンスを登録解除するには、次のコマンドレットを実行します。
    
   ```
   Unregister-CcAppliance
   ```

3. アプライアンス ディレクトリ の CloudConnector.ini ファイルを更新します。
    
4. 構成を更新するのには次のコマンドレットを実行する: (この手順は、バージョン 2; 以前のバージョンに該当する場合のみ、次の手順に進みます)。
    
   ```
   Import-CcConfiguration 
   ```

5. アプライアンスをもう一度登録するには、次のコマンドレットを実行します。
    
   ```
   Register-CcAppliance
   ```

6. 最新の構成を取得するには、サイトにあるその他すべてのアプライアンスで次のコマンドレットを実行します。
    
   ```
   Publish-CcAppliance
   ```

7. 現在のアプライアンスのクラウドのコネクタを再配置するのには、次のコマンドレットを実行します。
    
   ```
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a>複数のサイトの構成を変更する
<a name="BKMK_MultipleSites"> </a>

展開で複数のサイトの構成を変更するには、一度に 1 つのサイトを更新、1 つのサイトの手順を実行します。
  
## <a name="modify-the-configuration-of-your-office-365-tenant-to-enable-automatic-updates"></a>自動更新を有効にするために Office 365 テナントの構成を変更する
<a name="BKMK_MultipleSites"> </a>

オペレーティング システムの自動更新と Bits の自動更新を有効にするには、オンライン管理のためのビジネス テナント管理者のアカウントに、Skype を使用する必要があります、リモート PowerShell のテナントを次のように使用します。
  
オペレーティング システムの自動更新または自動更新のビットを無効にした場合、ホストと仮想マシンは、重要な Windows 更新を見落とす場合があり、クラウドのコネクタは自動的に新しいバージョンにアップグレードされません。 自動更新を有効にすることを強くお勧めします。
  
1. サイトの EnableAutoUpdate プロパティは、true (既定値) に設定する必要があります。 EnableAutoUpdate が True に設定されていることを確認するには、次のコマンドレットを実行します。
    
   ```
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. テナントの自動更新の時間枠を作成します。
    
    時間枠は、日単位、週単位、月単位で設定できます。すべての時間枠には、開始時刻と期間が必要です。
    
   - 日単位の時間枠の場合は、開始時刻と期間のみが必要です。 
    
   - 週単位の時間枠の場合は、1 つまたは複数の曜日が必要です。
    
   - 月単位の時間枠の場合は、2 種類あります。1 番目の種類では、日付を 1 つ指定します。2 番目の方法では、第何週の何曜日かを (それぞれ 1 つでも複数でも可) 指定します。
    
   - 各テナントに定義できる時間枠は 20 件です。新しいテナントには、オペレーティング システムの更新と BITS の更新用の既定の時間枠が作成されます。日単位、週単位、月単位の時間枠を設定するには、次のコマンドレットを実行します。
    
   ```
   New-CsTenantUpdateTimeWindow -Identity Night -Daily -StartTime 22:00 -Duration 6:00
   ```

   ```
   New-CsTenantUpdateTimeWindow -Identity WeekdayNight -Weekly -DaysOfWeek Monday,Tuesday,Wednesday,Thursday,Friday -StartTime 22:00 -Duration 4:00
   ```

   ```
   New-CsTenantUpdateTimeWindow -Identity FirstAndLastWeekend -Monthly -WeeksOfMonth First,Last -DaysOfWeek Sunday,Saturday -StartTime 0:00 -Duration 10:00
   ```

   ```
   New-CsTenantUpdateTimeWindow -Identity MidDayOfMonth -Monthly -DayOfMonth 15 -StartTime 0:00 -Duration 1.00:00
   ```

   - 更新時間枠をサイトに割り当てます。  
    
     BITS の更新時間枠と OS の更新時間枠は、個別に構成します。 どちらにも、1 つまたは複数の時間枠を割り当てることができます。 各時間枠は、異なるサイトや異なる用途 (BITS の更新と OS の更新) に割り当てることができます。 次のコマンドレットを実行して時間枠をサイトに設定します。  
    
   ```
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a>専用のテナント管理者の資格情報を更新する
<a name="BKMK_MultipleSites"> </a>

クラウド コネクタの Office 365 テナントの管理の変更は、必要なアクセス許可を持つアカウントで行われます。 クラウド コネクタ 2.0 より前のに、バージョンでは、そのアカウントが専用のグローバル テナント管理者のアカウントです。 クラウド コネクタ バージョン 2.0 以降では、そのアカウントにビジネス管理者の権利を Skype での Office 365 アカウントことができます。
  
Office 365 の管理者アカウントの資格情報を変更する場合は、展開している各コネクタのクラウド アプライアンスの次の管理者の PowerShell コマンドを実行して、クラウドのコネクタのローカルにキャッシュされた資格情報を更新する必要があります。
  
```
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a>ホスト サーバーのパスワードを更新する
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> このセクションは Cloud Connector バージョン 2.0 以降のみを対象としています。 
  
クラウド コネクタのすべての資格情報は、次のファイルに格納されます:"%systemdrive%\programdata\cloudconnector\credentials。\<CurrentUser\>.xml」です。 ホスト サーバーのパスワードを変更するときには、ローカルで格納されている資格情報を更新する必要があります。
  
クラウド コネクタ ・ アプライアンスのローカルに保存された資格情報を更新するには、 [Get CcCredential](get-cccredential.md)と[セット CcCredential](set-cccredential.md)コマンドレットを使用して、これらの手順に従います。
  
1. 次のコマンドを実行して、後で必要になるパスワードを取得します。 
    
   - Get-CcCredential -AccountType DomainAdmin -DisplayPassword
    
   - Get-CcCredential -AccountType VMAdmin -DisplayPassword
    
   - Get-CcCredential -AccountType CceService -DisplayPassword
    
2. ホスト サーバー上でお使いのアカウントのパスワードを変更します。
    
3. ホスト サーバーを再起動します。
    
4. 次のファイルを削除します。"% SystemDrive%\Programdata\Cloudconnector\credentials。\<CurrentUser\>.xml」です。
    
5. 管理者として PowerShell コンソールを起動し、実行して"登録 CcAppliance-ローカル"次の説明、パスワードを再入力します。 Cloud Connector の展開で前回使用したパスワードと同じパスワードを入力します。
    
既定では、VmAdmin および DomainAdmin では CceService と同じパスワードが使用されます。手順 1 で返された DomainAdmin、VMAdmin および CceService のパスワードが異なる場合は、次の手順を実行する必要があります。
  
1. Set-CcCredential -AccountType DomainAdmin を次のように実行します。
    
1. 以前のアカウントの資格情報を求められた場合は、CceService パスワードに使用した資格情報を入力します。
    
2. 新しいアカウントの資格情報を求められた場合は、手順 1 で返された DomainAdmin パスワードを入力します。
    
2. Set-CcCredential -AccountType VmAdmin を次のように実行します。
    
1. 以前のアカウントの資格情報を求められた場合は、CceService パスワードに使用した資格情報を入力します。
    
2. 新しいアカウントの資格情報を求められた場合は、手順 1 で返された VmAdmin パスワードを入力します。 
    
## <a name="update-the-password-for-the-cceservice-account"></a>CceService アカウントのパスワードを更新します。
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> クラウド コネクタ バージョン 2.0.1 に該当する場合、後でこのセクションでは。 
  
クラウド コネクタ サービスは、クラウドのコネクタの管理サービスを実行します。 CceService アカウントがクラウド コネクタのエディションの展開中に作成され、次のファイルに格納されている:"%systemdrive%\programdata\cloudconnector\credentials。\<CurrentUser\>.xml"および"%systemdrive%\programdata\cloudconnector\credentials.CceService.xml"です。
  
サイト ディレクトリの共有のすべてのアプライアンスにアクセスできることを確認するは、CceService のアカウントのパスワードはサイト内に展開されるすべてのアプライアンス上で同じである必要があります。 以下の点について留意してください。
  
- 既定では、[パスワードを無期限にする"と CceService のアカウントが構成されています。 パスワードを更新するときは、この構成を保持することをお勧めします。
    
- 非ピーク時間帯に、ビットまたは Windows の更新プログラムの自動更新の時間帯以外では、パスワードを更新する必要があります。 パスワードを更新すると、アプライアンス必要がありますを放電し、再起動すると、時間がかかります。 アプライアンスを再起動すると、自動更新の操作が中断されます。 
    
- CceService アカウントのパスワードを変更すると、すべての資格情報を指定し、ローカルに保存されたファイルに更新する必要があります。 
    
同じ PSTN のサイトに属しているアプライアンスそれぞれに対して、次の指定が必要になります。 
  
1. 後で使用するパスワードとアカウント名を取得するために次のコマンドを実行します。
    
   ```
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

2. アプライアンスを放電し、手動でのメンテナンス モードに移動する Enter CcUpdate コマンドレットを実行します。
    
3. ホスト サーバー上の CceService のアカウントのパスワードを更新します。
    
4. ホスト サーバーを再起動します。
    
5. 次の説明、パスワードを再入力するのには復元 CcCredentials コマンドレットを実行します。 
    
    CceService アカウントを除くクラウド コネクタの配置の前に入力したパスワードを入力することを確認します。 CceService ・ アカウントの新しいパスワードを入力します。 CceService アカウントの新しいパスワードは、PSTN のサイト内のすべてのアプライアンスで同じことを確認します。
    
6. 既定では、VmAdmin および DomainAdmin では CceService と同じパスワードが使用されます。手順 1 で返された DomainAdmin、VMAdmin および CceService のパスワードが異なる場合は、次の手順を実行する必要があります。
    
7. Set-CcCredential -AccountType DomainAdmin を次のように実行します。
    
   - 以前のアカウントの資格情報を求められた場合は、CceService パスワードに使用した資格情報を入力します。
    
   - 新しいアカウントの資格情報を求められた場合は、手順 1 で返された DomainAdmin パスワードを入力します。
    
8. Set-CcCredential -AccountType VmAdmin を次のように実行します。
    
   - 以前のアカウントの資格情報を求められた場合は、CceService パスワードに使用した資格情報を入力します。
    
   - 新しいアカウントの資格情報を求められた場合は、手順 1 で返された VmAdmin パスワードを入力します。 
    
9. 移動手動メンテナンス モードを終了する終了 CcUpdate コマンドレットを実行します。
    
10. 同じ PSTN サイト内のすべてのアプライアンス上の次の手順を完了すると後、は、サイトのルート ディレクトリ以下のファイルを削除します。
    
    - CcLockFile
    
    - Site_\<エッジ外部 Sip プールの fqdn\>
    
    - Tenant_\<エッジ外部 Sip プールの fqdn\>
    
    - TenantConfigLock_\<エッジ外部 Sip プールの fqdn\>
    
## <a name="add-a-new-sip-domain"></a>新しい SIP ドメインを追加する 
<a name="BKMK_UpdatePassword"> </a>

新しい SIP ドメイン (または複数の SIP ドメイン) を既存のクラウドのコネクタの配置に追加するには、次の操作を行います。
  
1. Office 365 でドメインを更新する手順を完了し、DNS レコードを追加できることを確認します。 Office 365 でドメインを設定する方法の詳細については、 [Office 365 にドメインの追加](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)を参照してください。
    
2. 新しい SIP ドメイン、またはドメインを持つクラウド コネクタ構成ファイルを更新します。
    
3. 新しいエッジ外部証明書を要求、クラウドのコネクタ構成で定義されている各 SIP ドメインの sip.domain の他の SAN 名。 
    
4. 新しい Microsoft Edge 外部証明書のパスを次のように設定します。
    
   ```
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    「[1 つのサイトの構成を変更する](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite)」または「[複数のサイトの構成を変更する](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites)」の手順を実行します。
    
## <a name="modify-the-primary-sip-domain"></a>プライマリ SIP ドメインを変更する
<a name="BKMK_UpdatePassword"> </a>

クラウド コネクタ展開にプライマリ SIP ドメインを変更する場合は、次の操作を行います。
  
1. Office 365 でドメインを更新する手順を完了し、DNS レコードを追加できることを確認します。 Office 365 でドメインを設定する方法の詳細については、 [Office 365 にドメインの追加](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)を参照してください。
    
2. 新しい SIP ドメインとは、クラウドのコネクタの構成ファイルを更新します。
    
3. 新しいエッジ外部証明書を要求、クラウドのコネクタ構成で定義されている各 SIP ドメインの sip.domain の他の SAN 名。 
    
4. 新しい Microsoft Edge 外部証明書のパスを次のように設定します。
    
   ```
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    サイト内でクラウドのコネクタの管理者 PowerShell で次のコマンドレットを実行しているアプライアンスそれぞれに対してテナント登録を削除します。
    
   ```
   Unregister-CcAppliance
   ```

6. 
    
    Skype for Business Online の PowerShell で次のコマンドを実行して、各サイトのサイト登録を削除します。
    
   ```
   Remove-CsHybridPSTNSite
   ```

7. 
    
    各アプライアンスをアンインストールするには、クラウドのコネクタの管理者 PowerShell で次のコマンドレットを実行しています。
    
   ```
   Uninstall-CcAppliance
   ```

8. 
    
     各アプライアンスを登録するには、クラウドのコネクタの管理者 PowerShell で次のコマンドレットを実行しています。
    
   ```
   Register-ccAppliance
   ```

9. 
    
     各アプライアンスをインストールする管理者 PowerShell でクラウド コネクタで次のコマンドレットを実行している、1 つずつ。
    
   ```
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a>外部境界の証明書を新しい証明書に置き換える
<a name="BKMK_UpdatePassword"> </a>

コネクタのクラウド アプライアンス上のエッジの外部の証明書を交換する場合は、新しいエッジの証明書を取得し、秘密キーと、完全な証明書チェーンを含む PFX ファイルを準備し、各アプライアンスで、次の操作を行います必要があります。
  
1. 入力 CcUpdate コマンドレットを使用してメンテナンス モードでのアプライアンスを配置します。
    
2. 次のコマンドを実行します。 
    
   ```
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    新しい証明書のパスワードが、以前と同じ場合は、インポートが許可されます。 パスワードが間違っている場合は、そのレジスタ CcAppliance コマンドレットを実行してパスワードをリセットする必要があります。 エラーが発生したが、パスワードが異なる場合は、-ローカルのパラメーターを使用し、繰り返しの手順 2 とします。 
    
4. 終了 CcUpdate コマンドレットを使用してメンテナンス モードからアプライアンスを実行します。
    

