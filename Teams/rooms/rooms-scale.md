---
title: Microsoft Endpoint Configuration Manager を使用して Microsoft Teams Rooms を展開する
author: lanachin
ms.author: v-lanac
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
ms.collection:
- M365-collaboration
description: Microsoft Endpoint Configuration Manager を使用した、大規模な Microsoft Teams Rooms の展開の方法について説明します。
no-loc:
- Microsoft
- Microsoft Corporation
- Microsoft Teams Rooms
- Microsoft Teams Room
- System Center
- Configuration Manager
- Windows
- Surface
- Surface Pro
- Windows PE
- Windows 10
- Windows 10 Enterprise
- Azure
- Azure Monitor
- Log Analytics
- Operations Management Suite
ms.openlocfilehash: f96b970165996cc27308ce616fb4875d741f8869
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905319"
---
# <a name="deploy-microsoft-teams-rooms-by-using-microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager を使用して Microsoft Teams Rooms を展開する

この記事では、Microsoft Endpoint Configuration Manager を使用して、Microsoft Teams Rooms の展開をするために必要なすべての情報を提供します。

構成マネージャーが提供する簡単な方法では、複数のターゲット デバイスにオペレーティング システムとその他のアプリケーションを展開することができます。

次に示すアプローチを使用して、構成マネージャーの構成を行い、組織のニーズに応じて、このガイド全体のサンプル パッケージとスクリプトをカスタマイズします。

