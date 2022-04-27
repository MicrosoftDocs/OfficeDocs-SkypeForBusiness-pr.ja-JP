---
title: Microsoft Teams のトラブルシューティングでログ ファイルを使用する
ms.reviewer: tejeshs
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 05/06/2021
audience: admin
ms.topic: troubleshooting
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Microsoft Teamsによって生成されるデバッグ、メディア、デスクトップのログについて説明します。このログを見つけることができます。また、監視とトラブルシューティングに役立つ方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4d8e3ab079498ecfca11a7d2ba48736aaf457329
ms.sourcegitcommit: bd05783dfb33a63e0eb083a2135f97d110dc81a3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2022
ms.locfileid: "65059108"
---
# <a name="use-log-files-to-monitor-and-troubleshoot-microsoft-teams"></a>ログ ファイルを使用してMicrosoft Teamsを監視およびトラブルシューティングする

クライアントによって自動的に生成されるログ ファイルには、次の 3 種類があります。これを利用して、Teamsの監視とトラブルシューティングを支援できます。

-   [デバッグ ログ](#debug-logs)

-   [メディア ログ](#media-logs)

-   [デスクトップ ログ](#desktop-logs)

この記事では、これらのログとその使用方法について説明します。 特定の問題のトラブルシューティングの詳細については、「[Teamsトラブルシューティング](/MicrosoftTeams/troubleshoot/teams)」を参照してください。 サポートに問い合わせる方法については、「サポートを [受ける](/microsoft-365/business-video/get-help-support)」を参照してください。 Microsoft サポートを使用してサポート 要求を作成する場合、サポート エンジニアはデバッグ ログを必要とします。 サポート要求を作成する前にデバッグ ログを手元に置くと、Microsoft は問題のトラブルシューティングをすばやく開始できます。 **メディア** ログまたは **デスクトップ** ログは、Microsoft から要求された場合にのみ必要です。

> [!NOTE]
> この記事では、 **デバッグ ログ** という用語は、トラブルシューティングに使用されるログを指します。 ただし、これらのログに対して生成されるファイルには、名前に **診断ログ** という用語が含まれます。  

## <a name="collect-and-enable-logging"></a>ログを収集して有効にする

問題が発生したらすぐにログを収集することが重要です。 ログは、数回のクリックだけで収集できます。

- Windows: システム トレイのTeams アイコンを右クリックし、[**サポート ファイルの収集**] を選択します。 

- Mac: [ヘルプ] メニューを選択し、[ **サポート ファイルの収集**] を選択します。

デバッグ、デスクトップ、メディアのログは、 _MSTeams Diagnostics Log \<local date and time\>_ という名前の 1 つのフォルダーに収集されます。 このフォルダーは、Microsoft サポートでサポート要求を開くときに圧縮および共有できます。 フォルダーには、デスクトップ、会議 (メディア)、およびデバッグ (Web) 用のフォルダーが含まれます。 次のキーボード ショートカットを使用してファイルを収集できます。

- Windows: <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>

- Mac: <kbd>Option</kbd> + <kbd>Command</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>


メディア ログは、メディア [ログ](#media-logs)で説明されている一部の CPU でのみ、既定でオンになっています。 それ以外の場合は、既定ではオフになっています。 メディア ログを有効にするには、ユーザーがTeams クライアントでオプションを有効にする必要があります。 **設定** > **General** に移動し、**会議診断のログ記録を有効にする (Teamsの再起動が必要)** を選択します。 ログを開始するには、Teams クライアントを再起動する必要があります (ドック (Mac) またはタスク バー (Windows) のアイコンを右クリックし、[終了] を選択 **して再起動します**。 終了したら、アプリ アイコンをクリックしてもう一度開きます)。

特定の会議またはライブ イベントで問題が発生した場合は、会議に関連付けられた URL を設定すると便利です。 これにより、ログ内の正確な会議またはライブ イベントを特定するのに役立つ追加情報が提供されます。 この情報は、会議の参加者、またはライブ イベントの発表者またはプロデューサーから収集できます。 この URL は、結合 URL にマウス ポインターを合わせ、[ **ハイパーリンクのコピー**] を選択することでキャプチャできます。

> [!NOTE]
> メディア ログ記録が有効になっている場合は、オーディオとビデオの問題を調査するために必要な追加のファイルが会議フォルダーに含まれます。 メディア ログが有効になっていない場合は、使用可能なログの数に制限があります。
  
> [!NOTE]
> デバッグ ログは、以前は以下のキーボード ショートカットを使用して収集されていました。 これらは引き続き機能し、 **サポート ファイルの収集** オプションと同じログ キャプチャを完了します。
>
> - Windows: <kbd>Crtl</kbd> + <kbd>Alt</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>
>
> - Mac: <kbd>Option</kbd> + <kbd>Command</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>


次の表は、さまざまなクライアントとそれに関連するログの概要を示しています。 ログ ファイルは、クライアントとオペレーティング システムに固有の場所に格納されます。


|クライアント |デバッグ|デスクトップ|メディア|
|---------|---------|---------|---------|
|Web    |X         |-         |-         |
|Windows     |X         |X         |X         |
|Mac OSX     |X         |X         |X         |
|Linux     |X         |X         |X         |
|iOS     |-         |-         |-         |
|Android     |-         |-         |-         |

サポートされるオペレーティング システムとブラウザーの完全なリストについては、「[Microsoft Teams のクライアントを取得する](get-clients.md)」をご覧ください。

## <a name="debug-logs"></a>デバッグ ログ

Windowsと Mac の手順については、「_ログの収集と有効化_」セクションを参照してください。 デバッグ ログは、Windows および Mac デスクトップ クライアントとブラウザー ベースのクライアントによって生成されます。 ログはテキスト ベースで、一番下から読み取られます。 テキスト ベースのエディターを使用して読み取ることができ、クライアントにログインするときに新しいログが作成されます。

デバッグ ログには次のデータ フローが表示されます。

-   ログイン

-   中間層サービスへの接続要求

-   通話/会話

Linux のログを収集するには:
- キーボード ショートカット: <kbd>CtrlAltShift1</kbd> + <kbd></kbd> + <kbd></kbd> + <kbd></kbd>  
- ファイルは次のページで使用できます。 `~/Downloads`

ブラウザーとWindowsのログを収集するには:
- キーボード ショートカット: <kbd>CtrlAltShift1</kbd> + <kbd></kbd> + <kbd></kbd> + <kbd></kbd>  
- ファイルは次のページで使用できます。 `%userprofile%\Downloads`

## <a name="media-logs"></a>メディア ログ

Windowsと Mac の手順については、「_ログの収集と有効化_」セクションを参照してください。 メディア ログには、Teams会議でのオーディオ、ビデオ、画面共有に関する診断データが含まれています。 これらは、通話関連の問題にリンクされているサポート ケースに必要です。

CPU が次の場合、コンピューターのメディア ログは既定でオンになります。
- 任意の Apple M1
- 任意の Intel Xeon
- U、G7、M、MQ シリーズを除くすべての Intel i9
- U、G7、M、MQ シリーズを除く、第 6 世代以降の Intel i7

それ以外の場合は、既定でオフになっています。 Teams会議の診断データを記録するには、ユーザーがTeams クライアントでオプションをオンにする必要があります。 **設定** > **General** に移動し、**会議診断のログ記録を有効にする (Teamsの再起動が必要**) チェック ボックスをオンにし、Teams再起動して問題を再現します。 

> [!NOTE]
> Teamsからサインアウトすると、メディア ログは既定にリセットされます。 

Microsoft サポートにログ ファイルを送信する場合は、ログ ファイルのタイムスタンプを確認して、問題を再現したときの期間をログがカバーしていることを確認してください。

Linux のログを収集するには:  
- ファイルは次の場所で使用できます。
  - `~/.config/Microsoft/Microsoft Teams/media-stack/\*\.blog`
  - `~/.config/Microsoft/Microsoft Teams/skylib/\*\.blog`

Windowsのログを収集するには:  
- ファイルは次の場所で使用できます。
  - `%appdata%\Microsoft\Teams\media-stack\\\*\.blog`
  - `%appdata%\Microsoft\Teams\skylib\\\*\.blog` 

Mac のログを収集するには:
- ファイルは次の場所で使用できます。
  - `~/Library/Application Support/Microsoft/Teams/media-stack\\\*\.blog`
  - `~/Library/Application Support/Microsoft/Teams/skylib\\\*\.blog`

生成されるログ ファイルとそのログ ファイルに含まれる情報の一覧を次に示します。

<br/>

|ログ ファイル名  |説明  |
|---------|---------|
|`Teams.msrtc-0-s1039525249.blog`     | メディア スタックに関連する情報が含まれます。 これには、解像度、デコーダー、エンコーダーの使用、送受信されたフレーム数、カメラとビデオベースの画面共有 (VBSS) セッションの状態などのチャネルの状態が含まれます。         |
|`rtmcontrol.msrtc-0-2415069487.blog`      |コントロールが指定されたときのタイムスタンプやマウス ポインター情報など、リモート コントロール アクションに関連する情報を記録します。          |
|`Teams_MediaStackETW-2-U-xr-U.etl`      |メディア スタック トレース イベントを記録します。         |
|`Debug-0-s2790420889.blog`    | レンダリング品質など、メディア エージェントに関連する情報が含まれます。          |
|`tscalling-0-2061129496.blog`   |ts 呼び出し元 API でイベントを記録します。       |

## <a name="desktop-logs"></a>デスクトップ ログ

Windowsと Mac の手順については、「_ログの収集と有効化_」セクションを参照してください。 デスクトップ ログ (ブートストラップ ログとも呼ばれます) には、デスクトップ クライアントとブラウザーの間で発生するログ データが含まれます。 メディア ログと同様に、これらのログは Microsoft から要求された場合にのみ必要です。 ログはテキスト ベースであり、トップダウン形式の任意のテキスト ベースのエディターを使用して読み取ることができます。

Linux のログを収集するには:
- システム トレイのMicrosoft Teams アイコンをクリックし、[ログの取得] を選択 **します**。
- ファイルは .`~/.config/Microsoft/Microsoft Teams/logs.txt`
  
Windowsのログを収集するには:
- システム トレイのMicrosoft Teams アイコンをクリックし、[**サポート ファイルの収集**] を選択します。
- ファイルは`logs.txt`自動的にメモ帳で開きます。

Teamsへのサインインに関する問題を調査する場合は、デスクトップ ログを手動で収集することが必要な場合があります。 これらのログ ファイルは、Windowsの %appdata%\Microsoft\Teams にあります。

## <a name="browser-trace"></a>ブラウザー トレース

一部のカテゴリのエラーでは、Microsoft サポートブラウザー トレースの収集が必要になる場合があります。 この情報は、エラーが発生した場合のTeams クライアントの状態に関する重要な詳細を提供できます。

ブラウザー トレースを開始する前に、Teamsにサインインしていることを確認します。 トレースを開始する前に、トレースに機密サインイン情報が含まれないようにすることが重要です。

サインインしたら、ブラウザーに応じて次のいずれかのリンクを選択し、指定された手順に従います。 

-   [Chrome & Edge (Chromium)](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [Edge](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [サファリ](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [Firefox](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> 手順では、Azure portalへの参照をすべてTeams クライアントに置き換えます。
  
## <a name="webrtc-logs-in-browsers"></a>ブラウザーの WebRTC ログ
WebRTC ログは、音声通話とビデオ通話の接続の詳細を提供することで、Microsoft サポートを支援できます。 Edge (Chromium) または Chrome で WebRTC ログにアクセスするには、次の手順に従います。 
  
1.  新しいタブを開き、次のいずれかの URL に移動します。
    -   エッジ (Chromium):`edge://webrtc-internals/`
    -   クロム： `chrome://webrtc-internals/`
  
2.  Teams Web アプリケーションを開き、問題を再現します。
  
3.  手順 1 でアクセスしたタブに戻るすると、少なくとも 2 つのタブが表示されます。
    -   GetUserMedia 要求
    -   `https://teams.microsoft.com/url`

4.  Teams アプリケーションの名前を含むタブを選択し、ページコンテンツを保存します。

## <a name="related-topics"></a>関連項目

[Teams のトラブルシューティング](/MicrosoftTeams/troubleshoot/teams)
