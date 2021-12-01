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
description: Microsoft Teams によって生成されたデバッグ ログ、メディア ログ、デスクトップ ログ、ログが見つかる場所、および監視とトラブルシューティングに役立つ方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 28fa78eb20b88fe0a159fab12636ce546453835e
ms.sourcegitcommit: be8b820caf4b5a1a91ad444ba93da1df20bf63ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2021
ms.locfileid: "61257318"
---
# <a name="use-log-files-to-monitor-and-troubleshoot-microsoft-teams"></a>ログ ファイルを使用して、ログの監視とトラブルシューティングを行Microsoft Teams

クライアントによって自動的に生成されるログ ファイルには、次の 3 種類があります。このファイルは、クライアントの監視とトラブルシューティングに役立Teams。

-   [デバッグ ログ](#debug-logs)

-   [メディア ログ](#media-logs)

-   [デスクトップ ログ](#desktop-logs)

この記事では、これらのログとログの使い方について説明します。 特定の問題のトラブルシューティングについては、「トラブルシューティング」を参照[Teamsしてください](/MicrosoftTeams/troubleshoot/teams)。 サポートに連絡する方法については、「サポートを受け取る [」を参照してください](/microsoft-365/business-video/get-help-support)。 Microsoft サポートでサポート要求を作成する場合、サポート エンジニアはデバッグ ログを必要とします。 サポート要求を作成する前にデバッグ ログを用意すると、Microsoft が問題のトラブルシューティングをすぐに開始できます。 **メディア** ログまたは **デスクトップ ログ** は、Microsoft から要求された場合にのみ必要です。

> [!NOTE]
> この記事では、デバッグ ログ **という用語は** 、トラブルシューティングに使用されるログを指します。 ただし、これらのログに対して生成されるファイルには、診断ログという用語 **が** 名前に含まれます。  

## <a name="collect-and-enable-logging"></a>ログを収集して有効にする

問題が発生するとすぐにログを収集することが重要です。 ログは、2 回のクリックだけで収集できます。

- Windows: システム トレイの [Teams] アイコンを右クリックし、[サポート ファイルの収集 **] を選択します**。 

- Mac: [ヘルプ] メニューを選択し、[サポート ファイルの収集 **] を選択します**。

デバッグ ログ、デスクトップ ログ、およびメディア ログは _、MSTeams Diagnostics Log \<local date and time\>_ という名前の 1 つのフォルダーに収集されます。 このフォルダーは、Microsoft サポートでサポート要求を開く際に圧縮および共有できます。 フォルダーには、デスクトップ、会議 (メディア)、デバッグ (Web) のフォルダーが含まれます。 次のキーボード ショートカットを使用して、ファイルを収集できます。

- Windows: Ctrl <kbd></kbd> + <kbd>Alt</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>

- Mac: <kbd>Option</kbd> + <kbd>Command</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>


メディア ログは既定でオフになっています。 メディア のログ記録を有効にするには、ユーザーはクライアントでオプションを有効Teamsがあります。 [全般]**設定**  >  **に移動** し、[会議の診断のログ記録を有効にする **] を選択します (Teams)。** ログTeamsを開始するには、クライアントを再起動する必要があります。

特定の会議またはライブ イベントで問題が発生した場合は、その URL を会議に関連付けることができます。 これにより、ログ内の正確な会議またはライブ イベントを特定するのに役立つ追加情報が提供されます。 この情報は、会議の参加者、またはライブ イベントの発表者またはプロデューサーから収集できます。 この URL は、結合 URL の上にマウス ポインターを置き、[ハイパーリンクのコピー] を選択 **することでキャプチャできます**。

> [!NOTE]
> メディア のログ記録が有効になっている場合は、オーディオとビデオの問題を調査するために必要な追加のファイルが [会議] フォルダーに含まれます。 メディア ログが有効になっていない場合、使用できるログの数は限られています。
  
> [!NOTE]
> デバッグ ログは、以前は以下のキーボード ショートカットを使用して収集されています。 これらは引き続き機能し、[サポート ファイルの収集] オプションと同 **じログ キャプチャが完了** します。
>
> - Windows: <kbd>Crtl</kbd> + <kbd>Alt</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>
>
> - Mac: <kbd>Option</kbd> + <kbd>Command</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>


次の表は、さまざまなクライアントとその関連ログの概要を示しています。 ログ ファイルは、クライアントとオペレーティング システムに固有の場所に格納されます。


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

詳細については _、「ログの収集と有効化_」セクションをWindows Mac の手順を参照してください。 デバッグ ログは、Windows Mac デスクトップ クライアントとブラウザー ベースのクライアントによって生成されます。 ログはテキスト ベースであり、ボトムアップから読み取りされます。 任意のテキスト ベースのエディターを使用して読み取り、クライアントにログインするときに新しいログが作成されます。

デバッグ ログには次のデータ フローが表示されます。

-   ログイン

-   中層サービスへの接続要求

-   通話/会話

Linux のログを収集するには:
- キーボード ショートカット: <kbd>Ctrl</kbd>  +  <kbd>Alt</kbd>  +  <kbd>Shift</kbd>  +  <kbd>1</kbd>  
- ファイルは、 `~/Downloads`

ブラウザーとブラウザーのログを収集Windows。
- キーボード ショートカット: <kbd>Ctrl</kbd>  +  <kbd>Alt</kbd>  +  <kbd>Shift</kbd>  +  <kbd>1</kbd>  
- ファイルは、 `%userprofile%\Downloads`

## <a name="media-logs"></a>メディア ログ

詳細については _、「ログの収集と有効化_」セクションをWindows Mac の手順を参照してください。 メディア ログには、音声、ビデオ、画面共有に関する診断データがTeamsされます。 これらは、通話関連の問題にリンクされているサポート ケースに必要です。

メディア ログは既定でオフになっています。 会議の診断データをTeamsするには、ユーザーがクライアントでオプションを有効Teamsがあります。 [全般]**設定** に移動し、[会議の診断のログ記録を有効にする (Teams を再起動する必要があります) チェック ボックスをオンにし、Teams を再起動して、問題を  >  再現します。  

ログ ファイルを Microsoft サポートに送信する場合は、ログ ファイルのタイムスタンプを確認して、問題を再現した時間をログで確実にカバーしてください。

Linux のログを収集するには:  
- ファイルは次の場所で使用できます。
  - `~/.config/Microsoft/Microsoft Teams/media-stack/\*\.blog`
  - `~/.config/Microsoft/Microsoft Teams/skylib/\*\.blog`

データのログを収集Windows。  
- ファイルは次の場所で使用できます。
  - `%userprofile%\Downloads\MSTeams Diagnostics Log\meeting\media-stack\\\*\.blog`
  - `%userprofile%\Downloads\MSTeams Diagnostics Log\meeting\skylib\\\*\.blog` 

生成されるログ ファイルとログ ファイルに含まれる情報の一覧を次に示します。

<br/>

|ログ ファイル名  |説明  |
|---------|---------|
|`Teams.msrtc-0-s1039525249.blog`     | メディア スタックに関連する情報が含まれる。 これには、解像度、デコーダーとエンコーダーの使用、送信および受信されたフレーム数、カメラとビデオ ベースの画面共有 (VBSS) セッションの状態などのチャネルの状態が含まれます。         |
|`rtmcontrol.msrtc-0-2415069487.blog`      |コントロールを指定した場合のタイムスタンプ、マウス ポインター情報など、リモート制御アクションに関連する情報を記録します。          |
|`Teams_MediaStackETW-2-U-xr-U.etl`      |メディア スタック トレース イベントを記録します。         |
|`Debug-0-s2790420889.blog`    | レンダリング品質など、メディア エージェントに関連する情報が含まれる。          |
|`tscalling-0-2061129496.blog`   |ts 呼び出し API のイベントを記録します。       |

## <a name="desktop-logs"></a>デスクトップ ログ

詳細については _、「ログの収集と有効化_」セクションをWindows Mac の手順を参照してください。 デスクトップ ログ (ブートストラップ ログとも呼ばれる) には、デスクトップ クライアントとブラウザーの間で発生するログ データが含まれます。 メディア ログと同様に、これらのログは Microsoft から要求された場合にのみ必要です。 ログはテキスト ベースであり、トップダウン形式の任意のテキスト ベースのエディターを使用して読み取り可能です。

Linux のログを収集するには:
- システム トレイの [Microsoft Teams] アイコンをクリックし、[ログの取得]**を選択します**。
- ファイルは で使用できます `~/.config/Microsoft/Microsoft Teams/logs.txt` 。
  
データのログを収集Windows。
- システム トレイのMicrosoft Teamsアイコンをクリックし、[サポート ファイルの収集]**を選択します**。
- ファイル `logs.txt` は自動的に開メモ帳されます。

アプリケーションへのサインインに関する問題Teams、デスクトップ ログを手動で収集する必要がある場合があります。 これらのログ ファイルは、%appdata%\Microsoft\Teams にWindows。

## <a name="browser-trace"></a>ブラウザートレース

一部のカテゴリのエラーについては、Microsoft サポートでブラウザー トレースの収集が必要になる場合があります。 この情報は、エラーが発生した場合のクライアントの状態Teams詳細を提供できます。

ブラウザーのトレースを開始する前に、ブラウザーのトレースにサインインTeams。 トレースに機密性の高いサインイン情報が含まれるので、トレースを開始する前にこれを行う必要があります。

サインインした後、ブラウザーに応じて次のリンクのいずれかを選択し、提供されている手順に従います。 

-   [Chrome & Edge (Chromium)](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [Edge](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [Safari](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [Firefox](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> この手順では、Azure portal へのすべての参照を新しいクライアントに置Teamsします。
  
## <a name="webrtc-logs-in-browsers"></a>ブラウザーでの WebRTC ログ
WebRTC ログは、音声通話とビデオ通話の接続の詳細を提供することで、Microsoft サポートを支援します。 Edge (Chromium) または Chrome で WebRTC ログにアクセスする手順に従います。 
  
1.  新しいタブを開き、次のいずれかの URL に移動します。
    -   Edge (Chromium):`edge://webrtc-internals/`
    -   Chrome: `chrome://webrtc-internals/`
  
2.  Web アプリケーションTeams開き、問題を再現します。
  
3.  手順 1 でアクセスしたタブに戻り、少なくとも 2 つのタブが表示されます。
    -   GetUserMedia 要求
    -   `https://teams.microsoft.com/url`

4.  アプリケーションの名前が表示されたタブTeamsページの内容を保存します。

## <a name="related-topics"></a>関連項目

[Teams のトラブルシューティング](/MicrosoftTeams/troubleshoot/teams)