![構成マネージャーを使用した Microsoft Teams Rooms の展開プロセス](../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> この解決方法は、Surface Pro ベースの展開でのみテストされています。 Surface Pro をベースにしていない構成については、メーカーのガイドラインに従ってください。

## <a name="validate-prerequisites"></a>前提条件の検証

Microsoft Teams Rooms を構成マネージャーで展開するにあたり、次の前提条件と要件を満たしていることをご確認ください。

### <a name="microsoft-endpoint-configuration-manager-requirements"></a>Microsoft Endpoint Configuration Manager の要件

-   Microsoft Endpoint Configuration Manager のバージョンは、少なくとも 1706 以上である必要があります。 1710 以降を使用することをお勧めします。 [構成マネージャー内の Windows 10 のサポート](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client)を確認し、構成マネージャーでサポートされている Windows 10 のバージョンを参照してください。

-   Windows 10 用の Windows アセスメント & デプロイメント キット (ADK) のサポートされているバージョンがインストールされている必要があります。 異なるバージョンの構成マネージャーで使用できる [Windows 10 ADK](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-adk) のバージョンを参照して、展開に正しいバージョンが含まれていることを確認してください。

-   サイト システム サーバーには配布ポイントの役割が割り当てられている必要があります。また、ネットワークを利用した展開を有効にするには、ブート イメージの[プレブート実行環境 (PXE) のサポート](https://docs.microsoft.com/configmgr/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network)を有効にする必要があります。 PXE のサポートが有効になっていない場合は、[起動可能なメディア](https://docs.microsoft.com/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network)を展開に使用できます。

-   新しいコンピューター (ベア メタル) の展開シナリオをサポートするには、ネットワーク アクセス アカウントを構成する必要があります。 ネットワーク アクセス アカウントの構成の詳細については、[「構成マネージャーで使用するアカウント」](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)を参照してください。

-   同じ Microsoft Teams Rooms のイメージを、複数のユニットに同時に展開した場合は、[マルチキャスト サポート](https://docs.microsoft.com/configmgr/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network)を有効にすることをお勧めします。

### <a name="networking-requirements"></a>ネットワークの要件

-   使用しているネットワークには、Microsoft Teams Rooms ユニットが展開されるサブネットに対して、IP アドレスを自動的に配布するように構成された動的ホスト構成プロトコル (DHCP) サーバーが必要です。

    > [!NOTE]
    > DHCP リース期間は、イメージの展開期間よりも長い値を設定する必要があります。 それ以外の場合、展開に失敗する可能性があります。

-   スイッチと仮想 LAN (VLAN) を含むネットワークは、PXE をサポートするように構成する必要があります。 IP Helper および PXE 構成の詳細については、ネットワーク ベンダーにお問い合わせください。 また、PXE サポートが有効になっていない場合は、[起動可能なメディア](https://docs.microsoft.com/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network)を使用することもできます。

    > [!NOTE]
    > Surface Pro デバイスの場合、ネットワークからの起動 (PXE ブート) は、Microsoft の Ethernet アダプター、またはドッキング ステーションを使用している場合にのみサポートされます。 サードパーティ製のイーサネット アダプターは Surface Pro による PXE ブートをサポートしていません。 詳細については、[「イーサネット アダプターと Surface の展開」](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment)を参照してください。

## <a name="configure-microsoft-endpoint-configuration-manager-for-operating-system-deployment"></a>オペレーティング システムの展開用に Microsoft Endpoint Configuration Manager を構成する

この記事では、構成マネージャーが正常に展開されていることを前提としているため、構成マネージャーを一から展開して構成するために必要なすべての手順については説明していません。 Microsoft Endpoint Configuration Manager の [ドキュメントと構成のガイダンス](https://docs.microsoft.com/configmgr/)は、優れたリソースです。構成マネージャーをまだ展開していない場合は、これらのリソースから始めることをお勧めします。

オペレーティング システムの展開 (OSD) 機能が正しく構成されていることを確認するには、次の手順を実行します。

### <a name="validate-and-upgrade-configuration-manager"></a>構成マネージャーの検証とアップグレード

1.  構成マネージャー コンソールで、[ **管理** ] \> [ **更新とサービス** ]に移動します。

2.  インストールされているビルドおよびインストールされていない更新プログラムを確認します。

3.  [構成マネージャーでの Windows 10 のサポート](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client)を確認します。展開をアップグレードする必要がある場合は、インストールする更新プログラムを選択し、[ **ダウンロード** ] を選択します。

4.  ダウンロードが完了したら、更新プログラムを選択し、[ **更新プログラム パックをインストール** ] を選択します。

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a>PXE とマルチキャストをサポートするように配布ポイントを構成する

1.  構成マネージャー コンソールで、[ **管理** ] \> [ **配布ポイント** ] に移動します。

2.  Microsoft Teams Rooms の展開に使用する配布ポイント サーバーを選択し、[ **プロパティ** ] を選択します。

3.  [ **PXE** ] タブを選択し、次の設定が有効になっていることを確認します。
    -   クライアントの PXE サポートの有効化
    -   この配布ポイントに受信 PXE 要求に応答することを許可する
    -   不明なコンピューターのサポートを有効にする

4.  *省略可能:* マルチキャストのサポートを有効にするには、[ **マルチキャスト** ] タブを選択し、次の設定が有効になっていることを確認します。
    -   マルチキャストで、複数のクライアントに同時にデータを送信できるようにする
    -   ネットワーク チームの推奨事項に応じて、UDP ポートの範囲を構成します。

### <a name="configure-the-network-access-account"></a>ネットワーク アクセス アカウントを構成する

1.  構成マネージャー コンソールで、[ **管理** ] \> [ **サイト構成** ] \> [ **サイト** ] に移動して、サイトを選びます。

2.  [ **設定** ] グループで、[ **サイト コンポーネントの構成** ] \> [ **ソフトウェア配布** ]を選択します。

3.  [ **ネットワーク アクセス アカウント** ] タブを選択します。1 つまたは複数のアカウントを設定し、[ **OK** ] を選択します。

> [!NOTE]
> アカウントには特別な権限は必要ありません。ただし、配布ポイント サーバー上の [ **ネットワークからこのコンピューターにアクセスする権限** ] を除きます。 汎用ドメイン ユーザー アカウントが適しています。 詳細については、[「構成マネージャーで使用されているアカウント」](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)を参照してください。

### <a name="configure-a-boot-image"></a>ブート イメージを構成する

1.  構成マネージャー コンソールで、[ **ソフトウェアライブラリ** ] \> [ **オペレーティングシステム** ] \> [ **ブートイメージ** ] に移動します。

2.  **ブート イメージ (x64)** を選択し、[ **プロパティ** ] を選択します。

3.  [ **データ ソース** ] タブを選択し、[ **PXE 対応の配布ポイントからこのブート イメージを展開する** ] を有効にします。

4.  必要なコンポーネントをインストールするには、[ **オプションコンポーネント** ] タブを選択します。

    1.  星型のアイコンを選び、 **HTML (WinPE) を検索します**

    2.  [ **OK** ] を選択して、HTML アプリケーション サポートをブート イメージに追加します。

5.  *省略可能:* 展開エクスペリエンスをカスタマイズするには、[ **カスタマイズ** ] タブを選択します。
    -   展開中にコマンド プロンプトにアクセスできるようにするには、[ **コマンドのサポート (テストのみ)** ] を有効にします。 この設定を有効にすると、展開中にいつでも [ **F8** ] を選択して、コマンド プロンプトを起動できます。
    -   展開中に表示されるカスタム背景画像を指定することもできます。 画像を設定するには、[ **カスタム背景画像ファイル （UNCパス) の指定** ] を有効にして、背景を選択します。

6.  メッセージが表示されたら、[ **はい** ] を選択し、更新されたブート イメージを配布ポイントに配布します。

詳細については、[「構成マネージャーを使用してブートイメージを管理する」](https://docs.microsoft.com/configmgr/osd/get-started/manage-boot-images)を参照してください。

> [!NOTE]
> PXE がサポートされていない環境向けに、構成マネージャーのタスク シーケンス ベースの展開を開始するために、起動可能な USB メディアを作成できます。 ブート可能なメディアには、ブート イメージ、オプションの実行可能コマンド、必須ファイル、および Windows PE へのブートとデプロイメントプロセスの残りの部分の構成マネージャーへの接続をサポートする、構成マネージャー バイナリのみが含まれています。 詳細については、「[ブート可能なメディアの作成](https://docs.microsoft.com/configmgr/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia)」を参照してください。

## <a name="create-configuration-manager-packages"></a>構成マネージャー パッケージを作成する

> [!IMPORTANT]
> 各 SRS インストーラー バージョンに要求されるオペレーティング システムのバージョンは、MSI リリースごとに変わります。 特定の MSI に最適なオペレーティング システム バージョンを決定するには、コンソール セットアップ スクリプトを一度実行します。 詳細については、「[Microsoft Endpoint Configuration Manager を使用して Microsoft Teams Rooms を展開する](rooms-scale.md)」 を参照してください。

構成マネージャーでは、Microsoft Teams Rooms ユニットの展開と構成を行うため、いくつかのパッケージが必要になります。

次のパッケージを作成して構成し、配布ポイント サーバーの役割が割り当てられた 構成マネージャー サイト システムに配布する必要があります。

| **パッケージ名**                     | **Type**               | **説明**                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| SRS v2-SRS アプリケーション パッケージ     | ソフトウェアパッケージ       | Microsoft Teams Rooms 展開キット用のパッケージ                                      |
| SRS v2-Sysprep パッケージ             | ソフトウェア パッケージ       | Microsoft Teams Rooms ユニットを構成するための、カスタム Unattended.xml 用のパッケージ            |
| SRS v2 - Set-SRSComputerName パッケージ | ソフトウェア パッケージ       | 展開中にコンピューター名を割り当てる HTML アプリケーション (HTA) 用のパッケージ    |
| SRS v2 - SRS のセットアップを構成する         | ソフトウェア パッケージ       | Microsoft Teams Rooms アプリの展開を構成するためのパッケージ                          |
| SRS v2 - OS アップデート パッケージ          | ソフトウェア パッケージ       | 必須のオペレーティング システム更新プログラムを展開するためのパッケージ                                      |
| SRS v2 - ルート証明書パッケージ    | ソフトウェア パッケージ       | 省略可能 -ルート証明書を展開するためのパッケージ (ドメインに参加しているユニットには必要ありません)  |
| SRS v2 - Microsoft Monitoring Agent パッケージ | ソフトウェア パッケージ       | 省略可能 - Microsoft Operations Management Suite エージェントを展開および構成するためのパッケージ|
| SRS v2 - WinPE 背景パッケージ    | ソフトウェア パッケージ       | カスタム背景画像を使用して、ブート イメージに使用するためのパッケージ                           |
| Windows 10 Enterprise                | オペレーティング システム イメージ | オペレーティング システムのインストール ファイル用のパッケージ (install.wim)                          |
| Surface Pro                          | ドライバー パッケージ         | Microsoft Surface Pro のデバイス ドライバーおよびファームウェア用のパッケージ                     |
| Surface Pro 4                        | ドライバー パッケージ         | Microsoft Surface Pro 4 のデバイス ドライバーおよびファームウェア用のパッケージ                   |

詳細については、「[構成マネージャー内のパッケージとプログラム](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs)」 を参照してください。

### <a name="create-folders-for-the-package-source-files"></a>パッケージ ソース ファイル用のフォルダーを作成する

構成マネージャーでは、最初に作成されたとき、および更新されたときに、パッケージのソース ファイルを特定のフォルダー構造に整理する必要があります。

Microsoft Endpoint Configuration Manager のサーバーの全体管理サイトまたはプライマリ サイト、あるいはパッケージ ソース ファイルのホストに使用しているサーバー共有上で、次のフォルダー構造を作成します。

-   SRS v2 - Microsoft Monitoring Agent パッケージ
-   SRS v2 - OS アップデート パッケージ
-   SRS v2 - ルート証明書パッケージ
-   SRS v2 - Set-SRSComputerName パッケージ
-   SRS v2-SRS アプリケーション パッケージ
-   SRS v2 - SRS のセットアップを構成する
-   SRS v2-Sysprep パッケージ
-   ドライバー
    -   Surface Pro
    -   Surface Pro 4
-   オペレーティング システム
    -   Windows 10 Enterprise

> [!TIP]
> パッケージのフォルダー構造、使用する必要のあるスクリプト、インポートする必要のあるタスク シーケンス テンプレートを含む zip ファイルを、[ダウンロード](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)して使用することもできます。

### <a name="create-the-monitoring-agent-package"></a>監視エージェント パッケージを作成する

1. <https://go.microsoft.com/fwlink/?LinkId=828603> から監視エージェントをダウンロードします。

2. コマンド プロンプト ウィンドウを開き、コマンド プロンプトで **MMASetup-AMD64.exe /C:** と入力し、パッケージを **SRS v2 - Microsoft Monitoring Agent パッケージ** フォルダーに展開します。

3. 構成マネージャー コンソールから、[ **ソフトウェアライブラリ** ] \> [ **アプリケーションの管理** ] \> [ **パッケージ** ] に移動し、[ **パッケージの作成** ] を選びます。

4. パッケージを作成するには、次の情報を入力します。

   - 名前<strong>: SRS v2 - Microsoft Monitoring Agent パッケージ</strong>

   - 製造元<strong>: Microsoft Corporation</strong>

   - バージョン<strong>: 8.1.11081.0</strong> (ダウンロードしたインストール ファイルのバージョンを入力してください)

   - [ **このパッケージには、ソース ファイルが含まれています** ] のチェック ボックスを選択し、 **SRS v2 - Microsoft Monitoring Agent パッケージ** フォルダーのパスを入力し、[ **次へ** ] を選択します。

5. [ **プログラムを作成しない** ] を選択し、[ **次へ** ] を選択します。

6. [ **設定の確認** ] を確認して、[ **次へ** ] を選択します。

7. **[閉じる]** を選択します。

### <a name="create-the-operating-system-updates-package"></a>オペレーティング システムの更新プログラム パッケージを作成する

1. [ **SRS v2 - OS 更新プログラムパッケージ** ] フォルダーで、 **Install-SRSv2-OS-Updates.ps1** という名前の新しい PowerShell スクリプトを作成します。

2. 次のスクリプトを **Install-SRSv2-OS-Updates.ps1** スクリプトにコピーします。 または、[ここ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)から Install-SRSv2-OS-Updates.ps1 スクリプトをダウンロードすることもできます。
   ```
   # Install-SRSv2-OS-Updates.ps1
   $strPath = split-path -parent $MyInvocation.MyCommand.Definition
   $total = gci $strPath *.msu | measure | Select-Object -expand Count
   $i = 0
   gci $strPath *.msu | ForEach-Object {
     $i++
     WUSA ""$_.FullName /quiet /norestart""
     Write-Progress -activity "Applying Mandatory Updates" -status "Installing
     $_ .. $i of $total" -percentComplete (($i / $total) * 100)
     Wait-Process -name wusa
   }
   ```
3. 必須の Windows Update パッケージを、同じフォルダーにダウンロードします。
   > [!NOTE]
   > この記事が公開された時点では、 [の KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) のみが必要でした。 [[Microsoft Teams Rooms コンソールを構成する](console.md)] を確認し、他の更新プログラムが必要かどうかを確認します。

4. 構成マネージャー コンソールから、[ **ソフトウェアライブラリ** ] \> [ **アプリケーションの管理** ] \> [ **パッケージ** ] に移動し、[ **パッケージの作成** ] を選びます。

5. パッケージを作成するには、次の情報を入力します。
   -   名前: **SRS v2 – OS 更新プログラムパッケージ**
   -   製造元: **Microsoft Corporation**
   -   バージョン: **1.0.0**
   -   [ **このパッケージには、ソース ファイルが含まれています** ] のチェック ボックスを選択し、 **SRS v2 - OS 更新プログラム パッケージ** フォルダーのパスを入力し、[ **次へ** ] を選択します。

6. [ **プログラムを作成しない** ] を選択し、[ **次へ** ] を選択します。

7. [ **設定の確認** ] を確認して、[ **次へ** ] を選択します。

8. **[閉じる]** を選択します。

### <a name="create-the-root-certificate-package-optional"></a>ルート証明書パッケージを作成する (省略可能)

このパッケージを作成して、Active Directory ドメインに参加しないデバイスのルート証明書を配布します。 次の両方の条件が該当する場合にのみ、このパッケージを作成します。
-   展開には、オンプレミスの Lync または Skype for Business サーバーが含まれます。
-   Microsoft Teams Rooms ユニットは、ドメイン メンバーの代わりにワーク グループで動作するように構成されています。

1.  ルート証明書を **SRS v2 –ルート証明書パッケージ** フォルダーにコピーします。

2.  構成マネージャー コンソールから、[ **ソフトウェアライブラリ** ] \> [ **アプリケーションの管理** ] \> [ **パッケージ** ] に移動し、[ **パッケージの作成** ] を選びます。

3.  パッケージを作成するには、次の情報を入力します。
    -   名前: **SRS v2 –ルート証明書パッケージ**
    -   製造元: *組織の名前*
    -   バージョン: **1.0.0**
    -   [ **このパッケージには、ソース ファイルが含まれています** ] のチェック ボックスを選択し、 **SRS v2 - ルート証明書パッケージ** フォルダーのパスを入力し、[ **次へ** ] を選択します。

4.  [ **プログラムを作成しない** ] を選択し、[ **次へ** ] を選択します。

5.  [ **設定の確認** ] を確認して、[ **次へ** ] を選択します。

6.  **[閉じる]** を選択します。

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a>Microsoft Teams Rooms 展開キット パッケージの作成

1.  <https://go.microsoft.com/fwlink/?linkid=851168>から最新バージョンの **Microsoft Teams Rooms 展開キット** をダウンロードし、ワークステーションにインストールします。

2.  **C:\\Program Files (x86)\\ Skype ミーティング システム展開キット** の内容を、 **SRS v2 - SRS アプリケーション パッケージ** フォルダにコピーします。

3.  構成マネージャー コンソールから、[ **ソフトウェアライブラリ** ] \> [ **アプリケーションの管理** ] \> [ **パッケージ** ] に移動し、[ **パッケージの作成** ] を選びます。

4.  パッケージを作成するには、次の情報を入力します。
    -   名前: **SRS v2 – SRS アプリケーション パッケージ**
    -   製造元: **Microsoft Corporation**
    -   バージョン: **3.1.104.0** (ダウンロードしたインストールファイルのバージョンを入力してください)
    -   [ **このパッケージには、ソース ファイルが含まれています** ] のチェック ボックスを選択し、 **SRS v2 - SRS アプリケーション パッケージ** フォルダーのパスを入力し、[ **次へ** ] を選択します。
5.  [ **プログラムを作成しない** ] を選択し、[ **次へ** ] を選択します。

6.  [ **設定の確認** ] を確認して、[ **次へ** ] を選択します。

7.  **[閉じる]** を選択します。

### <a name="create-the-computer-name-assignment-package"></a>コンピューター名の割り当てパッケージを作成する

1.  **SRS v2 - Set-SRSComputerName パッケージ** フォルダーで **Set-SRSComputerName.hta** という名前の新しい HTML アプリケーションを作成します。

2.  **Set-SRSComputerName.hta** ファイルに次のスクリプトをコピーします。 または、[ここ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)から Set-SRSComputerName.hta ファイルをダウンロードすることもできます。
    ```HTML
    <!DOCTYPE HTML>
    <html>
    <head>
    <title>Set SRS Computer Name</title>
    <HTA:APPLICATION
      APPLICATIONNAME="Set SRS Computer Name"
      ID="SetSRSComputerName"
      VERSION="1.0"
      SCROLL="no"
      SINGLEINSTANCE="yes"
      WINDOWSTATE="maximize"
      MaximizeButton="no"
      MinimizeButton="no"
      SysMenu="no"
      ShowInTaskbar="no"
      Caption="no"
      />
    <style type="text/css">
    body {
        background-color: #fdfeff;
        color: darkblue;
        font-family: Calibri;
        font-size: 12pt;
        margin: 4em 3em;
    }
    </style>
    </head>
    <script language="VBScript">
    Public strNewComputerName
    Sub GenerateComputerName()
        strComputer = "."
        Set objWMIService = GetObject("winmgmts:\\" & strComputer & "\root\cimv2")
        Set colItems = objWMIService.ExecQuery("Select * from Win32_BIOS",,48)
        For Each objItem in colItems
            strSerialNumber = objItem.SerialNumber
        Next
        strNewComputerName = "SRS-"  & right(replace(strSerialNumber, "-","") ,10)
        TextArea1.innerHTML = "The serial number of the device: " & strSerialNumber
        strHTMLText = strHTMLText & "<br> Computer name to be assigned: <font color = red>" & strNewComputerName & "</font>"
        strHTMLText = strHTMLText & "<br><br> Click Accept to use this as the computer name and continue deployment, or Change to set a new name."
        strHTMLText = strHTMLText & "<p><input type=""button"" value=""Accept"" name = ""Accept_Button"" onclick=""SetComputerName"" />"
        strHTMLText = strHTMLText & " <input type=""button"" value=""Change"" name = ""Change_Button"" onclick=""ChangeComputerName"" />"
        TextArea2.innerHTML = strHTMLText
    End Sub

    Sub SetComputerName()
        dim result
        result = MsgBox("Computer Name to be assigned: " & strNewComputerName &vbcrlf & "Are you sure you want to continue?", 36)
        If (result = vbYes) then
            SET env = CreateObject("Microsoft.SMS.TSEnvironment")
            env("OSDComputerName") = strNewComputerName
            self.close
        elseif (result = vbNo) then
            Window_OnLoad
        End If
    End Sub

    Sub UpdateComputerName()
        strNewComputerName = newcomputername.value
        if len(trim(strNewComputerName)) = 0 then
            MsgBox "Computer name cannot be empty." &vbcrlf & "Update and try again.",16
            exit sub
        end if
        SetComputerName
    End Sub

    Sub ChangeComputerName()
        TextArea2.innerHTML = "<p>Type the new computer name and click Accept:  <input type=""text"" name=""newcomputername"" value =" & strNewComputerName & " />"
        TextArea2.innerHTML = TextArea2.innerHTML & "<br><input type=""button"" value=""Update"" name = ""Update_Button"" onclick=""UpdateComputerName"" />"
    End Sub

    Sub Window_OnLoad
        Set oTSProgressUI = CreateObject("Microsoft.SMS.TsProgressUI")
        oTSProgressUI.CloseProgressDialog
        GenerateComputerName
    End Sub
    </script>

    <body>
    <span id = "TextArea1"></span>
    <span id = "TextArea2">
    </span>
    </body>
    </html>

    ```
3.  構成マネージャー コンソールから、[ **ソフトウェアライブラリ** ] \> [ **アプリケーションの管理** ] \> [ **パッケージ** ] に移動し、[ **パッケージの作成** ] を選びます。

4.  パッケージを作成するには、次の情報を入力します。

    -   名前: **SRS v2 - Set-SRSComputerName パッケージ**

    -   製造元: **Microsoft Corporation**

    -   バージョン: **1.0.0**

    -   [ **このパッケージには、ソース ファイルが含まれています** ] のチェック ボックスを選択し、 **SRS v2 - Set-SRSComputerName パッケージ** フォルダーのパスを入力し、[ **次へ** ] を選択します。

5.  [ **プログラムを作成しない** ] を選択し、[ **次へ** ] を選択します。

6.  [ **設定の確認** ] を確認して、[ **次へ** ] を選択します。

7.  **[閉じる]** を選択します。

### <a name="create-the-sysprep-package"></a>Sysprep パッケージを作成する

1. **SRS v2 – Sysprep パッケージ** フォルダーで、 **Unattend.xml** という名前の新しい XML ファイルを作成します。

2. **Unattend.xml** ファイルに次のテキストをコピーします。 または、[ここ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)から Unattend.xml ファイルをダウンロードすることもできます。
   ```XML
   <?xml version="1.0" encoding="utf-8"?>
   <unattend xmlns="urn:schemas-microsoft-com:unattend">
   <settings pass="specialize">
       <component name="Microsoft-Windows-Embedded-BootExp" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="NonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <DisableBootMenu>1</DisableBootMenu>
           <DisplayDisabled>1</DisplayDisabled>
       </component>
       <component name="Microsoft-Windows-powercpl" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <PreferredPlan>8c5e7fda-e8bf-4a96-9a85-a6e23a8c635c</PreferredPlan>
       </component>
   </settings>
   <settings pass="oobeSystem">
       <component name="Microsoft-Windows-Shell-Setup" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <OOBE>
               <HideEULAPage>true</HideEULAPage>
               <HideLocalAccountScreen>true</HideLocalAccountScreen>
               <HideOEMRegistrationScreen>true</HideOEMRegistrationScreen>
               <HideOnlineAccountScreens>true</HideOnlineAccountScreens>
               <HideWirelessSetupInOOBE>true</HideWirelessSetupInOOBE>
               <SkipMachineOOBE>true</SkipMachineOOBE>
               <SkipUserOOBE>true</SkipUserOOBE>
               <ProtectYourPC>1</ProtectYourPC>
           </OOBE>
           <AutoLogon>
               <Enabled>true</Enabled>
               <Username>Skype</Username>
               <Password>
                   <Value>UABhAHMAcwB3AG8AcgBkAA==</Value>
                   <PlainText>false</PlainText>
               </Password>
           </AutoLogon>
           <UserAccounts>
               <LocalAccounts>
                   <LocalAccount wcm:action="add">
                       <Password>
                           <Value>cwBmAGIAUABhAHMAcwB3AG8AcgBkAA==</Value>
                           <PlainText>false</PlainText>
                       </Password>
                       <Name>Admin</Name>
                       <Group>Administrators</Group>
                       <DisplayName>Administrator</DisplayName>
                       <Description>Administrator</Description>
                   </LocalAccount>
               </LocalAccounts>
           </UserAccounts>
       </component>
   </settings>
   <cpi:offlineImage cpi:source="wim:h:/install.wim#Windows 10 Enterprise" xmlns:cpi="urn:schemas-microsoft-com:cpi" />
   </unattend>
   ```
3. 構成マネージャー コンソールから、[ **ソフトウェアライブラリ** ] \> [ **アプリケーションの管理** ] \> [ **パッケージ** ] に移動し、[ **パッケージの作成** ] を選びます。

4. パッケージを作成するには、次の情報を入力します。
   -   名前: **SRS v2-Sysprep パッケージ**
   -   製造元: **Microsoft Corporation**
   -   バージョン: **1.0.0**
   -   [ **このパッケージには、ソース ファイルが含まれています** ] のチェック ボックスを選択し、 **SRS v2 - Sysprep パッケージ** フォルダーのパスを入力し、[ **次へ** ] を選択します。
5. [ **プログラムを作成しない** ] を選択し、[ **次へ** ] を選択します。

6. [ **設定の確認** ] を確認して、[ **次へ** ] を選択します。

7. **[閉じる]** を選択します。

### <a name="create-the-windows-10-enterprise-package"></a>Windows 10 Enterprise パッケージを作成する

1.  Windows 10 Enterprise x64 メディアを取得して、 **install.wim** ファイルを **オペレーティング システム \\Windows 10 Enterprise** フォルダーにコピーします。

2.  構成マネージャー コンソールから、[ **ソフトウェア ライブラリ** ] \> [ **オペレーティングシステム** ] \> [ **オペレーティング システム イメージ** ] に移動し、[ **オペレーティング システム イメージを追加** ] を選択します。

3.  コピーした **install.wim** ファイルのパスを指定し、[ **次へ** ] を選択します。

4.  [ **バージョン** ] フィールドを更新して、Windows 10 Enterprise のビルド番号と一致するようにし、[ **次へ** ] を選択します。

5.  [ **詳細** ] ページを確認し、[ **次へ** ] を選択します。

6.  **[閉じる]** を選択します。

詳細については、[「構成マネージャーを使用して OS イメージを管理する」](https://docs.microsoft.com/configmgr/osd/get-started/manage-operating-system-images)を参照してください。

### <a name="create-surface-pro-device-driver-packages"></a>Surface Pro デバイス ドライバー パッケージの作成

Microsoft Teams Rooms は Surface Pro と Surface Pro 4 の両方でサポートされています。 環境内にある Surface Pro のモデルごとに、ドライバー パッケージを作成する必要があります。

> [!IMPORTANT]
> ドライバーは、Windows 10 Enterprise ビルドおよび Microsoft Teams Rooms 展開キットのバージョンと互換性がある必要があります。 詳細については、[「Surface デバイス用の最新のファームウェアとドライバーをダウンロードする」](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) および [「コンソールを構成する」](console.md)を参照してください。

1.  最新のドライバーとファームウェアをダウンロードします。
    -   Surface Pro 用: <https://www.microsoft.com/download/details.aspx?id=55484>
    -   Surface Pro 4 用: <https://www.microsoft.com/download/details.aspx?id=49498>

2.  ダウンロードしたドライバーおよびファームウェアを抽出します。 コマンド プロンプト ウインドウを開き、コマンド プロンプトで次のいずれかのコマンドを入力します。
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro 4"`

3.  構成マネージャー コンソールで、[ **ソフトウェアライブラリ** ] \> [ **オペレーティングシステム** ] \> [ **ドライバー** ] に移動し、[ **ドライバーのインポート** ] を選択します。

4.  [ **次のネットワーク パス (UNC) にあるすべてのドライバーをインポート** ] を選択し、ソース フォルダーを選択します (例: C:\\_Sources\\ドライバー\\Surface Pro)。そして [ **次へ** ] を選択します。

5.  [ **インポートされたドライバーの詳細を指定する** ] のページで、一覧表示されているすべてのドライバーを選択し、[ **これらのドライバーを有効にして、コンピューターにインストールできるようにする** ] を選択します。

6.  [ **カテゴリ** ] を選択し、Surface のモデルと一致する新しいカテゴリを作成し、[ **OK** ] を選択し、[ **次へ** ] を選択します。

7.  **[新しいパッケージ]** を選択します。

8.  Surface Pro のモデルと一致するパッケージ名を指定し、ドライバー パッケージ ファイルを格納するフォルダーのパスを入力して、[ **OK** ] を選択し、[ **次へ** ] を選択します。

9.  [ **ブート イメージ** ] のページで、ブート イメージが選択されていないことを確認してから、[ **次へ** ] を選択します。

10. **[閉じる]** を選択します。

11. [ **ソフトウェア ライブラリ** ] \> [ **オペレーティング システム** ] \> [ **ドライバー** ] フォルダーに移動し、[ **フォルダー \> フォルダーの作成** ] を選択し、ドライバーをインポートした Surface Pro のモデルと一致するフォルダー名を入力します。

12. インポートされたすべてのドライバーを新たに作成したフォルダーに移動すると、操作が簡単になります。

> [!NOTE]
> 他の Surface Pro のモデルにも同じ手順を繰り返します。 詳細については、[「構成マネージャーでドライバーを管理する」](https://docs.microsoft.com/configmgr/osd/get-started/manage-drivers) を参照してください。

### <a name="create-microsoft-teams-rooms-configuration-package"></a>Microsoft Teams Rooms 構成パッケージの作成

1.  構成マネージャー コンソールから、[ **ソフトウェアライブラリ** ] \> [ **アプリケーションの管理** ] \> [ **パッケージ** ] に移動し、[ **パッケージの作成** ] を選びます。

2.  パッケージを作成するには、次の情報を入力します。

    -   名前: **SRS v2 - SRS セットアップパッケージを構成する**

    -   製造元: **Microsoft Corporation**

    -   バージョン: **1.0.0**

    -   [ **このパッケージには、ソース ファイルが含まれています** ] のチェック ボックスを選択し、 **SRS v2 - SRS セットアップの構成** フォルダーのパスを入力し、[ **次へ** ] を選択します。

3.  [ **プログラムを作成しない** ] を選択し、[ **次へ** ] を選択します。

4.  [ **設定の確認** ] を確認して、[ **次へ** ] を選択します。

5.  **[閉じる]** を選択します。



## <a name="distribute-configuration-manager-packages"></a>構成マネージャー パッケージの配布

すべてのパッケージを、構成マネージャーの階層の配布ポイントの役割が割り当てられているサーバーに配布する必要があります。 パッケージの配布を開始するには、次の手順に従います。

1.  ソフトウェアパッケージを配布します。

    1.  構成マネージャー コンソールで、 [ **ソフトウェアライブラリ** ] \> [ **アプリケーション管理** ] \> [ **パッケージ** ] に移動します。 配布するソフトウェアパッケージをすべて選択し、[ **コンテンツの配布** ] を選びます。

    2.  パッケージのリストを確認し、[ **次へ** ] を選択します。

    3.  すべての配布ポイントサーバー (または、構成マネージャーの階層によっては、配布ポイントグループ) を一覧に追加し、[ **次へ** ] を選択します。

    4.  [ **OK** ] を選択し、[ **閉じる** ] を選択します。

2.  ドライバー パッケージを配布します。

    1.  構成マネージャー コンソールで、[ **ソフトウェア ライブラリ** ] \> [ **オペレーティング システム** ] \> [ **ドライバー パッケージ** ] に移動します。 配布したいすべてのドライバーパッケージを選択し、[ **コンテンツの配布** ] を選択します。

    2.  パッケージのリストを確認し、[ **次へ** ] を選択します。

    3.  すべての配布ポイントサーバー (または、構成マネージャーの階層によっては、配布ポイントグループ) を一覧に追加し、[ **次へ** ] を選択します。

    4.  [ **OK** ] を選択し、[ **閉じる** ] を選択します。

3.  オペレーティング システム パッケージを配布します。

    1.  構成マネージャー コンソールで、[ **ソフトウェア ライブラリ** ] \> [ **オペレーティングシステム** ] \> [ **オペレーティング システム イメージ** ] に移動します。。 配布したいすべてのオペレーティング システム イメージを選択し、[ **コンテンツの配布** ] を選択します。

    2.  パッケージのリストを確認し、[ **次へ** ] を選択します。

    3.  すべての配布ポイントサーバー (または、構成マネージャーの階層によっては、配布ポイントグループ) を一覧に追加し、[ **次へ** ] を選択します。

    4.  [ **OK** ] を選択し、[ **閉じる** ] を選択します。

> [!NOTE]
> パッケージの配布には、パッケージサイズ、構成マネージャーの階層、配布ポイント サーバーの数、およびネットワークで使用可能な帯域幅によって、時間がかかる場合があります。
> 
> Microsoft Teams Rooms の展開を開始する前に、すべてのパッケージを配布する必要があります。
> 
> 構成マネージャー コンソールでパッケージ配布の状態を確認するには、 [ **監視** ] \> [ **配布状態** ] \> [ **コンテンツの状態** ] に進みます。

## <a name="configuration-manager-task-sequences"></a>構成マネージャーのタスク シーケンス

構成マネージャーでタスク シーケンスを使用して、オペレーティング システム イメージを対象のコンピューターに展開する手順を自動化します。 Microsoft Teams Rooms ユニットを自動で展開するには、対象の Microsoft Teams Rooms コンピューターの起動に使用したブート イメージ、インストールする Windows 10 Enterprise オペレーティング システム イメージ、およびその他のアプリケーションやソフトウェアアップデートなどの追加コンテンツを参照するタスク シーケンスを作成します。

### <a name="import-the-sample-task-sequence"></a>サンプル タスク シーケンスをインポートする

サンプル タスク シーケンスをダウンロードして簡単にインポートし、必要に応じてカスタマイズすることができます。

1.  サンプル タスク シーケンスを [**ダウンロード**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)し、共有の場所にダウンロードした zip ファイルをコピーします。
2.  構成マネージャー コンソールで、 [ **ソフトウェア ライブラリ** ] \> [ **オペレーティングシステム** ] \> [ **タスクシーケンス** ] に移動し、[ **インポート タスク シーケンス** ] を選びます。

3.  [ **参照** ] を選択して、手順 1 で使用した共有フォルダーの場所に移動し、 **Microsoft Teams Rooms の展開 (EN-US).zip** ファイルを選択し、[ **次へ** ] を選択します。

4.  [ **アクション** ] を [ **新規作成** ] に設定し、[ **次へ** ] を選択します。

5.  設定を確認して、[ **次へ** ] を選択します。

6.  **[閉じる]** を選択します。

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a>参照パッケージが各タスク シーケンスの手順に正しくリンクされていることを確認します。

1. インポートされたタスク シーケンスを選択し、[ **編集** ] を選択します。

    タスク シーケンス エディターが開き、Microsoft Teams Rooms ユニットを展開して構成するために必要な一連の手順が表示されます。

2. 各手順に従って、推奨される更新プログラムを完了します。

   1. **Windows PE での再起動** : この手順では、コンピューターを再起動し、Windows PXE に起動します。 この手順では、変更は必要ありません。

   2. **パーティションディスク 0 – UEFI** : この手順では、ディスク構成を消去し、構成された設定に基づいてパーティションを作成します。 このステップは変更しないことをお勧めします。

   3. **SRS コンピューター名を設定する** : この手順には、展開時に Microsoft Teams Rooms ユニットのコンピュータ名を設定するための UI を提供する HTML アプリケーションが含まれています。
      -  これは省略可能な手順ですが、代替プロセスを使用してコンピューター名を管理する場合にのみ無効にすることができます。
      -  **SRS v2 - Set-SRSComputerName** パッケージが選択されていることを確認します。 表示されない場合は、パッケージを参照して選択します。

   4. **オペレーティングシステムの適用** : この手順では、展開するオペレーティング システム イメージと、使用する無人 Sysprep 応答ファイルを指定します。
      -  正しい Windows 10 Enterprise オペレーティング システム イメージ ファイルが選択されていることを確認します。
      -  [ **カスタム インストールに無人または Sysprep 応答ファイルを使用する** ] が有効になっており、[ **SRS v2 - Sysprep パッケージ** ] が選択されていることを確認します。 また、 **ファイル名** が **unattend.xml** に設定されていることを確認します。

   5. **Windows の設定を適用する** : この手順では、Windows のインストールに関する情報を収集します。
      -  プロダクト キー、ローカル管理者アカウントのパスワード、タイムゾーン (必要に応じて) を含むライセンスと登録情報を提供します。

   6. **ネットワークの設定を適用する** : この手順では、ワークグループまたは Active Directory ドメイン名と組織ユニットを指定できます。
      > [!NOTE]
      > Microsoft Teams Rooms ユニットをActve Directory ドメインのメンバーとして展開する際に必要な推奨されるアクションについては、[「Skype ミーティング システム ドメイン結合の際に考慮する事項」](domain-joining-considerations.md)を参照してください。
   7. **ドライバーの適用:** この手順は、お使いの Surface Pro のモデルに基づいた、適用可能なデバイスドライバとファームウェアを展開するために使用します。 各手順を更新して、この展開に関連付けられている関連するドライバー パッケージを指定します。
      -   各ドライバーパッケージでは、Windows Management Instrumentation (WMI) フィルターを使用し、 Surface Pro のモデルに基づいて関連性の高いドライバーやファームウェアを展開します。
      -   展開が失敗するおそれがありますので、これらのドライバーの構成を変更しないことを強くお勧めします。

   8. **Windows と構成マネージャーをセットアップする** : この手順では、構成マネージャー クライアントを展開し、構成します。 組み込みの構成マネージャー クライアント パッケージを指定するには、この手順を更新します。

   9. **ルート証明書をインストールする** : この手順では、ドメインに参加していないデバイスのルート証明書を配布します。そのため、既定では無効となっており省略可能です。
      -   Microsoft Teams Rooms ユニットにルート証明書を展開する必要がある場合は、この手順を有効にします。
      -   この手順を実行する必要がある場合は、 **「SRS v2 – ルート証明書パッケージ」** と「 **64 ビット ファイル システム リダイレクトを無効にする** 」 が選択されていることを確認します。

   10. **監視エージェントをインストールして構成する** : この手順では、64 ビット版の Microsoft Azure Monitor エージェントをインストールし、ログ分析ワークスペースに接続するようにエージェントを構成します。
       -   この手順は既定では無効になっています。 監視エージェントを使用して Microsoft Teams Rooms の状態を監視する場合にのみ、この手順を有効にします。
       -   この手順を編集して、コマンドライン パラメーターを更新し、 **ワークスペース ID** と **ワークスペース キー** を指定します。
       -   運用管理スイートのワークスペース ID と主キーを取得に関する詳細については、「[Azure の監視用にテストデバイスを構成する](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring)」 を参照してください。
       -   「 **SRS v2 – Microsoft Monitoring Agent パッケージ** 」 と 「 **64 ビット ファイル システム リダイレクトを無効にする** 」 が選択されていることを確認します。
       -   Microsoft Teams Rooms の展開の状態を監視する方法の詳細については、「[Azure Monitor を使った Microsoft Teams Rooms 管理の計画](azure-monitor-plan.md)」、「[Azure Monitor を使った Microsoft Teams Rooms 管理の展開](azure-monitor-deploy.md)」、「[Azure Monitor を使った Microsoft Teams Rooms デバイスの管理](azure-monitor-manage.md)」を参照してください。

   11. **SRS v2 構成ファイルのコピー** : この手順では、Microsoft Teams Rooms の展開キットから、ローカル ハード ドライブに必要なセットアップファイルと構成ファイルをコピーします。 この手順では、カスタマイズは必要ありません。
       -   「 **SRS v2 – SRS アプリケーション パッケージ** 」 と「 **64 ビットファイルシステムのリダイレクトを無効にする** 」 が選択されていることを確認します。

   12. **Install-SRSv2-OS-Updates** : この手順では、Microsoft Teams Rooms の展開に必要なオペレーティング システムの更新プログラムを展開します。 以下の操作を行います。
       -   「[Microsoft Teams Rooms コンソールを構成する](console.md)」 をチェックして、必要な更新プログラムを確認します。
       -   **SRS v2 – OS 更新プログラム** パッケージに、必要な更新プログラムがすべて含まれていることを確認します。
       -   **SRS v2 – OS 更新プログラム パッケージ** が選択されていることを確認します。
       -   PowerShell の実行ポリシーが **バイパス** に設定されていることを確認します。

   13. **コンピューターを再起動する** : この手順では、オペレーティング システムの必要な更新プログラムのインストール後にコンピューターを再起動します。 この手順では、カスタマイズは必要ありません。

   14. **Windows コンポーネントを構成する** : この手順では、必要な Windows の機能を構成します。 この手順では、カスタマイズは必要ありません。

   15. **コンピューターを再起動する** : この手順では、Windows の機能を構成した後にコンピューターを再起動します。 この手順では、カスタマイズは必要ありません。

   16. **ローカル Skype ユーザーの追加** : この手順では、Windows に自動サインインして Microsoft Teams Rooms アプリケーションを起動するために使用するローカル Skype アカウントを作成します。 この手順には関連付けられているソフトウェアパッケージはありません。カスタマイズする必要はありません。

   17. **SRS アプリケーションをセットアップして構成する** : この手順では、オペレーティング システムの次の起動用に Microsoft Teams Rooms アプリケーションをインストールします。
       -   「 **SRS v2 – SRS セットアップ パッケージの構成** 」 と 「 **64 ビット ファイル システムのリダイレクトを無効にする** 」 が選択されていることを確認します。

> [!IMPORTANT]
> タスク シーケンスのステップは、指定された順序である必要があります。 ステップの順序を変更したり、追加の手順を構成したりすると、展開が破損する場合があります。
>
> **SRS アプリケーションのセットアップと構成** のステップは、タスク シーケンスの最後の手順である必要があります。それ以外の場合は、展開が失敗する可能性があります。

### <a name="create-deployment-for-the-task-sequence"></a>タスク シーケンスの展開を作成する

1. タスク シーケンスを選択し、[ **展開** ] を選択します。

2. [ **参照** ] を選択して、展開用のターゲット コレクションを選択します。

3. [ **すべての不明なコンピューター** ] を選択し、[ **OK** ] を選択します。

4. [ **次へ** ] を選択します。

5. **「目的」** のドロップ ダウン リストから、[ **使用可能** ] を選択します。

6. **「次のリストで利用可能にする」** で[ **メディアと PXE のみ** ] を選択し、[ **次へ** ] を選択します。
   > [!WARNING]
   > [ **目的** ] は、[ **使用可能** ] に設定されている必要があります。 [ **目的** ] が、 [ **必須** ]に設定されて **いない** ことを確認します。 また、 **「次に利用可能にする」** で、[ **メディアとPXEのみ** ] を選択していることを確認してください。
   >
   > これらの値を別の値に設定すると、起動したときに、すべてのコンピューターで Microsoft Teams Rooms の展開イメージが表示されることがあります。
7. スケジュールを指定せずに、 [ **次へ** ] を選択します。

8. [ **ユーザーエクスペリエンス** ] セクション内の内容を変更せずに、[ **次へ** ] を選択します。

9. [ **アラート** ] セクション内の内容を変更せずに、[ **次へ** ] を選択します。

10. [ **配布ポイント** ] セクション内の内容を変更せずに、[ **次へ** ] を選択します。

11. 設定を確認して、[ **次へ** ] を選択します。

12. **[閉じる]** を選択します。

<a name="validate-and-troubleshoot-the-solution"></a>ソリューションの検証およびトラブルシューティングを行う
--------------------------------------

Microsoft Endpoint Configuration Manager のタスク シーケンスを完了したら、タスク シーケンスが Microsoft Teams Rooms ユニットを展開し構成できることを検証するため、テスト実行を行う必要があります。

1.  サポートされているイーサネット アダプターのいずれかを使用するか、Surface dock を使用して、テスト デバイスをケーブル ネットワークに接続します。 使用している環境に PXE ブート機能が構成されていない場合は、[以前に作成した](https://docs.microsoft.com/configmgr/osd/deploy-use/create-bootable-media) USB フラッシュ ドライブのブート イメージを使用して USB から起動し、構成マネージャーに接続することができます。

2.  ファームウェアにアクセスし、PXE ブートを開始します。

    1.  Surface デバイスの電源が切れていることを確認します。

    2.  **「音量を上げる」** ボタンを長押しします。

    3.  **電源ボタン** を押して、離します。

    4.  デバイスが起動したら、 **「音量を上げる」** ボタンを放します。

    5.  **「ブート構成」** を選びます。

    6.  次のいずれかの操作を行います。

        -   [ **PXE ブート** ] を選択し、リストの先頭にドラッグします。 または、ネットワーク アダプターを左にスワイプして、デバイスからすぐに起動することもできます。 これは、ブート順序には影響しません。
        -   ブート メディアを含む USB フラッシュドライブを選びます。

3.  [ **終了** ] を選択し、[ **今すぐ再起動** ] を選択します。

4.  メッセージが表示されたら、ネットワーク ブート サービスの [ **実行** ] を選択します。

5.  Windows PE がメモリに読み込まれ、タスク シーケンス ウィザードが起動します。 [ **次へ** ] を選んで続行します。

6.  以前にインポートしたタスク シーケンスを選択し、[ **次へ** ] を選択します。

7.  ディスク構成が適用されると、デバイスのコンピューター名を指定するように求められます。 ユーザー インターフェイスには、Surface Pro デバイスのシリアル番号に基づいて推奨されるコンピューター名が表示されます。 提案された名前を受け入れるか、新しい名前を指定します。 コンピューター名の割り当て画面の指示に従います。 [ **承諾** ] を選択すると、展開が始まります。

8.  展開プロセスの残りの部分は自動的に行われ、ユーザーからの入力を求めることはありません。

9.  展開タスクのシーケンスでデバイスの構成が完了すると、Microsoft Teams Rooms のアプリケーション設定を構成するように求める次の構成画面が表示されます。

    ![Microsoft Teams Rooms アプリケーションの初期セットアップ画面](../media/room-systems-scale-image2.png)

10.  Surface Pro を Microsoft Teams Rooms コンソールに接続し、アプリケーション設定を構成します。

11.  [Microsoft Teams Rooms ヘルプ](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)に記載されている機能が、展開されたデバイスで機能していることを検証します。


インストールの失敗をトラブルシューティングするには、 **SMSTS.log** ファイルを確認します。このファイルは、構成マネージャー タスク シーケンスで実行されたすべてのステップを記録します。

SMSTS.log ファイルは、ビルド プロセスのステージに応じて、多くのパスの内のいずれかに格納されます。 次の表を確認し、SMSTS.log ファイルへのパスを確認します。


| **展開フェーズ**                                                            | **タスク シーケンスのログのパス**                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| WinPE (HDD フォーマット以前)                                                        | X:\\Windows\\Temp\\smstslog\\smsts.log             |
| WinPE (ハードフォーマット以降)                                                         | C:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log    |
| 構成マネージャー エージェントをインストールする前に、オペレーティング システムが展開された | c:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log    |
| オペレーティングシステムと構成マネージャー エージェントが展開されている                   | % windir%\\System32\\ccm\\logs\\Smstslog\\smsts.log |
| タスク シーケンスの実行が完了しました                                                | %windir%\\System32\\ccm\\logs\\smsts.log           |

> [!TIP]
> タスクシーケンスの実行中に、いつでも **F8** を選択してコマンド コンソールを開くことができ、 SMSTS.log ファイルにアクセスします。

PXE ブートの問題のトラブルシューティングを行うには、PXE のアクション固有の、構成マネージャー サーバー上の 2 つのログファイルを確認します。

-   構成マネージャー インストール ログ ディレクトリにある **Pxecontrol.log**

-   構成マネージャー 管理ポイント (MP) logs ディレクトリにある **Smspxe.log**

構成マネージャーのインストールの詳細なトラブルシューティングに使用できるログファイルの完全なリストについては、「Microsoft Endpoint Configuration Manager [ログファイルの参照](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/log-files)」を参照してください。
