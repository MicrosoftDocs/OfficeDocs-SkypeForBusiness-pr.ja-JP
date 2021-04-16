---
title: 仮想デスクトップ インフラストラクチャ用の Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jmorrow
audience: admin
description: 仮想デスクトップ インフラストラクチャ (VDI) 環境で Microsoft Teams を実行する方法について説明します。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9688b700d900720aa9af1c0f68cadee99d7de858
ms.sourcegitcommit: 2ce82f301f2d59da57f579a23038b2cab5e31360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2021
ms.locfileid: "51858050"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>仮想デスクトップ インフラストラクチャ用の Teams

この記事では、仮想化環境で Microsoft Teams を使用する場合の要件と制限について説明します。

## <a name="what-is-vdi"></a>VDI とは何ですか ?

仮想デスクトップ インフラストラクチャ (VDI) は、データセンターの集中サーバーでデスクトップ オペレーティング システムとアプリケーションをホストする仮想化テクノロジです。 これにより、完全に保護され、準拠し一元化されたソースとともに、ユーザーに完全に個人用に設定されたデスクトップ エクスペリエンスを提供します。

仮想化環境の Microsoft Teams はチャットと共同作業をサポートします。 また、Citrix、VMware プラットフォームを使用すれば、通話および会議機能もサポートされます。

仮想化環境の Teams は、複数の構成をサポートします。 これらには、VDI、専用、共有、永続、非永続のモードが含まれます。 機能は継続的に開発されており、定期的に追加されます。今後数か月または数年で機能が拡張されます。

仮想化環境での Teams の使用は、非仮想化環境での Teams の使用とは多少異なる場合があります。 たとえば、仮想化環境では一部の高度な機能が利用できない可能性があり、ビデオ解像度が異なる場合があります。

最適なユーザー エクスペリエンスを確保するには、この記事のガイダンスに従ってください。

> [!Note]
> 別のプラットフォームでの Teams VDI に関する詳細は、「[プラットフォームごとの Teams の機能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)」を参照してください。

## <a name="teams-on-vdi-components"></a>VDI 上の Teams のコンポーネント

仮想化環境で Teams を使用するには、次のコンポーネントが必要です。

- **仮想化ブローカー**: Azure などの仮想化プロバイダーへのリソースおよび接続マネージャー
- **仮想デスクトップ**: Microsoft Teams を実行する仮想マシン (VM) スタック
- **シン クライアント**: ユーザーが物理的にやり取りするエンドポイント
- **Teams デスクトップ アプリ**: Teams デスクトップ クライアント アプリ

## <a name="teams-on-vdi-requirements"></a>VDI 上の Teams の要件

### <a name="virtualization-provider-requirements"></a>仮想化プロバイダーの要件

Teams デスクトップ アプリは、主要な仮想化ソリューション プロバイダーで検証済みです。 複数の市場プロバイダーを使用している場合は、仮想化ソリューション プロバイダーに相談して、最小要件が満たされていることを確認することをお勧めします。
  
現在、音声/ビデオ (AV) 最適化を備えた VDI 上の Teams は、Windows Virtual Desktop、Citrix、VMware で認定されています。 このセクションの情報を確認して、適切に機能するためのすべての要件を満たしていることを確認してください。

### <a name="platforms-certified-for-teams"></a>Teams 認定プラットフォーム

次のプラットフォームには、Teams 用の仮想デスクトップ インフラストラクチャ ソリューションがあります。

|プラットフォーム|ソリューション|
|----|---|
|![Microsoft を表すロゴ](media/microsoft-logo.png)| <a href="/azure/virtual-desktop/teams-on-wvd" target="_blank">Windows Virtual Desktop</a> |
|![Citrix を表すロゴ](media/citrix-logo.png)| <a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix Virtual Apps and Desktops</a> |
|![VMware を表すロゴ](media/vmware-logo.png)| <a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware Horizon</a> |

### <a name="windows-virtual-desktop"></a>Windows Virtual Desktop

Windows Virtual Desktop は、VDI 上の Teams に AV 最適化を提供します。 詳細、要件およびインストールについては、「[Windows Virtual Desktop で Microsoft Teams を使用する](/azure/virtual-desktop/teams-on-wvd)」を参照してください。

