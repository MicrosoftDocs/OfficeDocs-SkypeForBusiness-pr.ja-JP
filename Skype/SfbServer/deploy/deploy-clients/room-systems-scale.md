---
title: システム センター構成マネージャーを使用して Microsoft チームの会議室を配置します。
author: jambirk
ms.author: jambirk
ms.reviewer: Turgayo
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
ms.collection: M365-voice
description: 大規模な展開でマイクロソフト チームの会議室を展開する方法については、このトピックを参照してください。
ms.openlocfilehash: fe6ffee0c6ab86496204ab4e17b86cc84a70a2a7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214916"
---
# <a name="deploy-microsoft-teams-rooms-by-using-system-center-configuration-manager"></a>システム センター構成マネージャーを使用して Microsoft チームの会議室を配置します。

この記事では、システム センター構成マネージャーを使用して、マイクロソフト チームの会議室の環境を作成するために必要なすべての情報を提供します。

システム センター構成マネージャーで提供される使用する方法、オペレーティング システムと複数のターゲット ・ デバイスには、他のアプリケーションを導入できます。

指示に従って、構成マネージャーの構成を以下に示す方法を使用し、サンプル パッケージと、組織の必要に応じて、このガイドで提供されているスクリプトをカスタマイズします。

![構成マネージャーを使用して Microsoft チームの会議室の展開プロセス](../../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> このソリューションは、Surface Pro ベースの環境でのみテストされています。 Surface Pro に基づかない場合、製造元のガイドラインに従います。

## <a name="validate-prerequisites"></a>前提条件を検証します。

マイクロソフト チームの会議室の構成マネージャーを使用してを展開するには、次の前提条件と要件を満たすことを確認します。

### <a name="system-center-configuration-manager-requirements"></a>システム センター構成マネージャーの要件

-   システム センター構成マネージャーのバージョンは、少なくとも 1706 をする必要がありますまたはそれ以上です。 1710 またはそれ以降を使用することをお勧めします。 [サポートの Windows 10 ですシステム センター構成マネージャーで](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client)の構成マネージャーをサポートしている 10 の Windows のバージョンに関する詳細をご覧ください。

-   Windows の評価と 10 の Windows の展開キット (ADK) のサポートされているバージョンをインストールする必要があります。 さまざまなバージョンの構成マネージャーを使用して、展開に適切なバージョンが含まれていることを確認する[10 ADK の Windows](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-adk)のバージョンを参照してください。

-   サイト システム サーバーする必要があります割り当てられている配布ポイントの役割とのネットワークによる展開を有効にするのには、[プレブート実行環境 (PXE) のサポート](https://docs.microsoft.com/sccm/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network)を有効にするブート イメージです。 Pxe ブートのサポートが有効でない場合は、展開では、[ブータブル メディア](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network)を使用できます。

-   コンピューター (ベア メタル) の新しい展開シナリオをサポートするためには、ネットワーク アクセス アカウントを構成しなければなりません。 ネットワーク アクセス アカウントの構成に関する詳細については、[システム センター構成マネージャーでのコンテンツにアクセスするアカウントの管理](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)を参照してください。

-   複数のユニットを同時に同じマイクロソフト チームの会議室のイメージを展開する場合、[マルチキャスト サポート](https://docs.microsoft.com/sccm/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network)を有効にすることをお勧めします。

### <a name="networking-requirements"></a>ネットワーク要件

-   ネットワークには、動的ホスト構成プロトコル (DHCP) サーバーは、マイクロソフト チームの会議室のユニットを配置する場所のサブネットに IP アドレスの配分を自動で構成されている必要があります。

    > [!NOTE]
    > DHCP のリース期間は、イメージの展開期間よりも長い値に設定しなければなりません。 それ以外の場合、展開が失敗する可能性があります。

-   PXE をサポートするためにスイッチ、仮想 Lan (Vlan) など、ネットワークを構成する必要があります。 IP ヘルパーと PXE の構成の詳細については、ネットワークの製造元を参照してください。 または、pxe ブートのサポートが有効になっていない場合は、展開の場合、[起動可能なメディア](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network)を使用できます。

    > [!NOTE]
    > Surface Pro のイーサネット アダプターまたはマイクロソフトからのドッキング ステーションを使用する場合のみ、デバイス、ネットワーク (PXE ブート) からの起動がサポートされます。 Surface Pro で PXE ブートをサポートしていないサードパーティ製のイーサネット アダプターです。 詳細については、[イーサネット アダプターとサーフェスの配置](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment)を参照してください。

## <a name="configure-system-center-configuration-manager-for-operating-system-deployment"></a>システム センター構成マネージャーをオペレーティング システムの展開の構成します。

この資料では、既に正常なシステム センター構成マネージャーの展開があり、詳細を展開し、最初から構成マネージャーを構成するために必要なすべての手順を実行しないと仮定します。 [ドキュメントおよび構成ガイド](https://docs.microsoft.com/sccm/)、システム センター構成マネージャーでは、優れたリソースです。構成マネージャーをまだ展開していない場合、これらのリソースを開始することをお勧めします。

オペレーティング システムの展開 (OSD) 機能が正しく構成されていることを確認するのにには、次の手順を使用します。

### <a name="validate-and-upgrade-configuration-manager"></a>検証し、構成マネージャーのアップグレード

1.  構成マネージャー コンソールで、**管理**ページに移動\>**の更新プログラムおよびサービス**です。

2.  まだインストールされていない適用可能な更新プログラム、インストールされているビルドを確認します。

3.  [10 System Center 構成マネージャーでの Windows のサポート](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client)を確認します。配置をアップグレードする場合をインストールする更新プログラムを選択し、**ダウンロード**します。

4.  ダウンロードが完了した後、更新プログラムを選択し、**更新パックをインストール**します。

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a>PXE、マルチキャストをサポートするために配布ポイントを構成します。

1.  構成マネージャー コンソールで、**管理**ページに移動\>**の配布ポイント**です。

2.  マイクロソフト チームの会議室の配置、サービスを提供し、**プロパティ**を選択し、配布ポイント サーバーを選択します。

3.  **PXE** ] タブを選択し、次の設定が有効になっていることを確認します。
    -   クライアントの pxe ブートのサポートを有効にします。
    -   受信 PXE 要求に応答するには、この配布ポイントを許可します。
    -   不明なコンピューターのサポートを有効にします。

4.  *オプション:* マルチキャスト サポートを有効にするには、[**マルチキャスト**] タブを選択し、[次の設定が有効になっていることを確認します。
    -   同時に複数のクライアントにデータを送信するマルチキャストを有効にします。
    -   ネットワーク チームの勧告に UDP ポートの範囲を構成します。

### <a name="configure-the-network-access-account"></a>ネットワーク アクセス アカウントを構成します。

1.  構成マネージャー コンソールで、**管理**ページに移動\>**サイトの構成** \> **サイト**、およびサイトを選択します。

2.  [**設定**] で、**サイトのコンポーネントの構成**を選択します\>**ソフトウェアの配布**。

3.  [**ネットワーク アクセス アカウント**] タブを 1 つまたは複数のアカウント] をクリックし **[ok]** を選択します。

> [!NOTE]
> アカウントには、配布ポイント サーバー上の**ネットワークからこのコンピューターへアクセス**を除く、任意の特別な権限が必要がありません。 汎用的なドメイン ユーザー アカウントに適切ななります。 詳細については、[システム センター構成マネージャーでのコンテンツにアクセスするアカウントの管理](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)を参照してください。

### <a name="configure-a-boot-image"></a>ブート イメージを構成します。

1.  **ソフトウェア ライブラリ**には、構成マネージャー コンソールで、 \> **のオペレーティング システム** \> **のブート イメージ**です。

2.  **ブート イメージ (x64)** を選択し、[**プロパティ**] を選択します。

3.  **データ ソース**] タブを選択し、 **PXE が有効な配布ポイントからは、このブート イメージの展開**を有効にします。

4.  必要なコンポーネントをインストールするのには [**オプション コンポーネント**] タブを選択します。

    1.  スターのアイコンを選択し、 **HTML (WinPE HTA)** を検索

    2.  ブート イメージへの HTML アプリケーションのサポートを追加するのには **[ok]** を選択します。

5.  *オプション:* 展開のエクスペリエンスをカスタマイズするには、[**カスタマイズ**] タブを選択します。
    -   展開時に、コマンド プロンプトへのアクセスが必要な場合 **(テストのみ)] コマンドのサポート**を有効にします。 これを有効にすると、展開中に**f8 キー**を選択してコマンド プロンプトを起動できます。
    -   展開時に表示するカスタムの背景イメージを指定することもできます。 イメージを設定するを有効にする**カスタムの背景イメージのファイルを指定 (UNC パス**の背景を選択します。

6.  ダイアログ ボックスが表示されたら、 **[はい]** を選択し、配布ポイントに更新されたブート イメージを配布します。

詳細については、[ブート イメージの管理システム センター構成マネージャーの使用](https://docs.microsoft.com/sccm/osd/get-started/manage-boot-images)を参照してください。

> [!NOTE]
> Pxe ブートのサポートがない環境の構成マネージャー タスク シーケンスに基づく展開を開始する起動可能な USB メディアを作成することができます。 のみブート イメージ、prestart コマンドのオプションと、必要なファイル、および構成マネージャーのバイナリ Windows PE を起動し、展開プロセスの残りの部分の構成マネージャーへの接続をサポートするために、ブート可能なメディアが含まれます。 詳細については、[ブータブル メディアを作成する方法](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia)を参照してください。

## <a name="create-configuration-manager-packages"></a>構成マネージャー パッケージを作成します。

構成マネージャーでは、いくつかのパッケージを展開し、マイクロソフト チームの会議室の単位を構成する必要があります。

作成し、次のパッケージを構成する必要があり、配布ポイント サーバーの役割が割り当てられている構成マネージャー サイト システムに配布します。

| **パッケージ名**                     | **型**               | **説明**                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| SRS v2 の SRS のアプリケーション パッケージ     | ソフトウェア パッケージ       | マイクロソフト チーム ルーム展開キットのパッケージ                                      |
| SRS v2 の Sysprep パッケージ             | ソフトウェア パッケージ       | マイクロソフト チームの会議室の単位を構成するのにはカスタムの Unattended.xml 用のパッケージ            |
| SRS v2 - セット-SRSComputerName パッケージ | ソフトウェア パッケージ       | パッケージの展開時にコンピューター名を割り当てるには、HTML アプリケーション (HTA)    |
| SRS v2 の SRS の設定を構成します。         | ソフトウェア パッケージ       | マイクロソフト チーム ルーム アプリケーションの展開を構成するパッケージ                          |
| SRS v2 - OS の更新パッケージ          | ソフトウェア パッケージ       | オペレーティング システムの必須更新プログラムを展開するパッケージ                                      |
| SRS v2 のルート証明書のパッケージ    | ソフトウェア パッケージ       | オプション - (ドメインに参加しているユニットは必要ありません) ルート証明書を展開するためのパッケージ  |
| SRS v2 - エージェント パッケージを監視する Microsoft | ソフトウェア パッケージ       | オプション ・ パッケージを展開し、運用管理スイートの Microsoft エージェントを構成するには|
| SRS v2 の WinPE の背景のパッケージ    | ソフトウェア パッケージ       | ブート イメージを使用するカスタムの背景イメージのパッケージ                           |
| 10 の Windows エンタープライズ                | オペレーティング システムのイメージ | オペレーティング システム インストール ファイル (install.wim) 用のパッケージ                          |
| Surface Pro                          | ドライバー パッケージ         | Microsoft Surface Pro のファームウェアとデバイス ドライバーのパッケージ                     |
| Surface Pro 4                        | ドライバー パッケージ         | Microsoft Surface Pro 4 のファームウェアとデバイス ドライバーのパッケージ                   |

詳細については、[パッケージとプログラムで、システム センター構成マネージャー](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs)を参照してください。

### <a name="create-folders-for-the-package-source-files"></a>パッケージのフォルダーを作成するには、ソース ファイル

構成マネージャーには、パッケージのソース ファイルを最初に作成しているとき、および更新されるときに特定のフォルダー構造で整理することが必要です。

システム センター構成マネージャー サーバーの全体管理サイトまたはプライマリ サイト、またはを使用してパッケージのソース ファイルをホストするサーバー共有には、次のフォルダー構造を作成します。

-   SRS v2 - エージェント パッケージを監視する Microsoft
-   SRS v2 - OS の更新パッケージ
-   SRS v2 のルート証明書のパッケージ
-   SRS v2 - セット-SRSComputerName パッケージ
-   SRS v2 の SRS のアプリケーション パッケージ
-   SRS v2 の SRS の設定を構成します。
-   SRS v2 の Sysprep パッケージ
-   ドライバー
    -   Surface Pro
    -   Surface Pro 4
-   オペレーティング ・ システム
    -   10 の Windows エンタープライズ

> [!TIP]
> [ダウンロード](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)にも可能性があり、パッケージ スクリプトを使用する必要がありますが、インポートする必要があるタスク シーケンスのテンプレート用のフォルダー構造を含む zip ファイルを使用します。

### <a name="create-the-monitoring-agent-package"></a>監視エージェント パッケージを作成します。

1. 監視エージェントをダウンロード<https://go.microsoft.com/fwlink/?LinkId=828603>。

2. コマンド プロンプト ウィンドウを開き、コマンド プロンプトで**MMASetup AMD64.exe の指定**を入力する**SRS v2 - マイクロソフトの監視エージェントのパッケージ**フォルダーにパッケージを抽出します。

3. **ソフトウェア ライブラリ**には、構成マネージャー コンソールで、 \> **アプリケーション管理** \> **パッケージ**、および**パッケージの作成**を選択します。

4. パッケージを作成するのには次の情報を入力します。

   - 名前<strong>: SRS v2 - エージェント パッケージを監視する Microsoft</strong>

   - 製造元<strong>: Microsoft Corporation</strong>

   - バージョン<strong>: 8.1.11081.0</strong> (ダウンロードしたインストール ファイルのバージョンを入力してください)

   - **このパッケージにソース ファイルが含まれています**] チェック ボックスをオンに、 **SRS の v2 - マイクロソフトの監視エージェントのパッケージ**のフォルダーにパスを入力し、**次へ**。

5. **プログラムを作成しない**を選択し、**次へ**します。

6. **設定の確認**] ページを確認し、**次へ**を選択します。

7. **閉じる**を選択します。

### <a name="create-the-operating-system-updates-package"></a>オペレーティング システム更新プログラム パッケージを作成します。

1. **SRS v2 - OS の更新プログラム パッケージ**のフォルダーに**インストール-SRSv2-OS の Updates.ps1**をという名前の新しい PowerShell スクリプトを作成します。

2. **インストール-SRSv2-OS の Updates.ps1**スクリプトに以下のスクリプトをコピーします。 または、[ここ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)からインストール-SRSv2-OS の Updates.ps1 スクリプトをダウンロードできます。
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
3. 必須の Windows 更新プログラム パッケージを同じフォルダーにダウンロードします。
   > [!NOTE]
   > この資料が公開された時点で、 [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu)だけが必要でした。 [マイクロソフト チームの会議室のコンソールを構成する](console.md)、他の更新プログラムが必要なかどうかを確認してください。

4. **ソフトウェア ライブラリ**には、構成マネージャー コンソールで、 \> **アプリケーション管理** \> **パッケージ**、および**パッケージの作成**を選択します。

5. パッケージを作成するのには次の情報を入力します。
   -   名前: の**SRS v2 – OS パッケージを更新します。**
   -   製造元: **Microsoft Corporation**
   -   バージョン: **1.0.0**
   -   **このパッケージにソース ファイルが含まれています**] チェック ボックスをオンに、 **SRS の v2 - OS の更新プログラム パッケージ**のフォルダーにパスを入力し、**次へ**。

