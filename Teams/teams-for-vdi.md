---
title: 仮想デスクトップ インフラストラクチャ用の Teams
author: LanaChin
ms.author: v-lanac
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
appliesto:
- Microsoft Teams
ms.openlocfilehash: 54d5f9fbf9821e88e17ebb8fe5dfa45f2b3c7270
ms.sourcegitcommit: 8816b58e175031cb0a71e0d0e89e447a7b83a760
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2020
ms.locfileid: "46597117"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>仮想デスクトップ インフラストラクチャ用の Teams

この記事では、仮想化環境で Microsoft Teams を使用する場合の要件と制限について説明します。

## <a name="what-is-vdi"></a>VDI とは何ですか ?

仮想デスクトップ インフラストラクチャ (VDI) は、データセンターの集中サーバーでデスクトップ オペレーティング システムとアプリケーションをホストする仮想化テクノロジです。 これにより、完全に保護され、準拠し一元化されたソースとともに、ユーザーに完全に個人用に設定されたデスクトップ エクスペリエンスを提供します。

仮想環境での Microsoft Teams では、チャットとコラボレーションがサポートされています。 また、Windows 仮想デスクトップまたは Citrix プラットフォームでは、通話と会議機能もサポートされます。

仮想化環境の Teams は、複数の構成をサポートしています。 これには、VDI、専用、共有、永続的、非永続的モードが含まれます。 機能は継続的に開発され、定期的に追加されます。機能は今後数か月または数年で拡張されます。

仮想環境で Teams を使用することは、仮想化されていない環境での Teams の使用とは多少異なる場合があります。 たとえば、一部の高度な機能は仮想化された環境では使用できない場合があり、ビデオの解像度が異なる場合があります。

最適なユーザー エクスペリエンスを確保するには、この記事のガイダンスに従ってください。

## <a name="teams-on-vdi-components"></a>VDI 上の Teams のコンポーネント

仮想化環境で Teams を使用するには、次のコンポーネントが必要です。

- **仮想化ブローカー**: Azure などの仮想化プロバイダーへのリソースおよび接続マネージャー
- **仮想デスクトップ**: Microsoft Teams を実行する仮想マシン (VM) スタック
- **シン クライアント**: ユーザーが物理的にやり取りするエンドポイント
- **Teams デスクトップアプリ**: teams デスクトップクライアントアプリ

## <a name="teams-on-vdi-requirements"></a>VDI 上の Teams の要件

### <a name="virtualization-provider-requirements"></a>仮想化プロバイダーの要件

Teams デスクトップ アプリは、主要な仮想化ソリューション プロバイダーで検証済みです。 市場プロバイダーが複数ある場合は、最小要件を満たしていることを確認するために、仮想化ソリューションプロバイダーに問い合わせることをお勧めします。
  
