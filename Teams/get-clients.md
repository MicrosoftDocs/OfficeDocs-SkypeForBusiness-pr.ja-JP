---
title: Microsoft Teams のクライアントを取得する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: harij, rafarhi
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams で利用できる Web、デスクトップ (Windows、Mac)、およびモバイル (Android、iOS) などのさまざまなクライアントを使用する方法を知る。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: d75a76ca7a98191f90005ebe6c1edf915fde4571
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "43778303"
---
# <a name="get-clients-for-microsoft-teams"></a>Microsoft Teams のクライアントを取得する 


Microsoft Teams には、デスクトップ (Windows、Mac、Linux)、Web、モバイル (Android および iOS) で利用できるクライアントがあります。 これらのクライアントすべてにアクティブなインターネット接続が必要で、オフライン モードはサポートされていません。

> [!NOTE]
> 2018 年 11 月 29 日付で、Microsoft Store から入手可能な Microsoft Teams の Windows 10 S (プレビュー) アプリが使用できなくなります。 代わりに、Windows 10 S モードを実行しているデバイスに、Teams デスクトップ クライアントをダウンロードしてインストールできるようになりました。 デスクトップ クライアントをダウンロードするには、[https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) にアクセスしてください。 Teams デスクトップ クライアントの MSI ビルドは、Windows 10 S モードを実行しているデバイスではまだ利用できません。
>
> Windows 10 S モードの詳細については、「[Windows 10 (S モード) について](https://www.microsoft.com/windows/s-mode)」を参照してください。 

## <a name="desktop-client"></a>デスクトップ クライアント

> [!TIP]
> Windows Desktop Clientの効果、計画や展開の方法については次のセッションを参照してください。[Teams Windows Desktop Client](https://aka.ms/teams-clients)

Microsoft Teams デスクトップクライアントは、スタンドアロンアプリケーションです。また、[エンタープライズ向けの microsoft 365 アプリでも利用でき](https://docs.microsoft.com/deployoffice/teams-install)ます。 Teams は、32 ビット版と 64 ビット版の Windows (8.1 以降) および Windows Server (2012 R2 以降) に加えて、macOS (10.10 以降) および Linux (`.deb` 形式と `.rpm` 形式) でも利用できます。 Windows で Teams を使用するには .NET Framework 4.5 以降が必要です。.NET Framework 4.5 以降がない場合は、Teams のインストーラーでインストールすることを勧めます。 Linux では、`apt` や `yum` などのパッケージ マネージャーにより、要件すべてのインストールが自動的に試みられます。 しかし、インストールされない場合は、Linux に Teams をインストールする前に、報告されている要件すべてをユーザーがインストールする必要があります。

デスクトップ クライアントは、チーム会議、グループ通話、およびプライベートな 1 対 1 での通話に対応するリアルタイム通信のサポート (オーディオ、ビデオ、およびコンテンツ共有) を提供します。

デスクトップ クライアントは、適切なローカルのアクセス許可を持っているエンド ユーザーによって、[https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) から直接ダウンロードおよびインストールできます (管理者権限は、Teams クライアントを PC にインストールする場合には必要ありませんが、Mac では必要になります) 。

> [!NOTE]
> Chromebook への Teams のインストールの詳細については、 [Chromebook に Microsoft Office をインストールして実行する方法](https://support.office.com/article/how-to-install-and-run-microsoft-office-on-a-chromebook-32f14a23-2c1a-4579-b973-d4b1d78561ad)を参照してください。

IT 管理者は、組織内のコンピューターにインストール ファイルを配布する方法を選択できます。 Microsoft Endpoint Configuration Manager (Windows) や Jamf Pro (macOS) などを選択できます。 Windows ディストリビューションの MSI パッケージを取得するには、[MSI を使用して Microsoft Teams をインストールする](msi-deployment.md)を参照ください。  

> [!NOTE]
> これらのメカニズムによるクライアントの配布は、Microsoft Teams クライアントの初回インストール時にのみ利用でき、それ以降の更新では利用できません。

### <a name="windows"></a>Windows

Windows での Microsoft Teams のインストールでは、32 ビットと 64 ビット アーキテクチャでダウンロード可能なインストーラーが提供されます。

> [!NOTE]
> Microsoft Teams のアーキテクチャ (32 ビットと 64 ビット) はインストールされている Windows および Office のアーキテクチャに依存しません。

Windows クライアントは、ユーザーのプロファイルの AppData フォルダーに展開されます。 ユーザーのローカル プロファイルへの展開で、権限を必要とせずクライアントをインストールする事ができます。 Windows クライアントは、次の場所を利用します。

- %LocalAppData%\\Microsoft\\Teams

- %LocalAppData%\\Microsoft\\TeamsMeetingAddin

- %AppData%\\Microsoft\\Teams

- %LocalAppData%\\SquirrelTemp

ユーザーが Microsoft Teams クライアントを使用して初めて通話を開始する時は、ユーザーに通信の許可を求める Windows ファイアウォール設定の警告が通知される場合があります。 警告を受け入れなくても通話は機能するため、このメッセージを無視するように指示される場合があります。

![[Windows セキュリティの重要な警告] ダイアログのスクリーンショット。](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> Windows ファイアウォール設定は、[キャンセル] の選択によりプロンプトが受け入れられなかった場合でも変更されます。TCP および UDP プロトコルの両方に関するブロック アクションで、teams.exe に関する2 つの着信ルールが作成されます。

ユーザーが Teams から最初の通話を行ったときに、ユーザーがファイアウォールルールを作成することをユーザーに要求しないようにするには、次の[PowerShell スクリプトのサンプル](#sample-powershell-script---inbound-firewall-rule)を使用します。 

### <a name="mac"></a>Mac

Mac ユーザーは、macOS コンピューターのパッケージ インストール ファイルを使用して、Teams をインストールできます。 Mac クライアントをインストールするには、管理者権限が必要です。 macOS クライアントは /Applications フォルダーにインストールされます。

#### <a name="install-teams-by-using-the-pkg-file"></a>パッケージ ファイルを使用して Teams をインストールします。

1. [Teams のダウンロード ページ](https://teams.microsoft.com/downloads)の、**Mac**で、**Download**をクリックします。
2. パッケージ ファイルをダブルクリックします。
3. インストール ウィザードに従ってインストールを完了します。
4. Teams は、/Applications フォルダーにインストールされます。 これはコンピューター全体のインストールです。

> [!NOTE]
> インストール時に、パッケージが管理者認証情報を要求します。 ユーザーは、管理者であるかどうかに関係なく、管理者認証情報を入力する必要があります。

もしユーザーが現時点で Teams の DMG インストールをしていて、パッケージのインストールと置き換えたい場合は、以下を実行してください。

1. Teams アプリを終了します。
2. Teams アプリをアンインストールします。
3. パッケージ ファイルをインストールします。

IT 管理者は、Teams の管理の展開を使用して、Jamf Pro などの組織のすべての Mac にインストール ファイルを配布することができます。

> [!NOTE]
> パッケージのインストールで問題が発生した場合は、報告してください。 この記事の最後の**フィードバック**セクションで、**製品のフィードバック**をクリックします。

### <a name="linux"></a>Linux

ユーザーは、ネイティブの Linux パッケージを `.deb` 形式と `.rpm` 形式でインストールできます。
DEB または RPM パッケージをインストールすると、パッケージリポジトリが自動的にインストールされます。
- DEB `https://packages.microsoft.com/repos/ms-teams stable main`
- RPM `https://packages.microsoft.com/yumrepos/ms-teams` 

システムのパッケージ マネージャーを使用して自動更新を有効にするための署名キーが自動的にインストールされます。 ただし、これは (https://packages.microsoft.com/keys/microsoft.asc) にもあります。 Microsoft Teams は毎月更新されており、リポジトリが正常にインストールされていれば、システム上の他のパッケージと同様に、システム パッケージ マネージャーによって自動更新が処理されます。

> [!NOTE] 
> バグが見つかった場合は、クライアント内から `Report a Problem` を使用してご報告ください。 既知の問題については、「[既知の問題](Known-issues.md)」を参照してください。
> Linux 向けの Teams のサポートについては、[Microsoft Q&A の Linux フォーラム サポート チャネル](https://docs.microsoft.com/answers/topics/teams.html) をご利用いただけます。 質問を投稿するときは、必ず `teams-linux` タグを使用してください。 

#### <a name="install-teams-using-deb-package"></a>DEB パッケージを使用して Teams をインストールする

1. https://aka.ms/getteams からパッケージをダウンロードします。
2. 次のいずれかの方法でインストールします。  
    - 適切なパッケージ管理ツールを開き、Linux アプリのセルフガイド インストール プロセスを実行します。
    - ターミナルから実行する場合は、「`sudo apt install **teams download file**`」と入力します。

Teams は、アクティビティから起動することも、ターミナルから「`Teams`」と入力して起動することもできます。 

#### <a name="install-teams-using-rpm-package"></a>RPM パッケージを使用して Teams をインストールする

1. https://aka.ms/getteams からパッケージをダウンロードします。
2. 次のいずれかの方法でインストールします。
    - 適切なパッケージ管理ツールを開き、Linux アプリのセルフガイド インストール プロセスを実行します。
    - ターミナルから実行する場合は、「`sudo yum install **teams download file**`」と入力します。

Teams は、アクティビティから起動することも、ターミナルから「`Teams`」と入力して起動することもできます。

#### <a name="install-manually-from-the-command-line"></a>コマンド ラインから手動でインストールする

Debian や Ubuntu のディストリビューションには、次のようにして手動でインストールします。
```
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -
 
sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/ms-teams stable main" > /etc/apt/sources.list.d/teams.list'
 
sudo apt update
sudo apt install teams
```

RHEL、Fedora、CentOS ベースのディストリビューションには、次のようにして手動でインストールします。
```
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
 
sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/teams.repo'
 
sudo dnf check-update
sudo dnf install teams
```

dnf の代わりに yum を使用する場合は、次のようにします。
```
yum check-update
sudo yum install teams
```

openSUSE ベースのディストリビューションには、次のようにして手動でインストールします。
```
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
 
sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\nautorefresh=1\nkeeppackages=0\ntype=rpm-md\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/teams.repo'
 
sudo zypper refresh
sudo zypper install teams
```

## <a name="web-client"></a>Web クライアント 

Web クライアント ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) は、さまざまなブラウザーから使用できる、完全な機能クライアントです。 Web クライアントは WebRTC を使用することによって通話と会議をサポートするため、Web ブラウザーで Teams を実行するためのプラグインやダウンロードの必要がありません。 ブラウザーはサードパーティの Cookie を許可するように設定する必要があります。 

[!INCLUDE [browser-support](includes/browser-support.md)]

Web クライアントは[https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)への接続時にブラウザーのバージョンの検出を実行します。 サポートされていないブラウザー バージョンを検出した場合、Web インターフェイスへのアクセスをブロックし、デスクトップ クライアントまたはモバイル アプリのダウンロードをユーザーに推奨します。

## <a name="mobile-clients"></a>モバイル クライアント

Microsoft Teams モバイル アプリは Android および iOS で利用可能で、外出先でチャット会話に参加しているユーザーを対象とし、ピア ツー ピアの音声通話を許可します。 モバイル アプリを使用する場合は、Google Play と Apple App Store の関連モバイル ストアに移動します。 Windows Phone App は 2018 年 7 月 20 日に廃止された為、動作しなくなる可能性があります。 

中国で Android 用 Teams を取得する方法については、[こちら](get-teams-android-in-china.md)を参照してください。 

Microsoft Teams モバイル アプリをサポートしているモバイル プラットフォームは次のとおりです。

-   **Android**: サポート対象は、最新の 4 つのメジャー バージョンの Android に限られています。 新しいメジャー バージョンの Android がリリースされると、その新しいバージョンと、その前の 3 つのバージョンが正式にサポートされます。

-   **iOS**: サポート対象は、最新の 2 つのメジャー バージョンの iOS に限られています。 新しいメジャー バージョンの iOS がリリースされると、その新しいバージョンの iOS と、その 1 つ前のバージョンが正式にサポートされます。

> [!NOTE]
> Teams が正常に動作するには、そのモバイル バージョンが公開されている必要があります。

モバイル アプリは、それぞれのモバイル プラットフォームのアプリ ストアからのみ配布および更新されます。 MDM やサイド ロードからモバイル アプリを配布することは、Microsoft ではサポートしていません。 サポートされているモバイル プラットフォームにモバイル アプリがインストールされると、Teams モバイル アプリ自体、そのバージョンが現在のリリースから 3 か月以内であればサポートされます。


| | | |
|---------|---------|---------|
|![判断ポイントを表すアイコン](media/Get_clients_for_Microsoft_Teams_image4.png)      |判断ポイント         |ユーザーが適切な Microsoft Teams クライアントをデバイスにインストールすることを妨げる制限事項はありますか?         |
|![次のステップを表すアイコン](media/Get_clients_for_Microsoft_Teams_image5.png)     |次のステップ         |組織によってソフトウェアのインストールが制限されている場合、処理が Microsoft Teams に対応していることを確認してください。注意: 管理者権限は、PC クライアント インストールでは必要ありませんが、Mac へのインストールでは必要になります。         |

## <a name="client-update-management"></a>クライアントの更新管理

クライアントは現在、Microsoft Teams サービスによって自動的に更新されています。IT 管理者が介入する必要はありません。 利用可能な更新プログラムがある場合、クライアントは自動的にその更新プログラムをダウンロードします。アプリが一定時間アイドル状態となった場合には更新処理が開始されます。

## <a name="client-side-configurations"></a>クライアント側の設定

現在、テナント管理者、PowerShell、グループ ポリシー オブジェクトまたはレジストリのいずれかを介してクライアントを設定するオプションはサポートされていません。

## <a name="notification-settings"></a>通知の設定

現在、IT 管理者がクライアント側の通知設定を設定するオプションはありません。通知オプションはすべてユーザーによって設定されます。次の図に、既定のクライアント設定の概要を示します。

![通知設定のスクリーンショット。](media/Get_clients_for_Microsoft_Teams_image6.png)

## <a name="sample-powershell-script---inbound-firewall-rule"></a>PowerShell スクリプトの例-受信ファイアウォールの規則

このサンプル スクリプトは、管理者アカウントのコンテキスト内のクライアント コンピューターで実行する必要があり、c:\users にある各ユーザーのフォルダーの新しい受信ファイアウォール ルールを作成します。 Teams がこのルールを検出すると、ユーザーが Teams からの最初の呼び出しを行うときに、ファイアウォール ルールを作成する為の Teams アプリケーションからユーザーへの指示ができなくなります。 

```powershell
<#
.SYNOPSIS
   Creates firewall rules for Teams.
.DESCRIPTION
   (c) Microsoft Corporation 2018. All rights reserved. Script provided as-is without any warranty of any kind. Use it freely at your own risks.
   Must be run with elevated permissions. Can be run as a GPO Computer Startup script, or as a Scheduled Task with elevated permissions. 
   The script will create a new inbound firewall rule for each user folder found in c:\users. 
   Requires PowerShell 3.0.
#>

#Requires -Version 3

$users = Get-ChildItem (Join-Path -Path $env:SystemDrive -ChildPath 'Users') -Exclude 'Public', 'ADMINI~*'
if ($null -ne $users) {
    foreach ($user in $users) {
        $progPath = Join-Path -Path $user.FullName -ChildPath "AppData\Local\Microsoft\Teams\Current\Teams.exe"
        if (Test-Path $progPath) {
            if (-not (Get-NetFirewallApplicationFilter -Program $progPath -ErrorAction SilentlyContinue)) {
                $ruleName = "Teams.exe for user $($user.Name)"
                "UDP", "TCP" | ForEach-Object { New-NetFirewallRule -DisplayName $ruleName -Direction Inbound -Profile Domain -Program $progPath -Action Allow -Protocol $_ }
                Clear-Variable ruleName
            }
        }
        Clear-Variable progPath
    }
}
```
