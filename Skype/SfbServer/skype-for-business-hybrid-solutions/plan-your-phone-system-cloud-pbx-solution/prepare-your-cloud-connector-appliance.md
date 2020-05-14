---
title: Cloud Connector アプライアンスの準備
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
ms.assetid: 6eacfa99-9759-4c13-aca3-8992c2ff2710
description: クラウドコネクタアプライアンスを展開するための準備方法と、電話システム (クラウド PBX) での使用方法について説明します。
ms.openlocfilehash: d00002719ed8aaac7d0f0fb0e5ceb5722acc289c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220067"
---
# <a name="prepare-your-cloud-connector-appliance"></a>Cloud Connector アプライアンスの準備

クラウドコネクタアプライアンスを展開するための準備方法と、電話システム (クラウド PBX) での使用方法について説明します。

このセクションでは、Skype for Business Cloud Connector エディションのインストールファイルを取得する方法、クラウドコネクタソフトウェアをインストールする方法、および展開用に Cloud Connector アプライアンスを準備する方法について説明します。 このセクションのすべての手順を完了すると、1つまたは複数のサイト用の Cloud Connector を展開する準備が整います。 既存の Cloud Connector の展開があり、まだ Cloud Connector バージョン2.1 にアップグレードしていない場合は、「 [Cloud connector の新しいバージョンへのアップグレード](upgrade-to-a-new-version-of-cloud-connector.md)」を参照してください。

> [!NOTE]
> Microsoft は、Cloud Connector エディションバージョン2.1 の現在のバージョンをサポートしています。 自動更新を構成した場合、Cloud Connector は自動的に更新されます。 手動更新を構成した場合は、リリースから60日以内にバージョン2.1 にアップグレードする必要があります。 Microsoft は、2.1 をリリースしてから60日後に、アップグレードに要する時間を確保するために、以前のバージョンをサポートします。 

> [!NOTE]
> Cloud Connector バージョン2.1 以降の場合、ホストアプライアンスには .NET Framework 4.6.1 以降がインストールされている必要があります。 

> [!IMPORTANT]
> 展開を成功させるには、コマンドレットを実行して Skype for Business Cloud Connector エディションを構成するときに、開始したのと同じコンソールセッションを常に使用します。 展開および構成中に異なるセッションに切り替えないようにします。 

> [!NOTE]
> 展開の最初のアプライアンスに対してのみ実行する手順として、サイトディレクトリの共有を作成する方法、bits をダウンロードする方法、Windows Server ISO イメージから仮想ハードディスク (VHDX) ファイルを準備する方法があります。 

## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a>Skype for Business Cloud Connector エディションのインストーラーをダウンロードする

1. Cloud Connector Vm が実行されるホストサーバーで、インストールファイルをダウンロードします [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) 。 

    > [!IMPORTANT]
    > インストール中に追加のファイルがダウンロードされるので、ホストサーバーは、Cloud Connector のインストール中にインターネットにアクセスできる必要があります。 

2. インストーラーを実行し、インストール時に既定値をそのまま使用します。

3. インストールが正常に完了したことを確認します。

## <a name="verify-the-installation-and-configure-the-environment"></a>インストールを確認して環境を構成する

1. 管理者として PowerShell コンソールを開き、次のコマンドレットを使用して Skype for Business Cloud Connector エディションのコマンドレットを使用できることを確認します。

   ```powershell
   Get-Command *-Cc*
   ```

    このコマンドを実行すると、Skype for Business Cloud Connector エディションのコマンドレットの一覧が返されます。

