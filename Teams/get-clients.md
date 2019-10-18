---
title: Microsoft Teams のクライアントを取得する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 04/25/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: harij, rafarhi
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams で利用できる Web、デスクトップ (Windows、Mac)、およびモバイル (Android、iOS) などのさまざまなクライアントを使用する方法を知る。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1e8a77a6d03735769e61f679126b3a5aac7f70e3
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "37563610"
---
<a name="get-clients-for-microsoft-teams"></a>Microsoft Teams のクライアントを取得する 
===========================

Microsoft Teams には、Web、デスクトップ (Windows、Mac)、およびモバイル (Android、iOS) で利用できるクライアントがあります。これらのクライアントはすべてインターネット接続が必要で、オフライン モードをサポートしていません。

> [!NOTE]
> 2018 年 11 月 29 日付で、Microsoft Store から入手可能な Microsoft Teams の Windows 10 S (プレビュー) アプリが使用できなくなります。 代わりに、Windows 10 S モードを実行しているデバイスに Teams デスクトップクライアントをダウンロードしてインストールできるようになりました。 デスクトップクライアントをダウンロードするには、 [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754)にアクセスしてください。 Teams デスクトップクライアントの MSI ビルドは、Windows 10 S モードを実行しているデバイスではまだ利用できません。
>
> Windows 10 S モードの詳細については、「 [windows 10 を S モードで導入](https://www.microsoft.com/windows/s-mode)する」を参照してください。 

<a name="desktop-client"></a>デスクトップ クライアント
--------------

> [!Tip]
> Windows Desktop Clientの効果、計画や展開の方法については次のセッションを参照してください。[Teams Windows Desktop Client](https://aka.ms/teams-clients)

Microsoft Teams デスクトップクライアントは、スタンドアロンアプリケーションであり、 [Office 365 ProPlus でも利用でき](https://docs.microsoft.com/en-us/deployoffice/teams-install)ます。 Microsoft Teams は、Windows (7 以上) の32 ビット、 64 ビット バージョン、および macOS (10.10 以上) で利用できます。 Windows で Teams を使用するには .NET Framework 4.5 以降が必要です。.NET Framework 4.5 以降がない場合は、Teams のインストーラーでインストールすることを勧めます。 

デスクトップ クライアントは、チーム会議、グループ通話、およびプライベートな 1 対 1 での通話に対応するリアルタイム通信のサポート (オーディオ、ビデオ、およびコンテンツ共有) を提供します。

デスクトップ クライアントは、適切なローカルのアクセス許可を持っているエンド ユーザーによって、[https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) から直接ダウンロードおよびインストールできます (管理者権限は、Teams クライアントを PC にインストールする場合には必要ありませんが、Mac では必要になります) 。

IT 管理者は好きな方法で、System Center Configuration Manager (Windows)、または Jamf Pro (macOS) などのインストール ファイルを組織のコンピューターに配布できます。 Windows ディストリビューションの MSI パッケージを取得するには、[MSI を使用して Microsoft Teams をインストールする](msi-deployment.md)を参照ください。  

> [!NOTE]
> これらのメカニズムによるクライアントの配布は、Microsoft Teams クライアントの初回インストール時にのみ利用でき、それ以降の更新では利用できません。

### <a name="windows"></a>Windows

Windows での Microsoft Teams のインストールでは、32 ビットと 64 ビット アーキテクチャでダウンロード可能なインストーラーが提供されます。

> [!NOTE]
> Microsoft Teams のアーキテクチャ (32 ビットと 64 ビット) はインストールされている Windows および Office のアーキテクチャに依存しません。

Windows クライアントは、ユーザーのプロファイルの AppData フォルダーに展開されます。 ユーザーのローカル プロファイルへの展開で、権限を必要とせずクライアントをインストールする事ができます。 Windows クライアントは、次の場所を利用します。

- %LocalAppData%\\Microsoft\\Teams

- % LocalAppData%\\Microsoft\\TeamsMeetingAddin

- %AppData%\\Microsoft\\Teams

- %LocalAppData%\\SquirrelTemp

ユーザーが Microsoft Teams クライアントを使用して初めて通話を開始する時は、ユーザーに通信の許可を求める Windows ファイアウォール設定の警告が通知される場合があります。 警告を受け入れなくても通話は機能するため、このメッセージを無視するように指示される場合があります。

![[Windows セキュリティの重要な警告] ダイアログのスクリーンショット。](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> Windows ファイアウォール設定は、[キャンセル] の選択によりプロンプトが受け入れられなかった場合でも変更されます。TCP および UDP プロトコルの両方に関するブロック アクションで、teams.exe に関する2 つの着信ルールが作成されます。

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

<a name="web-client"></a>Web クライアント 
----------

Web クライアント ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) は、さまざまなブラウザーから使用できる、完全な機能クライアントです。 Web クライアントは WebRTC を使用することによって通話と会議をサポートするため、Web ブラウザーで Teams を実行するためのプラグインやダウンロードの必要がありません。 ブラウザーはサードパーティの Cookie を許可するように設定する必要があります。 

[!INCLUDE [browser-support](includes/browser-support.md)]

Web クライアントは[https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)への接続時にブラウザーのバージョンの検出を実行します。 サポートされていないブラウザー バージョンを検出した場合、Web インターフェイスへのアクセスをブロックし、デスクトップ クライアントまたはモバイル アプリのダウンロードをユーザーに推奨します。

<a name="mobile-clients"></a>モバイル クライアント
--------------

Microsoft Teams モバイル アプリは Android および iOS で利用可能で、外出先でチャット会話に参加しているユーザーを対象とし、ピア ツー ピアの音声通話を許可します。 モバイル アプリを使用する場合は、Google Play と Apple App Store の関連モバイル ストアに移動します。 Windows Phone App は 2018 年 7 月 20 日に廃止された為、動作しなくなる可能性があります。 

Microsoft Teams モバイル アプリのサポートされるモバイル プラットフォームは次のとおりです。

-   **Android**: 4.4 以降

-   **iOS**: 10.0 以降

> [!NOTE]
> Teams が問題なく動作するためには、モバイル バージョンが利用可能な状態である必要があります。

モバイルアプリは、対応するモバイルプラットフォームのアプリストアのみを通じて配布および更新されます。 MDM またはサイドローディングによるモバイルアプリの配布は、Microsoft によってサポートされていません。 サポートされているモバイルプラットフォームにモバイルアプリをインストールすると、そのバージョンが現在のリリースの3か月間に含まれている場合は、Teams モバイルアプリ自体がサポートされます。


| | | |
|---------|---------|---------|
|![判断ポイントを示すアイコン](media/Get_clients_for_Microsoft_Teams_image4.png)      |判断ポイント         |ユーザーが適切な Microsoft Teams クライアントをデバイスにインストールすることを妨げる制限事項はありますか?         |
|![次の手順を示すアイコン](media/Get_clients_for_Microsoft_Teams_image5.png)     |次のステップ         |組織によってソフトウェアのインストールが制限されている場合、処理が Microsoft Teams に対応していることを確認してください。注意: 管理者権限は、PC クライアント インストールでは必要ありませんが、Mac へのインストールでは必要になります。         |

<a name="client-update-management"></a>クライアントの更新管理
------------------------

現在、クライアントは、IT 管理者による介入を必要とせずに、Microsoft Teams サービスによって自動的に更新されます。 更新プログラムが利用可能な場合、クライアントは更新プログラムを自動的にダウンロードします。アプリの有効期限 led が一定期間続いた場合は、更新プロセスが開始されます。

<a name="client-side-configurations"></a>クライアント側の設定
---------------------------

現在、テナント管理者、PowerShell、グループ ポリシー オブジェクトまたはレジストリのいずれかを介してクライアントを設定するオプションはサポートされていません。

<a name="notification-settings"></a>通知の設定
----------------------------

現在、IT 管理者がクライアント側の通知設定を設定するオプションはありません。通知オプションはすべてユーザーによって設定されます。次の図に、既定のクライアント設定の概要を示します。

![通知設定のスクリーンショット。](media/Get_clients_for_Microsoft_Teams_image6.png)

<a name="sample-powershell-script"></a>PowerShell のサンプル スクリプト
----------------------------

このサンプル スクリプトは、管理者アカウントのコンテキスト内のクライアント コンピューターで実行する必要があり、c:\users にある各ユーザーのフォルダーの新しい受信ファイアウォール ルールを作成します。 Teams がこのルールを検出すると、ユーザーが Teams からの最初の呼び出しを行うときに、ファイアウォール ルールを作成する為の Teams アプリケーションからユーザーへの指示ができなくなります。 

```

<#
.Synopsis
   Creates firewall rules for Teams.
.DESCRIPTION
   (c) Microsoft Corporation 2018. All rights reserved. Script provided as-is without any warranty of any kind. Use it freely at your own risks.
   Must be run with elevated permissions. Can be run as a GPO Computer Startup script, or as a Scheduled Task with elevated permissions. 
   The script will create a new inbound firewall rule for each user folder found in c:\users. 
   Requires PowerShell 3.0.
#>

#Requires -Version 3

$users = Get-ChildItem (Join-Path -Path $env:SystemDrive -ChildPath 'Users') -Exclude 'Public', 'ADMINI~*'
if ($users.Length -gt 0)
{
    foreach ($user in $users)
    {
        $progPath = Join-Path -Path $user.FullName -ChildPath "AppData\Local\Microsoft\Teams\Current\Teams.exe"
        if (Test-Path $progPath)
        {
            if (-not (Get-NetFirewallApplicationFilter -Program $progPath -ErrorAction SilentlyContinue))
            {
                $ruleName = "Teams.exe for user $($user.Name)"
                "UDP", "TCP" | ForEach-Object { New-NetFirewallRule -DisplayName $ruleName -Direction Inbound -Profile Domain -Program $progPath -Action Allow -Protocol $_ }
                Clear-Variable ruleName
            }
        }
        Clear-Variable progPath
    }
}

```