6. **プログラムを作成しない**を選択し、**次へ**します。

7. **設定の確認**] ページを確認し、**次へ**を選択します。

8. **閉じる**を選択します。

### <a name="create-the-root-certificate-package-optional"></a>ルート証明書のパッケージを作成する (省略可能)

Active Directory ドメインに参加しないデバイスのルート証明書を配布するには、このパッケージを作成します。 次の両方の条件を適用する場合にのみ、このパッケージを作成します。
-   展開には、設置が含まれています Lync または Skype ビジネス サーバー用です。
-   マイクロソフト チームの会議室の単位は、ドメインのメンバーではなくワークグループで作業するのには構成されます。

1.  ルート証明書を**SRS v2: ルート証明書のパッケージ**フォルダーにコピーします。

2.  **ソフトウェア ライブラリ**には、構成マネージャー コンソールで、 \> **アプリケーション管理** \> **パッケージ**、および**パッケージの作成**を選択します。

3.  パッケージを作成するのには次の情報を入力します。
    -   **SRS v2: ルート証明書のパッケージ**の名前。
    -   製造元:*組織の名前*
    -   バージョン: **1.0.0**
    -   **このパッケージにソース ファイルが含まれています**] チェック ボックスをオンに、 **SRS のバージョン 2: ルート証明書のパッケージ**のフォルダーにパスを入力し、**次へ**。