2. Vhd、SfBBits、および VersionInfo の各ファイルは、**サイトディレクトリ**に格納されます。

    次のコマンドレットを使用して、**サイトディレクトリ**の場所を見つけることができます。

   ```powershell
   Get-CcSiteDirectory
   ```

    このコマンドは、ファイルシステム内の場所を返します。 この場所は、ローカルフォルダーまたはファイル共有にすることができます。 **サイトディレクトリ**の既定の場所は次のとおりです。%userprofile%\cloudconnector\siteroot 既定の場所は、各サイトで作成された最初のアプライアンスのファイル共有に変更する必要があります。

    次の場所を選択する必要があります。

   - 各サイトで作成された最初のアプライアンスで作成されます。

   - 同じサイト内の他のホストサーバー (アプライアンス) がアクセスできる共有フォルダー。

     **サイトディレクトリ**を既定以外の場所に設定するには、次のコマンドレットを実行します。

   ```powershell
   Set-CcSiteDirectory <UNC File path>
   ```

    サイトの高可用性 (HA) を展開する場合は、コマンドレットを実行して、サイト内の各ホストサーバー上の同じ場所に**サイトディレクトリ**を設定してください。

    ログオンしてサイト内の各アプライアンスを展開するときに、現在のログオンアカウントが**サイトディレクトリ**に対して適切なアクセス権を持っていることを確認してください。

3. **アプライアンスディレクトリ**は、Skype For Business Cloud Connector エディションのローカルの作業ルートディレクトリであり、外部の証明書、インスタンス、およびログが保存される場所です。 既定の場所は次のとおりです。%USERPROFILE%\CloudConnector\ApplianceRoot.

    **アプライアンスディレクトリ**の場所を見つけるには、次のコマンドレットを実行します。

   ```powershell
   Get-CcApplianceDirectory
   ```

    **アプライアンスディレクトリ**を既定以外の場所に設定するには、次のコマンドレットを実行します。

   ```powershell
   Set-CcApplianceDirectory <File path>
   ```

    アプライアンスのディレクトリは、アプライアンスのローカルフォルダーに設定する必要があります。 Skype for Business Cloud Connector エディションの展開を開始する前に、**アプライアンスディレクトリ**のみを設定する必要があります。 展開後に変更する場合は、ホストサーバーを再展開する必要があります。

    > [!IMPORTANT]
    > **アプライアンスディレクトリ**へのパスにスペースを含めることはできません。

## <a name="set-the-path-for-the-external-edge-certificate"></a>外部エッジ証明書のパスを設定する

