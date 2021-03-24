---
title: クラウド コネクタ アプライアンスの準備
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
description: クラウド コネクタ アプライアンスを展開および電話システム (クラウド PBX) で使用するために準備する方法について説明します。
ms.openlocfilehash: 536e9b98520e4274e00d43d57224267f5b824dc9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092635"
---
# <a name="prepare-your-cloud-connector-appliance"></a>クラウド コネクタ アプライアンスの準備

> [!Important]
> Cloud Connector Edition は、Skype for Business Online と共に 2021 年 7 月 31 日に廃止されます。 組織が Teams にアップグレードしたら、直接ルーティングを使用してオンプレミスのテレフォニー ネットワークを Teams に接続する方法 [について説明します](/MicrosoftTeams/direct-routing-landing-page)。

クラウド コネクタ アプライアンスを展開および電話システム (クラウド PBX) で使用するために準備する方法について説明します。

このセクションでは、Skype for Business Cloud Connector Edition インストール ファイルを取得し、クラウド コネクタ ソフトウェアをインストールし、クラウド コネクタ アプライアンスを展開用に準備する方法について説明します。 このセクションのすべての手順を完了したら、1 つのサイトまたは複数のサイトに対してクラウド コネクタを展開する準備が整います。 既存のクラウド コネクタ展開を使用し、まだクラウド コネクタ バージョン 2.1 にアップグレードしていない場合は、「Upgrade to new version of Cloud Connector 」を [参照してください](upgrade-to-a-new-version-of-cloud-connector.md)。

> [!NOTE]
> Microsoft では、現在のバージョンの Cloud Connector Edition バージョン 2.1 がサポートされています。 自動更新を構成した場合、クラウド コネクタは自動的に更新されます。 手動更新プログラムを構成した場合は、リリースから 60 日以内にバージョン 2.1 にアップグレードする必要があります。 Microsoft は、2.1 のリリース後 60 日間、以前のバージョンをサポートし、アップグレードの時間を提供します。 

> [!NOTE]
> Cloud Connector バージョン 2.1 以降の場合、ホスト アプライアンスには 4.6.1 以降.NET Frameworkインストールされている必要があります。 

> [!IMPORTANT]
> 展開を成功するには、コマンドレットを実行して Skype for Business Cloud Connector Edition を構成する場合は、常に開始したコンソール セッションと同じコンソール セッションを使用します。 展開と構成中に異なるセッションに切り替えるのを避ける。 

> [!NOTE]
> 展開の最初のアプライアンスに対してのみ実行する手順として、サイト ディレクトリの共有の作成、ビットのダウンロード、Windows Server ISO イメージからの仮想ハード ディスク (VHDX) ファイルの準備があります。 

## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a>Skype for Business Cloud Connector Edition インストーラーをダウンロードする

1. クラウド コネクタ VM が実行されるホスト サーバーで、インストール ファイルをダウンロードします [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) 。 

    > [!IMPORTANT]
    > 追加のファイルはインストール中にダウンロードされますので、クラウド コネクタのインストール中にホスト サーバーがインターネットにアクセスできる必要があります。 

2. インストーラーを実行し、インストール中に既定値を受け入れる。

3. インストールが正常に完了したと確認します。

## <a name="verify-the-installation-and-configure-the-environment"></a>インストールを確認し、環境を構成する

1. 管理者として PowerShell コンソールを開き、次のコマンドレットを使用して Skype for Business Cloud Connector Edition コマンドレットを使用できます。

   ```powershell
   Get-Command *-Cc*
   ```

    このコマンドは、Skype for Business Cloud Connector Edition のコマンドレットの一覧を返す必要があります。

