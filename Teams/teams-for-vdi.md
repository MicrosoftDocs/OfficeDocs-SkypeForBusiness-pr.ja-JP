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
ms.openlocfilehash: 52c3a4fd1f8ce3871874468590662f223520dc07
ms.sourcegitcommit: 9787b84ab15ee2e14890151e966c81b4a4d43e62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/14/2021
ms.locfileid: "49868352"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>仮想デスクトップ インフラストラクチャ用の Teams

この記事では、仮想化環境で Microsoft Teams を使用する場合の要件と制限について説明します。

## <a name="what-is-vdi"></a>VDI とは何ですか ?

仮想デスクトップ インフラストラクチャ (VDI) は、データセンターの集中サーバーでデスクトップ オペレーティング システムとアプリケーションをホストする仮想化テクノロジです。 これにより、完全に保護され、準拠し一元化されたソースとともに、ユーザーに完全に個人用に設定されたデスクトップ エクスペリエンスを提供します。

仮想化された環境の Microsoft Teams は、チャットとコラボレーションをサポートします。 また、Windows Virtual Desktop、Citrix、V Desktop プラットフォームでは、呼び出しと会議の機能もサポートされています。

仮想化環境の Teams は、複数の構成をサポートしています。 VDI、専用モード、共有モード、永続的モード、非永続的モードがあります。 機能は継続的に開発され、定期的に追加されます。機能は今後数か月または数年で拡張されます。

仮想化された環境での Teams の使用は、仮想化されていない環境での Teams の使用と多少異なる場合があります。 たとえば、仮想化された環境では一部の高度な機能を利用できない場合や、ビデオの解像度が異なる場合があります。

最適なユーザー エクスペリエンスを確保するには、この記事のガイダンスに従ってください。

