---
title: 仮想デスクトップ インフラストラクチャ用の Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jmorrow
audience: admin
description: 仮想デスクトップ インフラストラクチャ (VDI) 環境で Microsoft Teams を実行する方法について説明します。
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7a4a05e6dabc3e319171cb71525b6c2175c8235c
ms.sourcegitcommit: a9a056b93b4add3a4d978bb341ea4b66a042b4d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2022
ms.locfileid: "62893626"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>仮想デスクトップ インフラストラクチャ用の Teams

この記事では、仮想化された環境でアプリケーションを使用する場合のMicrosoft Teams制限事項について説明します。

## <a name="what-is-vdi"></a>VDI とは何ですか ?

仮想デスクトップ インフラストラクチャ (VDI) は、データセンターの集中サーバーでデスクトップ オペレーティング システムとアプリケーションをホストする仮想化テクノロジです。 これにより、完全にセキュリティで保護され、準拠している一元化されたソースを使用するユーザーに対して、完全でパーソナライズされたデスクトップ エクスペリエンスを実現できます。

Teams環境では、チャットとコラボレーションがサポートされます。 また、Azure Virtual Desktop、Citrix、VMware プラットフォームでは、通話と会議の機能もサポートされています。

Teams仮想環境での複数の構成もサポートしています。 これらには、VDI、専用、共有、永続、非永続のモードが含まれます。 機能は継続的な開発中であり、定期的に追加され、機能は時間の中で拡張されます。

仮想化環境での Teams の使用は、非仮想化環境での Teams の使用とは多少異なる場合があります。 たとえば、仮想化環境では一部の高度な機能が利用できない可能性があり、ビデオ解像度が異なる場合があります。

最適なユーザー エクスペリエンスを確保するには、この記事のガイダンスに従ってください。

> [!Note]
> 別のプラットフォームでの Teams VDI に関する詳細は、「[プラットフォームごとの Teams の機能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)」を参照してください。

## <a name="teams-on-vdi-components"></a>VDI 上の Teams のコンポーネント

仮想化環境で Teams を使用するには、次のコンポーネントが必要です。

- **仮想化ブローカー**: Azure などの仮想化プロバイダーへのリソースおよび接続マネージャー
- **仮想デスクトップ**: 仮想マシンを実行する仮想マシン (VM) Teams
- **シン クライアント**: ユーザーが物理的にインターフェイスするデバイス
- **Teams デスクトップ アプリ**: Teams デスクトップ クライアント アプリ

## <a name="teams-on-vdi-requirements"></a>VDI 上の Teams の要件

### <a name="virtualization-provider-requirements"></a>仮想化プロバイダーの要件

Teams デスクトップ アプリは、主要な仮想化ソリューション プロバイダーで検証済みです。 複数の市場プロバイダーを使用している場合は、仮想化ソリューション プロバイダーに相談して、最小要件が満たされていることを確認することをお勧めします。
  
現在、Teams/ビデオ (AV) 最適化を使用した VDI での認証は、Azure Virtual Desktop、Citrix、VMware で認定されています。 このセクションの情報を確認して、適切に機能するためのすべての要件を満たしていることを確認してください。

### <a name="platforms-certified-for-teams"></a>Teams 認定プラットフォーム

次のプラットフォームには、Teams 用の仮想デスクトップ インフラストラクチャ ソリューションがあります。

|プラットフォーム|ソリューション|
|----|---|
|![Microsoft を表すロゴ。](media/microsoft-logo.png)| <a href="/azure/virtual-desktop/teams-on-wvd" target="_blank">Azure Virtual Desktop</a>、<a href="/windows-365/enterprise/teams-on-cloud-pc" target="_blank">Windows 365</a> |
|![Citrix を表すロゴ。](media/citrix-logo.png)| <a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix Virtual Apps and Desktops</a> |
|![VMware を表すロゴ。](media/vmware-logo.png)| <a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware Horizon</a> |

### <a name="azure-virtual-desktop"></a>Azure Virtual Desktop

Azure Virtual Desktop は、VDI 上の仮想マシンTeams AV 最適化を提供します。 要件とインストールの詳細については、「[Azure Virtual Desktop での Teams使用」を参照してください](/azure/virtual-desktop/teams-on-wvd)。

### <a name="windows-365"></a>Windows 365

Windows 365 では、Azure Virtual Desktop によって提供される AV 最適化を使用して、クラウド PC Teams最適なエクスペリエンスを実現します。 要件とインストールの詳細については、「クラウド PC で Teams[を使用する」を参照してください](/windows-365/enterprise/teams-on-cloud-pc)。

### <a name="citrix-virtual-apps-and-desktops-requirements"></a>Citrix Virtual Apps and Desktops の要件

