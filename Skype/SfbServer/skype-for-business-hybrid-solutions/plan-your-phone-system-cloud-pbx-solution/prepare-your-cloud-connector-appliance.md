---
title: Cloud Connector アプライアンスの準備
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
ms.assetid: 6eacfa99-9759-4c13-aca3-8992c2ff2710
description: Office 365 の電話システム (クラウド PBX) とともに展開および使用するために Cloud Connector アプライアンスを準備する方法について説明します。
ms.openlocfilehash: 3716c7c4b9d4b8daa0a4995ed7e3d77b400b587f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32240883"
---
# <a name="prepare-your-cloud-connector-appliance"></a>Cloud Connector アプライアンスの準備

Office 365 の電話システム (クラウド PBX) とともに展開および使用するために Cloud Connector アプライアンスを準備する方法について説明します。

このセクションでは、Skype for Business Cloud Connector エディションのインストール ファイルの取得、Cloud Connector ソフトウェアのインストール、展開に向けた Cloud Connector アプライアンスの準備を行う方法について説明します。 このセクションに示す手順を完了すれば、Cloud Connector を単一または複数のサイトに展開する準備が整います。 既存の Cloud Connector 展開が存在する場合に Cloud Connector バージョン 2.1 にまだアップグレードしていない場合は、[Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md) を参照してください。

> [!NOTE]
> Microsoft は、Cloud Connector Edition の現在のバージョンであるバージョン 2.1 をサポートします。 自動更新を構成している場合、Cloud Connector は自動的に更新されます。 手動更新を構成している場合、リリース後 60日以内にバージョン 2.1 に更新する必要があります。 Microsoft は、ユーザーによる更新期間を確保するため、2.1 のリリース後 60 日間において以前のバージョンをサポートします。 

> [!NOTE]
> Cloud Connector のバージョン 2.1 以降の場合、ホスト アプライアンスで .NET Framework 4.6.1 以降がインストールされている必要があります。   

> [!IMPORTANT]
> 展開を成功させるには、ビジネス クラウド コネクタ ・ エディションの Skype を構成するのには、コマンドレットを実行すると常に同じコンソール セッションを使用で起動するものとします。 展開中と設定中に、別のセッションに切り替えないでください。 

> [!NOTE]
> 展開における最初のアプライアンスのみに対して実行する手順として、サイト ディレクトリの共有の作成、ビットのダウンロード、Windows Server ISO イメージからの仮想ハードディスク (VHDX) ファイルの準備があります。 

## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a>Skype for Business Cloud Connector Edition インストーラのダウンロード

1. クラウド コネクタの Vm を実行するホスト サーバーにインストール ファイルをダウンロードします: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller)。 

    > [!IMPORTANT]
    > Cloud Connector のインストール中に新たなファイルがダウンロードされるので、インストール中はホスト サーバーからインターネットにアクセスできる必要があります。 

2. インストーラを実行し、インストール中にデフォルト値を受け入れます。

3. インストールが正常に完了したことを確認します。

## <a name="verify-the-installation-and-configure-the-environment"></a>インストールの検証と環境の設定

1. 管理者として PowerShell コンソールを開き、ビジネス クラウド コネクタ ・ エディションのコマンドレットの Skype が次のコマンドレットを使用して利用可能であることを確認します。

   ```
   Get-Command *-Cc*
   ```

    コマンドは、ビジネスのクラウド コネクタのエディションの Skype のコマンドレットの一覧を返す必要があります。