2. VHDs、SfBBits、VersionInfo ファイルはサイト ディレクトリに **格納されます**。

    次のコマンドレットを使用して **、サイト ディレクトリ** の場所を確認できます。

   ```powershell
   Get-CcSiteDirectory
   ```

    コマンドは、ファイル システム内の場所を返す必要があります。 場所には、ローカル フォルダーまたはファイル共有を指定できます。 サイト ディレクトリの既定の **場所** は、%USERPROFILE%\CloudConnector\SiteRoot です。 既定の場所は、各サイトで作成された最初のアプライアンスのファイル共有に変更する必要があります。

    選択する場所は次の場所である必要があります。

   - 各サイトで作成された最初のアプライアンスで作成されます。

   - 同じサイト内の他のホスト サーバー (アプライアンス) がアクセスできる共有フォルダー。

     サイト ディレクトリを **既定以外** の場所に設定するには、次のコマンドレットを実行します。

   ```powershell
   Set-CcSiteDirectory <UNC File path>
   ```

    サイトに高可用性 (HA) を展開する場合は、コマンドレットを実行してサイト **ディレクトリ** をサイト内の各ホスト サーバー上の同じ場所に設定してください。

    サイト内の各アプライアンスにログオンして展開する場合は、現在のログオン アカウントがサイト ディレクトリへの適切なアクセス権を **持っている必要があります**。

3. アプライアンス **ディレクトリは** 、Skype for Business Cloud Connector Edition のローカル作業ルート ディレクトリであり、外部証明書、インスタンス、ログが保存される場所です。 既定の場所は%USERPROFILE%\CloudConnector\ApplianceRoot です。

    アプライアンス ディレクトリの場所を見 **つけるには、** 次のコマンドレットを実行します。

   ```powershell
   Get-CcApplianceDirectory
   ```

    アプライアンス ディレクトリを **既定以外** の場所に設定するには、次のコマンドレットを実行します。

   ```powershell
   Set-CcApplianceDirectory <File path>
   ```

    アプライアンス ディレクトリは、アプライアンスのローカル フォルダーに設定する必要があります。 Skype for Business  Cloud Connector Edition 展開を開始する前に、アプライアンス ディレクトリのみを設定する必要があります。 展開後に変更する場合は、ホスト サーバーを再展開する必要があります。

    > [!IMPORTANT]
    > アプライアンス ディレクトリへの **パスにスペース** を含めることはできません。

## <a name="set-the-path-for-the-external-edge-certificate"></a>外部エッジ証明書のパスを設定する