4.  **プログラムを作成しない**を選択し、**次へ**します。

5.  **設定の確認**] ページを確認し、**次へ**を選択します。

6.  **閉じる**を選択します。

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a>マイクロソフト チーム ルーム展開キットのパッケージを作成します。

1.  **マイクロソフト チームの会議室の導入ガイド 』** の最新バージョンをダウンロードして<https://go.microsoft.com/fwlink/?linkid=851168>、ワークステーションにインストールするとします。

2.  内容をコピーする**c:\\Program Files (x86)\\Skype ルーム システムの 『 導入ガイド 』** **SRS v2 の SRS のアプリケーション パッケージ**のフォルダーにします。

3.  **ソフトウェア ライブラリ**には、構成マネージャー コンソールで、 \> **アプリケーション管理** \> **パッケージ**、および**パッケージの作成**を選択します。

4.  パッケージを作成するのには次の情報を入力します。
    -   **SRS v2 – SRS アプリケーション パッケージ**の名前:
    -   製造元: **Microsoft Corporation**
    -   バージョン: **3.1.104.0** (ダウンロードしたインストール ファイルのバージョンを入力してください)
    -   **このパッケージにソース ファイルが含まれています**] チェック ボックスをオンに、 **SRS v2 – SRS アプリケーション パッケージ**フォルダーへのパスを入力し、[**次へ**。
5.  **プログラムを作成しない**を選択し、**次へ**します。

6.  **設定の確認**] ページを確認し、**次へ**を選択します。