2. VHD ファイル、SfBBITS ファイル、VersionInfo ファイルが**サイト ディレクトリ**に格納されます。

    次のコマンドレットで**サイト ディレクトリ**の場所を見つけることができます。

   ```
   Get-CcSiteDirectory
   ```

    コマンドによってファイル システム内の場所が返されます。 この場所にはローカルのフォルダーまたはファイル共有が該当します。 **サイト ディレクトリ**のデフォルトの場所は、%USERPROFILE%\CloudConnector\SiteRoot です。 デフォルトの場所は、サイトごとに作成された最初のアプライアンス上のファイル共有に変更する必要があります。

    選択する場所は次を満たす必要があります。

   - サイトごとに作成された最初のアプライアンスで作成された場所であること。

   - 同じサイトの他のホスト サーバー (アプライアンス) がアクセスできる共有フォルダーであること。

     **サイト ディレクトリ**をデフォルト以外の場所に設定するには、次のコマンドレットを実行します。

   ```
   Set-CcSiteDirectory <UNC File path>
   ```

    サイトに高可用性 (HA) を展開する場合は、コマンドレットを実行してサイト内の各ホスト サーバーの同じ場所に**サイト ディレクトリ**を設定してください。

    ログオンしてサイト内で各アプライアンスを展開する場合、現在のログオン アカウントに**サイト ディレクトリ**への適切なアクセス権があることを確認してください。

3. **アプライアンス ディレクトリ**は、Skype ビジネス クラウド コネクタ ・ エディション、および外部の証明書、インスタンス、およびログの保存場所のローカル作業用のルート ディレクトリです。 デフォルトで次の場所になります: %USERPROFILE%\CloudConnector\ApplianceRoot

    **アプライアンス ディレクトリ**の場所を見つけるには、次のコマンドレットを実行します。

   ```
   Get-CcApplianceDirectory
   ```

    **アプライアンス ディレクトリ**をデフォルト以外の場所に設定するには、次のコマンドレットを実行します。

   ```
   Set-CcApplianceDirectory <File path>
   ```

    アプライアンス ディレクトリは、アプライアンスのローカル フォルダーに設定する必要があります。 ビジネス クラウド コネクタのエディションの展開での Skype を起動する前にのみ、**アプライアンスのディレクトリ**を設定してください。 展開後にそれを変更する場合は、ホスト サーバーを再び展開する必要があります。

    > [!IMPORTANT]
    > **アプライアンス ディレクトリ**へのパスにはスペースを含めないでください。

## <a name="set-the-path-for-the-external-edge-certificate"></a>外部 Edge 証明書のパスの設定