- 次のコマンドレットを実行して、ファイル名を含むパスを外部エッジ証明書に設定します。 例: C:\certs\cce\ap.contoso.com.pfx. 証明書には秘密キーが含まれている必要があります。

  ```powershell
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > -Target パラメーターはバージョン1.4.2 以降に固有のものであることに注意してください。 

    ファイル名を含む、外部証明書への完全パスを指定します。 証明書は、ローカルまたはファイル共有に保存できます。 証明書が共有フォルダーに格納されている場合は、共有フォルダーを各サイトの最初のアプライアンスに作成し、同じサイトに属する他のアプライアンスからアクセスできるようにする必要があります。 このコマンドレットは、外部証明書を**アプライアンスディレクトリ**にコピーします。

    > [!IMPORTANT]
    > **Cloud Connector バージョン1.4.2 以降に更新**した場合は、準備した外部証明書に秘密キーと、ルート ca 証明書と中間 CA 証明書を含む完全な証明書チェーンが含まれていることを確認してください。 **Cloud Connector バージョン1.4.2 にまだ更新していない場合は**、準備した外部証明書に秘密キーが含まれていることを確認してください。 この外部証明書は、既定で Windows によって信頼されている証明機関によって発行される必要があります。

## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a>外部 PSTN ゲートウェイ/SBC 証明書のパスを設定する

仲介サーバーと PSTN ゲートウェイ/SBC 間で TLS を使用している場合は、次のコマンドレットを実行して、ファイル名を含むパスをゲートウェイ証明書に設定します。 例: C:\certs\cce\sbc.contoso.com.cer. この証明書には、ルート CA と、ゲートウェイに割り当てられた証明書の中間チェーンが含まれている必要があります。

```powershell
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 
```

> [!NOTE]
> -Target パラメーターはバージョン1.4.2 以降に固有のものであることに注意してください。 

## <a name="create-virtual-switches-in-hyper-v-manager"></a>Hyper-v マネージャーで仮想スイッチを作成する

1. **Hyper-v マネージャー**  >  の**仮想スイッチマネージャー**を開き、[**新しい仮想スイッチマネージャー**] を選択します。

2. 外部仮想スイッチを作成し、それを内部ネットワークドメインに接続されている物理ネットワークアダプターにバインドします。

    この仮想スイッチに対して [**管理オペレーティングシステムによるこのネットワークアダプターの共有を許可する**] を選択します。

3. 外部仮想スイッチを作成し、それをインターネットにルーティングされる物理ネットワークアダプターにバインドします。

    この仮想スイッチに対して [**管理オペレーティングシステムによるこのネットワークアダプターの共有を許可する**] を選択解除します。

4. 境界ネットワークを内部ネットワークドメインの**Sfb**の企業向けスイッチに接続するスイッチの名前を設定します。

    境界ネットワークをインターネットに接続するスイッチの名前を、 **Sfb CCE Internet switch**に設定します。

## <a name="update-the-cloudconnectorini-configuration-file"></a>CloudConnector の .ini 構成ファイルを更新する

「 [Plan For Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) 」の「[展開パラメーターの決定](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)」で収集した情報を使用して、cloudconnector の .ini ファイルを準備します。

ファイルを更新するには、最初に次のコマンドレットを実行して、サンプルテンプレート (CloudConnector. サンプル) を取得します。

```powershell
Export-CcConfigurationSampleFile
```

サンプルテンプレートは**アプライアンスディレクトリ**に保存されます。

使用している環境の値で更新した後、ファイルを CloudConnector .ini として**アプライアンスディレクトリ**に保存します。 **Set-ccappliancedirectory**を実行して、**アプライアンスディレクトリ**へのパスを確認できます。

.Ini ファイルを更新するときは、次の点を考慮してください。

> [!NOTE]
> このセクションでは .ini ファイルのすべての値について説明していませんが、特別な考慮事項のあるものだけをここで説明します。 完全なリストについては、「 [Plan For Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) 」の「[展開パラメーターの決定](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)」セクションを参照してください。 追加のアプライアンスまたは新しいサイトで変更する必要がある値の詳細については、「[複数のサイトをクラウドコネクタに展開](deploy-multiple-sites-in-cloud-connector.md)する」のトピックの「[単一サイトと高可用性 (HA)](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) 」を参照してください。 

- **SiteName:** 既定値は**Site1**です。 既存または新規のサイトにアプライアンスを登録するために**register**を実行すると、コマンドレットは**SiteName**を使用して登録するサイトを決定するため、Cloud Connector を展開する前に更新する必要があります。

     アプライアンスを新しいサイトに登録する場合は、 **SiteName**の値が一意で、既存のサイトとは異なるものである必要があります。 アプライアンスを既存のサイトに登録する場合は、.ini ファイル内の**SiteName**の値は、Microsoft 365 または Office 365 組織の構成で定義されている名前と一致している必要があります。 構成ファイルをあるサイトから別のサイトにコピーする場合は、各サイトの**SiteName**の値を適宜更新してください。

- **ServerName:** サーバー名にドメイン名を含めることはできず、15文字に制限する必要があります。

- **ハードウェアの種類:** 値を設定しない場合、または null 値のままにした場合は、既定値の**Normal**が使用されます。 「 [Plan For Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md)」に記載されているように、ホストマシンごとに500の同時通話をサポートするために、より大規模な Cloud connector の展開を計画している場合は、 **Normal**を使用します。 50の同時通話をサポートする小規模な展開には、**最小値**を使用します。

- **インターネット/社内/管理仮想スイッチ:**: 作成した仮想スイッチの名前を追加します。 管理仮想スイッチの場合は、既定値のままにします。 展開スクリプトは、展開の開始時に管理仮想スイッチを作成し、展開が終了したら削除します。

- **Managementipprefix:**[ネットワーク] セクションの ManagementIPPrefix は、他の内部 Ip とは異なるサブネットである必要があります。 たとえば、既定値が示すように、ManagementIPPrefix は192.168.213.0 ですが、AD IPAddress は192.168.0.238 です。

    展開スクリプトは、各仮想マシンに管理ネットワークアダプターを作成し、管理 IP を割り当てて、それを管理仮想スイッチに接続します。 これにより、ホストサーバーは、この管理ネットワークを介して各仮想マシンに接続して管理できるようになります。 管理仮想スイッチは、展開が完了した時点で削除されます。

- **ベース VM 固有の構成:** このセクションの設定は、 **Convert-CcIsoToVhdx**コマンドレット用に構成する必要があります。

    ベース vm イメージの準備中に、ベース VM は内部ネットワークスイッチに接続されます。 次の設定は、VM がインターネットにアクセスできるようにするために重要です。

  - 一般的なBaseVMIP: ベース VM に割り当てる社内 IP アドレス。

  - LanCorpnetDefaultGateway: ベース VM に割り当てられる既定のゲートウェイ。

  - LanCorpnetDNSIPAddress: ベース VM に割り当てる DNS IP アドレス。

  - LanWSUSServer: Windows Server Update Service の IP アドレス。

  - LanWSUSStatusServer: Windows Server Update Service の状態サーバーの IP アドレス。

  - LanEnableReferSupport: IP/PBX へのトランク構成で SIP 参照サポートが有効または無効になっているかどうかを定義します。

- **内部 Ip:**

  - サブネットマスク CorpnetIPPrefixLength が正しいことを確認してください。

  - これらの内部 ip に IP 競合がないことを確認してください。

- **外部 Ip:**

  - MR パブリック IP の場合: nat 以外の場合は ExternalMRIPs を指定し、NAT の場合は ExternalMRPublicIPs を指定します。

  - ExternalSIPIPs と Externalsipips は同じでもかまいません。

  - サブネットマスクの Interne"ヒントのプレフィックスが正しいことを確認してください。

  - これらの外部 Ip に IP 競合がないことを確認してください。

- **ゲートウェイ**

  - ゲートウェイが1つしかない場合は、セカンダリゲートウェイのセクションを削除します。 3つ以上のゲートウェイがある場合は、既存の複数のセクションをコピーして貼り付け、更新することによって、追加のセクションを作成します。

  - ゲートウェイの IP アドレスとポートが正しいことを確認してください。

  - PSTN ゲートウェイレベルの HA をサポートするには、セカンダリゲートウェイを残し、使用するゲートウェイを追加します。 既存のエントリをコピーして貼り付け、更新することができます。

- 必要に応じて、LocalRoute 値を更新して発信通話番号を制限することもできます。

## <a name="download-the-bits-to-the-site-directory"></a>サイトディレクトリにビットをダウンロードする

次のコマンドレットを実行して、bits およびバージョン情報ファイルを**サイトディレクトリ**にダウンロードします。

```powershell
Start-CcDownload
```

> [!NOTE]
> 最初のアプライアンスのみに対してこの手順を実行する必要があります。 

## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a>ダウンロードした ISO ファイルからベース仮想ディスク (VHDX) を準備する

この手順では、Windows Server 2012 ISO イメージから仮想ハードディスク (VHDX) ファイルを準備します。 VHDX は、展開時に仮想マシンを作成するために使用されます。 一時仮想マシン (ベース VM) が作成され、ISO ファイルから Windows Server 2012 がインストールされます。 VM を作成すると、必要なコンポーネントがいくつかインストールされ、最新の Windows 更新プログラムが適用されます。 最後に、ベース VM は一般化 (sysprep) されクリーンアップされ、生成された仮想ディスクファイルのみが残されます。

> [!NOTE]
> 最初のアプライアンスのみに対してこの手順を実行する必要があります。 

この手順を進める前に、企業ネットワークスイッチが作成されていることを確認してください。 また、次の設定が CloudConnector .ini ファイルで正しく構成されていることを確認してください。

- LanCorpnetSwitchName

- 一般的なBaseVMIP

- LanCorpnetIPPrefixLength

- LanCorpnetDefaultGateway

- LanCorpnetDNSIPAddress

管理者として PowerShell コンソールを起動し、次のコマンドレットを実行して、ISO イメージを仮想ハードディスク (VHD) に変換します。

```powershell
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

