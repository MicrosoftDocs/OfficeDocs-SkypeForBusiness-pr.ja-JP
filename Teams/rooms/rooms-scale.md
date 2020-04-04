---
title: Microsoft Endpoint Configuration Manager を使用して Microsoft Teams ルームを展開する
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
- seo-marvel-mar2020
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
ms.collection:
- M365-collaboration
description: このトピックでは、大規模な展開での Microsoft Teams のルームの展開について説明します。
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
ms.openlocfilehash: 04d5945e042293ad0cb1597307fd4a2b596bee39
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2020
ms.locfileid: "43141020"
---
# <a name="deploy-microsoft-teams-rooms-by-using-microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager を使用して Microsoft Teams ルームを展開する

この記事では、Microsoft Teams のルーム展開を作成するために必要なすべての情報を Microsoft Endpoint Configuration Manager を使用して提供します。

Configuration Manager によって提供される使いやすい方法では、オペレーティングシステムとその他のアプリケーションを複数のターゲットデバイスに展開できます。

次の手順を使用して、構成マネージャーの構成について説明し、このガイダンス全体で組織に必要なサンプルパッケージとスクリプトをカスタマイズします。

![Microsoft Teams 室展開プロセス (Configuration Manager を使用)](../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> このソリューションは、Surface Pro ベースの展開でのみテストされています。 Surface Pro に基づかない構成については、製造元のガイドラインに従ってください。

## <a name="validate-prerequisites"></a>前提条件の検証

Configuration Manager を使用して Microsoft Teams のルームを展開するには、次の前提条件と要件を満たしていることを確認します。

### <a name="microsoft-endpoint-configuration-manager-requirements"></a>Microsoft Endpoint Configuration Manager の要件

-   Microsoft Endpoint Configuration Manager バージョンは、少なくとも1706以上でなければなりません。 1710以降の使用をお勧めします。 Configuration manager でサポートされている Windows 10 のバージョンについては、「 [Configuration manager での windows 10 のサポート」](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client)を参照してください。

-   Windows 10 でサポートされているバージョンの Windows アセスメント & デプロイメントキット (ADK) がインストールされている必要があります。 さまざまなバージョンの Configuration Manager で使用できる[Windows 10 ADK](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-adk)のバージョンを確認し、展開に適切なバージョンが含まれていることを確認します。

-   サイトシステムサーバーには、配布ポイントの役割が割り当てられている必要があります。また、ネットワークで開始された展開を有効にするために、ブートイメージを[プレブート実行環境 (PXE) のサポート](https://docs.microsoft.com/configmgr/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network)に対して有効にする必要があります。 PXE のサポートが有効になっていない場合は、展開用に[起動可能なメディア](https://docs.microsoft.com/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network)を使用できます。

-   ネットワークアクセスアカウントは、新しいコンピューター (ベアメタル) の展開シナリオをサポートするように構成する必要があります。 ネットワークアクセスアカウントの構成の詳細については、「[構成マネージャーで使用されているアカウント](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)」を参照してください。

-   同じ Microsoft Teams のルームイメージを複数のユニットに同時に展開する可能性がある場合は、[マルチキャストサポート](https://docs.microsoft.com/configmgr/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network)を有効にすることをお勧めします。

### <a name="networking-requirements"></a>ネットワーク要件

-   ネットワークには、Microsoft Teams のルームユニットが展開されるサブネットへの IP アドレスの自動配布用に構成された動的ホスト構成プロトコル (DHCP) サーバーが必要です。

    > [!NOTE]
    > DHCP リース期間は、イメージの展開期間よりも長い値に設定する必要があります。 そうしないと、展開が失敗する可能性があります。

-   スイッチや仮想 Lan (Vlan) などのネットワークは、PXE をサポートするように構成する必要があります。 IP ヘルパーと PXE 構成の詳細については、ネットワークベンダーにお問い合わせください。 または、PXE のサポートが有効になっていない場合は、展開用に[起動可能なメディア](https://docs.microsoft.com/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network)を使用できます。

    > [!NOTE]
    > Surface Pro デバイスでは、ネットワークからの起動 (PXE ブート) は、Microsoft のイーサネットアダプターまたはドッキングステーションを使っている場合にのみサポートされます。 サードパーティのイーサネットアダプターは Surface Pro による PXE ブートをサポートしていません。 詳細については[、「イーサネットアダプターとサーフェスの展開](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment)」をご覧ください。

## <a name="configure-microsoft-endpoint-configuration-manager-for-operating-system-deployment"></a>オペレーティングシステムの展開用に Microsoft Endpoint Configuration Manager を構成する

この記事では、構成マネージャーが正常に展開されていることを前提としており、構成マネージャーを最初から展開して構成するために必要なすべての手順については詳しく説明しません。 Microsoft Endpoint Configuration Manager の[ドキュメントと構成ガイダンス](https://docs.microsoft.com/configmgr/)は、優れたリソースです。まだ構成マネージャーを展開していない場合は、これらのリソースから始めることをお勧めします。

オペレーティングシステムの展開 (OSD) 機能が正しく構成されていることを確認するには、次の手順を使用します。

### <a name="validate-and-upgrade-configuration-manager"></a>構成マネージャーの検証とアップグレード

1.  Configuration Manager コンソールで、[**管理** \> **更新とサービス**] に移動します。

2.  インストールされているビルドと、まだインストールされていない更新プログラムを確認します。

3.  [構成マネージャーでの Windows 10 のサポートを](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client)確認する展開をアップグレードする必要がある場合は、インストールする更新プログラムを選び、[**ダウンロード**] を選びます。

4.  ダウンロードが完了したら、更新プログラムを選択して、[**更新プログラムパックのインストール**] を選択します。

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a>PXE とマルチキャストをサポートするように配布ポイントを構成する

1.  Configuration Manager コンソールで、[**管理** \> ]**配布ポイント**に移動します。

2.  Microsoft Teams ルームの展開を実行する配布ポイントサーバーを選択し、[**プロパティ**] を選択します。

3.  [ **PXE** ] タブを選択し、次の設定が有効になっていることを確認します。
    -   クライアントに対して PXE のサポートを有効にする
    -   この配布ポイントから受信 PXE 要求への応答を許可する
    -   不明なコンピューターのサポートを有効にする

4.  *オプション:* マルチキャストのサポートを有効にするには、[**マルチキャスト**] タブを選択し、次の設定が有効になっていることを確認します。
    -   マルチキャストで複数のクライアントにデータを同時に送信できるようにする
    -   ネットワークチームの推奨事項に従って UDP ポート範囲を構成する

### <a name="configure-the-network-access-account"></a>ネットワークアクセスアカウントを構成する

1.  Configuration Manager コンソールで、[**管理** \> **サイトの構成** \> **サイト**] に移動し、サイトを選びます。

2.  [**設定**] グループで、[**サイトコンポーネント** \> **ソフトウェア配布**の構成] を選びます。

3.  [**ネットワークアクセスアカウント**] タブを選びます。1つまたは複数のアカウントをセットアップし、[ **OK]** を選択します。

> [!NOTE]
> アカウントには特別な権限は必要ありません。ただし、配布ポイントサーバーの [**ネットワーク経由でコンピューターにアクセス**する] 権限は使用できません。 一般的なドメインユーザーアカウントが適切です。 詳細については、「[構成マネージャーで使用されているアカウント](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)」を参照してください。

### <a name="configure-a-boot-image"></a>ブートイメージを構成する

1.  Configuration Manager コンソールで、[**ソフトウェアライブラリ** \> **オペレーティングシステム** \> **ブートイメージ**] に移動します。

2.  [**ブートイメージ (x64)**] を選択し、[**プロパティ**] を選択します。

3.  [**データソース**] タブを選択し、[ **PXE 対応の配布ポイントからこのブートイメージを展開**する] を有効にします。

4.  [**オプションコンポーネント**] タブを選択して、必要なコンポーネントをインストールします。

    1.  星アイコンを選択し、HTML を検索する **(WinPE-HTA)**

    2.  [ **OK]** を選択して、HTML アプリケーションのサポートをブートイメージに追加します。

5.  *オプション:* 展開エクスペリエンスをカスタマイズするには、[**カスタマイズ**] タブを選択します。
    -   展開時にコマンドプロンプトにアクセスする必要がある場合は、**コマンドのサポート (テスト専用)** を有効にします。 この機能が有効になっている場合は、展開中に**F8**を選択してコマンドプロンプトを開始できます。
    -   また、展開中に表示されるカスタムの背景画像を指定することもできます。 画像を設定するには、**カスタムの背景画像ファイル (UNC パスを指定**し、背景を選択します) を有効にします。

6.  メッセージが表示されたら、[**はい**] を選択し、更新されたブートイメージを配布ポイントに配布します。

詳細については、「[構成マネージャーでブートイメージを管理](https://docs.microsoft.com/configmgr/osd/get-started/manage-boot-images)する」を参照してください。

> [!NOTE]
> ブート可能な USB メディアを作成して、PXE をサポートしていない環境の構成マネージャーのタスクシーケンスベースの展開を開始することができます。 起動可能なメディアには、ブートイメージ、オプションの起動コマンドと必要なファイル、および構成マネージャーのバイナリが含まれます。これには、Windows PE の起動と、展開プロセスの残りの部分に対して Configuration Manager への接続がサポートされます。 詳細については、「[起動可能なメディアを作成する](https://docs.microsoft.com/configmgr/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia)」を参照してください。

## <a name="create-configuration-manager-packages"></a>Configuration Manager パッケージを作成する

> [!IMPORTANT]
> 各 SRS インストーラーバージョンに必要なオペレーティングシステムのバージョンが、MSI のすべてのリリースで変更されています。 特定の MSI で最適なオペレーティングシステムバージョンを判断するには、コンソールセットアップスクリプトを1回実行します。 詳細については、「 [Microsoft Endpoint Configuration Manager を使用して Microsoft Teams ルームを展開](rooms-scale.md)する」を参照してください。

Configuration Manager では、Microsoft Teams のルームユニットを展開して構成するために、多数のパッケージが必要です。

次のパッケージを作成して構成し、配布ポイントサーバーの役割が割り当てられている Configuration Manager サイトシステムに配布する必要があります。

| **パッケージ名**                     | **種類**               | **説明**                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| SRS v2-SRS アプリケーションパッケージ     | ソフトウェアパッケージ       | Microsoft Teams 室展開キット用パッケージ                                      |
| SRS v2-Sysprep パッケージ             | ソフトウェアパッケージ       | Microsoft Teams のルームユニットを構成するためのカスタムの unattend.xml パッケージ            |
| SRS v2-セットアップ-SRSComputerName パッケージ | ソフトウェアパッケージ       | 展開時にコンピューター名を割り当てる HTML アプリケーション (HTA) のパッケージ    |
| SRS v2-SRS の設定を構成する         | ソフトウェアパッケージ       | Microsoft Teams の会議アプリの展開を構成するパッケージ                          |
| SRS v2-OS 更新プログラムパッケージ          | ソフトウェアパッケージ       | 必須のオペレーティングシステム更新プログラムを展開するパッケージ                                      |
| SRS v2-ルート証明書パッケージ    | ソフトウェアパッケージ       | オプション-ルート証明書を展開するパッケージ (ドメインに参加しているユニットには必要ありません)  |
| SRS v2-Microsoft Monitoring Agent パッケージ | ソフトウェアパッケージ       | オプション-Microsoft Operations Management Suite エージェントの展開と構成を行うパッケージ|
| SRS v2-WinPE バックグラウンドパッケージ    | ソフトウェアパッケージ       | ブートイメージと共に使用するカスタムの背景イメージのパッケージ                           |
| Windows 10 Enterprise                | オペレーティングシステムのイメージ | オペレーティングシステムインストールファイル (.wim) のパッケージ                          |
| Surface Pro                          | ドライバーパッケージ         | Microsoft Surface Pro のデバイスドライバーとファームウェアのパッケージ                     |
| Surface Pro 4                        | ドライバーパッケージ         | Microsoft Surface Pro 4 のデバイスドライバーとファームウェアのパッケージ                   |

詳細については、「[構成マネージャーでのパッケージとプログラム](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs)」を参照してください。

### <a name="create-folders-for-the-package-source-files"></a>パッケージソースファイルのフォルダーを作成する

Configuration Manager では、最初に作成され、更新されるときに、パッケージソースファイルを特定のフォルダー構造で整理する必要があります。

Microsoft Endpoint Configuration Manager サーバーの全体管理サイトまたはプライマリサイト、またはパッケージソースファイルのホストに使用しているサーバー共有で、次のフォルダー構造を作成します。

-   SRS v2-Microsoft Monitoring Agent パッケージ
-   SRS v2-OS 更新プログラムパッケージ
-   SRS v2-ルート証明書パッケージ
-   SRS v2-セットアップ-SRSComputerName パッケージ
-   SRS v2-SRS アプリケーションパッケージ
-   SRS v2-SRS の設定を構成する
-   SRS v2-Sysprep パッケージ
-   デバイス
    -   Surface Pro
    -   Surface Pro 4
-   オペレーティングシステム
    -   Windows 10 Enterprise

> [!TIP]
> また、インポートする必要があるパッケージ、使用する必要があるスクリプト、およびタスクシーケンステンプレートのフォルダー構造を含む zip ファイルを[ダウンロード](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)して使用することもできます。

### <a name="create-the-monitoring-agent-package"></a>監視エージェントパッケージを作成する

1. から<https://go.microsoft.com/fwlink/?LinkId=828603>監視エージェントをダウンロードします。

2. コマンドプロンプトウィンドウを開いて、コマンドプロンプトに**MMASetup-AMD64/c**を入力して、 **SRS V2-Microsoft Monitoring Agent パッケージ**フォルダーにパッケージを抽出します。

3. Configuration Manager コンソールで、[**ソフトウェアライブラリ** \> **アプリケーション管理** \> **パッケージ**] に移動し、[**パッケージの作成**] を選択します。

4. パッケージを作成するには、次の情報を入力します。

   - 名前<strong>: SRS v2-Microsoft Monitoring Agent パッケージ</strong>

   - 製造元<strong>: Microsoft Corporation</strong>

   - バージョン<strong>: 8.1.11081.0</strong> (ダウンロードしたインストールファイルのバージョンを入力します)

   - [**このパッケージはソースファイルを含む**] チェックボックスをオンにして、 **SRS V2-Microsoft Monitoring Agent パッケージ**フォルダーへのパスを入力し、[**次へ**] を選択します。

5. [**プログラムを作成しない**] を選び、[**次へ**] を選びます。

6. [**設定の確認**] ページを確認して、[**次へ**] を選びます。

7. [**閉じる**] を選びます。

### <a name="create-the-operating-system-updates-package"></a>オペレーティングシステムの更新パッケージを作成する

1. **SRS v2-OS 更新パッケージ**フォルダーで、 **Install-SRSv2-OS-Updates**という名前の新しい PowerShell スクリプトを作成します。

2. 次のスクリプトを**Install-SRSv2-OS-Updates**スクリプトにコピーします。 または、[ここ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)から Install-SRSv2-OS-Updates スクリプトをダウンロードすることもできます。
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
3. 同じフォルダーに、必須の Windows 更新プログラムパッケージをダウンロードします。
   > [!NOTE]
   > この記事が公開された時点では、 [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu)のみが必要でした。 他の更新プログラムが必要かどうかを確認するには、 [Microsoft Teams のルームコンソールの構成](console.md)を確認します。

4. Configuration Manager コンソールで、[**ソフトウェアライブラリ** \> **アプリケーション管理** \> **パッケージ**] に移動し、[**パッケージの作成**] を選択します。

5. パッケージを作成するには、次の情報を入力します。
   -   名前: **SRS v2 – OS 更新プログラムパッケージ**
   -   製造元: **Microsoft Corporation**
   -   バージョン: **1.0.0**
   -   [**このパッケージはソースファイルを含む**] チェックボックスをオンにして、 **SRS V2-OS 更新パッケージ**フォルダーへのパスを入力し、[**次へ**] を選択します。

6. [**プログラムを作成しない**] を選び、[**次へ**] を選びます。

7. [**設定の確認**] ページを確認して、[**次へ**] を選びます。

8. [**閉じる**] を選びます。

### <a name="create-the-root-certificate-package-optional"></a>ルート証明書パッケージを作成する (省略可能)

このパッケージを作成して、Active Directory ドメインに参加しないデバイスのルート証明書を配布します。 このパッケージを作成するのは、次の両方の条件が当てはまる場合のみです。
-   展開には、オンプレミスの Lync または Skype for Business Server が含まれます。
-   Microsoft Teams のルームユニットは、ドメインメンバーではなくワークグループで機能するように構成されています。

1.  ルート証明書を**SRS v2 –ルート証明書パッケージ**フォルダーにコピーします。

2.  Configuration Manager コンソールで、[**ソフトウェアライブラリ** \> **アプリケーション管理** \> **パッケージ**] に移動し、[**パッケージの作成**] を選択します。

3.  パッケージを作成するには、次の情報を入力します。
    -   名前: **SRS v2 –ルート証明書パッケージ**
    -   製造元:*組織の名前*
    -   バージョン: **1.0.0**
    -   [**このパッケージはソースファイルを含む**] チェックボックスをオンにして、 **SRS V2 –ルート証明書パッケージ**フォルダーへのパスを入力し、[**次へ**] を選択します。

4.  [**プログラムを作成しない**] を選び、[**次へ**] を選びます。

5.  [**設定の確認**] ページを確認して、[**次へ**] を選びます。

6.  [**閉じる**] を選びます。

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a>Microsoft Teams のルーム展開キットパッケージを作成する

1.  から<https://go.microsoft.com/fwlink/?linkid=851168>最新バージョンの**Microsoft Teams ルーム展開キット**をダウンロードして、ワークステーションにインストールします。

2.  **C:\\Program Files (x86)\\Skype Room System Deployment Kit**から、 **srs v2-srs アプリケーションパッケージ**フォルダーにコンテンツをコピーします。

3.  Configuration Manager コンソールで、[**ソフトウェアライブラリ** \> **アプリケーション管理** \> **パッケージ**] に移動し、[**パッケージの作成**] を選択します。

4.  パッケージを作成するには、次の情報を入力します。
    -   名前: **srs v2 – Srs アプリケーションパッケージ**
    -   製造元: **Microsoft Corporation**
    -   バージョン: **3.1.104.0** (ダウンロードしたインストールファイルのバージョンを入力します)
    -   [**このパッケージはソースファイルを含む**] チェックボックスをオンにして、 **SRS V2 – srs アプリケーションパッケージ**フォルダーへのパスを入力し、[**次へ**] を選択します。
5.  [**プログラムを作成しない**] を選び、[**次へ**] を選びます。

6.  [**設定の確認**] ページを確認して、[**次へ**] を選びます。

7.  [**閉じる**] を選びます。

### <a name="create-the-computer-name-assignment-package"></a>コンピューター名割り当てパッケージを作成する

1.  [ **SRS v2-セットアップ-SRSComputerName パッケージ**] フォルダーで、 **Set-SRSComputerName**という名前の新しい HTML アプリケーションを作成します。

2.  次のスクリプトを**Set-SRSComputerName**ファイルにコピーします。 または、[ここ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)から Set-SRSComputerName ファイルをダウンロードすることもできます。
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
3.  Configuration Manager コンソールで、[**ソフトウェアライブラリ** \> **アプリケーション管理** \> **パッケージ**] に移動し、[**パッケージの作成**] を選択します。

4.  パッケージを作成するには、次の情報を入力します。

    -   名前: **SRS v2-セットアップ-SRSComputerName パッケージ**

    -   製造元: **Microsoft Corporation**

    -   バージョン: **1.0.0**

    -   [**このパッケージはソースファイルを含む**] チェックボックスをオンにして、 **SRS v2-セットアップ-Srscomputername パッケージ**フォルダーへのパスを入力し、[**次へ**] を選択します。

5.  [**プログラムを作成しない**] を選び、[**次へ**] を選びます。

6.  [**設定の確認**] ページを確認して、[**次へ**] を選びます。

7.  [**閉じる**] を選びます。

### <a name="create-the-sysprep-package"></a>Sysprep パッケージを作成する

1. [ **SRS v2 – Sysprep パッケージ]** フォルダーで、 **unattend.xml**という名前の新しい xml ファイルを作成します。

2. 次のテキストを**unattend.xml**ファイルにコピーします。 または、[ここ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)から unattend.xml ファイルをダウンロードすることもできます。
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
3. Configuration Manager コンソールで、[**ソフトウェアライブラリ** \> **アプリケーション管理** \> **パッケージ**] に移動し、[**パッケージの作成**] を選択します。

4. パッケージを作成するには、次の情報を入力します。
   -   名前: **SRS v2-Sysprep パッケージ**
   -   製造元: **Microsoft Corporation**
   -   バージョン: **1.0.0**
   -   [**このパッケージはソースファイルを含む**] チェックボックスをオンにし、[ **SRS V2 – Sysprep パッケージ**] フォルダーへのパスを入力して、[**次へ**] を選択します。
5. [**プログラムを作成しない**] を選び、[**次へ**] を選びます。

6. [**設定の確認**] ページを確認して、[**次へ**] を選びます。

7. [**閉じる**] を選びます。

### <a name="create-the-windows-10-enterprise-package"></a>Windows 10 Enterprise パッケージを作成する

1.  Windows 10 Enterprise x64 メディアを取得し、**インストール .wim**ファイルを**オペレーティングシステム\\の Windows 10 enterprise**フォルダーにコピーします。

2.  Configuration Manager コンソールで、[**ソフトウェアライブラリ** \> **オペレーティング** \>システムの**オペレーティングシステムイメージ**] に移動し、[**オペレーティングシステムイメージの追加**] を選択します。

3.  コピーした**インストール .wim**ファイルへのパスを指定し、[**次へ**] を選択します。

4.  [**バージョン**] フィールドを更新して、Windows 10 Enterprise のイメージのビルド番号と一致するようにし、[**次へ**] を選択します。

5.  [**詳細**] ページを確認し、[**次へ**] を選択します。

6.  [**閉じる**] を選びます。

詳細については、「[構成マネージャーを使用して OS イメージを管理](https://docs.microsoft.com/configmgr/osd/get-started/manage-operating-system-images)する」を参照してください。

### <a name="create-surface-pro-device-driver-packages"></a>Surface Pro デバイスドライバーパッケージを作成する

Microsoft Teams のルームは Surface Pro と Surface Pro 4 の両方でサポートされています。 環境内にある Surface Pro モデルごとにドライバーパッケージを作成する必要があります。

> [!IMPORTANT]
> ドライバーは、Windows 10 Enterprise ビルドおよび Microsoft Teams 室展開キットのバージョンと互換性がある必要があります。 詳細については、「 [Surface デバイス用の最新のファームウェアとドライバーをダウンロード](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices)して[本体を構成する](console.md)」を参照してください。

1.  最新のドライバーとファームウェアをダウンロードします。
    -   Surface Pro の場合:<https://www.microsoft.com/download/details.aspx?id=55484>
    -   Surface Pro 4 の場合:<https://www.microsoft.com/download/details.aspx?id=49498>

2.  ダウンロードしたドライバーとファームウェアを抽出します。 コマンドプロンプトウィンドウを開き、コマンドプロンプトで次のいずれかのコマンドを入力します。
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro 4"`

3.  Configuration Manager コンソールで、[**ソフトウェアライブラリ** \> **オペレーティングシステム** \> **ドライバー**] に移動し、[**ドライバーのインポート**] を選択します。

4.  [**次のネットワークパス (UNC) のすべてのドライバーをインポートする**] を選択し、ソースフォルダー (\\たとえば\\、\\C: _Sources Drivers Surface Pro) を選び、[**次へ**] を選びます。

5.  [**インポートしたドライバーの詳細を指定**してください] ページで、一覧表示されているすべてのドライバーを選び、[これらのドライバーを有効にする] を選択して、[**コンピューターにインストールを許可する**] を選びます。

6.  [**カテゴリ**] を選択し、Surface モデルに一致する新しいカテゴリを作成して、[ **OK**] を選択し、[**次へ**] を選択します。

7.  [**新しいパッケージ**] を選びます。

8.  Surface Pro モデルと一致するパッケージ名を指定し、ドライバーパッケージファイルを保存するフォルダーパスを入力して、[ **OK**] を選択し、[**次へ**] を選択します。

9.  [**ブートイメージ**] ページで、[ブートイメージ] が選択されていないことを確認し、[**次へ**] を選択します。

10. [**閉じる**] を選びます。

11. [ **Software Library** \> **オペレーティングシステム** \> **ドライバー**] に移動し、[フォルダーの** \>作成] フォルダー**を選択し、ドライバーをインポートした Surface Pro モデルと一致するフォルダー名を入力します。

12. 新しく作成したフォルダーに、インポートされたすべてのドライバーを移動して、移動や操作が簡単にできるようにします。

> [!NOTE]
> 他の Surface Pro モデルにも同じ手順を繰り返します。 詳細については、「[構成マネージャーでドライバーを管理](https://docs.microsoft.com/configmgr/osd/get-started/manage-drivers)する」を参照してください。

### <a name="create-microsoft-teams-rooms-configuration-package"></a>Microsoft Teams 会議室構成パッケージを作成する

1.  Configuration Manager コンソールで、[**ソフトウェアライブラリ** \> **アプリケーション管理** \> **パッケージ**] に移動し、[**パッケージの作成**] を選択します。

2.  パッケージを作成するには、次の情報を入力します。

    -   名前: **srs v2-Srs セットアップパッケージを構成する**

    -   製造元: **Microsoft Corporation**

    -   バージョン: **1.0.0**

    -   [**このパッケージはソースファイルを含む**] チェックボックスをオンにし、[ **SRS V2-srs セットアップ**] フォルダーへのパスを入力して、[**次へ**] を選択します。

3.  [**プログラムを作成しない**] を選び、[**次へ**] を選びます。

4.  [**設定の確認**] ページを確認して、[**次へ**] を選びます。

5.  [**閉じる**] を選びます。



## <a name="distribute-configuration-manager-packages"></a>Configuration Manager パッケージを配布する

すべてのパッケージは、構成マネージャー階層で配布ポイントの役割が割り当てられているサーバーに配布する必要があります。 パッケージの配布を開始するには、次の手順に従います。

1.  ソフトウェアパッケージを配布します。

    1.  Configuration Manager コンソールで、[**ソフトウェアライブラリ** \> **アプリケーション管理** \> **パッケージ**] に移動します。 配布するすべてのソフトウェアパッケージを選択し、[コンテンツの**配布**] を選択します。

    2.  パッケージの一覧を確認し、[**次へ**] を選択します。

    3.  すべての配布ポイントサーバー (構成マネージャーの階層に応じて配布ポイントグループ) を一覧に追加し、[**次へ**] を選択します。

    4.  [**次へ**] を選択し、[**閉じる**] を選択します。

2.  ドライバーパッケージを配布します。

    1.  Configuration Manager コンソールで、[**ソフトウェアライブラリ** \> **オペレーティングシステム** \> **ドライバーパッケージ**] に移動します。 配布するドライバーパッケージをすべて選択し、[**コンテンツの配布**] を選択します。

    2.  パッケージの一覧を確認し、[**次へ**] を選択します。

    3.  すべての配布ポイントサーバー (構成マネージャーの階層に応じて配布ポイントグループ) を一覧に追加し、[**次へ**] を選択します。

    4.  [**次へ**] を選択し、[**閉じる**] を選択します。

3.  オペレーティングシステムパッケージを配布します。

    1.  Configuration Manager コンソールで、[**ソフトウェアライブラリ** \> **オペレーティング** \>システムの**オペレーティングシステムイメージ**] に移動します。 配布するすべてのオペレーティングシステムイメージを選択し、[コンテンツの**配布**] を選択します。

    2.  パッケージの一覧を確認し、[**次へ**] を選択します。

    3.  すべての配布ポイントサーバー (構成マネージャーの階層に応じて配布ポイントグループ) を一覧に追加し、[**次へ**] を選択します。

    4.  [**次へ**] を選択し、[**閉じる**] を選択します。

> [!NOTE]
> パッケージの配布には、パッケージサイズ、構成マネージャー階層、配布ポイントサーバーの数、ネットワークで利用可能な帯域幅に応じて、時間がかかる場合があります。
> 
> Microsoft Teams のルームユニットの展開を開始する前に、すべてのパッケージを配布する必要があります。
> 
> Configuration Manager コンソールでパッケージ配布の状態を確認するには、「**配布ステータス** \> **コンテンツの状態**を**監視** \>する」を参照してください。

## <a name="configuration-manager-task-sequences"></a>構成マネージャーのタスクシーケンス

タスクシーケンスを構成マネージャーと共に使用して、ターゲットコンピューターにオペレーティングシステムイメージを展開するための手順を自動化します。 Microsoft Teams のルームユニットを自動化された方法で展開するには、リンク先の Microsoft Teams 室のコンピューター、インストールする Windows 10 Enterprise オペレーティングシステムイメージ、その他のアプリケーションやソフトウェア更新プログラムなどのその他の他のコンテンツを開始するために使用されるブートイメージを参照するタスクシーケンスを作成します。

### <a name="import-the-sample-task-sequence"></a>サンプルのタスクシーケンスをインポートする

サンプルのタスクシーケンスをダウンロードして簡単にインポートし、ニーズに合わせてカスタマイズすることができます。

1.  サンプルタスクシーケンスを[**ダウンロード**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)して、ダウンロードした zip ファイルを共有の場所にコピーします。
2.  Configuration Manager コンソールで、[**ソフトウェアライブラリ** \>の**オペレーティングシステム** \>の**タスクシーケンス**] に移動し、[**タスクシーケンスのインポート**] を選択します。

3.  [**参照**] を選択し、手順1で使用した共有フォルダーの場所に移動し、 **Microsoft Teams のルーム展開 (en-us)** ファイルを選択して、[**次へ**] を選択します。

4.  [**新規作成**]**アクション**を設定して、[**次へ**] を選択します。

5.  設定を確認し、[**次へ**] を選択します。

6.  [**閉じる**] を選びます。

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a>参照パッケージが各タスクシーケンスの手順に正しくリンクされていることを確認します。

1. インポートしたタスクシーケンスを選択し、[**編集**] を選択します。

    タスクシーケンスエディターが開き、Microsoft Teams のルームユニットを展開して構成するために必要な一連の手順が表示されます。

2. 各手順を順番に実行し、推奨される更新プログラムを完了します。

   1. **WINDOWS PE で再起動**します。この手順では、コンピューターが再起動し、windows PXE が起動されます。 この手順で変更を加える必要はありません。

   2. **パーティションディスク0– UEFI**: この手順を実行すると、ディスク構成が消去され、構成された設定に基づいてパーティションが作成されます。 この手順には変更を加えないことをお勧めします。

   3. **SRS コンピューター名を設定**する: この手順には、展開時に Microsoft Teams のルームユニットのコンピューター名を設定するための UI を提供する HTML アプリケーションが含まれています。
      -  これは省略可能な手順ですが、別のプロセスでコンピューターの名前付けを管理する場合にのみ無効にすることができます。
      -  **SRS v2-セットアップ-SRSComputerName**パッケージが選択されていることを確認します。 表示されていない場合は、パッケージを参照して選択します。

   4. **オペレーティングシステムの適用**: この手順では、展開するオペレーティングシステムイメージと、使用する無人 Sysprep 応答ファイルを指定します。
      -  正しい Windows 10 Enterprise オペレーティングシステムイメージファイルが選択されていることを確認します。
      -  **カスタムインストールに無人または sysprep の応答ファイルを使用**する機能が有効になっていることを確認し、[ **SRS V2-sysprep パッケージ**] が選択されていることを確認します。 また、**ファイル名**が**unattend.xml**に設定されていることを確認します。

   5. **Windows の設定を適用**する: この手順では、windows インストールに関する情報を収集します。
      -  プロダクトキー、ローカル管理者アカウントのパスワード、タイムゾーン (必要に応じて) を含む、ライセンスおよび登録情報を提供します。

   6. **ネットワーク設定を適用**する: この手順では、ワークグループまたは Active Directory ドメイン名と組織単位を指定できます。
      > [!NOTE]
      > 「 [Skype Room System domain](domain-joining-considerations.md) 」をご覧ください。推奨される操作については、「Microsoft Teams ルームユニットを Actve ディレクトリドメインのメンバーとして展開する」を参照してください。
   7. **ドライバーを適用します。** この手順とサブステップを使って、使用している Surface Pro モデルに基づいて、該当するデバイスドライバーとファームウェアを展開します。 各手順を更新して、この展開に関連する関連するドライバーパッケージを指定します。
      -   各ドライバパッケージは、Windows Management Instrumentation (WMI) フィルターを活用して Surface Pro の作成とモデルに基づいて関連するドライバーとファームウェアを展開するように構成されています。
      -   これらのドライバーの構成を変更しないようにすることを強くお勧めします。そうしないと、展開が失敗する可能性があります。

   8. **Windows と構成マネージャーのセットアップ**: この手順では、configuration manager クライアントを展開して構成します。 この手順を更新して、組み込みの Configuration Manager クライアントパッケージを指定します。

   9. [**ルート証明書のインストール**]: この手順では、ドメインに参加していないデバイスのルート証明書を配布します。そのため、既定ではオプションで無効になります。
      -   Microsoft Teams のルームユニットにルート証明書を展開する必要がある場合は、この手順を有効にします。
      -   この手順を実行する必要がある場合は、 **SRS v2 –ルート証明書パッケージ**と**64 ビットファイルシステムリダイレクション**が選択されていることを確認します。

   10. **Monitoring Agent のインストールと構成**: この手順では、64ビットバージョンの Microsoft Azure Monitor エージェントをインストールし、ログ分析ワークスペースに接続するようにエージェントを構成します。
       -   この手順は、既定では無効になっています。 この手順を有効にするのは、監視エージェントを使用して Microsoft Teams のルームの正常性を監視する場合のみです。
       -   この手順を編集し、コマンドラインパラメーターを更新して、**ワークスペース ID**と**ワークスペースキー**を指定します。
       -   Operations Management Suite のワークスペース ID と主キーの入手方法の詳細については、「 [Azure Monitoring のテストデバイスを構成する](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring)」を参照してください。
       -   **SRS v2 – Microsoft Monitoring Agent パッケージ**と**64 ビットファイルシステムリダイレクション**が選択されていることを確認します。
       -   Microsoft Teams 室の展開の正常性を監視する方法の詳細については、「 [Azure monitor を使用した microsoft Teams 会議室管理の計画](azure-monitor-plan.md)」を参照してください。 azure monitor で microsoft [teams の](azure-monitor-deploy.md)ルーム管理を展開し、 [Azure monitor で microsoft Teams 室のデバイスを管理](azure-monitor-manage.md)します。

   11. **SRS V2 構成ファイルをコピー**する: この手順では、必要なセットアップファイルと構成ファイルを Microsoft Teams のルーム展開キットからローカルのハードドライブにコピーします。 この手順をカスタマイズする必要はありません。
       -   **Srs v2 – Srs アプリケーションパッケージ**と**64 ビットファイルシステムリダイレクション**が選択されていることを確認します。

   12. **SRSv2-OS-更新プログラム**: この手順では、Microsoft Teams ルームの展開に必要なオペレーティングシステムの必須更新プログラムが展開されます。 以下の操作を行います。
       -   必要な更新プログラムを確認するには[、Microsoft Teams 室コンソールを構成](console.md)することを確認します。
       -   **SRS v2 – OS 更新パッケージ**に必要な更新プログラムがすべて含まれていることを確認します。
       -   [ **SRS v2 – OS 更新プログラムパッケージ]** が選択されていることを確認します。
       -   PowerShell 実行ポリシーが**バイパス**されるように設定されていることを確認します。

   13. **コンピューターの再起動**: この手順は、オペレーティングシステムの必須更新プログラムがインストールされた後にコンピューターを再起動します。 この手順をカスタマイズする必要はありません。

   14. **Windows コンポーネントの構成**: この手順では、必要な windows 機能を構成します。 この手順をカスタマイズする必要はありません。

   15. **コンピューターを再起動**する: この手順は、Windows の機能が構成された後にコンピューターを再起動します。 この手順をカスタマイズする必要はありません。

   16. **ローカル Skype ユーザの追加**: この手順では、Windows に自動的にサインインするために使用されるローカルの skype アカウントを作成して、Microsoft Teams のルームアプリケーションを起動します。 この手順には、関連付けられたソフトウェアパッケージはありません。また、そのためのカスタマイズは必要ありません。

   17. **SRS アプリケーションをセットアップして構成する**: この手順では、オペレーティングシステムを次に起動するために Microsoft Teams 室のアプリケーションインストールが構成されます。
       -   **Srs v2 – Srs セットアップパッケージを構成**し、 **64 ビットファイルシステムリダイレクション**が選択されていることを確認します。

> [!IMPORTANT]
> タスクシーケンスの手順は、指定された順序で行う必要があることに注意してください。 手順の順序を変更したり、追加の手順を構成したりすると、展開が壊れることがあります。
>
> **SRS アプリケーションのセットアップと構成**は、タスクシーケンスの最後の手順として行う必要があります。そうしないと、展開が失敗する可能性があります。

### <a name="create-deployment-for-the-task-sequence"></a>タスクシーケンスの展開を作成する

1. タスクシーケンスを選択し、[**展開**] を選択します。

2. [**参照**] を選択して展開用のターゲットコレクションを選択します。

3. [**すべての不明なコンピューター** ] を選択し、[ **OK]** を選択します。

4. [**次へ**] を選びます。

5. [**目的**] ドロップダウンリストで [**利用可能**] を選びます。

6. [**以下のものを利用可能にする**] ボックスの一覧で [**メディアと PXE のみ**] を選び、[**次**へ] を選びます。
   > [!WARNING]
   > **目的**を**利用できる**ように設定することは非常に重要です。 **目的**が [**必須**」に設定されて**いない**ことを確認します。 また、**次の [利用可能にする**] で [**メディアと PXE] のみ**を選択してください。
   >
   > これらの値を別の値に設定すると、すべてのコンピューターで、起動時に Microsoft Teams のルームの展開イメージが取得されることがあります。
7. スケジュールを指定せずに、[**次へ**] を選択します。

8. [**ユーザーエクスペリエンス**] セクション内の何も変更せず、[**次へ**] を選びます。

9. [**通知**] セクション内の何も変更せず、[**次へ**] を選びます。

10. [**配布ポイント**] セクション内の何も変更せず、[**次へ**] を選びます。

11. 設定を確認し、[**次へ**] を選択します。

12. [**閉じる**] を選びます。

<a name="validate-and-troubleshoot-the-solution"></a>ソリューションの検証とトラブルシューティングを行う
--------------------------------------

Microsoft Endpoint Configuration Manager のタスクシーケンスが完了したら、タスクシーケンスで Microsoft Teams のルームユニットを展開して構成できることを確認するために、テスト実行を実行する必要があります。

1.  サポートされているイーサネットアダプターのいずれかを使用するか、Surface dock を使用して、テストデバイスを有線ネットワークに接続します。 使用している環境に対して PXE ブート機能が構成されていない場合は、[前に作成](https://docs.microsoft.com/configmgr/osd/deploy-use/create-bootable-media)した usb フラッシュドライブのブートイメージを使用して、usb から起動し、構成マネージャーに接続できます。

2.  ファームウェアにアクセスし、PXE ブートを開始します。

    1.  Surface デバイスの電源がオフになっていることを確認します。

    2.  [**音量を上げる**] ボタンを押したままにします。

    3.  **電源**ボタンを押してから離します。

    4.  デバイスの起動が開始されたら、[**音量を上げる**] ボタンを放します。

    5.  [**ブート構成**] を選びます。

    6.  次のいずれかを実行します。

        -   [ **PXE ブート**] を選択し、一覧の一番上にドラッグします。 または、ネットワークアダプターを左にスワイプして、すぐにデバイスを起動することもできます。 これにより、起動順序は変わりません。
        -   ブートメディアを含む USB フラッシュドライブを選択します。

3.  [**終了**] を選択し、[**今すぐ再起動**] を選択します。

4.  メッセージが表示されたら、[ネットワークブートサービスの**入力**] を選択します。

5.  Windows PE はメモリに読み込まれ、タスクシーケンスウィザードが開始されます。 [**次へ**] を選択して続行します。

6.  前にインポートしたタスクシーケンスを選択し、[**次へ**] を選択します。

7.  ディスク構成が適用されると、デバイスのコンピューター名を指定するように求められます。 ユーザーインターフェイスには、Surface Pro デバイスのシリアル番号に基づく推奨コンピューター名が表示されます。 提案された名前を受け入れるか、新しい名前を指定することができます。 [コンピューター名の割り当て] 画面の指示に従います。 [**承諾**] を選択すると、展開が開始されます。

8.  展開プロセスの残りの部分は自動であり、ユーザーにより多くの入力を求められることはありません。

9.  展開タスクシーケンスによるデバイスの構成が完了すると、Microsoft Teams の会議の設定を構成するように求められる次の構成画面が表示されます。

    ![Microsoft Teams 室アプリケーションの最初のセットアップ画面](../media/room-systems-scale-image2.png)

10.  Surface Pro を Microsoft Teams 室コンソールに接続し、アプリケーション設定を構成します。

11.  [Microsoft Teams のルーム](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)に記載されている機能が、展開されたデバイスで機能していることを確認します。


インストールに失敗した場合のトラブルシューティングを行うには、 **Smsts .log**ファイルを確認します。これは、構成マネージャーのタスクシーケンスで実行されたすべてのステップをログに記録します。

SMSTS ファイルは、ビルドプロセスの段階に応じて、多数のパスのいずれかに保存されます。 次の表を参照して SMSTS .log ファイルへのパスを確認します。


| **展開フェーズ**                                                            | **タスクシーケンスのログパス**                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| WinPE (HDD 形式の前)                                                        | X:\\Windows\\Temp\\smstslog\\smsts .log             |
| WinPE (HDD 形式の後)                                                         | C:\\_SMSTaskSequence\\Smstslog\\\\smsts .log をログに記録します。    |
| Configuration Manager エージェントをインストールする前に、オペレーティングシステムが展開されました | c:\\_SMSTaskSequence\\Smstslog\\\\smsts .log をログに記録します。    |
| オペレーティングシステムと Configuration Manager エージェントが展開されている                   | % windir%\\System32\\ccm\\ログ\\Smstslog\\smsts .log |
| タスクシーケンスの実行が完了しました                                                | % windir%\\System32\\ccm\\は\\smsts .log をログに記録します。           |

> [!TIP]
> タスクシーケンス中に**F8**を選択してコマンドコンソールを開き、smsts .log ファイルにアクセスすることができます。

PXE ブートの問題のトラブルシューティングを行うには、PXE の操作に固有の、Configuration Manager サーバー上の2つのログファイルを確認します。

-   **Pxecontrol。** Configuration Manager のインストールログディレクトリにあります。

-   **Smspxe**(Configuration Manager 管理ポイント (MP) logs ディレクトリにあります)

構成マネージャーのインストールをさらにトラブルシューティングするために使用できるログファイルの完全な一覧については、「Microsoft Endpoint Configuration Manager の[ログファイルリファレンス](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/log-files)」を参照してください。