7.  **閉じる**を選択します。

### <a name="create-the-computer-name-assignment-package"></a>コンピューター名のアサイン パッケージを作成します。

1.  **SRS v2 - セット SRSComputerName パッケージ**フォルダーには、**セット SRSComputerName.hta**をという名前の新しい HTML アプリケーションを作成します。

2.  **セット SRSComputerName.hta**ファイルに次のスクリプトをコピーします。 または、[ここ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)からセット SRSComputerName.hta ファイルをダウンロードできます。
    ```
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
3.  **ソフトウェア ライブラリ**には、構成マネージャー コンソールで、 \> **アプリケーション管理** \> **パッケージ**、および**パッケージの作成**を選択します。

4.  パッケージを作成するのには次の情報を入力します。

    -   **SRS v2 - セット SRSComputerName パッケージ**の名前:

    -   製造元: **Microsoft Corporation**

    -   バージョン: **1.0.0**

    -   **このパッケージにソース ファイルが含まれています**] チェック ボックスをオンに、 **SRS の v2 - セット SRSComputerName パッケージ**のフォルダーにパスを入力し、**次へ**。

5.  **プログラムを作成しない**を選択し、**次へ**します。

6.  **設定の確認**] ページを確認し、**次へ**を選択します。

7.  **閉じる**を選択します。

### <a name="create-the-sysprep-package"></a>Sysprep パッケージを作成します。

1. **SRS v2 – パッケージの Sysprep**フォルダーには、 **Unattend.xml**をという名前の新しい XML ファイルを作成します。

2. **Unattend.xml**ファイルに次のテキストをコピーします。 または、Unattend.xml ファイルを[ここ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)からダウンロードできます。
   ```
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
3. **ソフトウェア ライブラリ**には、構成マネージャー コンソールで、 \> **アプリケーション管理** \> **パッケージ**、および**パッケージの作成**を選択します。

4. パッケージを作成するのには次の情報を入力します。
   -   **SRS v2 の Sysprep のパッケージ**の名前:
   -   製造元: **Microsoft Corporation**
   -   バージョン: **1.0.0**
   -   **このパッケージにソース ファイルが含まれています**] チェック ボックスをオンに、 **SRS v2 – パッケージの Sysprep**フォルダーにパスを入力し、**次へ**。
5. **プログラムを作成しない**を選択し、**次へ**します。

6. **設定の確認**] ページを確認し、**次へ**を選択します。

7. **閉じる**を選択します。

### <a name="create-the-windows-10-enterprise-package"></a>10 エンタープライズの Windows パッケージを作成します。

1.  、10 企業の Windows x64 メディアを入手し、 **install.wim**ファイルのコピー、**のオペレーティング システム\\10 企業の Windows**フォルダー。