- 次のコマンドレットを実行して、ファイル名を含むパスを外部エッジ証明書に設定します。 たとえば、C:\certs\cce\ap.contoso.com.pfx。 証明書には、プライベート キーが含まれている必要があります。

  ```powershell
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > -Target パラメーターはバージョン 1.4.2 以降に固有のパラメーターです。 

    ファイル名を含む外部証明書への完全なパスを指定します。 証明書は、ローカルまたはファイル共有に保存できます。 証明書が共有フォルダーに保存されている場合は、共有フォルダーを各サイトの最初のアプライアンス上に作成し、同じサイトに属する他のアプライアンスからアクセスできる必要があります。 このコマンドレットは、外部証明書をアプライアンス ディレクトリに **コピーします**。

    > [!IMPORTANT]
    > Cloud Connector バージョン **1.4.2** 以降に更新した場合は、準備された外部証明書にプライベート キーと、ルート CA 証明書と中間 CA 証明書を含む完全な証明書チェーンが含まれている必要があります。 **Cloud Connector バージョン 1.4.2** にまだ更新されていない場合は、準備された外部証明書にプライベート キーが含まれている必要があります。 この外部証明書は、既定で Windows によって信頼されている証明機関によって発行する必要があります。

## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a>外部 PSTN ゲートウェイ/SBC 証明書のパスを設定する

仲介サーバーと PSTN ゲートウェイ/SBC の間で TLS を使用している場合は、次のコマンドレットを実行して、ファイル名を含むパスをゲートウェイ証明書に設定します。 たとえば、C:\certs\cce\sbc.contoso.com.cer。 証明書には、ゲートウェイに割り当てられた証明書のルート CA と中間チェーンが含まれている必要があります。

```powershell
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 
```

> [!NOTE]
> -Target パラメーターはバージョン 1.4.2 以降に固有のパラメーターです。 

## <a name="create-virtual-switches-in-hyper-v-manager"></a>Hyper-V マネージャーで仮想スイッチを作成する

1. **Hyper-V Manager 仮想スイッチ**  >  **マネージャーを開き、[** 新しい仮想スイッチ マネージャー **] を選択します**。

2. 外部仮想スイッチを作成し、内部ネットワーク ドメインに接続されている物理ネットワーク アダプターにバインドします。

    [ **この仮想スイッチのこのネットワーク アダプターを共有する管理オペレーティング** システムを許可する] を選択します。

3. 外部仮想スイッチを作成し、インターネットにルーティングされる物理ネットワーク アダプターにバインドします。

    [管理オペレーティング **システムでこの仮想スイッチのこのネットワーク アダプターを共有** する] を選択します。

4. 境界ネットワークを内部ネットワーク ドメイン SfB CCE Corpnet Switch に接続するスイッチ **の名前を設定します**。

    境界ネットワークをインターネット SfB CCE インターネット スイッチに接続するスイッチ **の名前を設定します**。

## <a name="update-the-cloudconnectorini-configuration-file"></a>構成ファイルCloudConnector.ini更新する

「Plan for Business [Cloud Connector Edition」](plan-skype-for-business-cloud-connector-edition.md)の[](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)「展開パラメーターの決定」で収集した情報を使用して、CloudConnector.iniファイルを準備します。

ファイルを更新するには、まず次のコマンドレットを実行してサンプル テンプレートを取得します (CloudConnector.Sample.ini)。

```powershell
Export-CcConfigurationSampleFile
```

サンプル テンプレートはアプライアンス ディレクトリに **格納されます**。

環境の値を使用して更新した後、アプライアンス ディレクトリにファイルCloudConnector.iniとして **保存します**。 **Get-CcApplianceDirectory を** 実行して、アプライアンス ディレクトリへのパスを **決定できます**。

.ini ファイルを更新する場合は、次の点を考慮してください。

> [!NOTE]
> このセクションでは、.ini ファイルのすべての値について説明する必要はありません。ここでは、特別な考慮事項を持つ値についてのみ説明します。 完全な一覧については、「Plan [](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) for Skype for Business Cloud Connector Edition」の「展開パラメーターの決定」[セクションを参照](plan-skype-for-business-cloud-connector-edition.md)してください。 追加のアプライアンスまたは新しいサイトに対して変更する必要がある値の詳細については、「Cloud [Connector](deploy-multiple-sites-in-cloud-connector.md)で複数のサイトを展開する」のトピックの「高可用性[(HA)](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site)を備えた単一サイト」を参照してください。 

- **SiteName:** 既定値は **Site1 です**。 **Register-CcAppliance** を実行してアプライアンスを既存または新しいサイトに登録する場合、コマンドレットは **SiteName** を使用して登録するサイトを決定するために、クラウド コネクタを展開する前に更新する必要があります。

     アプライアンスを新しいサイトに登録する場合 **、SiteName** の値は一意で、既存のサイトとは異なる値である必要があります。 アプライアンスを既存のサイトに登録する場合は **、.ini** ファイルの SiteName の値が、Microsoft 365 または Office 365 組織構成で定義されている名前と一致している必要があります。 あるサイトから別のサイトに構成ファイルをコピーする場合は、必ずサイトごとに **SiteName** の値を更新してください。

- **ServerName:** サーバー名にはドメイン名を含めず、15 文字に制限する必要があります。

- **HardwareType:** 値を null に設定または残しておかなかった場合は、既定値 **の Normal が** 使用されます。 「Plan [for Skype for Business Cloud Connector Edition」](plan-skype-for-business-cloud-connector-edition.md)の説明に従って、ホスト コンピューターごとに 500 の同時呼び出しをサポートするために、より大きなバージョンのクラウド コネクタを展開する予定の場合は、標準を使用します。  50 **回** の同時呼び出しをサポートする小規模な展開には、Minimum を使用します。

- **Internet/Corpnet/Management 仮想スイッチ:** 作成した仮想スイッチの名前を追加します。 管理仮想スイッチの場合は、既定値のままにします。 展開スクリプトは、展開の開始時に管理仮想スイッチを作成し、展開が完了すると削除します。

- **ManagementIPPrefix:** [ネットワーク] セクションの ManagementIPPrefix は、他の内部 IP とは異なるサブネットである必要があります。 たとえば、既定値が示すように、ManagementIPPrefix は 192.168.213.0、AD IPAddress は 192.168.0.238 です。

    展開スクリプトは、各仮想マシンに管理ネットワーク アダプターを作成し、管理 IP を割り当て、管理仮想スイッチに接続します。 これにより、ホスト サーバーは、この管理ネットワークを介して各仮想マシンに接続して管理できます。 展開が完了すると、管理仮想スイッチが削除されます。

- **基本 VM 固有の構成:** このセクションの設定は **、Convert-CcIsoToVhdx コマンドレット用に構成する必要** があります。

    基本 VM イメージの準備中に、基本 VM は内部ネットワーク スイッチに接続されます。 VM がインターネットにアクセスするには、次の設定が重要です。

  - [共通]BaseVMIP: 基本 VM に割り当てる corpnet IP アドレス。

  - [ネットワーク]CorpnetDefaultGateway: 基本 VM に割り当てられる既定のゲートウェイ。

  - [ネットワーク]CorpnetDNSIPAddress: ベース VM に割り当てる DNS IP アドレス。

  - [ネットワーク]WSUSServer: Windows Server Update Service の IP アドレス。

  - [ネットワーク]WSUSStatusServer: Windows Server Update Service 状態サーバーの IP アドレス。

  - [ネットワーク]EnableReferSupport: これは、IP/PBX のトランク構成で SIP REFER のサポートが有効か無効かを定義します。

- **内部の IPs:**

  - サブネット マスク CorpnetIPPrefixLength が正しいか確認します。

  - これらの内部 IP に対して IP の競合が発生しなかご確認ください。

- **外部 AP:**

  - MR パブリック IP の場合: NAT 以外の場合は ExternalMRIP、NAT の場合は ExternalMRPublicIP を指定します。

  - ExternalSIPIPs と ExternalMRIP は同じにできます。

  - サブネット マスク InternetIPPrefixLength が正しいか確認します。

  - これらの外部 IP に対して IP 競合が発生しなかからなか確認してください。

- **ゲートウェイ:**

  - ゲートウェイが 1 つのみである場合は、セカンダリ ゲートウェイのセクションを削除します。 2 つ以上のゲートウェイがある場合は、既存のゲートウェイをコピーして貼り付け、更新することで、追加のセクションを作成します。

  - ゲートウェイの IP アドレスとポートが正しいか確認します。

  - PSTN ゲートウェイ レベルの HA をサポートするには、セカンダリ ゲートウェイを離れ、使用する追加のゲートウェイを追加します。 既存のエントリをコピーして貼り付け、更新できます。

- 必要に応じて、LocalRoute 値を更新して発信通話番号を制限できます。

## <a name="download-the-bits-to-the-site-directory"></a>サイト ディレクトリにビットをダウンロードする

次のコマンドレットを実行して、ビットおよびバージョン情報ファイルをサイト ディレクトリに **ダウンロードします**。

```powershell
Start-CcDownload
```

> [!NOTE]
> この手順は、最初のアプライアンスでのみ実行する必要があります。 

## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a>ダウンロードした ISO ファイルから基本仮想ディスク (VHDX) を準備する

この手順では、ISO イメージから仮想ハード ディスク (VHDX) Windows Server 2012準備します。 VHDX は、展開中に仮想マシンを作成するために使用されます。 一時的な仮想マシン (基本 VM) が作成されWindows Server 2012 ISO ファイルからインストールされます。 VM が作成されると、必要なコンポーネントがインストールされ、最新の Windows 更新プログラムが適用されます。 最後に、基本 VM は一般化 (sysprep) され、クリーンアップされ、生成された仮想ディスク ファイルだけが残されます。

> [!NOTE]
> この手順は、最初のアプライアンスでのみ実行する必要があります。 

この手順に進む前に、corpnet スイッチが作成されている必要があります。 また、次の設定がファイルファイルで正しく構成CloudConnector.iniします。

- [ネットワーク]CorpnetSwitchName

- [共通]BaseVMIP

- [ネットワーク]CorpnetIPPrefixLength

- [ネットワーク]CorpnetDefaultGateway

- [ネットワーク]CorpnetDNSIPAddress

管理者として PowerShell コンソールを起動し、次のコマンドレットを実行して、ISO イメージを仮想ハード ディスク (VHD) に変換します。

```powershell
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

