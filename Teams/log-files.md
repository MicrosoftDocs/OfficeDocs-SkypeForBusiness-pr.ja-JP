---
title: Microsoft Teams のトラブルシューティングでログ ファイルを使用する
ms.reviewer: tejeshs
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 09/25/2017
audience: admin
ms.topic: troubleshooting
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Microsoft Teams によって生成されるデバッグ ログ、メディア ログ、デスクトップ ログ、これらのログの場所、トラブルシューティングでのログの活用について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: f816830f24a3d1180cb33a91a3f02d30d360cfef
ms.sourcegitcommit: 2c2176b9d32b8f7218e8d11e82c0ae01318bfdc5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "52264877"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a>Microsoft Teams のトラブルシューティングでログ ファイルを使用する
=================================================

クライアントによって自動的に生成される 3 種類のログ ファイルがあります。このファイルは、クライアントのトラブルシューティングに役立Microsoft Teams。

-   デバッグ ログ

-   メディア ログ

-   デスクトップ ログ

Microsoft サポートでサポート要求を作成する場合、サポート エンジニアはデバッグ ログを必要とします。 サポート要求を作成する前にデバッグ ログを用意すると、Microsoft が問題のトラブルシューティングをすぐに開始できます。 **メディア** ログまたは **デスクトップ ログ** は、Microsoft から要求された場合にのみ必要です。

> [!NOTE]
> この記事では、デバッグ ログ **という用語は** 、トラブルシューティングに使用されるログを指します。 ただし、これらのログに対して生成されるファイルには、診断ログという用語 **が** 名前に含まれます。  

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

<a name="debug-logs"></a>デバッグ ログ
---------------------------

これらは最も一般的なログであり、すべての Microsoft サポート ケースで必要です。 デバッグ ログは、Windows Mac デスクトップ クライアントとブラウザー ベースのクライアントによって生成されます。 ログはテキスト ベースであり、ボトムアップから読み取されます。 任意のテキスト ベースのエディターを使用して読み取り、クライアントにログインするときに新しいログが作成されます。

デバッグ ログには次のデータ フローが表示されます。

-   ログイン

-   中層サービスへの接続要求

-   通話/会話

デバッグ ログは、次の OS 固有の方法を使用して生成されます。

-   Windows:

      キーボード ショートカット: Ctrl + Alt + Shift + 1

-   Mac OSX:

      キーボード ショートカット: Option + Command + Shift + 1

-   Linux:

      キーボード ショートカット: Ctrl + Alt + Shift + 1

デバッグ ログは、次のフォルダーに自動的にダウンロードされます。

-   Windows: %userprofile%\\Downloads

-   Mac OSX: ~/Downloads

-   Linux: ~/Downloads

-   ブラウザー: 既定の保存場所にデバッグ ログを保存するように求められます

<a name="media-logs"></a>メディア ログ
---------------------------

メディア ログには、音声、ビデオ、画面の共有に関する診断データがTeamsされます。 これらは、通話関連の問題にリンクされているサポート ケースに必要です。

メディア ログは既定でオフになっています。 会議の診断データをTeamsするには、ユーザーがクライアントでオプションを有効Teamsがあります。 [全般 **設定** に移動し、[会議の診断のログ記録を有効にする (Teams を再起動する必要があります) チェック ボックスをオンにし、Teams を再起動して、問題を  >  再現します。 

次の表に、メディア ログの場所の概要を示します。 ログ ファイルを Microsoft サポートに送信する場合は、ログ ファイルのタイムスタンプを確認して、問題を再現した時間をログで確実にカバーしてください。

|クライアント |場所 |
|---------|---------|
|Windows     |%appdata%\Microsoft\Teams\media-stack \\ *.blog         |
|            |%appdata%\Microsoft\Teams\skylib \\ *.blog
|            |%appdata%\Microsoft\Teams\media-stack \\ *.etl         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/media-stack/*.blog         |
|            |~/Library/Application Support/Microsoft/Teams/skylib/*.blog         |
|Linux       |~/.config/Microsoft/Microsoft Teams/media-stack/*.blog         |
|            |~/.config/Microsoft/Microsoft Teams/skylib/*.blog         |

生成されるログ ファイルとログ ファイルに含まれる情報の一覧を次に示します。

|ログ ファイル名  |説明  |
|---------|---------|
|Teams.msrtc-0-s1039525249.blog     | メディア スタックに関連する情報が含まれる。 これには、解像度、デコーダーとエンコーダーの使用、送信および受信されたフレーム数、カメラとビデオ ベースの画面共有 (VBSS) セッションの状態などのチャネルの状態が含まれます。         |
|rtmcontrol.msrtc-0-2415069487.blog      |コントロールが指定された場合のタイムスタンプ、マウス ポインター情報など、リモート制御アクションに関連する情報を記録します。          |
|Teams_MediaStackETW-2-U-xr-U.etl      |メディア スタック トレース イベントを記録します。         |
|Debug-0-s2790420889.blog    | レンダリング品質など、メディア エージェントに関連する情報が含まれる。          |
|tscalling-0-2061129496.blog   |ts 呼び出し API のイベントを記録します。       |

<a name="desktop-logs"></a>デスクトップ ログ
---------------------

デスクトップ ログ (ブートストラップ ログとも呼ばれる) には、デスクトップ クライアントとブラウザーの間で発生するログ データが含まれます。 メディア ログと同様に、これらのログは Microsoft から要求された場合にのみ必要です。 ログはテキスト ベースであり、トップダウン形式の任意のテキスト ベースのエディターを使用して読み取り可能です。

Windows:

 - システム トレイの **[Microsoft Teams]** アイコンを右クリックし、[ログの取得]**を選択します**。

Mac OsX:

 - [ヘルプ **] プルダウン メニュー** から **[ログの** 取得] を選択します。

Linux:

 - システム トレイの **[Microsoft Teams]** アイコンをクリックし、[ログの取得]**を選択します**。

|クライアント |場所 |
|---------|---------|
|Windows     |%appdata%\Microsoft\Teams\logs.txt         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/logs.txt         |
|Linux       |~/.config/Microsoft/Microsoft Teams/logs.txt         |


<a name="browser-trace"></a>ブラウザートレース
---------------------------

一部のカテゴリのエラーについては、Microsoft サポートでブラウザー トレースの収集が必要になる場合があります。 この情報は、エラーが発生した場合のクライアントの状態Teams詳細を提供できます。

ブラウザーのトレースを開始する前に、ブラウザーにサインインTeams。 トレースに機密性の高いサインイン情報が含まれるので、トレースを開始する前にこれを行う必要があります。

サインインした後、ブラウザーに応じて次のリンクのいずれかを選択し、提供されている手順に従います。 

-   [Chrome & Edge (Chromium)](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [Edge](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [Safari](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [Firefox](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> この手順では、Azure portal へのすべての参照を、新しいクライアントTeamsします。 

## <a name="related-topics"></a>関連トピック

[Teams のトラブルシューティング](/MicrosoftTeams/troubleshoot/teams)
