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
ms.openlocfilehash: 4b922607955d8b825006217bd2fe333eaadbc1ce
ms.sourcegitcommit: cbdc80c302e97d18a923ef57bb5d4b6cf7676d00
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/30/2022
ms.locfileid: "64556568"
---
# <a name="get-clients-for-microsoft-teams"></a>Microsoft Teams のクライアントを取得する

> [!TIP]
> **PC、Mac、またはモバイル デバイスに Teams をインストールしますか?** 「[Teams クライアントのインストール](https://go.microsoft.com/fwlink/?linkid=855754)」を確認してください。

Microsoft Teams は、PC、Mac、およびモバイル デバイスにインストールでき、Web ブラウザーを介してアクセスすることもできます。 ほとんどのエンド ユーザーは、[クライアントを自分でインストールする](https://go.microsoft.com/fwlink/?linkid=855754)だけで Teams の使用を開始できます。 Teams クライアントをインストールした後、ユーザー名とパスワードを使用してログインするだけです。

IT プロフェッショナルであり、Teams のインストール エクスペリエンスとその要件について詳しく知りたい場合は、この記事でクライアント オペレーティング システムを選択し、詳細を確認してください。

さまざまなプラットフォームでの各クライアントの機能の詳細については、「[プラットフォームごとの Teams の機能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)」を参照してください。

## <a name="desktop-clients"></a>デスクトップ クライアント

Teams デスクトップ クライアントは、スタンドアロン アプリケーションとして、および次のオペレーティング システム用の [Microsoft 365 Apps for enterprise](/deployoffice/teams-install) の一部として利用できます。

- 32 ビットおよび 64 ビット バージョンの Windows (8.1 以降)
- ARM 上の Windows 10 用の ARM64
- Windows Server (2012 R2 以降)
- macOS
- Linux (`.deb` および `.rpm` 形式)
- Chrome OS (詳細については、「[Chromebook で Microsoft Office を使用する方法](https://support.office.com/article/how-to-install-and-run-microsoft-office-on-a-chromebook-32f14a23-2c1a-4579-b973-d4b1d78561ad)」を参照してください)

デスクトップ クライアントは、適切なローカルのアクセス許可を持っているエンド ユーザーによって、[https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) から直接ダウンロードおよびインストールできます (管理者権限は、Teams クライアントを Windows PC にインストールする場合には必要ありませんが、Mac では必要になります)。

IT プロフェッショナルは、組織内のコンピューターにインストール ファイルを配布する方法を選択できます。 Microsoft Endpoint Configuration Manager (Windows) や Jamf Pro (macOS) などを選択できます。 Teams の配布の詳細については、以下を参照してください。

- **Windows** [Endpoint Configuration Manager を使用して Teams をインストールする](msi-deployment.md)
- **MacOS** [Jamf Pro](https://www.jamf.com/products/jamf-pro/)

> [!NOTE]
> これらのメカニズムによるクライアントの配布は、Teams クライアントの初回インストール時にのみ利用でき、それ以降の更新では利用できません。 Teams の更新プロセスについては、「[Teams の更新プロセス](teams-client-update.md)」を参照してください。

### <a name="windows"></a>[Windows](#tab/Windows)

> [!TIP]
> Windows Desktop Clientの効果、計画や展開の方法については次のセッションを参照してください。[Teams Windows Desktop Client](https://aka.ms/teams-clients)

Teams on Windows は、[32 ビット](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)、[64 ビット](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)、および [ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) アーキテクチャでダウンロード可能な MSI インストーラーを提供します。 Teams の x86 アーキテクチャ (32 ビットと 64 ビット) はインストールされている Windows および Office のアーキテクチャに依存しません。 64 ビット システムでは、64 ビット版の Teams のご使用をお勧めします。

Teams を使用するには .NET Framework 4.5 以降が必要です。.NET Framework 4.5 以降がインストールされていない場合、Teams のインストーラーでインストールすることになります。

Windows クライアントは、ユーザーのプロファイルにある AppData フォルダーに展開されます。ユーザーのローカル プロファイルに展開すると、クライアントは管理者特権を必要とせずにインストール可能になります。Windows クライアントは次の場所を利用してインストールされます。

- %LocalAppData%\\Microsoft\\Teams

- %LocalAppData%\\Microsoft\\TeamsMeetingAddin

- %AppData%\\Microsoft\\Teams

- %LocalAppData%\\SquirrelTemp

ユーザーが Teams クライアントを使用して初めて通話を開始すると、ユーザーに通信の許可を求める Windows ファイアウォール設定に関する警告が通知される場合があります。警告を受け入れなくても通話は機能するため、このメッセージを無視するように指示される場合があります。

![[Windows セキュリティの重要な警告] ダイアログのスクリーンショット。](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> Windows ファイアウォール設定は、[キャンセル] の選択によりプロンプトが受け入れられなかった場合でも変更されます。TCP および UDP プロトコルの両方に関する許可アクションで、teams.exe に関する2 つの着信ルールが作成されます。

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
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -

sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/ms-teams stable main" > /etc/apt/sources.list.d/teams.list'

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

Teams のモバイル アプリは Android および iOSで利用でき、チャットベースの会話に参加している外出中のユーザーを対象としており、ピアツーピアの音声通話が使用できます。モバイル アプリについては、Google Play と Apple App Store にアクセスしてください。

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

## <a name="browser-client"></a>ブラウザー クライアント

ブラウザー クライアント ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) は、さまざまなブラウザーから使用できる完全で機能的なクライアントです。 ブラウザー クライアントは WebRTC を使用することによって通話と会議をサポートするため、ブラウザーで Teams を実行するためのプラグインやダウンロードの必要がありません。 ブラウザーはサードパーティの Cookie を許可するように設定する必要があります。

[!INCLUDE [browser-support](includes/browser-support.md)]

ブラウザー クライアントは、[https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753) への接続時にブラウザー バージョンの検出を実行します。サポートされていないブラウザー バージョンを検出した場合、ブラウザー インターフェイスへのアクセスをブロックし、ユーザーによるデスクトップ クライアントまたはモバイル アプリのダウンロードを推奨します。
