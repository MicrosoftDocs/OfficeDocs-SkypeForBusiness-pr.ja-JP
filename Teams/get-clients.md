---
title: Microsoft Teams のクライアントを取得する
author: dstrome
ms.author: dstrome
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: harij, rafarhi
ms.localizationpriority: high
search.appverid: MET150
description: Microsoft Teams で利用可能なさまざまなクライアントを PC、Mac、およびモバイル デバイスにインストールする方法について説明します。
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 33175aecc41dbc631fe8ab16db225762969b5ad6
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614039"
---
# <a name="get-clients-for-microsoft-teams"></a>Microsoft Teams のクライアントを取得する

> [!TIP]
> **PC、Mac、またはモバイル デバイスに Teams をインストールしますか?** 「[Teams クライアントのインストール](https://go.microsoft.com/fwlink/?linkid=855754)」を確認してください。

Microsoft Teams は、PC、Mac、およびモバイル デバイスにインストールでき、Web ブラウザーを介してアクセスすることもできます。 ほとんどのエンド ユーザーは、[クライアントを自分でインストールする](https://go.microsoft.com/fwlink/?linkid=855754)だけで Teams の使用を開始できます。 Teams クライアントをインストールした後、ユーザー名とパスワードを使用してログインするだけです。

IT プロフェッショナルであり、Teams のインストール エクスペリエンスとその要件について詳しく知りたい場合は、この記事でクライアント オペレーティング システムを選択し、詳細を確認してください。

さまざまなプラットフォームでの各クライアントの機能の詳細については、「[プラットフォームごとの Teams の機能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)」を参照してください。

## <a name="desktop-clients"></a>デスクトップ クライアント

Teams デスクトップ クライアントは、スタンドアロン アプリケーションとして、および次のオペレーティング システム用の [Microsoft 365 Apps for enterprise](/deployoffice/teams-install) の一部として利用できます。

- 32 ビットおよび 64 ビット バージョンの Windows (8.1 以降、Windows 10 LTSC を除く) 
- ARM 上の Windows 10 用の ARM64 
- Windows Server (2012 R2 以降)
- macOS
- Linux (`.deb` および `.rpm` 形式)
- Chrome OS (詳細については、「[Chromebook で Microsoft Office を使用する方法](https://support.office.com/article/how-to-install-and-run-microsoft-office-on-a-chromebook-32f14a23-2c1a-4579-b973-d4b1d78561ad)」を参照してください)

Desktop clients can be downloaded and installed by end users directly from [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) if they have the appropriate local permissions. Admin permissions aren't required to install the Teams client on Windows PCs but are required on Macs.

IT プロフェッショナルは、組織内のコンピューターにインストール ファイルを配布する方法を選択できます。 Microsoft Endpoint Configuration Manager (Windows) や Jamf Pro (macOS) などを選択できます。 Teams の配布の詳細については、以下を参照してください。

- **Windows** [Endpoint Configuration Manager を使用して Teams をインストールする](msi-deployment.md)
- **MacOS** [Jamf Pro](https://www.jamf.com/products/jamf-pro/)

> [!NOTE]
> これらのメカニズムによるクライアントの配布は、Teams クライアントの初回インストール時にのみ利用でき、それ以降の更新では利用できません。 Teams の更新プロセスについては、「[Teams の更新プロセス](teams-client-update.md)」を参照してください。

### <a name="windows"></a>[Windows](#tab/Windows)

> [!TIP]
> Windows Desktop Clientの効果、計画や展開の方法については次のセッションを参照してください。[Teams Windows Desktop Client](https://aka.ms/teams-clients)

Teams on Windows は、[32 ビット](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)、[64 ビット](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)、および [ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) アーキテクチャでダウンロード可能な MSI インストーラーを提供します。 Teams の x86 アーキテクチャ (32 ビットと 64 ビット) はインストールされている Windows および Office のアーキテクチャに依存しません。 64 ビット システムでは、64 ビット版の Teams のご使用をお勧めします。

Teams には、.NET Framework 4.5 以降が必要です。 .NET Framework 以降がインストールされていない場合、Teams インストーラーがインストールを提案します。

The Windows client is deployed to the AppData folder located in the user’s profile. Deploying to the user’s local profile allows the client to be installed without requiring elevated permissions. The Windows client leverages the following locations:

- %LocalAppData%\\Microsoft\\Teams

- %LocalAppData%\\Microsoft\\TeamsMeetingAddin

- %AppData%\\Microsoft\\Teams

- %LocalAppData%\\SquirrelTemp

When users initiate a call using the Teams client for the first time, they might notice a warning with the Windows firewall settings that asks for users to allow communication. Users might be instructed to ignore this message because the call will work, even when the warning is dismissed.

![[Windows セキュリティの重要な警告] ダイアログのスクリーンショット。](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> Windows ファイアウォールの構成が変更されます。 TCP プロトコルと UDP プロトコルの両方のteams.exeに対する 2 つの受信規則が作成されます。 
> - ユーザーがローカル管理者であり、[アクセスを許可する] をクリックした場合にのみアクションを許可します。
> - ユーザーがローカル管理者でない場合はアクションをブロックし、いずれの場合も、"キャンセル" を選択してプロンプトが閉じられたときにアクションをブロックします。

ユーザーが Teams から最初の呼び出しを行うときに、Teams がユーザーにファイアウォール ルールの作成を要求しないようにする場合は、[サンプル スクリプト - Microsoft Teams ファイアウォール PowerShell スクリプト](client-firewall-script.md)の PowerShell スクリプトを使用します。

### <a name="mac"></a>[Mac](#tab/Mac)

Mac ユーザーは、macOS コンピューターのパッケージ インストール ファイルを使用して、Teams をインストールできます。 Mac クライアントをインストールするには、管理者権限が必要です。 macOS クライアントは /Applications フォルダーにインストールされます。

1. [Teams のダウンロード ページ](https://teams.microsoft.com/downloads)の、**Mac** で、**Download** をクリックします。
2. パッケージ ファイルをダブルクリックします。
3. インストール ウィザードに従ってインストールを完了します。
4. Teams は、/Applications フォルダーにインストールされます。 これはコンピューター全体のインストールです。

> [!NOTE]
> インストール時に、パッケージが管理者認証情報を要求します。 ユーザーは、管理者であるかどうかに関係なく、管理者認証情報を入力する必要があります。

もしユーザーが現時点で Teams の DMG インストールをしていて、パッケージのインストールと置き換えたい場合は、以下を実行してください。

1. Teams アプリを終了します。
2. Teams アプリをアンインストールします。
3. パッケージ ファイルをインストールします。

IT プロフェッショナルは、Jamf Pro などの管理された展開ソリューションを使用して、Teams インストール ファイルを組織内のすべての Mac に配布できます。

### <a name="linux"></a>[Linux](#tab/Linux)

Linux では、`apt` や `yum` などのパッケージ マネージャーにより、要件すべてのインストールが自動的に試みられます。 しかし、インストールされない場合は、Linux に Teams をインストールする前に、報告されている要件すべてをユーザーがインストールする必要があります。

ユーザーは、ネイティブの Linux パッケージを `.deb` 形式と `.rpm` 形式でインストールできます。 DEB パッケージか RPM パッケージをインストールすると、パッケージ リポジトリが自動的にインストールされます。

- DEB `https://packages.microsoft.com/repos/ms-teams stable main`
- RPM `https://packages.microsoft.com/yumrepos/ms-teams`

システムのパッケージ マネージャーを使用して自動更新を有効にするための署名キーが自動的にインストールされます。 ただし、これは <https://packages.microsoft.com/keys/microsoft.asc> にもあります。 Teams は毎月更新されており、リポジトリが正常にインストールされていれば、システム上の他のパッケージと同様に、システム パッケージ マネージャーによって自動更新が処理されます。

#### <a name="install-teams-using-deb-package"></a>DEB パッケージを使用して Teams をインストールする

1. <https://aka.ms/getteams> からパッケージをダウンロードします。
2. 次のいずれかの方法でインストールします。
    - 適切なパッケージ管理ツールを開き、Linux アプリのセルフガイド インストール プロセスを実行します。
    - ターミナルから実行する場合は、「`sudo dpkg -i **teams download file**`」と入力します。

Teams は、アクティビティから起動することも、ターミナルから「`teams`」と入力して起動することもできます。

#### <a name="install-teams-using-rpm-package"></a>RPM パッケージを使用して Teams をインストールする

1. <https://aka.ms/getteams> からパッケージをダウンロードします。
2. 次のいずれかの方法でインストールします。
    - 適切なパッケージ管理ツールを開き、Linux アプリのセルフガイド インストール プロセスを実行します。
    - ターミナルから実行する場合は、「`sudo yum install **teams download file**`」と入力します。

Teams は、アクティビティから起動することも、ターミナルから「`teams`」と入力して起動することもできます。

#### <a name="install-manually-from-the-command-line"></a>コマンド ラインから手動でインストールする

Debian や Ubuntu のディストリビューションには、次のようにして手動でインストールします。

```bash
curl https://packages.microsoft.com/keys/microsoft.asc | sudo gpg --dearmor -o /usr/share/keyrings/microsoft-archive-keyring.gpg

sudo sh -c 'echo "deb [arch=amd64 signed-by=/usr/share/keyrings/microsoft-archive-keyring.gpg] https://packages.microsoft.com/repos/ms-teams stable main" > /etc/apt/sources.list.d/teams.list'

sudo apt update
sudo apt install teams
```

RHEL、Fedora、CentOS ベースのディストリビューションには、次のようにして手動でインストールします。

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc

sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/teams.repo'

sudo dnf check-update
sudo dnf install teams
```

dnf の代わりに yum を使用する場合は、次のようにします。

```bash
yum check-update
sudo yum install teams
```

openSUSE ベースのディストリビューションには、次のようにして手動でインストールします。

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc

sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\nautorefresh=1\nkeeppackages=0\ntype=rpm-md\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/teams.repo'

sudo zypper refresh
sudo zypper install teams
```

---

## <a name="mobile-clients"></a>モバイル クライアント

The Teams mobile apps are available for Android and iOS, and are geared for on-the-go users participating in chat-based conversations and allow peer-to-peer audio calls. For mobile apps, go to the relevant mobile stores Google Play and the Apple App Store.

Teams モバイル アプリをサポートしているモバイル プラットフォームは次のとおりです。

- **Android**: サポート対象は、最新の 4 つのメジャー バージョンの Android に限られています。 新しいメジャー バージョンの Android がリリースされると、その新しいバージョンと、その前の 3 つのバージョンが正式にサポートされます。

- **iOS**: サポート対象は、最新の 2 つのメジャー バージョンの iOS に限られています。 新しいメジャー バージョンの iOS がリリースされると、その新しいバージョンの iOS と、その 1 つ前のバージョンが正式にサポートされます。

> [!NOTE]
> Teams が正常に動作するには、そのモバイル バージョンが公開されている必要があります。

モバイル アプリは、それぞれのモバイル プラットフォームのアプリ ストアからのみ配布および更新されます。 MDM やサイド ロードからモバイル アプリを配布することは、Microsoft ではサポートしていません。 サポートされているモバイル プラットフォームにモバイル アプリがインストールされると、Teams モバイル アプリ自体、そのバージョンが現在のリリースから 3 か月以内であればサポートされます。

中国にいる場合は、次のアプリ ストアから Teams をインストールできます。

- **Xiaomi** <https://aka.ms/TeamsXiaomi>
- **Huawei** <https://aka.ms/TeamsHuawei>
- **Oppo** Oppo ストアで "Teams" を検索する
- **Baidu** <https://aka.ms/teams_baidu_direct_dl>

> [!NOTE]
> ユーザーが中国ベースの Android アプリ ストアから Teams をインストールし、Teams のプッシュ通知を有効にすると、Microsoft は中国ベースのプッシュ通知サービスを通じて Teams プッシュ通知を提供します。

## <a name="browser-client"></a>ブラウザー クライアント

ブラウザー クライアント ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) は、さまざまなブラウザーから使用できる完全で機能的なクライアントです。 ブラウザー クライアントは WebRTC を使用することによって通話と会議をサポートするため、ブラウザーで Teams を実行するためのプラグインやダウンロードの必要がありません。 ブラウザーはサードパーティの Cookie を許可するように設定する必要があります。

[!INCLUDE [browser-support](includes/browser-support.md)]

The browser client performs browser version detection upon connecting to [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753). If an unsupported browser version is detected, it will block access to the browser interface and recommend that the user download the desktop client or mobile app.