- 次のコマンドレットを実行して、Microsoft Edge 外部証明書へのパスをファイル名も含めて設定します (例: C:\certs\cce\ap.contoso.com.pfx)。証明書には秘密キーが含まれる必要があります。

  ```
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > -Target パラメーターはバージョン 1.4.2 固有のものであることに注意してください。 

    ファイル名を含む、外部証明書への完全なパスを指定します。 証明書はローカルまたはファイル共有に格納できます。 証明書を共有フォルダーに格納する場合、その共有フォルダーは各サイトの最初のアプライアンス上に作成し、同一のサイトに属するその他のアプライアンスによってアクセス可能である必要があります。 このコマンドレットは、外部証明書を**アプライアンス ディレクトリ**にコピーします。

    > [!IMPORTANT]
    > **Cloud Connector バージョン 1.4.2 以降に更新している場合は**、準備した外部証明書に、プライベート キー、およびルート CA 証明書および中間 CA 証明書を含む完全な証明書チェーンが含まれていることを確認します。 **Cloud Connector のバージョン1.4.2　にまだ更新していない場合は**、準備した外部証明書にプライベート キーが含まれていることを確認します。 この外部証明書は、既定で Windows で信頼されている認証局が発行したものである必要があります。

## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a>外部 PSTN ゲートウェイ/SBC 証明書のパスの設定

仲介サーバーと PSTN ゲートウェイと SBC の間で TLS を使用する場合は、ゲートウェイの証明書に、ファイル名を含むパスを設定するのには次のコマンドレットを実行します。 例: C:\certs\cce\sbc.contoso.com.cer。 証明書は、ルート CA と中間ゲートウェイに割り当てられている証明書のチェーンに含まれている必要があります。

```
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 
```

> [!NOTE]
> -Target パラメーターはバージョン 1.4.2 固有のものであることに注意してください。 

## <a name="create-virtual-switches-in-hyper-v-manager"></a>Hyper-V マネージャーでの仮想スイッチの作成

1. **HYPER-V マネージャー**を開き > **仮想スイッチ マネージャー**、および**新しい仮想スイッチ マネージャー**を選択します。

2. 外部仮想スイッチを作成し、それを内部のネットワーク ドメインに接続される物理ネットワーク アダプターにバインドします。

    この仮想スイッチに **[管理オペレーティング システムによるこのネットワーク アダプターの共有を許可する]** を選びます。

3. 外部仮想スイッチを作成して、インターネットにルーティングされる物理ネットワーク アダプターにバインドします。

    この仮想スイッチについての [**管理オペレーティング システムによるこのネットワーク アダプターの共有を許可する**] の選択を解除します。

4. 境界ネットワークを内部ネットワーク ドメインに接続するスイッチの名前を **SfB CCE Corpnet Switch** に設定します。

    境界ネットワークをインターネットに接続するスイッチの名前を、**SfB CCE Internet Switch** に設定します。

## <a name="update-the-cloudconnectorini-configuration-file"></a>CloudConnector.ini 構成ファイルの更新

[ビジネス クラウド コネクタ ・ エディションの Skype の計画](plan-skype-for-business-cloud-connector-edition.md)のトピック[を決定する配置パラメーター](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)で収集した情報を使用して CloudConnector.ini ファイルを準備します。

ファイルを更新するには、まず次のコマンドレットを実行してサンプルのテンプレート (CloudConnector.Sample.ini) を入手します。

```
Export-CcConfigurationSampleFile
```

サンプルのテンプレートは**アプライアンス ディレクトリ**に保存されています。

環境に応じた値でファイルを更新したら、ファイルを CloudConnector.ini として**アプライアンス ディレクトリ**に保存します。 **Get-CcApplianceDirectory** を実行して**アプライアンス ディレクトリ**へのパスを決めることができます。

.ini ファイルを更新するとき、次を考慮します。

> [!NOTE]
> このセクションでは .ini ファイルのすべての値を取り上げておらず、特別な考慮が必要な値のみを説明しています。 完全なリスト、[ビジネス クラウド コネクタ ・ エディションの Skype の計画](plan-skype-for-business-cloud-connector-edition.md)のトピック[を決定する展開のパラメーター](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) 」を参照してください。 追加のアプライアンスまたは新しいサイト用に変更する必要がある値の詳細については、トピック [ の「](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site)マルチサイト展開と高可用性 (HA) 対応の単一サイトの比較[Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md)」を参照してください。 

- **SiteName:** デフォルト値は **Site1** です。Cloud Connector の展開前にこれを更新する必要があります。その理由は、**Register-CcAppliance** を実行して既存または新規のサイトにアプライアンスを登録するとき、コマンドレットが **SiteName** を使ってどのサイトに登録するかを決めるからです。

     新規サイトにアプライアンスを登録する場合は、**SiteName** の値は一意で既存のサイトと異なる必要があります。 アプライアンスの既存のサイトを登録する場合は、.ini ファイル内の**サイト名**の値は、Office 365 テナント構成で定義されている名前と一致しなければなりません。 あるサイトから別のサイトに構成ファイルをコピーする場合は、必ずサイトごとに **SiteName** の値を更新してください。

- **ServerName:** サーバー名はドメイン名を含まず、15 文字に制限する必要があります。

- **HardwareType:** 設定または、null 値のままにしない、**通常**の既定値が適用されます。 [Skype ビジネス クラウド コネクタ ・ エディションのための計画](plan-skype-for-business-cloud-connector-edition.md)で説明するように、ホスト マシンごとの 500 の同時呼び出しをサポートするクラウドのコネクタの大きなバージョンを展開する場合は、**標準**を使用します。 50 の同時通話をサポートする小規模な展開の場合は **Minimum** を使用します。

- **インターネット/Corpnet/管理仮想スイッチ:** 作成した仮想スイッチの名前を追加します。 管理仮想スイッチの場合は、デフォルト値をそのまま残します。 展開スクリプトは展開の始まりで管理仮想スイッチを作成し、展開の終わりに削除します。

- **ManagementIPPrefix:** ネットワーク セクションの ManagementIPPrefix は、他の内部 IP とは異なるサブネットである必要があります。例えば、デフォルト値が示すように、ManagementIPPrefix は 192.168.213.0、AD IPAddress は 192.168.0.238 となります。

    展開スクリプトは管理ネットワーク アダプターを仮想マシンごとに作成し、管理 IP を割り当て、それを管理仮想スイッチに接続します。これによりホスト サーバーは、この管理ネットワーク経由で各仮想マシンに接続しそれらを管理できます。管理仮想スイッチは展開が終了すると削除されます。

- **ベース VM 固有の設定:** このセクションの設定は **Convert-CcIsoToVhdx** コマンドレットに対して設定する必要があります。

    ベース VM イメージを準備するとき、ベース VM は内部ネットワーク スイッチに接続されます。次の設定は、VM がインターネットに接続できるようにするために重要です。

  - [Common]BaseVMIP: ベース VM に割り当てられる corpnet IP アドレス。

  - [Network]CorpnetDefaultGateway: ベース VM に割り当てられるデフォルトのゲートウェイ。

  - [Network]CorpnetDNSIPAddress: ベース VM に割り当てられる DNS IP アドレス。

  - [Network]WSUSServer: Windows Server Update Service の IP アドレス。

  - [Network]WSUSStatusServer: Windows Server Update Service ステータス サーバーの IP アドレス。

  - [Network]EnableReferSupport: IP/PBX へのトランク構成で SIP REFER のサポートが有効化または無効化されるかを定義します。

- **内部 IP:**

  - CorpnetIPPrefixLength のサブネット マスクが正しいことを確認します。

  - これらの内部 ip アドレスの IP が競合していないことを確認します。

- **外部 IP:**

  - MR パブリック ip: NAT 以外の ExternalMRIPs、または NAT の ExternalMRPublicIPs のいずれかを指定します。

  - ExternalSIPIPs と ExternalMRIPs を同じにすることができます。

  - InternetIPPrefixLength のサブネット マスクが正しいことを確認します。

  - これらの外部 ip アドレスの IP が競合していないことを確認します。

- **ゲートウェイ:**

  - ゲートウェイが 1 つだけある場合は、セカンダリ ゲートウェイのセクションを削除します。ゲートウェイが 3 つ以上ある場合は、既存のセクションをコピー貼り付けしてから、それを更新します。

  - ゲートウェイの IP アドレスとポートが正しいことを確認します。

  - PSTN ゲートウェイ レベルの HA をサポートするには、セカンダリ ゲートウェイを残し、新たなゲートウェイをいくつか追加して使います。 コピーして既存のエントリを貼り付けると、それを更新します。

- 必要に応じて、送信呼び出しの数を制限するのには LocalRoute の値を更新できます。

## <a name="download-the-bits-to-the-site-directory"></a>サイト ディレクトリに BITS をダウンロードします。

次のコマンドレットを実行して、BITS ファイルとバージョン情報ファイルを**サイト ディレクトリ**にダウンロードします。

```
Start-CcDownload
```

> [!NOTE]
> 最初のアプライアンスでのみ、この手順を実行する必要があります。 

## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a>ダウンロードした ISO ファイルからベース仮想ディスク (VHDX) を準備します。

この手順では、Windows Server 2012 の ISO イメージから仮想ハード ディスク (VHDX) ファイルを準備します。 VHDX は展開時の仮想マシン作成に使われます。 一時的な仮想マシン (VM の基本) が作成され、Windows Server 2012 は、ISO ファイルからインストールされます。 VM を作成した後、必要なコンポーネントがいくつかインストールされ、最新の Windows 更新プログラムが適用されます。 最後に、ベース VM の一般化 (sysprep) とクリーンアップが行われ、生成された仮想ディスク ファイルのみが残ります。

> [!NOTE]
> 最初のアプライアンスでのみ、この手順を実行する必要があります。 

この手順を進める前に、corpnet スイッチが作成されていることを確認してください。また、CloudConnector.ini ファイルで次の設定が正しく行われていることを確認してください。

- [Network]CorpnetSwitchName

- [Common]BaseVMIP

- [Network]CorpnetIPPrefixLength

- [Network]CorpnetDefaultGateway

- [Network]CorpnetDNSIPAddress

PowerShell を管理者として起動し、次のコマンドレットを実行して ISO イメージを仮想ハード ディスク (VHD) に変換します。

```
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