> [!Note]
> さまざまなプラットフォームでの Teams VDI の詳細については、プラットフォーム別 [の Teams の機能を参照してください](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。

## <a name="teams-on-vdi-components"></a>VDI 上の Teams のコンポーネント

仮想化環境で Teams を使用するには、次のコンポーネントが必要です。

- **仮想化ブローカー**: Azure などの仮想化プロバイダーへのリソースおよび接続マネージャー
- **仮想デスクトップ**: Microsoft Teams を実行する仮想マシン (VM) スタック
- **シン クライアント**: ユーザーが物理的にやり取りするエンドポイント
- **Teams デスクトップ アプリ**: Teams デスクトップ クライアント アプリ

## <a name="teams-on-vdi-requirements"></a>VDI 上の Teams の要件

### <a name="virtualization-provider-requirements"></a>仮想化プロバイダーの要件

Teams デスクトップ アプリは、主要な仮想化ソリューション プロバイダーで検証済みです。 複数の市場プロバイダーでは、仮想化ソリューション プロバイダーに問い合わせて、最低限の要件を満たしていることを確認することをお勧めします。
  
現在、オーディオ/ビデオ (AV) を使用した VDI 上の Teams の最適化は、Windows Virtual Desktop、Citrix、VMware で認定されています。 このセクションの情報を確認して、適切な機能のすべての要件を満たしていることを確認します。

### <a name="platforms-certified-for-teams"></a>Teams 向け認定プラットフォーム

次のプラットフォームには、Teams 用の仮想デスクトップ インフラストラクチャ ソリューションがあります。

|プラットフォーム|解決方法|
|----|---|
|![Microsoft を表すロゴ](media/microsoft-logo.png)| <a href="https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd" target="_blank">Windows 仮想デスクトップ</a> |
|![Citrix を表すロゴ](media/citrix-logo.png)| <a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix Virtual Apps and Desktops</a> |
|![VMware を表すロゴ](media/vmware-logo.png)| <a href="https://www.vmware.com/products/horizon.html" target="_blank">Vの水平線</a> |

### <a name="windows-virtual-desktop"></a>Windows 仮想デスクトップ

Windows Virtual Desktop は、VDI 上の Teams の AV 最適化を提供します。 詳細と要件とインストールについては、「Windows 仮想デスクトップで Teams を使用する [」を参照してください](https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd)。

### <a name="citrix-virtual-apps-and-desktops-requirements"></a>Citrix Virtual Apps and Desktops の要件

Citrix Virtual Apps and Desktops (以前の XenApp および XenDesktop) は、VDI 上の Teams に AV 最適化を提供します。 Citrix Virtual Apps and Desktops を使用すると、VDI 上の Teams はチャットと共同作業に加えて、通話および会議機能をサポートします。

Citrix 仮想アプリとデスクトップの最新バージョンは、Citrix のダウンロード [サイトからダウンロードできます](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/)。 (最初にサインインする必要があります。) 必要なコンポーネントは、デフォルトで [Citrix Workspace アプリ (CWA)](https://www.citrix.com/downloads/workspace-app/) および Virtual Delivery Agent (VDA) にバンドルされています。 CWA や VDA に追加のコンポーネントやプラグインをインストールする必要はありません。

サーバーおよびクライアントの最新の要件については、[この Citrix Web サイト](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)を参照してください。

### <a name="vmware-horizon-workspace-and-desktop-requirements"></a>V Desktop の水平線ワークスペースとデスクトップの要件

V Horizon は、ハイブリッド クラウド全体で仮想デスクトップとアプリを安全に配信するための最新のプラットフォームです。 優れたエンド ユーザー エクスペリエンスを提供するために、VMware Horizon は Teams のメディア最適化を提供します。 この最適化により、仮想デスクトップやアプリ全体の全体的な生産性が向上し、Teams を使用して通話や会議を行う際のユーザー エクスペリエンスが向上します。

VMware Horizon の最新バージョンは [、V客様の [ダウンロード] ページからダウンロード](https://my.vmware.com/web/vmware/downloads/#all_products) できます。 既定では、必要なメディア最適化コンポーネントは水平線エージェントと水平線クライアントの一部であり、Teams の最適化機能を使用するために追加のプラグインをインストールする必要はありません。

Teams のメディア最適化を構成する方法に関する最新の要件と手順を取得するには、この VMware Web [サイトを参照してください](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html)。

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a>VDI で Teams デスクトップ アプリをインストールまたは更新する

MSI パッケージを使用したマシンごとのインストールまたはユーザーごとのインストールを用いて、VDI 用の Teams デスクトップ アプリを展開できます。 どのアプローチを使用するかについては、永続的なセットアップを使用するか、または非永続的なセットアップを使用するか、および組織の関連機能のニーズに応じて決定します。

専用の永続的なセットアップの場合、どちらのアプローチでも機能します。 ただし、永続的でないセットアップの場合、Teams を効率的に動作するには、コンピューター単位のインストールが必要です。 [非永続のセットアップ](#non-persistent-setup)のセクションを参照してください。

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

非永続的セットアップで Teams を使用するには、Teams のランタイム データ同期を効率的に行うには、プロファイル キャッシュ マネージャーも必要です。 効率的なデータ同期により、ユーザーのセッション中に適切なユーザー固有の情報 (ユーザーのデータ、プロファイル、設定など) がキャッシュされます。 これら 2 つのフォルダーのデータが同期されます。<br>
- C:\Users\username\AppData\Local\Microsoft\IdentityCache (%localAppdata%\Microsoft\IdentityCache)
- C:\Users\username\AppData\Roaming\Microsoft\Teams (%appdata%\Microsoft\Teams)

> [!NOTE]
> Teams アプリがアプリケーションの実行に必要なランタイム データとファイルを確実に取得するには、ローミング フォルダー (またはフォルダー リダイレクトを使用している場合はキャッシュ マネージャー) が必要です。 これは、ネットワーク遅延の問題やネットワークの不具合を軽減するために必要です。そうしないと、使用できないデータやファイルが原因でアプリケーション エラーが発生し、エクスペリエンスが遅くなります。

さまざまなキャッシュ マネージャー ソリューションが利用可能です。 たとえば、[FSLogix](https://docs.microsoft.com/fslogix/overview) があります。 具体的な構成手順については、キャッシュ マネージャー プロバイダーに問い合わせてください。

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a>Teams は、非永続的なセットアップ用のコンテンツ除外リストをキャッシュしました

Teams キャッシュ フォルダー %appdata%/Microsoft/Teams から以下を除外します。 これらの項目を除外すると、非永続的セットアップをさらに最適化するために、ユーザー キャッシュ のサイズを小さくすることができます。

- .txt ファイル
- メディアスタック フォルダー
- meeting-addin\Cache (%appdata%\Microsoft\Teams\meeting-addin\Cache)

### <a name="microsoft-365-apps-for-enterprise-considerations"></a>エンタープライズ向け Microsoft 365 アプリに関する考慮事項

VDI でエンタープライズ向け Microsoft 365 アプリを使用して Teams を展開する場合は、次の点を考慮してください。

#### <a name="new-deployments-of-teams-through-microsoft-365-apps-for-enterprise"></a>エンタープライズ向け Microsoft 365 アプリを使用した Teams の新しい展開

エンタープライズ向け Microsoft 365 アプリを通じて Teams を展開する前に、コンピューター単位のインストールを使用して展開されている既存の Teams アプリを最初にアンインストールする必要があります。

エンタープライズ向け Microsoft 365 アプリを通じた Teams は、ユーザーごとにインストールされます。 詳細については、[VDI で Teams デスクトップ アプリをインストールまたは更新する](#install-or-update-the-teams-desktop-app-on-vdi)セクションを参照してください。

#### <a name="teams-deployments-through-microsoft-365-apps-for-enterprise-updates"></a>エンタープライズ更新プログラム用の Microsoft 365 アプリを使用した Teams の展開

Teams は、エンタープライズ向け Microsoft 365 アプリの既存のインストールにも追加されています。 エンタープライズ向け Microsoft 365 アプリは Teams をユーザーごとにのみインストールしますので、「VDI に Teams デスクトップ アプリをインストールまたは更新する」 [セクションを参照](#install-or-update-the-teams-desktop-app-on-vdi) してください。

#### <a name="using-teams-with-per-machine-installation-and-microsoft-365-apps-for-enterprise"></a>コンピューター単位のインストールとエンタープライズ向け Microsoft 365 アプリで Teams を使用する

エンタープライズ向け Microsoft 365 アプリは、Teams のマシンごとのインストールをサポートしています。 コンピューター単位のインストールを使用するには、エンタープライズ向け Microsoft 365 アプリから Teams を除外する必要があります。 「TEAMS [デスクトップ アプリを VM](#deploy-the-teams-desktop-app-to-the-vm) に展開する」と [「Microsoft 365 Apps for Enterprise」](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise) セクションで Teams 展開を除外する方法を参照してください。

#### <a name="how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise"></a>エンタープライズ向け Microsoft 365 アプリを通じて Teams の展開を除外する方法

Teams とエンタープライズ向け Microsoft 365 アプリの詳細については、「エンタープライズ向け [Microsoft 365](https://docs.microsoft.com/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) アプリの新しいインストールから Teams を除外する方法」と「グループ ポリシーを使用して [Teams](https://docs.microsoft.com/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams)のインストールを制御する」を参照してください。

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a>Teams デスクトップ アプリを VM に展開する

1. 次のリンクのいずれかを使用して、VDI VM オペレーティング システムに一致する Teams MSI パッケージをダウンロードします。

    - [32 ビット版](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)
    - [64 ビット版](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)

    > [!NOTE]
    > 政府機関向けクラウドの場合、MSI ファイルへのダウンロード リンクについては [、「Microsoft Endpoint Configuration Manager](msi-deployment.md) を使用して Microsoft Teams をインストールする」を参照してください。

    必要な Teams デスクトップ アプリの最小バージョンはバージョン 1.3.00.4461 です。 (PSTN 保留は、以前のバージョンではサポートされていません)。

2. 次のコマンドのいずれかを実行して、MSI を VDI VM にインストールします。

    - ユーザー単位のインストール (既定)
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        このプロセスは既定のインストールで、Teams を %AppData% ユーザー フォルダーにインストールします。 この時点で、ゴールデン イメージのセットアップは完了です。 非永続的セットアップでは、Teams はユーザーごとのインストールで適切に動作しません。

    - マシンごとのインストール

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        このプロセスでは、64 ビットオペレーティング システムのプログラム ファイル (x86) フォルダーと 32 ビットオペレーティング システムの [プログラム ファイル] フォルダーに Teams をインストールします。 この時点で、ゴールデン イメージのセットアップは完了です。 非永続的なセットアップについては、マシンごとに Teams をインストールする必要があります。

        次の対話型ログオン セッションは、Teams を開始し、資格情報を要求します。

        > [!NOTE]
        > これらの例では **、ALLUSERS=1 パラメーターも使用** します。 このパラメーターを設定すると、コンピューターのすべてのユーザーの [コントロール パネル] の [プログラムと機能] および [Windows の設定] の [アプリと機能] に Teams Machine-Wide Installer が表示されます。 管理者の資格情報を持っている場合は、すべてのユーザーが Teams をアンインストールできます。
        **ALLUSERS=1 と ALLUSER=1** の違いを理解することが **重要です**。 **ALLUSERS=1** パラメーターは、VDI 環境と VDI 以外の環境で使用できます **。ALLUSER=1** パラメーターは、マシンごとのインストールを指定するために VDI 環境でのみ使用されます。

3. VDI VM から MSI をアンインストールします。 Teams をアンインストールするには 2 つの方法があります。

    - PowerShell スクリプト: この [PowerShell](scripts/powershell-script-deployment-cleanup.md) スクリプトを使用して、Teams をアンインストールし、ユーザーの Teams フォルダーを削除できます。 Teams がコンピューターにインストールされた各ユーザー プロファイルのスクリプトを実行します。
    - コマンド ライン: 次のコマンドを実行します。
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```

      このプロセスでは、オペレーティング システム環境に応じて、プログラム ファイル (x86) フォルダーまたはプログラム ファイル フォルダーから Teams をアンインストールします。

## <a name="teams-on-vdi-performance-considerations"></a>VDI 上の Teams のパフォーマンスに関する考慮事項

仮想化されたセットアップ構成にはさまざまなものがあります。それぞれが最適化に異なるフォーカスを持っています。 たとえば、構成はユーザー密度に重点を置く場合があります。 計画する場合は、組織の作業負荷のニーズに基づいてセットアップを最適化するために、次の点を考慮してください。

- 最小要件: 一部のワークロードでは、最小要件を超えるリソースを使用したセットアップが必要になる場合があります。 たとえば、より多くのコンピューティング リソースを必要とするアプリケーションを使用する開発者向けのワークロード。
- 依存関係: インフラストラクチャ、ワークロード、および Teams デスクトップ アプリ以外の環境に関するその他の考慮事項への依存関係が含まれます。
- VDI の無効な機能: Teams は、VDI の GPU 負荷集中型機能を無効にします。これは、一時的な CPU 使用率の改善に役立ちます。 以下の機能は無効です。
    - Teams CSS アニメーション
    - Giphy の自動起動

## <a name="teams-on-vdi-with-calling-and-meetings"></a>通話と会議を含む VDI 上の Teams

チャットやコラボレーションに加えて、通話と会議を含む VDI 上の Teams は、サポートされている仮想化プロバイダー プラットフォームで利用できます。 サポートされる機能は、WebRTC メディア スタックと仮想化プロバイダーの実装に基づいて行います。 次の図では、このアーキテクチャの概要を説明します。

![VDI アーキテクチャ上の Teams を示す図](media/teams-on-vdi-architecture.png)

> [!IMPORTANT]
> 現在、VDI で AV 最適化なしで Teams を実行し、最適化にまだサポートされていない機能 (アプリ共有時に制御を渡す機能など) を使用している場合は、Teams のリダイレクトを無効にするために仮想化プロバイダー ポリシーを設定する必要があります。 つまり、Teams のメディア セッションは最適化されません。 Teams のリダイレクトをオフにするポリシーを設定する方法の手順については、仮想化プロバイダーにお問い合わせください。

### <a name="network-requirements"></a>ネットワーク要件

環境を評価して、クラウド全体での音声とビデオの展開に影響を与える可能性のあるリスクおよび要件を特定することをお勧めします。 [Skype for Business ネットワーク評価ツール](https://www.microsoft.com/download/details.aspx?id=53885)を使用して、ネットワークが Teams に対応しているかどうかをテストします。

Teams 用にネットワークを準備する方法の詳細については、「Teams 用に組織のネットワークを準備する」を [参照してください](prepare-network.md)。

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a>VDI上の Skype for Business から VDI 上の Teams に移行する

VDI 上の Skype for Business から VDI 上の Teams に移行する場合、2 つのアプリケーションの違いに加えて、VDI も実装されている場合にはいくつかの違いがあります。 Skype for Business VDI ではサポートされていて、Teams VDI では現在サポートされていない機能は、次のとおりです。

- VDI の一部の AV 機能を無効にするプラットフォームごとのポリシー
- アプリ共有時の制御の受け渡し
- 音声なしのチャットからの画面共有
- ビデオと画面の共有の同時送受信

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a>Chrome ブラウザーの Teams と VDI の Teams デスクトップ アプリの比較

Chrome ブラウザーの Teams は、AV 最適化を備えた VDI 用の Teams デスクトップ アプリに代わるものを提供しません。 チャットと共同作業のエクスペリエンスは期待どおりに機能します。 メディアが必要な場合、Chrome ブラウザーでユーザーの期待に応え得ないエクスペリエンスがあります。

- オーディオとビデオのストリーミングエクスペリエンスが最適ではない可能性があります。 遅延が発生したり、品質が低下したりする場合があります。
- デバイス設定は、ブラウザーの設定では使用できません。
- デバイス管理はブラウザーを介して処理され、ブラウザー サイト設定で複数の設定が必要です。
- デバイスの設定は、Windows デバイス管理でも設定する必要がある場合があります。

## <a name="teams-on-vdi-with-chat-and-collaboration"></a>チャットと共同作業を備えた VDI 上の Teams

組織で Teams のチャットおよび共同作業機能のみを使用する場合は、ユーザーレベル ポリシーを設定して、Teams の通話および会議機能を無効にすることができます。 

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>通話および会議機能を無効にするポリシーを設定する

Microsoft Teams 管理センターまたは PowerShell を使用してポリシーを設定できます。 ポリシーの変更が反映されるには、時間 (数時間) かかる場合があります。 指定したアカウントの変更がすぐに表示されない場合は、数時間後にもう一度お試しください。

[**通話ポリシー**](teams-calling-policy.md): Teams には、すべての通話機能が無効になっている組み込みの DisallowCalling 通話ポリシーが含まれています。 DisallowCalling ポリシーを、仮想化環境で Teams を使用する組織内のすべてのユーザーに割り当てます。

[**会議ポリシー**](meeting-policies-in-teams.md): Teams には、すべての会議機能が無効になっている組み込みの AllOff 会議ポリシーが含まれています。 AllOff ポリシーを、仮想化環境で Teams を使用する組織内のすべてのユーザーに割り当てます。

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターを使用してポリシーを割り当てる

ユーザーに DisallowCalling 呼び出しポリシーと AllOff 会議ポリシーを割り当てるには、

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

次の例は、[Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) を使用して、DisallowCalling 通話ポリシーをユーザーに割り当てる方法を示しています。

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

PowerShell を使用して通話ポリシーを管理する方法の詳細については、「[Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)」を参照してください。

次の例は、[Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) を使用して、AllOff 会議ポリシーをユーザーに割り当てる方法を示しています。

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

PowerShell を使用して会議ポリシーを管理する方法の詳細については、「[Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)」を参照してください。

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-optimize-teams-with-calling-and-meetings"></a>チャットとコラボレーションを使用して VDI 上の Teams を移行し、通話と会議で Teams を最適化する

通話と会議の機能をオフにするためのユーザー レベルのポリシーを設定したチャットとコラボレーションを使用して、VDI に Teams を既存の実装している場合、AV の最適化を使用して Teams に移行する場合は、VDI ユーザーに対してそれらの Teams の呼び出しと会議機能を有効にするためのポリシーを設定する必要があります。

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a>通話および会議機能を有効にするポリシーを設定する

Microsoft Teams 管理センターまたは PowerShell を使用して、通話および会議ポリシーを設定し、ユーザーに割り当てることができます。 ポリシーの変更が反映されるまでに時間がかかる場合があります (数時間)。 指定したアカウントの変更がすぐに表示されない場合は、数時間が経過した後にもう一度お試しください。

[**通話ポリシー**](teams-calling-policy.md): Teams の通話ポリシーは、ユーザーが使用できる通話機能を制御します。 Teams には、すべての通話機能が有効になっている組み込みの AallowCalling 通話ポリシーが含まれています。 すべての通話機能を有効にするには、AllowCalling ポリシーを割り当てます。 または、カスタム通話ポリシーを作成して、必要な通話機能を有効にし、ユーザーに割り当てます。 

[**会議ポリシー**](meeting-policies-in-teams.md): Teams の会議ポリシーは、ユーザーが作成できる会議の種類と、組織内のユーザーによってスケジュールされた会議参加者が利用できる機能を制御します。 Teams には、すべての会議機能が有効になっている組み込みの AllOn 会議ポリシーが含まれています。 すべての会議機能を有効にするには、AllOn ポリシーを割り当てます。 または、カスタム会議ポリシーを作成して、必要な会議機能を有効にし、ユーザーに割り当てます。

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターを使用してポリシーを割り当てる

AllowCalling 呼び出しポリシーと AllOn 会議ポリシーをユーザーに割り当てるには、

1. Microsoft Teams 管理センターの左側のナビゲーションで、[**ユーザー**] に移動します。
2. ユーザー名の左側をクリックしてユーザーを選択し、[**編集を設定する**] をクリックします。
3. 以下の操作を行います。
    1.  [**通話ポリシー**] で、[**AllowCalling**] をクリックします。
    2.  [**会議ポリシー**] で、[**AllOn**] をクリックします。
4. [**適用**] をクリックします。

複数のユーザーに同時にポリシーを割り当てるには、次の操作を行います。

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動し、ユーザーを検索するか、表示にフィルターを適用してユーザーを表示します。
2. [**&#x2713;** (チェックマーク)] の列からユーザーを選択します。 すべてのユーザーを選択するには、表 **&#x2713;** 上部にあるチェック マーク (チェック マーク) をクリックします。
3. [**設定の編集**] をクリックし、必要な変更を行い、[**適用**] をクリックします。

または、次の操作も実行できます。

1. Microsoft Teams 管理センターの左側のナビゲーションで、割り当てるポリシーに移動します。 次に例を示します。
    - [**音声**]  >  [**通話ポリシー**] の順に移動し、[**AllowCalling**] をクリックします。
    - [**会議**]  >  [**会議ポリシー**] の順に移動し、[**AllOn**] をクリックします。
2. [**ユーザーを管理する**] を選択します。
3. [**ユーザーを管理する**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] をクリックします。 追加するユーザーごとに、この手順を繰り返します。
4. ユーザーの追加が完了したら、[**保存**] をクリックします。

#### <a name="assign-policies-using-powershell"></a>PowerShell を使用してポリシーを割り当てる

次の例は、[Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) を使用して、AllowCalling 通話ポリシーをユーザーに割り当てる方法を示しています。

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity "user email id"
```

PowerShell を使用して通話ポリシーを管理する方法の詳細については、「[Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)」を参照してください。

次の例は、[Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) を使用して、AllOn 会議ポリシーをユーザーに割り当てる方法を示しています。

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity "user email id"
```

PowerShell を使用して会議ポリシーを管理する方法の詳細については、「[Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)」を参照してください。

## <a name="control-fallback-mode-in-teams"></a>Teams でフォールバック モードを制御する

ユーザーがサポートされていないエンドポイントから接続すると、ユーザーはフォールバック モードになりますが、AV は最適化されません。 次のレジストリ DWORD 値のいずれかを設定して、フォールバック モードを無効または有効にできます。

- HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback
- HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback

フォールバック モードを無効にするには、値を **1 に設定します**。 音声のみを有効にするには、値を **2 に設定します**。 値が存在しない場合、または **0** (ゼロ) に設定されている場合は、フォールバック モードが有効になります。

この機能は、バージョン 1.3.00.13565 以降の Teams で使用できます。

## <a name="known-issues-and-limitations"></a>既知の問題と制限事項

### <a name="client-deployment-installation-and-setup"></a>クライアントの展開、インストール、およびセットアップ

- マシンごとのインストールでは、VDI 上の Teams は、非 VDI Teams のクライアントと同様に自動的に更新されません。 [VDI で Teams デスクトップ アプリをインストールまたは更新する](#install-or-update-the-teams-desktop-app-on-vdi)セクションの説明に従って新しい MSI をインストールし、VM イメージを更新する必要があります。 現在のバージョンをアンインストールして新しいバージョンに更新する必要があります。
- Teams は、ユーザーごとまたはマシンごとに展開する必要があります。 Teams のユーザーごとおよびマシンごとの同時展開はサポートされていません。 マシンごとまたはユーザーごとからこれらのモードのいずれかに移行するには、アンインストール手順に従っていずれかのモードに再展開します。
- 現時点では、Windows Virtual Desktop および VLinux ベースのクライアントは MacOS および Linux ベースのクライアントをサポートしません。
- 現時点では、Citrix は MacOs クライアントをサポートしません。
- Citrix は、エンドポイントに定義された明示的な HTTP プロキシの使用をサポートしていません。

### <a name="calling-and-meetings"></a>通話と会議

次の通話機能と会議機能はサポートされていません。

- 拡張緊急サービス
- Teams アプリとデバイス間の HID ボタンと LED コントロール
- 背景のぼかしと効果
- ブロードキャストとライブ イベントのプロデューサーと発表者の役割
- 場所に基づくルーティング (LBR)
- コール パーク
- コール キュー
- 共有システムのオーディオ/コンピューターのサウンド
- ダイレクト ルーティングのメディア バイパス

> [!NOTE]
> 現在は非 VDI 環境でのみ利用可能な通話および会議機能の追加に取り組んでいます。 これには、品質に対するより多くの管理者による制御、追加の画面共有シナリオ、Teams に最近追加された高度な機能が含まれる場合があります。 今後の機能の詳細については、Teams の担当者にお問い合わせください。

通話と会議に関する既知の問題と制限事項を次に示します。

- Skype for Business との相互運用性は、音声通話に限定されます。ビデオ モダリティはありません。
- 会議またはグループ通話では、単一の着信ビデオ ストリームのみがサポートされます。 複数のユーザーがビデオを送信する場合、常に主要な発表者のビデオのみが表示されます。
- 受信および送信ビデオ ストリームの解像度は、720p に制限されています。 これは WebRTC の制限です。
- 受信カメラまたは画面共有ストリームからの 1 つのビデオ ストリームのみがサポートされます。 受信画面共有がある場合、その画面共有は、主なスピーカーのビデオではなく表示されます。
- デバイスが切断され、再接続された場合、Teams はユーザーが選択した最後のオーディオ デバイスを使用するために切り替えされません。
- 送信画面の共有:
    - アプリケーションの共有はサポートされていません。
- 制御の受け渡し:
    - 画面共有またはアプリケーション共有セッション中はサポートされていません。
    - PowerPoint 共有セッション中はサポートされます。
- Citrix 専用の制限事項
    - マルチモニター設定での画面共有の場合、メイン モニターのみ共有されます。
    - CWA での高 DPI スケーリングはサポートされていません。

VDI に関連しない Teams の既知の問題については、組織内の [サポート チームを参照してください](Known-issues.md)。

## <a name="troubleshooting"></a>トラブルシューティング

### <a name="troubleshoot-citrix-components"></a>Citrix コンポーネントのトラブルシューティング

#### <a name="teams-crashes-or-the-teams-sign-in-screen-is-blank"></a>Teams がクラッシュする、または Teams のサインイン画面が空白である

これは、Citrix VDA バージョン 1906 および 1909 の既知の問題です。 この問題を回避するには、次のレジストリ DWORD 値を追加し、204 (16 進数) に設定します。

HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe

次に、VDA を再起動します。 詳細については、この Citrix サポート記事「Teams の HDX 最適化のトラブルシューティング [」を参照してください](https://support.citrix.com/article/CTX253754)。

## <a name="related-topics"></a>関連項目

- [MSI を使用して Microsoft Teams をインストールする](msi-deployment.md)
- [Teams での PowerShell の概要](teams-powershell-overview.md)
- [Windows Virtual デスクトップで Microsoft Teams を使用する](https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd)