2.  **ソフトウェア ライブラリ**には、構成マネージャー コンソールで、 \> **のオペレーティング システム** \> **オペレーティング システム イメージ**、および [**オペレーティング システム イメージを追加**します。

3.  **Install.wim**ファイルをコピーしたパスを指定し、**次へ**を選択します。

4.  10 エンタープライズの Windows イメージのビルド番号が一致するように **[バージョン**] フィールドを更新し、**次へ**を選択します。

5.  、**詳細**ページを確認し、**次へ**を選択します。

6.  **閉じる**を選択します。

詳細については、[オペレーティング システム イメージの管理システム センター構成マネージャーの使用](https://docs.microsoft.com/sccm/osd/get-started/manage-operating-system-images)を参照してください。

### <a name="create-surface-pro-device-driver-packages"></a>Surface Pro デバイス ドライバー パッケージを作成します。

Surface Pro と Surface Pro 4 の両方のマイクロソフト チームの会議室がサポートされています。 環境内の各 Surface Pro モデル用のドライバー パッケージを作成する必要があります。

> [!IMPORTANT]
> ドライバーは、Windows 10 エンタープライズ ビルドとマイクロソフト チーム ルーム展開キットのバージョンと互換性のあるである必要があります。 詳細については、[最新のファームウェア、および表面のデバイス用のドライバーをダウンロード](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices)し[、コンソールの構成](console.md)を参照してください。

1.  最新のドライバーとファームウェアをダウンロードします。
    -   Surface Pro: の<https://www.microsoft.com/download/details.aspx?id=55484>
    -   Surface Pro の 4 を実行します。<https://www.microsoft.com/download/details.aspx?id=49498>

2.  ダウンロードしたドライバーとファームウェアを抽出します。 コマンド プロンプト ウィンドウを開き、コマンド プロンプトで次のコマンドのいずれかを入力します。
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro 4"`

3.  **ソフトウェア ライブラリ**には、構成マネージャー コンソールで、 \> **のオペレーティング システム** \> **ドライバー**、および**インポート ドライバー**を選択します。

4.  **次のネットワーク パス (UNC) のすべてのドライバーをインポート**] を選択、コピー元フォルダーを選択 (例、c:\\_Sources\\ドライバー\\Surface Pro)、し、**次へ**を選択します。

5.  **読み込まれたドライバーの詳細を指定**] ページで、一覧表示されているすべてのドライバーを選択し、選択**これらのドライバーを有効にしてコンピューターにインストールを許可します**。

6.  **カテゴリ**を選択して、サーフェス モデルと一致する新しいカテゴリを作成、 **[ok]** を選択し、**次へ**。

7.  **新しいパッケージ**を選択します。

8.  Surface Pro のモデルと一致するパッケージ名を指定して、 **[ok]** を選択して、[**次へ**]、ドライバー パッケージ内のファイルを格納するフォルダーのパスを入力します。

9.  [**ブート イメージ**] ページで、ブート イメージが選択されていると、**次へ**を選択しであることを確認します。

10. **閉じる**を選択します。

11. **ソフトウェア ライブラリ**を参照して\>**のオペレーティング システム** \> **ドライバー**を選択**フォルダー\>フォルダーの作成**、Surface Pro のドライバーをインポートしたモデルと一致するフォルダー名を入力します。

12. インポートされたすべてのドライバーを簡単に移動および操作の新しく作成したフォルダーに移動します。

> [!NOTE]
> 他の Surface Pro モデルをする必要があります、同じ手順を実行します。 詳細については、[システム センター構成マネージャーでの管理ドライバー](https://docs.microsoft.com/sccm/osd/get-started/manage-drivers)を参照してください。

### <a name="create-microsoft-teams-rooms-configuration-package"></a>マイクロソフトのチーム会議室の構成パッケージを作成します。

1.  **ソフトウェア ライブラリ**には、構成マネージャー コンソールで、 \> **アプリケーション管理** \> **パッケージ**、および**パッケージの作成**を選択します。

2.  パッケージを作成するのには次の情報を入力します。

    -   名前: **SRS v2 の SRS のセットアップ パッケージを構成します。**

    -   製造元: **Microsoft Corporation**

    -   バージョン: **1.0.0**

    -   **このパッケージにソース ファイルが含まれています**] チェック ボックスをオンに、 **SRS v2 の SRS の設定を構成する**フォルダーのパスを入力し、[**次へ**。

3.  **プログラムを作成しない**を選択し、**次へ**します。

4.  **設定の確認**] ページを確認し、**次へ**を選択します。

5.  **閉じる**を選択します。



## <a name="distribute-configuration-manager-packages"></a>構成マネージャー パッケージを配布します。

すべてのパッケージは、構成マネージャー階層内の配布ポイントの役割が割り当てられているサーバーに分散する必要があります。 パッケージの配布を開始するには、次の手順に従います。

1.  ソフトウェア パッケージを配布します。

    1.  **ソフトウェア ライブラリ**には、構成マネージャー コンソールで、 \> **アプリケーション管理** \> **パッケージ**です。 、配布するすべてのソフトウェア パッケージを選択し、**コンテンツを配布**します。

    2.  、パッケージのリストを確認し、**次へ**を選択します。

    3.  すべての配布ポイント サーバー (または、構成マネージャー階層に応じて、配布ポイント グループ) をリストに追加し、**次へ**します。

    4.  **次へ**を選択し、[**閉じる**] を選択します。

2.  ドライバー パッケージを配布します。

    1.  **ソフトウェア ライブラリ**には、構成マネージャー コンソールで、 \> **のオペレーティング システム** \> **のドライバー パッケージ**。 、配布するすべてのドライバー パッケージを選択し、**コンテンツを配布**します。

    2.  、パッケージのリストを確認し、**次へ**を選択します。

    3.  すべての配布ポイント サーバー (または、構成マネージャー階層に応じて、配布ポイント グループ) をリストに追加し、**次へ**します。

    4.  **次へ**を選択し、[**閉じる**] を選択します。