現時点では、AV (音声/ビデオ (AV) 最適化による VDI 上の Teams は、Windows 仮想デスクトップと Citrix で認定されています。 このセクションの情報を確認して、適切な機能の要件をすべて満たしていることを確認します。

### <a name="platforms-certified-for-teams"></a>Teams で認定したプラットフォーム

次のプラットフォームには、Teams 向けの仮想デスクトップインフラストラクチャソリューションがあります。

|プラットフォーム|ソリューション|
|----|---|
|![Microsoft を表すロゴ](media/microsoft-logo.png)| <a href="https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd" target="_blank">Windows 仮想デスクトップ</a> |
|![Citrix を表すロゴ](media/citrix-logo.png)| <a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix Virtual Apps and Desktops</a> |

### <a name="windows-virtual-desktop"></a>Windows 仮想デスクトップ

Windows 仮想デスクトップでは、VDI 上の Teams に AV の最適化が提供されています。 詳細と要件とインストールの詳細については、「 [Windows 仮想デスクトップで Teams を使用](https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd)する」を参照してください。

### <a name="citrix-virtual-apps-and-desktops-requirements"></a>Citrix Virtual Apps and Desktops の要件

Citrix Virtual Apps and Desktops (以前の XenApp および XenDesktop) は、VDI 上の Teams に AV 最適化を提供します。 Citrix Virtual Apps and Desktops を使用すると、VDI 上の Teams はチャットと共同作業に加えて、通話および会議機能をサポートします。

Citrix の[ダウンロードサイト](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/)で、Citrix の仮想アプリとデスクトップの最新バージョンをダウンロードできます。 (最初にサインインする必要があります。) 必要なコンポーネントは、デフォルトで [Citrix Workspace アプリ (CWA)](https://www.citrix.com/downloads/workspace-app/) および Virtual Delivery Agent (VDA) にバンドルされています。 CWA や VDA に追加のコンポーネントやプラグインをインストールする必要はありません。

サーバーおよびクライアントの最新の要件については、[この Citrix Web サイト](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)を参照してください。

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a>VDI で Teams デスクトップ アプリをインストールまたは更新する

MSI パッケージを使用したマシンごとのインストールまたはユーザーごとのインストールを用いて、VDI 用の Teams デスクトップ アプリを展開できます。 どのアプローチを使用するかについては、永続的なセットアップを使用するか、または非永続的なセットアップを使用するか、および組織の関連機能のニーズに応じて決定します。

専用の永続的なセットアップの場合、どちらのアプローチでも機能します。 ただし、非永続的なセットアップの場合、チームは効率的に作業するために、コンピューターごとにインストールする必要があります。 [非永続のセットアップ](#non-persistent-setup)のセクションを参照してください。

マシンごとのインストールでは、自動更新は無効になっています。 つまり、Teams アプリを更新するには、現在のバージョンをアンインストールして新しいバージョンに更新する必要があります。 ユーザーごとのインストールでは、自動更新は有効になっています。 ほとんどの VDI の展開について、マシンごとのインストールを使用して Teams を展開することをお勧めします。

最新の Teams バージョンに更新するには、アンインストール手順から始めて、次に最新の Teams バージョンを展開します。

VDI 環境での Teams AV の最適化が適切に機能するには、シン クライアント エンドポイントがインターネットにアクセスできる必要があります。 シン クライアント エンドポイントでインターネット アクセスが利用できない場合、最適化のスタートアップは成功しません。 これは、ユーザーが最適化されていないメディア状態にあることを意味します。

#### <a name="dedicated-persistent-setup"></a>専用の永続的なセットアップ

専用の永続的なセットアップでは、ユーザーのローカル オペレーティング システムの変更は、ユーザーがログオフした後も保持されます。 永続的なセットアップでは、チームはユーザーごととコンピューターごとの両方のインストールをサポートしています。

推奨される最低限の VM 構成は次のとおりです。

|パラメーター  |ワークステーションのオペレーティング システム  |サーバーオペレーティングシステム  |
|---------|---------|---------|
|vCPU   |    2 コア     |  4、6、または 8。<br>基礎となる Non-Uniform Memory Access (NUMA) 構成を理解し、それに応じて VM を構成することが重要です。     |
|RAM     |   4 GB      | ユーザー 1 人あたり 512 から 1024 MB        |
|ストレージ    | 8 GB        | 40 から 60 GB        |

#### <a name="non-persistent-setup"></a>非永続的なセットアップ

非永続的なセットアップでは、ユーザーのローカル オペレーティング システムの変更は、ユーザーがログオフした後は保持されません。 このようなセットアップは、一般的に共有マルチユーザー セッションです。 VM 構成は、ユーザー数と使用可能な物理ボックス リソースによって異なります。

非永続的なセットアップの場合、Teams デスクトップ アプリは、ゴールデン イメージに対してマシンごとにインストールする必要があります。 (詳細に関しては、[VDI での Teams デスクトップ アプリのインストールまたは更新](#install-or-update-the-teams-desktop-app-on-vdi)セクションを参照してください) これにより、Teams アプリがユーザー セッション中でも効率的に起動できるようになります。

非永続的なセットアップで Teams を使用する場合も、効率的な Teams のランタイムデータ同期のためのプロファイルキャッシュマネージャーが必要です。これにより、適切なユーザー固有の情報 (ユーザーデータ、プロファイル、設定など) がユーザーセッション中にキャッシュされます。 この2つのフォルダー内のデータが同期されていることを確認します。  

- C:\Users\username\AppData\Local\Microsoft\IdentityCache (%localAppdata%\Microsoft\IdentityCache)
- C:\Users\username\AppData\Roaming\Microsoft\Teams (%appdata%\Microsoft\Teams)

さまざまなキャッシュ マネージャー ソリューションが利用可能です。 たとえば、[FSLogix](https://docs.microsoft.com/fslogix/overview) があります。 具体的な構成手順については、キャッシュ マネージャー プロバイダーに問い合わせてください。

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a>Teams は、非永続的なセットアップ用のコンテンツ除外リストをキャッシュしました

Teams キャッシュ フォルダー %appdata%/Microsoft/Teams から以下を除外します。 これらの項目を除外すると、非永続的なセットアップをさらに最適化するために、ユーザーのキャッシュサイズを小さくすることができます。

- .txt ファイル
- メディアスタック フォルダー
- meeting-addin\Cache (%appdata%\Microsoft\Teams\meeting-addin\Cache)

### <a name="microsoft-365-apps-for-enterprise-considerations"></a>企業向けの Microsoft 365 アプリの考慮事項

VDI で企業向けの Microsoft 365 アプリを使用して Teams を展開する場合は、次の点を考慮してください。

#### <a name="new-deployments-of-teams-through-microsoft-365-apps-for-enterprise"></a>Microsoft 365 アプリを使用した、エンタープライズ向けの新しいチーム展開

企業向けの Microsoft 365 アプリを使用してチームを展開する前に、コンピューターごとのインストールを使用して展開された既存の Teams アプリをアンインストールする必要があります。

企業向けの Microsoft 365 アプリを使用した Teams は、ユーザーごとにインストールされます。 詳細については、[VDI で Teams デスクトップ アプリをインストールまたは更新する](#install-or-update-the-teams-desktop-app-on-vdi)セクションを参照してください。

#### <a name="teams-deployments-through-microsoft-365-apps-for-enterprise-updates"></a>Microsoft 365 アプリを使用した、エンタープライズアップデート向けの Teams の展開

Teams は、エンタープライズ向けの Microsoft 365 アプリの既存のインストールにも追加されています。 エンタープライズ用の Microsoft 365 アプリでは、ユーザーごとにチームをインストールするため、「 [VDI 上の teams デスクトップアプリをインストールまたは更新](#install-or-update-the-teams-desktop-app-on-vdi)する」セクションを参照してください。

#### <a name="using-teams-with-per-machine-installation-and-microsoft-365-apps-for-enterprise"></a>コンピューターごとのインストールと Microsoft 365 アプリでの Teams の使用 (エンタープライズ向け)

エンタープライズ向けの Microsoft 365 アプリでは、各コンピューターの Teams インストールをサポートしていません。 コンピューターごとのインストールを使用するには、enterprise 用の Microsoft 365 アプリから Teams を除外する必要があります。 「 [Teams デスクトップアプリを VM に展開](#deploy-the-teams-desktop-app-to-the-vm)する」および「[エンタープライズ向けの Microsoft 365 アプリを通じてチームの展開を除外する方法](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise)」を参照してください。

#### <a name="how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise"></a>企業向けの Microsoft 365 アプリからチームの展開を除外する方法

企業向けのチームおよび Microsoft 365 アプリの詳細については、「 [enterprise 用の microsoft 365 アプリの新しいインストールからチームを除外する](https://docs.microsoft.com/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus)」および「[グループポリシーを使用して teams のインストールを制御](https://docs.microsoft.com/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams)する方法」を参照してください。

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a>Teams デスクトップ アプリを VM に展開する

1. 次のリンクのいずれかを使用して、VDI VM オペレーティング システムに一致する Teams MSI パッケージをダウンロードします。

    - [32 ビット版](https://statics.teams.cdn.office.net/production-windows/1.3.00.13565/Teams_windows.msi)
    - [64 ビット版](https://statics.teams.cdn.office.net/production-windows-x64/1.3.00.13565/Teams_windows_x64.msi)

    必要な Teams デスクトップアプリの最小バージョンはバージョン1.3.00.4461 です。 (以前のバージョンでは、PSTN 保留はサポートされていません)。

2. 次のコマンドのいずれかを実行して、MSI を VDI VM にインストールします。

    - ユーザーごとのインストール (既定)
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        このプロセスは既定のインストールであり、Teams を% AppData% ユーザーフォルダーにインストールします。 この時点で、ゴールデン イメージのセットアップは完了です。 ユーザーごとのインストールで永続的なセットアップ以外の環境では、チームは適切に動作しません。

    - マシンごとのインストール

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        このプロセスでは、64ビットオペレーティングシステムの Program Files (x86) フォルダーと、32ビットオペレーティングシステムの Program Files フォルダーに Teams をインストールします。 この時点で、ゴールデン イメージのセットアップは完了です。 非永続的なセットアップについては、マシンごとに Teams をインストールする必要があります。

        次の対話型ログオン セッションは、Teams を開始し、資格情報を要求します。

    > [!NOTE]
    > これらの例では、 **ALLUSERS = 1**パラメーターも使用します。 このパラメーターを設定すると、チームのコンピューター全体のインストーラーがコントロールパネルの [プログラムと機能] に表示され、[アプリ] では、コンピューターのすべてのユーザーの Windows 設定の & 機能が表示されます。 すべてのユーザーが管理者の資格情報を持っている場合は、チームをアンインストールできます。
    **ALLUSERS = 1**と**alluser = 1**の違いを理解しておくことが重要です。 **ALLUSERS = 1**パラメーターは非 VDI および vdi 環境で使うことができますが、 **alluser = 1**パラメーターは vdi 環境でのみ使用され、コンピューター単位のインストールを指定します。

3. VDI VM から MSI をアンインストールします。
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```

      このプロセスでは、オペレーティングシステムの環境に応じて、Program Files (x86) フォルダーまたは Program Files フォルダーから Teams がアンインストールされます。

## <a name="teams-on-vdi-performance-considerations"></a>VDI 上の Teams のパフォーマンスに関する考慮事項

さまざまな仮想化設定が用意されており、それぞれが最適化のために異なるフォーカスが設定されています。 たとえば、構成ではユーザーの密度に重点を置いている場合があります。 計画するときは、組織の作業負荷のニーズに合わせて、次の点を考慮してセットアップを最適化してください。

- 最小要件: 一部のワークロードでは、最小要件を超えるリソースを使用してセットアップを行う必要があります。 たとえば、より多くのコンピューティング リソースを必要とするアプリケーションを使用する開発者向けのワークロード。
- 依存関係: インフラストラクチャ、ワークロード、および Teams デスクトップ アプリ以外の環境に関するその他の考慮事項への依存関係が含まれます。
- VDI の無効な機能: Teams は、VDI の GPU 負荷集中型機能を無効にします。これは、一時的な CPU 使用率の改善に役立ちます。 以下の機能は無効です。
    - Teams CSS アニメーション
    - Giphy の自動起動

## <a name="teams-on-vdi-with-calling-and-meetings"></a>通話と会議を含む VDI 上の Teams

チャットと共同作業に加えて、通話と会議のサポートを備えた VDI 上の Teams は、Citrix ベースのプラットフォームで利用できます。 サポートされる機能は、WebRTC メディア スタックおよび Citrix 固有の実装に基づいています。 次の図では、このアーキテクチャの概要を説明します。

![VDI アーキテクチャ上の Teams を示す図](media/teams-on-vdi-architecture.png)

次の通話および会議機能はサポートされていません。

- 拡張緊急サービス
- Teams アプリとデバイス間の HID ボタンと LED コントロール
- 背景のぼかしと効果
- ブロードキャスト/ライブ イベント
- 場所に基づくルーティング (LBR)
- コール パーク
- コール キュー

> [!IMPORTANT]
> 現在、VDI で AV 最適化なしで Teams を実行しており、最適化でまだサポートされていない機能 (アプリ共有時の制御の受け渡しなど) を使用する場合、Citrix ポリシーを設定して Teams のリダイレクトを無効にする必要があります。 つまり、Teams のメディア セッションは最適化されません。 Teams のリダイレクトを無効にするポリシーを設定する方法の手順については、この [Citrix Web サイト](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/policies/reference/ica-policy-settings/multimedia-policy-settings.html)を参照してください。

現在は非 VDI 環境でのみ利用可能な通話および会議機能の追加に取り組んでいます。 これには、品質、追加の画面共有シナリオ、チームに最近追加された高度な機能など、より多くの管理者の制御が含まれる場合があります。 今後の機能の詳細については、Teams の担当者にお問い合わせください。

### <a name="network-requirements"></a>ネットワーク要件

環境を評価して、クラウド全体での音声とビデオの展開に影響を与える可能性のあるリスクおよび要件を特定することをお勧めします。 [Skype for Business ネットワーク評価ツール](https://www.microsoft.com/download/details.aspx?id=53885)を使用して、ネットワークが Teams に対応しているかどうかをテストします。

Teams のネットワークを準備する方法について詳しくは、「 [teams 用に組織のネットワークを準備](prepare-network.md)する」をご覧ください。

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a>VDI上の Skype for Business から VDI 上の Teams に移行する

VDI 上の Skype for Business から VDI 上の Teams に移行する場合、2 つのアプリケーションの違いに加えて、VDI も実装されている場合にはいくつかの違いがあります。 Skype for Business VDI ではサポートされていて、Teams VDI では現在サポートされていない機能は、次のとおりです。

- メディアのビットレートを制限するポリシーを使用した VDI 通話エクスペリエンスの制御
- VDI の一部の AV 機能を無効にするプラットフォームごとのポリシー
- アプリ共有時の制御の受け渡し
- 音声なしのチャットからの画面共有
- ビデオと画面の共有の同時送受信

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a>Chrome ブラウザーの Teams と VDI の Teams デスクトップ アプリの比較

Chrome ブラウザーの Teams は、AV 最適化を備えた VDI 用の Teams デスクトップ アプリに代わるものを提供しません。 チャットと共同作業のエクスペリエンスは期待どおりに機能します。 メディアが必要な場合は、Chrome ブラウザーでユーザーの期待を満たせない場合があります。

- オーディオとビデオのストリーミングのエクスペリエンスが最適でないことがあります。 ユーザーには、遅延または品質の低下が発生する可能性があります。
- デバイス設定は、ブラウザーの設定では使用できません。
- デバイス管理はブラウザーを介して処理され、ブラウザー サイト設定で複数の設定が必要です。
- デバイス設定は、Windows デバイス管理でも設定する必要があります。

## <a name="teams-on-vdi-with-chat-and-collaboration"></a>チャットと共同作業を備えた VDI 上の Teams

組織で Teams のチャットおよび共同作業機能のみを使用する場合は、ユーザーレベル ポリシーを設定して、Teams の通話および会議機能を無効にすることができます。 この機能レベルには、Citrix Virtual Apps and Desktops は必要ありません。

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>通話および会議機能を無効にするポリシーを設定する

Microsoft Teams 管理センターまたは PowerShell を使用してポリシーを設定できます。 ポリシーの変更が反映されるまでには、多少時間がかかることがあります。 指定したアカウントの変更がすぐに表示されない場合は、数時間後にもう一度お試しください。

[**通話ポリシー**](teams-calling-policy.md): Teams には、すべての通話機能が無効になっている組み込みの DisallowCalling 通話ポリシーが含まれています。 DisallowCalling ポリシーを、仮想化環境で Teams を使用する組織内のすべてのユーザーに割り当てます。

[**会議ポリシー**](meeting-policies-in-teams.md): Teams には、すべての会議機能が無効になっている組み込みの AllOff 会議ポリシーが含まれています。 AllOff ポリシーを、仮想化環境で Teams を使用する組織内のすべてのユーザーに割り当てます。

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターを使用してポリシーを割り当てる

DisallowCalling の通話ポリシーと割り当てをユーザーに割り当てるには、次の操作を行います。

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

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-citrix-with-calling-and-meetings"></a>チャットとコラボレーションを使用する VDI 上の Teams を、通話と会議を使用する Citrix に移行します。

ユーザーレベル ポリシーを設定して通話および会議機能を無効にしたチャットとコラボレーションを使用する VDI 上の Teams の既存の実装があり、AV 最適化を備えた Citrix に移行する場合、VDI 上の Teams のユーザーに通話および会議機能を有効にするポリシーを設定する必要があります。

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a>通話および会議機能を有効にするポリシーを設定する

Microsoft Teams 管理センターまたは PowerShell を使用して、通話および会議ポリシーを設定し、ユーザーに割り当てることができます。 ポリシーの変更が反映されるまでに時間がかかる場合があります (数時間)。 指定したアカウントの変更がすぐに表示されない場合は、数時間が経過した後にもう一度お試しください。

[**通話ポリシー**](teams-calling-policy.md): Teams の通話ポリシーは、ユーザーが使用できる通話機能を制御します。 Teams には、すべての通話機能が有効になっている組み込みの AallowCalling 通話ポリシーが含まれています。 すべての通話機能を有効にするには、AllowCalling ポリシーを割り当てます。 または、カスタム通話ポリシーを作成して、必要な通話機能を有効にし、ユーザーに割り当てます。 

[**会議ポリシー**](meeting-policies-in-teams.md): Teams の会議ポリシーは、ユーザーが作成できる会議の種類と、組織内のユーザーによってスケジュールされた会議参加者が利用できる機能を制御します。 Teams には、すべての会議機能が有効になっている組み込みの AllOn 会議ポリシーが含まれています。 すべての会議機能を有効にするには、AllOn ポリシーを割り当てます。 または、カスタム会議ポリシーを作成して、必要な会議機能を有効にし、ユーザーに割り当てます。

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターを使用してポリシーを割り当てる

AllowCalling の通話ポリシーと、すべての会議ポリシーをユーザーに割り当てるには:

1. Microsoft Teams 管理センターの左側のナビゲーションで、[**ユーザー**] に移動します。
2. ユーザー名の左側をクリックしてユーザーを選択し、[**編集を設定する**] をクリックします。
3. 以下の操作を行います。
    1.  [**通話ポリシー**] で、[**AllowCalling**] をクリックします。
    2.  [**会議ポリシー**] で、[**AllOn**] をクリックします。
4. [**適用**] をクリックします。

複数のユーザーに同時にポリシーを割り当てるには、次の操作を行います。

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動し、ユーザーを検索するか、表示にフィルターを適用してユーザーを表示します。
2. [**&#x2713;** (チェックマーク)] の列からユーザーを選択します。 すべてのユーザーを選択するには、テーブルの上部にある **&#x2713;** (チェックマーク) をクリックします。
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

## <a name="known-issues-and-limitations"></a>既知の問題と制限事項

### <a name="client-deployment-installation-and-setup"></a>クライアントの展開、インストール、およびセットアップ

- マシンごとのインストールでは、VDI 上の Teams は、非 VDI Teams のクライアントと同様に自動的に更新されません。 [VDI で Teams デスクトップ アプリをインストールまたは更新する](#install-or-update-the-teams-desktop-app-on-vdi)セクションの説明に従って新しい MSI をインストールし、VM イメージを更新する必要があります。 現在のバージョンをアンインストールして新しいバージョンに更新する必要があります。
- Teams は、ユーザーごとまたはマシンごとに展開する必要があります。 Teams のユーザーごとおよびマシンごとの同時展開はサポートされていません。 マシンごとまたはユーザーごとからこれらのモードのいずれかに移行するには、アンインストール手順に従っていずれかのモードに再展開します。
- 現時点では、Citrix は MacOs と Linux ベースのクライアントをサポートしていません。
- Citrix は、エンドポイントに定義された明示的な HTTP プロキシの使用をサポートしていません。

### <a name="calling-and-meetings"></a>通話と会議

- Skype for Business の相互運用性は音声通話に限定されます。ビデオのモダリティはありません。
- 匿名ユーザーとしての Teams 会議への参加については、AV 最適化されていません。 ユーザーは会議に参加でき、最適化されていないエクスペリエンスを経験します。
- 会議またはグループ通話では、単一の着信ビデオ ストリームのみがサポートされます。 複数のユーザーがビデオを送信する場合、常に主要な発表者のビデオのみが表示されます。
- 受信および送信ビデオ ストリームの解像度は、720p に制限されています。 これは WebRTC の制限です。
- 受信カメラまたは画面共有ストリームからの 1 つのビデオ ストリームのみがサポートされます。 着信画面が表示されている場合は、その画面共有が、主要なスピーカーのビデオではなく、表示されます。
- 送信画面の共有:
    - アプリケーションの共有はサポートされていません。
- 制御の受け渡し:
    - 画面共有またはアプリケーション共有セッション中はサポートされていません。
    - PowerPoint 共有セッション中はサポートされます。
- Citrix のみの制限
    - デュアルトーンマルチ周波数 (DTMF) テレフォニーシステムとの相互操作は、現在サポートされていません。
    - マルチモニター設定での画面共有の場合、メイン モニターのみ共有されます。
    - CWA での高 DPI スケーリングはサポートされていません。

VDI に関連していない Teams の既知の問題については、「[組織のサポートチーム](Known-issues.md)」をご覧ください。

## <a name="troubleshooting"></a>トラブルシューティング

#### <a name="troubleshoot-citrix-components"></a>Citrix コンポーネントのトラブルシューティング

VDA および CWA の問題のトラブルシューティング方法については、[このCitrix Web サイト](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)を参照してください。

## <a name="related-topics"></a>関連項目

- [MSI を使用して Microsoft Teams をインストールする](msi-deployment.md)
- [Teams での PowerShell の概要](teams-powershell-overview.md)
- [Windows 仮想デスクトップで Microsoft Teams を使用する](https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd)