ISO イメージへの完全なパス (ファイル名を含む) を指定します。 たとえば、C:\ISO\WindowsServer2012R2.iso。

作成された VHD ファイルは、サイト ディレクトリ **\Bits\VHD** フォルダーに格納されます。 **Get-CcSiteDirectory** を実行すると、サイト ディレクトリへのパスを取得できます。

> [!IMPORTANT]
> 既定では、プロキシ設定は基本 VM で構成されていません。 Windows Update 経由で VM を更新するためにネットワーク環境でプロキシが必要な場合は、"Convert-CcIsoToVhdx" を実行するときに -PauseBeforeUpdate スイッチを追加する必要があります。 スクリプトは Windows Update の前に一時停止し、VM で手動でプロキシを設定する機会があります。 プロキシがセットアップされ、VM がインターネットにアクセスしたら、スクリプトを再開して残りの手順を完了できます。 

### <a name="create-vhds-for-a-multi-site-deployment"></a>複数サイト展開の VHD を作成する

これは、複数サイト展開にのみ適用されるオプションの手順です。

複数サイト展開を展開する場合は、サイトごとに ISO を VHD に変換する必要があります。 最初のサイト用に作成された VHDX を、2 番目のサイトのホスト サーバーにコピーできます。

 追加サイトのホスト サーバー上で、同じファイルの場所 **(Site Directory** \Bits\VHD フォルダー) と同じファイル名でファイルをコピーします。