ISO イメージの完全パス (ファイル名を含む) を指定します。 たとえば、次のように入力します。

作成された VHD ファイルは、**サイトディレクトリ**\ bit\ vhd フォルダーに格納されます。 **取得-CcSiteDirectory**を実行することにより、**サイトディレクトリ**へのパスを取得することができます。

> [!IMPORTANT]
> 既定では、ベース VM でプロキシ設定が構成されていません。 Windows Update を介して VM を更新するためにネットワーク環境でプロキシが必要な場合は、"Convert-CcIsoToVhdx" を実行するときに-PauseBeforeUpdate スイッチを追加する必要があります。 このスクリプトは、Windows Update の前に一時停止し、VM でプロキシを手動でセットアップする機会があります。 プロキシがセットアップされ、VM がインターネットにアクセスできるようになったら、スクリプトを再開して残りの手順を完了できます。 

### <a name="create-vhds-for-a-multi-site-deployment"></a>複数サイト展開用の Vhd を作成する

これは、複数サイト展開のみに適用されるオプションの手順です。

複数サイト展開を展開する場合は、各サイトの ISO を VHD に変換する必要はありません。 最初のサイト用に作成された VHDX を、2番目のサイトのホストサーバーにコピーできます。

 別のサイトのホストサーバー上で、同じファイルの場所 (**サイトディレクトリ**\ ビット \ VHD フォルダー) に同じファイル名を使用してファイルをコピーします。