3.  オペレーティング システム パッケージを配布します。

    1.  **ソフトウェア ライブラリ**には、構成マネージャー コンソールで、 \> **のオペレーティング システム** \> **オペレーティング システムのイメージ**です。 、配布するすべてのオペレーティング システム イメージを選択し、**コンテンツを配布**します。

    2.  、パッケージのリストを確認し、**次へ**を選択します。

    3.  すべての配布ポイント サーバー (または、構成マネージャー階層に応じて、配布ポイント グループ) をリストに追加し、**次へ**します。

    4.  **次へ**を選択し、[**閉じる**] を選択します。

> [!NOTE]
> パッケージの配布には、パッケージのサイズ、構成マネージャー階層、配布ポイント サーバーの数は、ネットワークで利用できる帯域幅によっては、時間をかかる場合があります。
> 
> マイクロソフト チームの会議室のユニットを展開する前にすべてのパッケージを配布する必要があります。
> 
> 構成マネージャー コンソールで、パッケージの配布ステータスを確認するには**監視**することで\>**の配布ステータス** \> **コンテンツの状態**です。

## <a name="configuration-manager-task-sequences"></a>構成マネージャーのタスク シーケンス

使用して、タスク シーケンスがシステム センター構成マネージャーをセットアップ先のコンピューターにオペレーティング システム イメージを展開するための手順を自動化します。 自動化された方法でマイクロソフト チームの会議室のユニットを配置するには、マイクロソフト チームの会議室のセットアップ先のコンピューター、10 企業の Windows オペレーティング システム イメージをインストールしていずれかを起動するために使用するブート イメージを参照するタスク シーケンスを作成します。他のアプリケーションやソフトウェア更新プログラムなどの他の追加コンテンツ。

### <a name="import-the-sample-task-sequence"></a>サンプル タスク シーケンスをインポートします。

ダウンロードし簡単にサンプルのタスク シーケンスをインポートしてお客様のニーズを満たすためにカスタマイズできます。

1.  サンプルのタスク シーケンス[**をダウンロード**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)し、共有の場所にダウンロードした zip ファイルをコピーします。
2.  **ソフトウェア ライブラリ**には、構成マネージャー コンソールで、 \> **のオペレーティング システム** \> **タスク シーケンス**、および選択し、**タスク シーケンスのインポート**します。

3.  **参照**を選択して、手順 1 で使用する共有フォルダーの場所に、**マイクロソフト チームの会議室の展開 (EN-US) の .zip**ファイルを選択し、**次**のように選択を移動します。

4.  **アクション**を**新規作成**] を設定し、**次へ**を選択します。

5.  設定内容を確認し、**次へ**を選択します。

6.  **閉じる**を選択します。

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a>各タスク シーケンスのステップには、参照のパッケージが正しくリンクされているかを検証します。

1. 、インポートされたタスク シーケンスを選択し、**編集**を選択します。

    タスク シーケンス エディターが開き、展開し、マイクロソフト チームの会議室のユニットを構成する必要がある連続した各ステップが表示されます。