ISO イメージへの完全なパスをファイル名も含めて指定します (例: C:\ISO\WindowsServer2012R2.iso)。

作成された VHD ファイルは、**サイト ディレクトリ**の \Bits\VHD フォルダーに格納されます。 **サイト ディレクトリ**へのパスは **Get-CcSiteDirectory** を実行して取得できます。

> [!IMPORTANT]
> デフォルトで、ベース VM でプロキシ設定は構成されません。 プロキシは、ネットワーク環境で Windows Update を使用して VM を更新すると、「変換 CcIsoToVhdx」を実行すると、- PauseBeforeUpdate スイッチを追加してください。 Windows Update の前に、スクリプトを一時停止し、VM 上でプロキシを手動で設定することがあります。 VM がインターネットにアクセスできるようにプロキシを設定したら、スクリプトを再開して残りの手順を完了できます。 

### <a name="create-vhds-for-a-multi-site-deployment"></a>マルチサイト展開でのVHD の作成

このオプションの手順は、マルチサイト展開のみに適用されます。

マルチサイト展開を行う場合、サイトごとに ISO から VHD に変換する必要はありません。最初のサイトに作成した VHDX を、2 番目のサイトのホスト サーバーにコピーできます。

 追加のサイトのホスト サーバー上の同じファイル名と同じファイルの場所 (**サイトのディレクトリ**\Bits\VHD フォルダー) にファイルをコピーします。