## <a name="set-the-powershell-execution-policy-to-remotesigned"></a>PowerShell 実行ポリシーを RemoteSigned に設定します。

提供されている PowerShell スクリプトでは、実行ポリシーを RemoteSigned に設定する必要があります。 現在の設定を表示するには、管理者として PowerShell コンソールを開き、次のコマンドレットを実行します。

```powershell
Get-ExecutionPolicy
```

"RemoteSigned" に設定されていない場合は、次のコマンドレットを実行して変更します。

```powershell
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a>ホストマシンのローカルグループポリシーを変更する (バージョン1.4.1 以前)

> [!NOTE]
> このタスクは、Cloud Connector バージョン1.4.2 以降では必要ありません。 

CceService アカウントは、Skype for Business Cloud Connector エディションの展開時に作成されます。 Cloud Connector Management Service を実行し、cloudconnector をアンインストールするためのアクセス許可を必要とします。 ユーザーがログオフしたときにユーザーのレジストリをアンロードしないように指定するには、Cloud Connector ホストコンピューターのグループポリシー設定を変更する必要があります。 次の手順を実行します。

### <a name="to-change-the-group-policy-setting"></a>グループポリシー設定を変更するには

1. Gpedit.msc を実行して**グループポリシーエディター**を開きます。

2. **グループポリシーエディター**で、[管理用テンプレート > System > > UserProfile] に移動します。ユーザーのログオフ時に強制的にユーザーレジストリをアンロードしないようにします。 

3. その値を**有効**に設定します。

## <a name="set-up-your-microsoft-365-or-office-365-organization"></a>Microsoft 365 または Office 365 組織をセットアップする

Microsoft 365 または Office 365 組織で Skype for Business Online と電話システムを使用する必要があります。 Cloud Connector を使用する前に、テナントがセットアップおよび構成されていることを確認してください。

一部の Microsoft 365 および Office 365 のセットアップ手順では、テナントリモート PowerShell (TRPS) を使用して、Microsoft 365 または Office 365 組織を構成する必要があります。 **これは、ホストサーバーにインストールする必要があります。** PowerShell の Skype for Business Online モジュールは、「 [skype For Business online, Windows PowerShell モジュール」](https://www.microsoft.com/download/details.aspx?id=39366)からダウンロードできます。

Cloud Connector online management に専用の Skype for Business 管理者アカウントを作成します (例: CceOnlineManagmentAdministrator)。 このアカウントはアプライアンスによって使用され、アプライアンスを追加または削除したり、自動 OS 更新を有効または無効にしたり、自動バイナリ更新を有効または無効にしたりします。 このアカウントのパスワードを期限切れにならないように設定します。これにより、有効期限が切れるたびにサービスのパスワードを変更する必要はありません。