Citrix Virtual Apps and Desktops (以前の XenApp および XenDesktop) は、VDI 上の Teams に AV 最適化を提供します。 Citrix Virtual Apps and Desktops を使用すると、VDI 上の Teams はチャットと共同作業に加えて、通話および会議機能をサポートします。

Citrix Virtual Apps と Desktops の最新バージョンは、Citrix のダウンロード [サイトからダウンロードできます](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/)。 (最初にサインインする必要があります。) 必要なコンポーネントは、デフォルトで [Citrix Workspace アプリ (CWA)](https://www.citrix.com/downloads/workspace-app/) および Virtual Delivery Agent (VDA) にバンドルされています。 CWA や VDA に追加のコンポーネントやプラグインをインストールする必要はありません。

サーバーとクライアントの最新の要件については、Citrix Web サイトの「[Microsoft Teamsの最適化](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)」を参照してください。

### <a name="vmware-horizon-workspace-and-desktop-requirements"></a>VMware Horizon Workspace and Desktop の要件

VMware Horizon は、ハイブリッド クラウド全体に仮想デスクトップとアプリを安全に配信するためのモダン プラットフォームです。 優れたエンドユーザー エクスペリエンスを提供するために、VMware Horizon は Teams のメディア最適化を提供します。 この最適化により、仮想デスクトップやアプリ全体の総体的な生産性が向上し、Teams を使用して通話や会議を行う際のユーザー エクスペリエンスが向上します。

VMware Horizon の最新バージョンは、[VMware ダウンロード](https://customerconnect.vmware.com/downloads/#all_products) ページからダウンロードできます。 既定では、必要なメディア最適化コンポーネントは Horizon Agent と Horizon Client に含まれているため、Teams の最適化機能を使用するために追加のプラグインをインストールする必要はありません。

Teams のメディア最適化を構成する方法に関する最新の要件と手順については、VMware Web サイト[](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html)の「Microsoft Teams のメディア最適化の構成」を参照してください。

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a>VDI で Teams デスクトップ アプリをインストールまたは更新する

MSI パッケージを使用したマシンごとのインストールまたはユーザーごとのインストールを用いて、VDI 用の Teams デスクトップ アプリを展開できます。 どのアプローチを使用するかについては、永続的なセットアップを使用するか、または非永続的なセットアップを使用するか、および組織の関連機能のニーズに応じて決定します。

専用の永続的なセットアップでは、マシンごとのインストールとユーザーごとのインストールの両方が機能します。 ただし、非永続的なセットアップの場合、Teams が効率的に機能するにはマシンごとにインストールする必要があります。 [非永続のセットアップ](#non-persistent-setup)のセクションを参照してください。

マシンごとのインストールでは、自動更新が無効になります。 つまり、Teams アプリを更新するには、現在のバージョンをアンインストールして新しいバージョンに更新する必要があります。 ユーザーごとのインストールでは、自動更新が有効になります。

ほとんどの VDI の展開について、マシンごとのインストールを使用して Teams を展開することをお勧めします。 最新の Teams バージョンに更新するには、アンインストール手順から始めて、次に最新の Teams バージョンを展開します。

VDI Teams AV 最適化を正常に機能するには、シン クライアント デバイスがインターネットにアクセスできる必要があります。 シン クライアント デバイスでインターネット アクセスが利用できない場合、最適化の起動は成功しない。 これは、ユーザーが最適化されていないメディア状態にあることを意味します。

#### <a name="dedicated-persistent-setup"></a>専用の永続的なセットアップ

専用の永続的なセットアップでは、ユーザーのローカル オペレーティング システムの変更は、ユーザーがログオフした後も保持されます。 永続的なセットアップの場合、Teams はユーザーごとのインストールとマシンごとのインストールの両方をサポートします。

推奨される最低限の VM 構成は次のとおりです。

|パラメーター  |ワークステーションのオペレーティング システム  |サーバー オペレーティング システム  |
|---------|---------|---------|
|vCPU   |    2 コア     |  4、6、または 8 コア<br>基礎となる Non-Uniform Memory Access (NUMA) 構成を理解し、それに応じて VM を構成することが重要です。     |
|RAM     |   4 GB      | ユーザーあたり 512 MB ~ 1 GB        |
|ストレージ    | 8 GB        | 40 GB ~ 60 GB        |

#### <a name="non-persistent-setup"></a>非永続的なセットアップ

非永続的なセットアップでは、ユーザーのローカル オペレーティング システムの変更は、ユーザーがログオフした後は保持されません。 このようなセットアップは、一般的に共有マルチユーザー セッションです。 VM の構成は、ユーザー数と使用可能な物理サーバー リソースによって異なります。

非永続的なセットアップの場合、Teams デスクトップ アプリは、ゴールデン イメージに対してマシンごとにインストールする必要があります。 これにより、ユーザー セッション中にTeamsアプリを効率的に起動できます。 詳細については、「[VDI で Teams デスクトップ アプリをインストールまたは更新する](#install-or-update-the-teams-desktop-app-on-vdi)」セクションを参照してください。

非永続的なTeamsでデータを使用するには、ランタイム データ同期を効率的に行うプロファイル キャッシュ マネージャー Teams必要があります。 効率的なデータ同期により、適切なユーザー固有の情報 (ユーザーのデータ、プロファイル、設定など) がユーザーのセッション中にキャッシュされます。 これら 2 つのフォルダー内のデータが同期されます。<br>

- `C:\Users\username\AppData\Local\Microsoft\IdentityCache (%LocalAppData%\Microsoft\IdentityCache)`
- `C:\Users\username\AppData\Roaming\Microsoft\Teams (%AppData%\Microsoft\Teams)`

> [!NOTE]
> Teams アプリがアプリケーションの実行に必要なランタイム データとファイルを確実に取得するには、ローミング フォルダー (またはフォルダー リダイレクトを使用している場合はキャッシュ マネージャー) が必要です。 これは、ネットワーク遅延の問題やネットワークの不具合を軽減するために必要です。それを行わない場合、データやファイルが利用できないことにより、アプリケーション エラーが発生し、動作が遅くなります。

FSLogix など、さまざまなキャッシュ マネージャー [ソリューションを使用できます](/fslogix/overview)。 具体的な構成手順については、キャッシュ マネージャー プロバイダーに問い合わせてください。

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a>Teams は、非永続的なセットアップ用のコンテンツ除外リストをキャッシュしました

キャッシュ フォルダーから次Teamsを除外します`%AppData%/Microsoft/Teams`。 これらのアイテムを除外すると、ユーザーのキャッシュ サイズが小さくなり、非永続的なセットアップがさらに最適化されます。

- .txt ファイル
- メディアスタック フォルダー
- `%AppData%\Microsoft\Teams\meeting-addin\Cache`

### <a name="microsoft-365-apps-for-enterprise-considerations"></a>Microsoft 365 Apps for enterprise に関する考慮事項

VDI で Microsoft 365 Apps for enterprise を使用して Teams を展開する場合は、次のことを考慮してください。

#### <a name="new-deployments-of-teams-through-microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps for enterprise を使用した Teams の新しい展開

Microsoft 365 Apps for enterprise を介して Teams を展開する前に、まず、マシンごとのインストールを使用して展開されている既存の Teams アプリをアンインストールする必要があります。

Microsoft 365 Apps for enterprise を介した Teams は、ユーザーごとにインストールされます。 詳細については、「[VDI で Teams デスクトップ アプリをインストールまたは更新する](#install-or-update-the-teams-desktop-app-on-vdi)」セクションを参照してください。

#### <a name="teams-deployments-through-microsoft-365-apps-for-enterprise-updates"></a>Microsoft 365 Apps for enterprise の更新プログラムを使用した Teams の展開

Teams は、Microsoft 365 Apps for enterprise の既存のインストールにも追加される予定です。 Microsoft 365 Apps for enterprise では、Teams はユーザーごとにのみインストールされるため、「[VDI で Teams デスクトップ アプリをインストールまたは更新する](#install-or-update-the-teams-desktop-app-on-vdi)」セクションを参照してください。

#### <a name="using-teams-with-per-machine-installation-and-microsoft-365-apps-for-enterprise"></a>マシンごとのインストールと Microsoft 365 Apps for enterprise での Teams の使用

Microsoft 365 Apps for enterprise は、Teams のマシンごとのインストールをサポートしていません。 マシンごとのインストールを使用するには、Microsoft 365 Apps for enterprise から Teams を除外する必要があります。 「[Teams デスクトップ アプリを VM に展開する](#deploy-the-teams-desktop-app-to-the-vm)」と「[Microsoft 365 Apps for enterprise を介した Teams の展開を除外する方法](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise)」セクションを参照してください。

#### <a name="how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps for enterprise を介した Teams の展開を除外する方法

Teams と Microsoft 365 Apps for enterprise の詳細については、「[Microsoft 365 Apps for enterprise の新規インストールから Teams を除外する方法](/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-microsoft-365-apps)」と「[グループ ポリシーを使用して Teams のインストールを制御する](/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams)」を参照してください。

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a>Teams デスクトップ アプリを VM に展開する

1. 次のリンクのいずれかを使用して、VDI VM オペレーティング システムに一致する Teams MSI パッケージをダウンロードします。

    - [32 ビット版](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)
    - [64 ビット版](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)

    > [!NOTE]
    > 政府機関向けクラウドについては、MSI ファイルへのダウンロード リンクTeamsインストーラー [(MSI)](msi-deployment.md) Windowsを使用した一括インストールに関するページを参照してください。

    必要な Teams デスクトップ アプリの最小バージョンは、バージョン 1.3.00.4461 です。 PSTN 保留は、以前のバージョンではサポートされていません。

2. 次のいずれかのコマンドを実行して、MSI を VDI VM にインストールします。

    - ユーザーごとのインストール (既定)
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        このプロセスは既定のインストールで、ユーザー フォルダー Teamsをインストール`%AppData%`します。 この時点で、ゴールデン イメージのセットアップは完了です。

        > [!IMPORTANT]
        > 非永続的なセットアップでのユーザーごとのインストールでは、Teams は適切に動作しません。

    - マシンごとのインストール

        ```console
        reg add "HKLM\SOFTWARE\Microsoft\Teams" /v IsWVDEnvironment /t REG_DWORD /d 1 /f
        ```

        このプロセスにより、必要なレジストリ キーがマシンに追加され、Teams VDI インスタンスが知らされます。  インストールしない場合、インストーラーは次のエラーを返します。"インストールに失敗しました。  VDI 環境が検出されない場合は、すべてのユーザーにインストールできません。"

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        このプロセスではTeams `%ProgramFiles(x86)%` 64 `%ProgramFiles%` ビット オペレーティング システム上のフォルダーと 32 ビット オペレーティング システム上のフォルダーにインストールされます。 この時点で、ゴールデン イメージのセットアップは完了です。

        > [!IMPORTANT]
        >  非永続的なセットアップについては、マシンごとに Teams をインストールする必要があります。

        次の対話型ログオン セッションが開始されると、Teamsし、資格情報の入力を求めるメッセージが表示されます。

        > [!NOTE]
        > これらの例では、 パラメーターも使用 `ALLUSERS=1` します。 このパラメーターを設定すると、Teams Machine-Wide **インストーラー** がコントロール パネルの **プログラムと機能** と、コンピューターのすべてのユーザーの **Windows 設定 のアプリ &** 機能に表示されます。 管理者の資格情報を持っている場合は、すべてのユーザーが Teams をアンインストールできます。
        >
        > と の違いを理解することが重要 `ALLUSERS=1` です `ALLUSER=1`。 パラメーターは非 VDI 環境と VDI `ALLUSER=1` 環境で使用できます。一`ALLUSERS=1`方、 パラメーターは VDI 環境でのみ使用され、マシンごとのインストールを指定するために使用されます。

3. VDI VM から MSI をアンインストールします。 Teams をアンインストールする方法は 2 つあります。

    - **PowerShell スクリプト**: Teams 展開 [クリーンアップ PowerShell](scripts/powershell-script-deployment-cleanup.md) スクリプトを使用して、Teams をアンインストールし、ユーザーの Teams フォルダーを削除できます。 Teams がコンピューターにインストールされているユーザー プロファイルごとにスクリプトを実行します。
    - **コマンド ライン**: 次のコマンドを実行します。
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```

      このプロセスではTeamsの環境`%ProgramFiles(x86)%`に応じて、`%ProgramFiles%`フォルダーまたはフォルダーからアプリケーションをアンインストールします。

## <a name="teams-on-vdi-performance-considerations"></a>VDI 上の Teams のパフォーマンスに関する考慮事項

さまざまな仮想化セットアップ構成があり、それぞれ最適化の焦点が異なります。 たとえば、ある構成ではユーザー密度に焦点が当てられます。 計画するときは、組織のワークロードのニーズに基づいてセットアップを最適化するために、以下を考慮してください。

- **最小要件**: 一部のワークロードでは、最小要件を超えるリソースを使用したセットアップが必要になる場合があります。 たとえば、より多くのコンピューティング リソースを必要とするアプリケーションを使用する開発者向けのワークロード。
- **依存関係:** これには、インフラストラクチャ、ワークロード、およびデスクトップ アプリ以外の環境に関するTeamsがあります。
- **VDI の無効な** 機能: Teams一時的な CPU 使用率の向上に役立つ VDI の GPU 集中型機能を無効にします。 以下の機能は無効です。
    - Teams CSS アニメーション
    - Giphy の自動起動

## <a name="teams-on-vdi-with-calling-and-meetings"></a>通話と会議を含む VDI 上の Teams

チャットと共同作業に加えて、通話と会議のサポートを備えた VDI 上の Teams は、サポートされている仮想化プロバイダーのプラットフォームで利用できます。 サポートされる機能は、WebRTC メディア スタックおよび仮想化プロバイダーの実装に基づいています。 次の図では、このアーキテクチャの概要を説明します。

![VDI アーキテクチャTeamsを示す図。](media/teams-on-vdi-architecture.png)

> [!IMPORTANT]
> 現在、VDI で AV 最適化なしで Teams を実行していて、最適化でまだサポートされていない機能 (アプリ共有時の制御の受け渡しなど) を使用している場合、仮想化プロバイダーのポリシーを設定して Teams のリダイレクトを無効にする必要があります。 これは、Teams のメディア セッションが最適化されないことを意味します。 Teams のリダイレクトを無効にするようにポリシーを設定する方法の手順については、仮想化プロバイダーにお問い合わせください。

### <a name="network-requirements"></a>ネットワーク要件

環境を評価して、クラウド全体での音声とビデオの展開に影響を与える可能性のあるリスクおよび要件を特定することをお勧めします。 [Skype for Business ネットワーク評価ツール](https://www.microsoft.com/download/details.aspx?id=53885)を使用して、ネットワークが Teams に対応しているかどうかをテストします。

Teams 用にネットワークを準備する方法の詳細については、「[Teams 用に組織のネットワークを準備する](prepare-network.md)」を参照してください。

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a>VDI上の Skype for Business から VDI 上の Teams に移行する

VDI 上の Skype for Business から VDI 上の Teams に移行する場合、2 つのアプリケーションの違いに加えて、VDI も実装されている場合にはいくつかの違いがあります。 Skype for Business VDI ではサポートされていて、Teams VDI では現在サポートされていない機能は、次のとおりです。

- VDI の一部の AV 機能を無効にするプラットフォームごとのポリシー
- アプリ共有時の制御の受け渡し
- 音声なしのチャットからの画面共有
- ビデオと画面の共有の同時送受信

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a>Chrome ブラウザーの Teams と VDI の Teams デスクトップ アプリの比較

Chrome ブラウザーの Teams は、AV 最適化を備えた VDI 用の Teams デスクトップ アプリに代わるものを提供しません。 チャットと共同作業のエクスペリエンスは期待どおりに機能します。 メディアが必要な場合、一部の機能が Chrome ブラウザーでのユーザーの期待に合致しない場合があります。

- 音声とビデオのストリーミング エクスペリエンスが最適にならない場合があります。 ユーザーに遅延が発生したり、品質が低下したりする可能性があります。
- デバイス設定は、ブラウザーの設定では使用できません。
- デバイス管理はブラウザーを介して処理され、ブラウザー サイト設定で複数の設定が必要です。
- デバイス設定は、Windows デバイス管理でも設定する必要がある場合があります。

## <a name="teams-on-vdi-with-chat-and-collaboration"></a>チャットと共同作業を備えた VDI 上の Teams

組織で Teams のチャットおよび共同作業機能のみを使用する場合は、ユーザーレベル ポリシーを設定して、Teams の通話および会議機能を無効にすることができます。

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>通話および会議機能を無効にするポリシーを設定する

ポリシーを設定するには、管理センターまたは PowerShell Teamsを使用します。 ポリシーの変更が反映されるのは最大数時間です。 指定したアカウントの変更がすぐに表示されない場合は、数時間後にもう一度お試しください。

[**呼び出**](teams-calling-policy.md)しポリシー: Teamsには、すべての呼び出し機能がオフになっている組み込みの **DisallowCalling** 呼び出しポリシーが含まれています。 仮想環境で使用している組織内のすべてのユーザーに **DisallowCalling** ポリシー Teams割り当てる。

[**会議ポリシー**](meeting-policies-overview.md): Teamsすべての会議機能がオフになっている組み込みの **AllOff** 会議ポリシーが含まれています。 **AllOff ポリシーを、** 仮想化環境で使用する組織内のすべてのユーザー Teams割り当てる。

#### <a name="assign-policies-using-the-teams-admin-center"></a>管理センターでポリシーをTeamsする

**DisallowCalling 呼び出しポリシーと** **AllOff** 会議ポリシーをユーザーに割り当てるには:

1. 管理センターの左側のナビゲーションTeams、[ユーザー] に移動 **します**。
2. ユーザー名の左側をクリックしてユーザーを選択し、[**編集を設定する**] をクリックします。
3. 以下の操作を行います。
    1. [**通話ポリシー**] で、[**DisallowCalling**] をクリックします。
    2. [**会議ポリシー**] で、[**AllOff**] をクリックします。
4. [**適用**] をクリックします。

複数のユーザーに同時にポリシーを割り当てるには、次の操作を行います。

1. Teams 管理センターの左側のナビゲーションで、[ユーザー] に移動し、ユーザーを検索するか、ビューをフィルター処理して、必要なユーザーを表示します。
2. [**&#x2713;** (チェックマーク)] の列からユーザーを選択します。 すべてのユーザーを選択するには、表の上部にある [**&#x2713;** (チェックマーク)] をクリックします。
3. [**設定の編集**] をクリックし、必要な変更を加え、[**適用**] をクリックします。

または、次の操作も実行できます。

1. 管理センターの左側のTeams、割り当てるポリシーに移動します。 次に例を示します。
    - [**音声**]  >  [**通話ポリシー**] の順に移動し、[**DisallowCalling**] をクリックします。
    - [**会議**]  >  [**会議ポリシー**] の順に移動し、[**AllOff**] をクリックします。
2. [**ユーザーを管理する**] を選択します。
3. [**ユーザーを管理する**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] をクリックします。 追加するユーザーごとに、この手順を繰り返します。
4. ユーザーの追加が完了したら、[**保存**] をクリックします。

#### <a name="assign-policies-using-powershell"></a>PowerShell を使用してポリシーを割り当てる

次の例は、 [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) `DisallowCalling` を使用して呼び出し元ポリシーをユーザーに割り当てる方法を示しています。

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

PowerShell を使用して通話ポリシーを管理する方法の詳細については、「[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)」を参照してください。

次の例は、 [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) `AllOff` を使用して会議ポリシーをユーザーに割り当てる方法を示しています。

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

PowerShell を使用して会議ポリシーを管理する方法の詳細については、「[Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)」を参照してください。

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-optimize-teams-with-calling-and-meetings"></a>チャットと共同作業を備えた VDI 上の Teams を移行して、通話と会議を備えた Teams を最適化する

ユーザーレベル ポリシーで通話および会議機能を無効にするように設定したチャットと共同作業を備えた VDI 上の Teams の既存の実装があり、AV 最適化を備えた Teams に移行する場合、VDI 上の Teams ユーザーのために通話および会議機能を有効にするポリシーを設定する必要があります。

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a>通話および会議機能を有効にするポリシーを設定する

管理センターまたは PowerShell Teamsを使用して、通話ポリシーと会議ポリシーを設定してユーザーに割り当てできます。 ポリシーの変更が反映されるまでに時間がかかる場合があります (数時間)。 指定したアカウントの変更がすぐに表示されない場合は、数時間が経過した後にもう一度お試しください。

[**通話ポリシー**](teams-calling-policy.md): Teams の通話ポリシーは、ユーザーが使用できる通話機能を制御します。 Teamsには、すべての呼び出し機能が有効になっている組み込みの **AllowCalling** 呼び出しポリシーが含まれています。 すべての通話機能を有効にする場合は、 **AllowCalling ポリシーを割り当** てる必要があります。 または、カスタム通話ポリシーを作成して、必要な通話機能を有効にし、ユーザーに割り当てます。

[**会議ポリシー**](meeting-policies-overview.md): Teams の会議ポリシーは、ユーザーが作成できる会議の種類と、組織内のユーザーによってスケジュールされた会議参加者が利用できる機能を制御します。 Teamsには、すべての会議機能が有効になっている組み込みの **AllOn** 会議ポリシーが含まれています。 すべての会議機能を有効にする場合は、 **AllOn ポリシーを割り当** てる必要があります。 または、カスタム会議ポリシーを作成して、必要な会議機能を有効にし、ユーザーに割り当てます。

#### <a name="assign-policies-using-the-teams-admin-center"></a>管理センターでポリシーをTeamsする

**AllowCalling 通話ポリシーと** **AllOn 会議** ポリシーをユーザーに割り当てるには:

1. 管理センターの左側のナビゲーションTeams、[ユーザー] に移動 **します**。
2. ユーザー名の左側をクリックしてユーザーを選択し、[**編集を設定する**] をクリックします。
3. 以下の操作を行います。
    1. [**通話ポリシー**] で、[**AllowCalling**] をクリックします。
    2. [**会議ポリシー**] で、[**AllOn**] をクリックします。
4. [**適用**] をクリックします。

複数のユーザーに同時にポリシーを割り当てるには、次の操作を行います。

1. Teams 管理センターの左側のナビゲーションで、[ユーザー] に移動し、ユーザーを検索するか、ビューをフィルター処理して、必要なユーザーを表示します。
2. [**&#x2713;** (チェックマーク)] の列からユーザーを選択します。 すべてのユーザーを選択するには、表の上部にある [**&#x2713;** (チェックマーク)] をクリックします。
3. [**設定の編集**] をクリックし、必要な変更を加え、[**適用**] をクリックします。

または、次の操作も実行できます。

1. 管理センターの左側のTeams、割り当てるポリシーに移動します。 次に例を示します。
    - [**音声**]  >  [**通話ポリシー**] の順に移動し、[**AllowCalling**] をクリックします。
    - [**会議**]  >  [**会議ポリシー**] の順に移動し、[**AllOn**] をクリックします。
2. [**ユーザーを管理する**] を選択します。
3. [**ユーザーを管理する**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] をクリックします。 追加するユーザーごとに、この手順を繰り返します。
4. ユーザーの追加が完了したら、[**保存**] をクリックします。

#### <a name="assign-policies-using-powershell"></a>PowerShell を使用してポリシーを割り当てる

次の例は、 [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) `AllowCalling` を使用して呼び出し元ポリシーをユーザーに割り当てる方法を示しています。

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity "user email id"
```

PowerShell を使用して通話ポリシーを管理する方法の詳細については、「[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)」を参照してください。

次の例は、 [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) `AllOn` を使用して会議ポリシーをユーザーに割り当てる方法を示しています。

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity "user email id"
```

PowerShell を使用して会議ポリシーを管理する方法の詳細については、「[Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)」を参照してください。

## <a name="control-fallback-mode-in-teams"></a>Teams でフォールバック モードを制御する

ユーザーがサポートされていないエンドポイントから接続すると、ユーザーはフォールバック モードになり、AV は最適化されません。 次のいずれかのレジストリ値を設定することで、フォールバック モードを無効または有効 `DWORD` にできます。

- `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback`
- `HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback`

フォールバック モードを無効にするには、値を **1** に設定します。 音声のみを有効にするには、値を **2** に設定します。 値が存在しない場合、または **0** (ゼロ) に設定されている場合は、フォールバック モードが有効になります。

この機能は、バージョン 1.3.00.13565 以降の Teams で使用できます。

## <a name="disable-audio-and-video-settings-for-vdi"></a>VDI のオーディオとビデオの設定を無効にする

Teams VDI ポリシーは、Teams モジュールで使用できます。 これらのポリシーはアクティブであり、最適化されていない VDI 環境に適用されます。

- `New-CsTeamsVdiPolicy`
- `Grant-CsTeamsVdiPolicy`
- `Remove-CsTeamsVdiPolicy`
- `Set-CsTeamsVdiPolicy`

> [!NOTE]
> これは、最適化されていない環境にのみ使用されます。

### <a name="update-a-module-name"></a>モジュール名を更新する

```PowerShell
Update-Module -Name MicrosoftTeams -AllowPrerelease

<# Import and connect to online (CSOnline runs the policies) #>
Import-Module microsoftTeams
if( -not $sess){
    $session = New-CsOnlineSession
    $pss = Import-PSSession $session
}
<# Check out the commands #>
Get-Command -Noun *VDI*
<#
```

### <a name="set-policies-to-limit-calling-features"></a>呼び出し機能を制限するポリシーを設定する

VDI ポリシーが VDI `DisableCallsAndMeetings` 上の仮想マシンに`$true`Teams設定されているユーザーは、次の機能を実行できない場合があります。

- 通話を行います。
- 会議に参加します。
- チャットからの画面共有。

すべての種類の呼び出しを無効にする必要があります。

> [!NOTE]
> これは、最適化されていない環境にのみ使用されます。

```PowerShell
New-CsTeamsVdiPolicy -Identity DisableCallsAndMeetingsTrue -DisableCallsAndMeetings $true -DisableAudioVideoInCallsAndMeetings $false

<# Assign policy #>
$user = 'meganb@jvteams.xyz'
Grant-CsTeamsVdiPolicy -Identity $user -PolicyName DisableCallsAndMeetingsTrue

<# Wait for some time until the policy is applied #>
Get-CSOnlineUser -Identity $user | FL UserPrincipalName, *vdi*

<# Show all policies #>
Get-CsTeamsVdiPolicy | FT Iden*, Disable*
```

VDI ポリシーが VDI `DisableAudioVideoInCallsAndMeetings` にサインインするために設定されているユーザーは`$true`、VDI Teamsにサインインすると、次の条件を実行します。

- チャットから共有を画面に表示できます。
- 会議に参加して画面を共有し、音声を電話に移動できます。
- VDI からのユーザー間の音声通話とビデオ通話を保留にできない。

> [!NOTE]
> これは、最適化されていない環境にのみ使用されます。

```powershell
$PolName = "DisableCallsAndMeetingsAV"

New-CsTeamsVdiPolicy -Identity $PolName -DisableCallsAndMeetings $false -DisableAudioVideoInCallsAndMeetings $true
Grant-CsTeamsVdiPolicy -Identity $user -PolicyName $PolName

<# Wait for some time until the policy is applied #>
Get-CSOnlineUser -identity $user | FL UserPrincipalName, *vdi*

<# Cleanup afterwards #>
$cleanup = $false
if($cleanup){

    "Doing cleanup"

    # De-assign policy from user  
    Grant-CsTeamsVdiPolicy -Identity $user -PolicyName $null
    Get-CSOnlineUser -identity $user | FL UserPrincipalName, *vdi*

    # Remove policies
    Get-CsTeamsVdiPolicy | ?{$_.identity -ne 'Global'} | remove-csTeamsVdiPolicy
}
```

## <a name="known-issues-and-limitations"></a>既知の問題と制限事項

### <a name="client-deployment-installation-and-setup"></a>クライアントの展開、インストール、およびセットアップ

- マシンごとのインストールでは、VDI 上の Teams は、非 VDI Teams のクライアントと同様に自動的に更新されません。 [VDI で Teams デスクトップ アプリをインストールまたは更新する](#install-or-update-the-teams-desktop-app-on-vdi)セクションの説明に従って新しい MSI をインストールし、VM イメージを更新する必要があります。 現在のバージョンをアンインストールして新しいバージョンに更新する必要があります。
- Citrix 環境では、Teams の実行中にユーザーが仮想マシンから切断された場合、Teams の更新により、再接続時にユーザーが AV 用に最適化されていない状態になる可能性があります。 ユーザーは、このシナリオを回避Teams Citrix 仮想マシンから切断する前に、アプリケーションを終了することをお勧めします。
- Teams は、ユーザーごとまたはマシンごとに展開する必要があります。 Teams のユーザーごとおよびマシンごとの同時展開はサポートされていません。 マシンごとまたはユーザーごとからこれらのモードのいずれかに移行するには、アンインストール手順に従っていずれかのモードに再展開します。
- 現時点では、Azure Virtual Desktop は macOS および Linux ベースのクライアントをサポートしません。
- テナントの高速切り替えにより、画面共有が利用できないなど、VDI で呼び出し関連の問題が発生する可能性があります。 クライアントを再起動すると、これらの問題が軽減されます。

### <a name="calling-and-meetings"></a>通話と会議

次の通話および会議機能はサポートされていません。

- 新しい会議エクスペリエンスなどのマルチウィンドウ機能、または新しい会議エクスペリエンスに付属する機能
- 拡張緊急サービス
- Teams アプリとデバイス間の HID ボタンと LED コントロール
- 背景のぼかしと効果
- ブロードキャストとライブ イベントのプロデューサーと発表者の役割
- 場所に基づくルーティング (LBR)
- PSTN 通話呼び出しの呼び出し音
- 共有システムのオーディオ/コンピューターのサウンド
- ダイレクト ルーティングのメディア バイパス
- ズーム コントロール

> [!NOTE]
> 現在は非 VDI 環境でのみ利用可能な通話および会議機能の追加に取り組んでいます。 これらには、品質についての管理者制御の強化、画面共有シナリオの追加、および最近 Teams に追加された高度な機能が含まれる可能性があります。 今後の機能の詳細については、Teams の担当者にお問い合わせください。

通話と会議に関する既知の問題と制限事項を次に示します。

- Skype for Business との相互運用性は、音声通話に限定されます。ビデオ モダリティはありません。
- 受信および送信ビデオ ストリームの解像度は、720p に制限されています。
- 受信カメラまたは画面共有ストリームからの 1 つのビデオ ストリームのみがサポートされます。 受信画面共有がある場合、主要な発表者のビデオではなく、その画面共有が表示されます。
- デバイスが切断されて再接続された場合、ユーザーが最後に選択したオーディオ デバイスが使用されるように切り替えられません。
- ライブ イベントは最適化されません。
- 送信画面の共有:
  - アプリケーションの共有はサポートされていません。
- 制御の受け渡し:
  - 画面共有またはアプリケーション共有セッション中はサポートされていません。
  - PowerPoint 共有セッション中はサポートされます。

VDI に関連しない Teams の既知の問題については、「[組織で Teams をサポートする](/MicrosoftTeams/troubleshoot/teams-welcome)」を参照してください。

## <a name="troubleshooting"></a>トラブルシューティング

### <a name="troubleshoot-citrix-components"></a>Citrix コンポーネントのトラブルシューティング

#### <a name="teams-crashes-or-the-teams-sign-in-screen-is-blank"></a>Teams がクラッシュする、または Teams のサインイン画面が空白になる

これは、Citrix VDA バージョン 1906 および 1909 の既知の問題です。 この問題を回避するには、次のレジストリ値を追加 `DWORD` し、(16 進数) `204` に設定します。

```console

HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe

```

次に、VDA を再起動します。 詳細については、Citrix のサポートに関する記事「HDX の最適化のトラブルシューティング[」を参照Microsoft Teams](https://support.citrix.com/article/CTX253754)。

## <a name="related-topics"></a>関連トピック

- [Teams インストーラー (MSI) をWindows一括インストールする](msi-deployment.md)
- [Teams での PowerShell の概要](teams-powershell-overview.md)
- [Azure Virtual Desktop Microsoft Teamsを使用する](/azure/virtual-desktop/teams-on-wvd)