### <a name="citrix-virtual-apps-and-desktops-requirements"></a>Citrix Virtual Apps and Desktops の要件

Citrix Virtual Apps and Desktops (以前の XenApp および XenDesktop) は、VDI 上の Teams に AV 最適化を提供します。 Citrix Virtual Apps and Desktops を使用すると、VDI 上の Teams はチャットと共同作業に加えて、通話および会議機能をサポートします。

Citrix Virtual Apps and Desktops の最新バージョンは、[Citrix ダウンロード サイト](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/)からダウンロードできます。 (最初にサインインする必要があります。) 必要なコンポーネントは、デフォルトで [Citrix Workspace アプリ (CWA)](https://www.citrix.com/downloads/workspace-app/) および Virtual Delivery Agent (VDA) にバンドルされています。 CWA や VDA に追加のコンポーネントやプラグインをインストールする必要はありません。

サーバーおよびクライアントの最新の要件については、[この Citrix Web サイト](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)を参照してください。

### <a name="vmware-horizon-workspace-and-desktop-requirements"></a>VMware Horizon Workspace and Desktop の要件

VMware Horizon は、ハイブリッド クラウド全体に仮想デスクトップとアプリを安全に配信するためのモダン プラットフォームです。 優れたエンドユーザー エクスペリエンスを提供するために、VMware Horizon は Teams のメディア最適化を提供します。 この最適化により、仮想デスクトップやアプリ全体の総体的な生産性が向上し、Teams を使用して通話や会議を行う際のユーザー エクスペリエンスが向上します。

VMware Horizon の最新バージョンは、[VMware ダウンロード](https://my.vmware.com/web/vmware/downloads/#all_products) ページからダウンロードできます。 既定では、必要なメディア最適化コンポーネントは Horizon Agent と Horizon Client に含まれているため、Teams の最適化機能を使用するために追加のプラグインをインストールする必要はありません。

Teams のメディア最適化を構成する方法に関する最新の要件と手順を入手するには、[こちらの VMware Web サイト](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html)をご覧ください。

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a>VDI で Teams デスクトップ アプリをインストールまたは更新する

MSI パッケージを使用したマシンごとのインストールまたはユーザーごとのインストールを用いて、VDI 用の Teams デスクトップ アプリを展開できます。 どのアプローチを使用するかについては、永続的なセットアップを使用するか、または非永続的なセットアップを使用するか、および組織の関連機能のニーズに応じて決定します。

専用の永続的なセットアップの場合、どちらのアプローチでも機能します。 ただし、非永続的なセットアップの場合、Teams が効率的に機能するにはマシンごとにインストールする必要があります。 [非永続のセットアップ](#non-persistent-setup)のセクションを参照してください。

マシンごとのインストールでは、自動更新は無効になっています。 つまり、Teams アプリを更新するには、現在のバージョンをアンインストールして新しいバージョンに更新する必要があります。 ユーザーごとのインストールでは、自動更新は有効になっています。 ほとんどの VDI の展開について、マシンごとのインストールを使用して Teams を展開することをお勧めします。

最新の Teams バージョンに更新するには、アンインストール手順から始めて、次に最新の Teams バージョンを展開します。

VDI 環境での Teams AV の最適化が適切に機能するには、シン クライアント エンドポイントがインターネットにアクセスできる必要があります。 シン クライアント エンドポイントでインターネット アクセスが利用できない場合、最適化のスタートアップは成功しません。 これは、ユーザーが最適化されていないメディア状態にあることを意味します。

#### <a name="dedicated-persistent-setup"></a>専用の永続的なセットアップ

専用の永続的なセットアップでは、ユーザーのローカル オペレーティング システムの変更は、ユーザーがログオフした後も保持されます。 永続的なセットアップの場合、Teams はユーザーごとのインストールとマシンごとのインストールの両方をサポートします。

推奨される最低限の VM 構成は次のとおりです。

|パラメーター  |ワークステーションのオペレーティング システム  |サーバー オペレーティング システム  |
|---------|---------|---------|
|vCPU   |    2 コア     |  4、6、または 8。<br>基礎となる Non-Uniform Memory Access (NUMA) 構成を理解し、それに応じて VM を構成することが重要です。     |
|RAM     |   4 GB      | ユーザー 1 人あたり 512 から 1024 MB        |
|ストレージ    | 8 GB        | 40 から 60 GB        |

#### <a name="non-persistent-setup"></a>非永続的なセットアップ

非永続的なセットアップでは、ユーザーのローカル オペレーティング システムの変更は、ユーザーがログオフした後は保持されません。 このようなセットアップは、一般的に共有マルチユーザー セッションです。 VM 構成は、ユーザー数と使用可能な物理ボックス リソースによって異なります。

非永続的なセットアップの場合、Teams デスクトップ アプリは、ゴールデン イメージに対してマシンごとにインストールする必要があります。 (詳細に関しては、[VDI での Teams デスクトップ アプリのインストールまたは更新](#install-or-update-the-teams-desktop-app-on-vdi)セクションを参照してください) これにより、Teams アプリがユーザー セッション中でも効率的に起動できるようになります。

非永続的なセットアップで Teams を使用するには、効率的なTeamsランタイムデータ同期のために、プロファイル キャッシュ マネージャーも必要です。 効率的なデータ同期により、適切なユーザー固有の情報 (ユーザーのデータ、プロファイル、設定など) がユーザーのセッション中にキャッシュされます。 以下の 2 つのフォルダーのデータが同期されていることを確認してください。<br>
- C:\Users\username\AppData\Local\Microsoft\IdentityCache (%localAppdata%\Microsoft\IdentityCache)
- C:\Users\username\AppData\Roaming\Microsoft\Teams (%appdata%\Microsoft\Teams)

> [!NOTE]
> Teams アプリがアプリケーションの実行に必要なランタイム データとファイルを確実に取得するには、ローミング フォルダー (またはフォルダー リダイレクトを使用している場合はキャッシュ マネージャー) が必要です。 これは、ネットワーク遅延の問題やネットワークの不具合を軽減するために必要です。それを行わない場合、データやファイルが利用できないことにより、アプリケーション エラーが発生し、動作が遅くなります。

さまざまなキャッシュ マネージャー ソリューションが利用可能です。 たとえば、[FSLogix](/fslogix/overview) があります。 具体的な構成手順については、キャッシュ マネージャー プロバイダーに問い合わせてください。

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a>Teams は、非永続的なセットアップ用のコンテンツ除外リストをキャッシュしました

Teams キャッシュ フォルダー %appdata%/Microsoft/Teams から以下を除外します。 これらのアイテムを除外すると、ユーザーのキャッシュ サイズが小さくなり、非永続的なセットアップがさらに最適化されます。

- .txt ファイル
- メディアスタック フォルダー
- meeting-addin\Cache (%appdata%\Microsoft\Teams\meeting-addin\Cache)

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

Teams と Microsoft 365 Apps for enterprise の詳細については、「[Microsoft 365 Apps for enterprise の新規インストールから Teams を除外する方法](/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus)」と「[グループ ポリシーを使用して Teams のインストールを制御する](/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams)」を参照してください。

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a>Teams デスクトップ アプリを VM に展開する

1. 次のリンクのいずれかを使用して、VDI VM オペレーティング システムに一致する Teams MSI パッケージをダウンロードします。

    - [32 ビット版](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)
    - [64 ビット版](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)

    > [!NOTE]
    > 政府機関向けクラウドの場合、MSI ファイルのダウンロード リンクについては、「[Microsoft Endpoint Configuration Manager を使用して Microsoft Teams をインストールする](msi-deployment.md)」を参照してください。

    必要な Teams デスクトップ アプリの最小バージョンは、バージョン 1.3.00.4461 です。 (PSTN ホールドは以前のバージョンではサポートされていません。)

2. 次のいずれかのコマンドを実行して、MSI を VDI VM にインストールします。

    - ユーザーごとのインストール (既定)
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        このプロセスは既定のインストールで、Teams は %AppData% ユーザー フォルダーにインストールされます。 この時点で、ゴールデン イメージのセットアップは完了です。 非永続的なセットアップでのユーザーごとのインストールでは、Teams は適切に動作しません。

    - マシンごとのインストール

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        このプロセスでは、Teams は 64 ビット オペレーティング システムの Program Files (x86) フォルダー、および 32 ビット オペレーティング システム の Program Files フォルダーにインストールされます。 この時点で、ゴールデン イメージのセットアップは完了です。 非永続的なセットアップについては、マシンごとに Teams をインストールする必要があります。

        次の対話型ログオン セッションは、Teams を開始し、資格情報を要求します。

        > [!NOTE]
        > これらの例でも **ALLUSERS=1** パラメーターを使用します。 このパラメーターを設定すると、コンピューターのすべてのユーザーの [コントロール パネル] の [プログラムと機能] および [Windows の設定] の [アプリと機能] に Teams Machine-Wide Installer が表示されます。 管理者の資格情報を持っている場合は、すべてのユーザーが Teams をアンインストールできます。
        **ALLUSERS=1** と **ALLUSER=1** の違いを理解することが重要です。 **ALLUSERS=1** パラメーターは、非 VDI 環境および VDI 環境の両方で使用できますが、**ALLUSER=1** パラメーターは、VDI 環境でのみマシンごとのインストールを指定するために使用されます。

3. VDI VM から MSI をアンインストールします。 Teams をアンインストールする方法は 2 つあります。

    - PowerShell スクリプト: [この PowerShell スクリプト](scripts/powershell-script-deployment-cleanup.md)を使用して、Teams をアンインストールしてユーザーの Teams フォルダーを削除できます。 Teams がコンピューターにインストールされているユーザー プロファイルごとにスクリプトを実行します。
    - コマンド ライン: 次のコマンドを実行します。
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```

      このプロセスでは、オペレーティング システムの環境に応じて、Program Files (x86) フォルダーまたは Program Files フォルダーから Teams がアンインストールされます。

## <a name="teams-on-vdi-performance-considerations"></a>VDI 上の Teams のパフォーマンスに関する考慮事項

さまざまな仮想化セットアップ構成があり、それぞれ最適化の焦点が異なります。 たとえば、ある構成ではユーザー密度に焦点が当てられます。 計画するときは、組織のワークロードのニーズに基づいてセットアップを最適化するために、以下を考慮してください。

- 最小要件: 一部のワークロードでは、最小要件を超えるリソースを使用したセットアップが必要になる場合があります。 たとえば、より多くのコンピューティング リソースを必要とするアプリケーションを使用する開発者向けのワークロード。
- 依存関係: インフラストラクチャ、ワークロード、および Teams デスクトップ アプリ以外の環境に関するその他の考慮事項への依存関係が含まれます。
- VDI の無効な機能: Teams は、VDI の GPU 負荷集中型機能を無効にします。これは、一時的な CPU 使用率の改善に役立ちます。 以下の機能は無効です。
    - Teams CSS アニメーション
    - Giphy の自動起動

## <a name="teams-on-vdi-with-calling-and-meetings"></a>通話と会議を含む VDI 上の Teams

チャットと共同作業に加えて、通話と会議のサポートを備えた VDI 上の Teams は、サポートされている仮想化プロバイダーのプラットフォームで利用できます。 サポートされる機能は、WebRTC メディア スタックおよび仮想化プロバイダーの実装に基づいています。 次の図では、このアーキテクチャの概要を説明します。

![VDI アーキテクチャ上の Teams を示す図](media/teams-on-vdi-architecture.png)

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

- 音声とビデオのストリーミング エクスペリエンスが最適にならない場合があります。 遅延や品質低下が発生する場合があります。
- デバイス設定は、ブラウザーの設定では使用できません。
- デバイス管理はブラウザーを介して処理され、ブラウザー サイト設定で複数の設定が必要です。
- デバイス設定は、Windows デバイス管理でも設定する必要がある場合があります。

## <a name="teams-on-vdi-with-chat-and-collaboration"></a>チャットと共同作業を備えた VDI 上の Teams

組織で Teams のチャットおよび共同作業機能のみを使用する場合は、ユーザーレベル ポリシーを設定して、Teams の通話および会議機能を無効にすることができます。 

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>通話および会議機能を無効にするポリシーを設定する

Microsoft Teams 管理センターまたは PowerShell を使用してポリシーを設定できます。 ポリシーの変更が反映されるまでに時間がかかる場合があります (数時間)。 指定したアカウントの変更がすぐに表示されない場合は、数時間後にもう一度お試しください。

[**通話ポリシー**](teams-calling-policy.md): Teams には、すべての通話機能が無効になっている組み込みの DisallowCalling 通話ポリシーが含まれています。 DisallowCalling ポリシーを、仮想化環境で Teams を使用する組織内のすべてのユーザーに割り当てます。

[**会議ポリシー**](meeting-policies-in-teams.md): Teams には、すべての会議機能が無効になっている組み込みの AllOff 会議ポリシーが含まれています。 AllOff ポリシーを、仮想化環境で Teams を使用する組織内のすべてのユーザーに割り当てます。

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターを使用してポリシーを割り当てる

DisallowCalling 通話ポリシーと AllOff 会議ポリシーをユーザーに割り当てるには、以下を実行します。

1. Microsoft Teams 管理センターの左側のナビゲーションで、[**ユーザー**] に移動します。
2. ユーザー名の左側をクリックしてユーザーを選択し、[**編集を設定する**] をクリックします。
3. 以下の操作を行います。
    1.  [**通話ポリシー**] で、[**DisallowCalling**] をクリックします。
    2.  [**会議ポリシー**] で、[**AllOff**] をクリックします。
4. [**適用**] をクリックします。

複数のユーザーに同時にポリシーを割り当てるには、次の操作を行います。

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動し、ユーザーを検索するか、表示にフィルターを適用してユーザーを表示します。
2. [**&#x2713;** (チェックマーク)] の列からユーザーを選択します。 すべてのユーザーを選択するには、表の上部にある [&#x2713; (チェックマーク)] をクリックします。
3. [**設定の編集**] をクリックし、必要な変更を行い、[**適用**] をクリックします。

または、次の操作も実行できます。

1. Microsoft Teams 管理センターの左側のナビゲーションで、割り当てるポリシーに移動します。 次に例を示します。
    - [**音声**]  >  [**通話ポリシー**] の順に移動し、[**DisallowCalling**] をクリックします。
    - [**会議**]  >  [**会議ポリシー**] の順に移動し、[**AllOff**] をクリックします。
2. [**ユーザーを管理する**] を選択します。
3. [**ユーザーを管理する**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] をクリックします。 追加するユーザーごとに、この手順を繰り返します。
4. ユーザーの追加が完了したら、[**保存**] をクリックします。

#### <a name="assign-policies-using-powershell"></a>PowerShell を使用してポリシーを割り当てる

次の例は、[Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) を使用して、DisallowCalling 通話ポリシーをユーザーに割り当てる方法を示しています。

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

PowerShell を使用して通話ポリシーを管理する方法の詳細については、「[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)」を参照してください。

次の例は、[Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) を使用して、AllOff 会議ポリシーをユーザーに割り当てる方法を示しています。

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

PowerShell を使用して会議ポリシーを管理する方法の詳細については、「[Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)」を参照してください。

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-optimize-teams-with-calling-and-meetings"></a>チャットと共同作業を備えた VDI 上の Teams を移行して、通話と会議を備えた Teams を最適化する

ユーザーレベル ポリシーで通話および会議機能を無効にするように設定したチャットと共同作業を備えた VDI 上の Teams の既存の実装があり、AV 最適化を備えた Teams に移行する場合、VDI 上の Teams ユーザーのために通話および会議機能を有効にするポリシーを設定する必要があります。

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a>通話および会議機能を有効にするポリシーを設定する

Microsoft Teams 管理センターまたは PowerShell を使用して、通話および会議ポリシーを設定し、ユーザーに割り当てることができます。 ポリシーの変更が反映されるまでに時間がかかる場合があります (数時間)。 指定したアカウントの変更がすぐに表示されない場合は、数時間が経過した後にもう一度お試しください。

[**通話ポリシー**](teams-calling-policy.md): Teams の通話ポリシーは、ユーザーが使用できる通話機能を制御します。 Teams には、すべての通話機能が有効になっている組み込みの AallowCalling 通話ポリシーが含まれています。 すべての通話機能を有効にするには、AllowCalling ポリシーを割り当てます。 または、カスタム通話ポリシーを作成して、必要な通話機能を有効にし、ユーザーに割り当てます。 

[**会議ポリシー**](meeting-policies-in-teams.md): Teams の会議ポリシーは、ユーザーが作成できる会議の種類と、組織内のユーザーによってスケジュールされた会議参加者が利用できる機能を制御します。 Teams には、すべての会議機能が有効になっている組み込みの AllOn 会議ポリシーが含まれています。 すべての会議機能を有効にするには、AllOn ポリシーを割り当てます。 または、カスタム会議ポリシーを作成して、必要な会議機能を有効にし、ユーザーに割り当てます。

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターを使用してポリシーを割り当てる

AllowCalling 通話ポリシーと AllOn 会議ポリシーをユーザーに割り当てるには、以下を実行します。

1. Microsoft Teams 管理センターの左側のナビゲーションで、[**ユーザー**] に移動します。
2. ユーザー名の左側をクリックしてユーザーを選択し、[**編集を設定する**] をクリックします。
3. 以下の操作を行います。
    1.  [**通話ポリシー**] で、[**AllowCalling**] をクリックします。
    2.  [**会議ポリシー**] で、[**AllOn**] をクリックします。
4. [**適用**] をクリックします。

複数のユーザーに同時にポリシーを割り当てるには、次の操作を行います。

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動し、ユーザーを検索するか、表示にフィルターを適用してユーザーを表示します。
2. [**&#x2713;** (チェックマーク)] の列からユーザーを選択します。 すべてのユーザーを選択するには、表の上部にある [**&#x2713;** (チェックマーク)] をクリックします。
3. [**設定の編集**] をクリックし、必要な変更を加え、[**適用**] をクリックします。

または、次の操作も実行できます。

1. Microsoft Teams 管理センターの左側のナビゲーションで、割り当てるポリシーに移動します。 次に例を示します。
    - [**音声**]  >  [**通話ポリシー**] の順に移動し、[**AllowCalling**] をクリックします。
    - [**会議**]  >  [**会議ポリシー**] の順に移動し、[**AllOn**] をクリックします。
2. [**ユーザーを管理する**] を選択します。
3. [**ユーザーを管理する**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] をクリックします。 追加するユーザーごとに、この手順を繰り返します。
4. ユーザーの追加が完了したら、[**保存**] をクリックします。

#### <a name="assign-policies-using-powershell"></a>PowerShell を使用してポリシーを割り当てる

次の例は、[Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) を使用して、AllowCalling 通話ポリシーをユーザーに割り当てる方法を示しています。

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity "user email id"
```

PowerShell を使用して通話ポリシーを管理する方法の詳細については、「[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)」を参照してください。

次の例は、[Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) を使用して、AllOn 会議ポリシーをユーザーに割り当てる方法を示しています。

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity "user email id"
```

PowerShell を使用して会議ポリシーを管理する方法の詳細については、「[Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)」を参照してください。

## <a name="control-fallback-mode-in-teams"></a>Teams でフォールバック モードを制御する

ユーザーがサポートされていないエンドポイントから接続すると、ユーザーはフォールバック モードになり、AV は最適化されません。 次のレジストリ DWORD 値のいずれかを設定して、フォールバック モードを無効または有効にできます。

- HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback
- HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback

フォールバック モードを無効にするには、値を **1** に設定します。 音声のみを有効にするには、値を **2** に設定します。 値が存在しない場合、または **0** (ゼロ) に設定されている場合は、フォールバック モードが有効になります。

この機能は、バージョン 1.3.00.13565 以降の Teams で使用できます。

## <a name="known-issues-and-limitations"></a>既知の問題と制限事項

### <a name="client-deployment-installation-and-setup"></a>クライアントの展開、インストール、およびセットアップ

- マシンごとのインストールでは、VDI 上の Teams は、非 VDI Teams のクライアントと同様に自動的に更新されません。 [VDI で Teams デスクトップ アプリをインストールまたは更新する](#install-or-update-the-teams-desktop-app-on-vdi)セクションの説明に従って新しい MSI をインストールし、VM イメージを更新する必要があります。 現在のバージョンをアンインストールして新しいバージョンに更新する必要があります。
- Citrix 環境では、Teams の実行中にユーザーが仮想マシンから切断した場合、Teams の更新により、再接続時にユーザーが AV 用に最適化されていない状態になる可能性があります。 このシナリオを回避するには、ユーザーが Citrix Virtual Machine から切断する前に Teams を終了することをお勧めします。
- Teams は、ユーザーごとまたはマシンごとに展開する必要があります。 Teams のユーザーごとおよびマシンごとの同時展開はサポートされていません。 マシンごとまたはユーザーごとからこれらのモードのいずれかに移行するには、アンインストール手順に従っていずれかのモードに再展開します。
- 現時点では、Windows Virtual Desktop と VMware は、MacOS と Linux ベースのクライアントをサポートしていません。

### <a name="calling-and-meetings"></a>通話と会議

次の通話および会議機能はサポートされていません。

- 新しい会議エクスペリエンスなどのマルチウィンドウ機能、または新しい会議エクスペリエンスに付属する機能
- 拡張緊急サービス
- Teams アプリとデバイス間の HID ボタンと LED コントロール
- 背景のぼかしと効果
- ブロードキャストとライブ イベントのプロデューサーと発表者の役割
- 場所に基づくルーティング (LBR)
- コール パーク
- コール キュー
- 共有システムのオーディオ/コンピューターのサウンド
- ダイレクト ルーティングのメディア バイパス
- 共有コンテンツを拡大する

> [!NOTE]
> 現在は非 VDI 環境でのみ利用可能な通話および会議機能の追加に取り組んでいます。 これらには、品質についての管理者制御の強化、画面共有シナリオの追加、および最近 Teams に追加された高度な機能が含まれる可能性があります。 今後の機能の詳細については、Teams の担当者にお問い合わせください。

通話と会議に関する既知の問題と制限事項を次に示します。

- Skype for Business との相互運用性は、音声通話に限定されます。ビデオ モダリティはありません。
- 会議またはグループ通話では、単一の着信ビデオ ストリームのみがサポートされます。 複数のユーザーがビデオを送信する場合、常に主要な発表者のビデオのみが表示されます。
- 受信および送信ビデオ ストリームの解像度は、720p に制限されています。 これは WebRTC の制限です。
- 受信カメラまたは画面共有ストリームからの 1 つのビデオ ストリームのみがサポートされます。 受信画面共有がある場合、主要な発表者のビデオではなく、その画面共有が表示されます。
- デバイスが切断されて再接続された場合、ユーザーが最後に選択したオーディオ デバイスが使用されるように切り替えられません。
- 送信画面の共有:
    - アプリケーションの共有はサポートされていません。
- 制御の受け渡し:
    - 画面共有またはアプリケーション共有セッション中はサポートされていません。
    - PowerPoint 共有セッション中はサポートされます。
- Citrix 限定の制限事項
    - マルチモニター設定での画面共有の場合、メイン モニターのみ共有されます。
    - CWA での高 DPI スケーリングはサポートされていません。

VDI に関連しない Teams の既知の問題については、「[組織で Teams をサポートする](/MicrosoftTeams/troubleshoot/teams-welcome)」を参照してください。

## <a name="troubleshooting"></a>トラブルシューティング

### <a name="troubleshoot-citrix-components"></a>Citrix コンポーネントのトラブルシューティング

#### <a name="teams-crashes-or-the-teams-sign-in-screen-is-blank"></a>Teams がクラッシュする、または Teams のサインイン画面が空白になる

これは、Citrix VDA バージョン 1906 および 1909 の既知の問題です。 この問題を回避するには、次のレジストリ DWORD 値を追加し、204 (16 進数) に設定します。

HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe

次に、VDA を再起動します。 詳細については、この Citrix サポート記事「[Teams の HDX 最適化のトラブルシューティング](https://support.citrix.com/article/CTX253754)」を参照してください。

## <a name="related-topics"></a>関連項目

- [MSI を使用して Microsoft Teams をインストールする](msi-deployment.md)
- [Teams での PowerShell の概要](teams-powershell-overview.md)
- [Windows Virtual Desktop で Microsoft Teams を使用する](/azure/virtual-desktop/teams-on-wvd)