2. 各ステップを紹介し、推奨される更新プログラムを完了します。

   1. **Windows PE で再起動**: この手順が再起動し、Windows の PXE にコンピューターを起動します。 変更は、この手順で必要ではありません。

   2. **パーティション ディスク 0-UEFI**: この手順は、ディスク構成を消去し、構成した設定に基づいてパーティションを作成します。 おすべての変更この手順をお勧めします。

   3. **SRS コンピューター名の設定**: この手順には、展開時にマイクロソフト チーム ルーム単位のコンピューター名を設定するための UI を提供する HTML アプリケーションが含まれています。
      -  これはオプションの手順ですが、それのみを無効にできます、別のプロセスによって名前付けのコンピューターを管理する場合は。
      -  **SRS v2 - セット SRSComputerName**パッケージが選択されていることを確認します。 いない場合は、パッケージを参照して選択します。

   4. **オペレーティング システムの適用**: この手順は、オペレーティング システム イメージを展開して、無人 Sysprep 応答ファイルを使用するを指定します。
      -  正しい 10 企業の Windows オペレーティング システム イメージ ファイルが選択されていることを確認します。
      -  **無人を使用するかカスタム インストール用応答ファイルを Sysprep**を有効にすると、 **SRS v2 の Sysprep のパッケージ**が選択されていることを確認します。 **Unattend.xml**に**ファイル名**が設定されていることを確認もします。

   5. **Windows の設定を適用**: この手順は、Windows のインストールに関する情報を収集します。
      -  プロダクト キー、ローカルの管理者アカウントのパスワード、および (必要) に応じて、タイム ゾーンを含むライセンスと登録の情報を提供します。

   6. **ネットワーク設定を適用**: この手順では、ワークグループまたは Active Directory ドメイン名と組織単位を指定することができます。
      > [!NOTE]
      > Actve ディレクトリ ドメインのメンバーとしてマイクロソフト チームの会議室のユニットを展開する必要がある、推奨される操作の[Skype ルーム ・ システム ・ ドメインへの参加に関する考慮事項](domain-joining-considerations.md)を参照してください。
   7. **ドライバーを適用する:** この手順とその下位の手順は、適用可能なデバイス ドライバーとファームウェアがある Surface Pro モデルをベースに展開する使用されます。 この展開に関連付けられている関連するドライバー パッケージを指定するには、各ステップを更新します。
      -   関連ドライバーを展開する Windows 管理インストルメンテーション (WMI) フィルターを活用する各ドライバー パッケージを構成し、Surface Pro のファームウェアの製造元しモデルします。
      -   これらのドライバーの構成を変更、配置が失敗する可能性がありますそれ以外の場合のことを強くお勧めします。

   8. **Windows と構成マネージャーの設定**: このステップの配置し、構成マネージャーのクライアントを構成します。 組み込みの構成マネージャーのクライアント パッケージを指定するには、この手順を更新します。

   9. **ルート証明書のインストール**: この手順は: ドメインに参加しているデバイスでは、ルート証明書を配布し、そのため、省略可能な既定で無効になっています。
      -   マイクロソフト チームの会議室のユニットにルート証明書を展開する必要がある場合は、この手順を有効にします。
      -   この手順を実行する必要がある場合は、 **SRS のバージョン 2: ルート証明書のパッケージ**と**ファイル システムのリダイレクトを無効にする 64 ビット**がオンになっていることを確認します。

   10. **インストールし監視エージェントの構成**: この手順は、Microsoft Azure のモニター ・ エージェントの 64 ビット バージョンをインストールし、エージェントが、ログの分析機能のワークスペースへの接続を構成します。
       -   この手順は既定で無効になります。 マイクロソフト チームの部屋にいるユニットの状態を監視する監視エージェントを使用しようとしている場合にのみ、この手順を有効にします。
       -   このステップを編集し、自分の**ワークスペースの ID**と**キーのワークスペース**を指定するコマンド ライン パラメーターを更新します。
       -   操作の管理スイートのワークスペース ID とプライマリ ・ キーの入手方法の詳細については、 [Azure を監視するためのデバイスをテスト構成](azure-monitor.md#configure-test-devices-for-azure-monitoring)を参照してください。
       -   **SRS v2 – マイクロソフトの監視エージェントのパッケージ**と**ファイル システムのリダイレクトを無効にする 64 ビット**がオンになっていることを確認します。
       -   マイクロソフト チームの会議室の配置の正常性の監視の詳細については、「 [Azure のモニターを使用して Microsoft チーム部屋計画の管理](../../plan-your-deployment/clients-and-devices/azure-monitor.md) [Azure モニターを使用してマイクロソフトの展開チームの会議室の管理](azure-monitor.md)および[管理 Microsoft の使用」を参照してください。Azure のモニターを使用してデバイスを会議室のチーム](../../manage/skype-room-systems-v2/azure-monitor.md)です。

   11. **V2 構成ファイルのコピーの SRS**: ここでは、マイクロソフトのチーム会議室 『 導入ガイド 』 からローカル ハード ドライブに必要なセットアップと構成ファイルをコピーします。 カスタマイズは、この手順は必要ではありません。
       -   **SRS v2 – SRS アプリケーション パッケージ**と**ファイル システムのリダイレクトを無効にする 64 ビット**がオンになっていることを確認します。

   12. **SRSv2-OS の更新プログラムをインストール**: この手順は、マイクロソフト チームの会議室の配置に必要なオペレーティング システムの必須更新プログラムを配置します。 次の手順を実行します。
       -   必要な更新プログラムを確認するのには、[マイクロソフト チームの会議室のコンソールの構成](console.md)を確認します。
       -   **SRS v2 – OS の更新プログラム パッケージ**に必要なすべての更新プログラムが含まれていることを確認します。
       -   **SRS v2 – OS の更新プログラム パッケージ**が選択されていることを確認します。
       -   PowerShell 実行ポリシーを**バイパス**に設定されていることを確認します。

   13. **コンピューターの再起動**: この手順は、オペレーティング システムの必須更新プログラムをインストールした後にコンピューターを再起動します。 カスタマイズは、この手順は必要ではありません。

   14. **Windows コンポーネントの構成**: この手順が必要な Windows の機能を構成します。 カスタマイズは、この手順は必要ではありません。

   15. **コンピューターの再起動**: この手順は、Windows の機能を構成した後にコンピューターを再起動します。 カスタマイズは、この手順は必要ではありません。

   16. **ローカル Skype ユーザーの追加**: この手順が自動的に Windows にサインインし、チームの会議室をマイクロソフトのアプリケーションを起動するために使用するローカル Skype アカウントを作成します。 この手順は、それに関連付けられている任意のソフトウェア パッケージを持っていないし、カスタマイズすることの必要はありません。

   17. **設定セットアップおよび SRS のアプリケーションを構成する**: この手順は、オペレーティング システムの次回の起動時には、マイクロソフト チームの会議室アプリケーションのインストールを構成します。
       -   **SRS v2 – SRS セットアップ パッケージの構成**と**ファイル システムのリダイレクトを無効にする 64 ビット**がオンになっていることを確認します。

> [!IMPORTANT]
> タスク シーケンスの手順が記載されている順序である必要がありますが非常に重要です。 手順の順序を変更または追加の手順を構成するには、展開を壊れる可能性があります。
>
> **設定セットアップおよび SRS のアプリケーションを構成する**の手順は、タスク シーケンスの最後のステップをする必要があります、それ以外の場合、展開が失敗可能性があります。

### <a name="create-deployment-for-the-task-sequence"></a>展開タスク シーケンスを作成します。

1. タスク シーケンスを選択し、[**配置**] を選択します。

2. 展開のターゲット コレクションを選択する**参照**を選択します。

3. **すべての不明なコンピューター**を選択し、 **[ok]** を選択します。

4. **次へ**を選択します。

5. **目的**のドロップ ダウン リストで**利用可能な**を選択します。

6. **次に使用できるように**する] の一覧で、**のみメディアおよび PXE**を選択し、**次へ**を選択します。
   > [!WARNING]
   > **目的**が**使用可能**に設定されているが非常に重要です。 **目的**では**ない**に**必要な**設定を確認します。 また **、次に使用できるように**する**だけのメディアと PXE**を選択することを確認します。
   >
   > 別のものにこれらの値を設定すると、すべてのコンピューターを起動したときマイクロソフト チームの会議室の展開イメージを取得する可能性があります。