## <a name="set-the-powershell-execution-policy-to-remotesigned"></a>PowerShell 実行ポリシーを RemoteSigned に設定する

提供される PowerShell スクリプトでは、実行ポリシーを RemoteSigned に設定する必要があります。現在の設定を表示するには、管理者として PowerShell コンソールを開き、次のコマンドレットを実行します。

```
Get-ExecutionPolicy
```

「RemoteSigned」に設定されていない場合は、次のコマンドレットを実行して設定を変更します。

```
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a>ホスト マシンでローカルグループ ポリシーを変更します (バージョン 1.4.1 以前)。

> [!NOTE]
> Cloud Connector バージョン 1.4.2 以降では、このタスクは不要です。 

Skype for Business Cloud Connector エディションの展開時に CceService アカウントが作成されます。 クラウド コネクタの管理サービスを実行して、cloudconnector.msi をアンインストールするのには権限が必要です。 ユーザーのログオフ時にユーザー レジストリがアンロードされないように指定するには、Cloud Connector のホスト コンピューター上のグループ ポリシー設定を変更する必要があります。 以下の手順を実行します。

### <a name="to-change-the-group-policy-setting"></a>グループ ポリシー設定を変更するには

1. Gpedit.msc を実行することによって、**グループ ポリシー エディター**を開きます。

2. **グループ ポリシー エディター**で、[管理用テンプレート] > [システム] > [ユーザー プロファイル] > [ユーザーのログオフ時に強制的にユーザー レジストリをアンロードしない] に移動します。 

3. その値が**有効**に設定します。

## <a name="set-up-your-office-365-tenant"></a>Office 365 テナントの設定

Skype for Business Online と Office 365 の電話システムを使用している Office 365 テナントが必要です。 テナントを設定し、クラウドのコネクタを使用する前に構成されていることを確認してください。

いくつかの Office 365 のセットアップ手順では、テナント リモート PowerShell (TRPS) を使用して、Office 365 テナントを構成する必要があります。 **これはホスト サーバー上にインストールしてください。** PowerShell からのオンライン ビジネス モジュールの Skype をダウンロードする: [Windows PowerShell モジュール ビジネス オンラインの Skype](https://www.microsoft.com/en-us/download/details.aspx?id=39366)です。

クラウド コネクタのオンライン管理、CceOnlineManagmentAdministrator などのビジネス管理者のアカウント用の専用の Skype を作成します。 このアカウントはアプライアンスによって使用され、アプライアンスの追加や削除、自動 OS 更新の有効化や無効化、自動バイナリ更新の有効化や無効化を行うことができます。 このアカウントのパスワードが期限切れにならないように設定すると、サービスが期限切れになるたびにパスワードを変更する必要がなくなります。