## <a name="set-the-powershell-execution-policy-to-remotesigned"></a>PowerShell 実行ポリシーを RemoteSigned に設定する

指定された PowerShell スクリプトでは、実行ポリシーを RemoteSigned に設定する必要があります。 現在の設定を表示するには、管理者として PowerShell コンソールを開き、次のコマンドレットを実行します。

```powershell
Get-ExecutionPolicy
```

"RemoteSigned" に設定されていない場合は、次のコマンドレットを実行して変更します。

```powershell
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a>ホスト コンピューターのローカル グループ ポリシーの変更 (バージョン 1.4.1 以前)

> [!NOTE]
> このタスクは、Cloud Connector バージョン 1.4.2 以降では必要ありません。 

CceService アカウントは、Skype for Business Cloud Connector Edition の展開中に作成されます。 クラウド コネクタ管理サービスを実行し、クラウド コネクタ管理サービスをアンインストールするためのアクセス許可がcloudconnector.msi。 Cloud Connector ホスト コンピューターのグループ ポリシー設定を変更して、ユーザーがログオフするときにユーザー レジストリをアンロードしなけれと指定する必要があります。 以下の手順に従います。

### <a name="to-change-the-group-policy-setting"></a>グループ ポリシー設定を変更するには

1. gpedit.msc **を実行して** グループ ポリシー エディターを開きます。

2. グループ ポリシー **エディター** で、[管理用テンプレート] > System > UserProfile > [ユーザー ログオフ時にユーザー レジストリを強制的にアンロードしない] に移動します。 

3. 値を [有効] に **設定します**。

## <a name="set-up-your-microsoft-365-or-office-365-organization"></a>Microsoft 365 または 365 Officeをセットアップする

Skype for Business Online および電話システムOffice Microsoft 365 または 365 組織が必要です。 クラウド コネクタを使用する前に、テナントがセットアップおよび構成されていることを確認してください。

一部の Microsoft 365 および Office 365 セットアップ手順では、テナント リモート PowerShell (TRPS) を使用して Microsoft 365 または 365 組織Officeする必要があります。 **これはホスト サーバーにインストールする必要があります。** PowerShell 用の Skype for Business Online モジュールは [、Skype for Business Online、skype for Business Online、](https://www.microsoft.com/download/details.aspx?id=39366)および Windows PowerShellダウンロードできます。

CceOnlineManagmentAdministrator など、クラウド コネクタ のオンライン管理用の専用の Skype for Business 管理者アカウントを作成します。 このアカウントは、アプライアンスを追加または削除したり、自動 OS 更新を有効または無効にしたり、自動バイナリ更新を有効または無効にしたりするためにアプライアンスによって使用されます。 このアカウントのパスワードを有効期限が切れることはありませんので、有効期限が切れる度にサービスのパスワードを変更する必要はありません。