7. ない任意のスケジュールを指定する] をクリック**します。**

8. ない**ユーザー エクスペリエンス**セクション内のすべての変更] をクリック**します。**

9. ない、[**通知**] セクション内のすべての変更] をクリック**します。**

10. されない、[**配布ポイント**] セクション内のすべての変更] をクリック**します。**

11. 設定を確認し、**次へ**を選択します。

12. **閉じる**を選択します。

<a name="validate-and-troubleshoot-the-solution"></a>検証し、ソリューションのトラブルシューティングを行う
--------------------------------------

システム センター構成マネージャーのタスク シーケンスが完了したら、タスク シーケンスが展開し、マイクロソフト チームの会議室のユニットの構成を検証するために実行するテストを実行する必要があります。

1.  サポートされているイーサネット アダプターのいずれかまたは表面のドッキング ステーションを使用してワイヤード (有線) ネットワークへのテスト デバイスを接続します。 環境内の PXE ブート機能が構成されていない場合は、USB からブートし、構成マネージャーに接続する USB フラッシュ ドライブで[以前に作成した](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media)ブート イメージを使用できます。

2.  ファームウェアにアクセスし、PXE ブートを開始します。

    1.  サーフェスのデバイスの電源を切ったことを確認します。

    2.  **音量アップ**ボタンを押したままにします。

    3.  キーを押し、**電源**ボタンを離します。

    4.  デバイス ブートには、**ボリュームの**ボタンを離すと開始します。

    5.  **ブート構成**を選択します。

    6.  次のいずれかの操作を行います。

        -   **PXE ブート**を選択し、一覧の一番上にドラッグします。 代わりに、デバイスをすぐに起動するようにネットワーク アダプターの左を読み取ることができます。 これは、起動順序には影響しません。
        -   ブート メディアを保持している USB フラッシュ ドライブを選択します。

3.  **終了**] を選択し、[**今すぐ再起動**します。

4.  ダイアログ ボックスが表示されたら、ネットワーク ブート サービスの**入力**を選択します。

5.  Windows PE をメモリにロードされ、タスク シーケンス ウィザードが開始されます。 **次**へを選択します。

6.  以前では、インポートしたタスク シーケンスを選択し、[**次へ**を選択します。

7.  ディスク構成を適用した後、デバイスのコンピューター名を指定するように求めします。 Surface Pro デバイスのシリアル番号に基づいて推奨されるコンピューター名は、ユーザー インターフェイスが表示されます。 提案された名前をそのまま使用するか、新しいパスワードを指定します。 コンピューター名の割り当て] 画面の指示に従います。 **承諾**を選択すると、展開を開始します。

8.  展開プロセスの残りの部分は、自動、複数のユーザーの入力を要求しません。

9.  展開タスク シーケンスでは、デバイスの構成が完了すると、チームの会議室をマイクロソフトのアプリケーション設定を構成するように指示する次の構成] 画面が表示されます。

    ![マイクロソフト チームの会議室のアプリケーションのセットアップの初期画面](../../media/room-systems-scale-image2.png)

10.  Surface Pro、マイクロソフト チームの会議室のコンソールに接続し、アプリケーションの設定を構成します。

11.  展開済みのデバイスの[Microsoft チームの会議室のヘルプ](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)に記載されている機能が動作しているかを検証します。


インストールの失敗をトラブルシューティングするには、 **SMSTS.log**ファイルは、構成マネージャーのタスク シーケンスで実行されるすべての手順をログに記録を確認してください。

SMSTS.log ファイルは、複数のビルド プロセスの段階に応じて、パスのいずれかに格納されます。 SMSTS.log ファイルへのパスを識別するのには次の表を確認してください。


| **展開フェーズ**                                                            | **タスク シーケンスのログのパス**                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| WinPE の HDD をフォーマットする前に、                                                        | X:\\Windows\\Temp\\smstslog\\smsts.log             |
| WinPE の HDD のフォーマット後、                                                         | C:\\_SMSTaskSequence\\ログ\\Smstslog\\smsts.log    |
| オペレーティング システムの展開、構成マネージャー エージェントをインストールする前に、 | c:\\_SMSTaskSequence\\ログ\\Smstslog\\smsts.log    |
| オペレーティング システムと構成マネージャー エージェントを展開                   | %windir%\\System32\\ccm\\ログ\\Smstslog\\smsts.log |
| タスク シーケンスの実行が完了しました                                                | %windir%\\System32\\ccm\\ログ\\smsts.log           |

> [!TIP]
> 開くにはコマンド コンソールでは、タスク シーケンス中に**f8 キー**を選択し、SMSTS.log ファイルへのアクセスを取得できます。

PXE ブートの問題をトラブルシューティングするには、PXE のアクションに固有の構成マネージャー サーバー上のログの 2 つファイルを確認します。

-   **Pxecontrol.log**、構成マネージャーのインストール ・ ログ ・ ディレクトリ内にあります。

-   **Smspxe.log**、構成マネージャー管理ポイント (MP) のログ ディレクトリにあります。

さらに、構成マネージャーのインストールのトラブルシューティングに使用できるログ ファイルの完全なリストは、[システム センター構成マネージャーのログ ファイル](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files)を参照してください。
