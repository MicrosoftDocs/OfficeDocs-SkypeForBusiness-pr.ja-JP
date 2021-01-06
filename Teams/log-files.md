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
ms.openlocfilehash: 295886e7a5c50107672d17dcfa06067ba1b0ac9b
ms.sourcegitcommit: 48b8801b86a6c900c224853590daa3cb3c8d4ded
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2021
ms.locfileid: "49761095"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a>Microsoft Teams のトラブルシューティングでログ ファイルを使用する
=================================================

クライアントによって自動的に生成される 3 種類のログ ファイルがあります。これは、Microsoft Teams のトラブルシューティングを支援するために利用できます。

-   デバッグ ログ

-   メディア ログ

-   デスクトップ ログ

Microsoft サポートでサポート要求を作成する場合、サポート エンジニアはデバッグ ログを必要とします。 サポート要求を作成する前にデバッグ ログを用意すると、Microsoft は問題のトラブルシューティングをすばやく開始できます。 **メディア** ログ **またはデスクトップ** ログは、Microsoft から要求された場合にのみ必要です。

> [!NOTE]
> この記事では、デバッグ ログ **という用語は** 、トラブルシューティングに使用されるログを参照しています。 ただし、これらのログに対して生成されるファイルには、名前に診断 **ログという** 用語が含まれます。  

次の表では、さまざまなクライアントとその関連ログの概要を示します。 ログ ファイルは、クライアントとオペレーティング システムに固有の場所に保存されます。


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

これらは最も一般的なログであり、すべての Microsoft サポート ケースで必要です。 デバッグ ログは、Windows および Mac のデスクトップ クライアントおよびブラウザー ベースのクライアントによって生成されます。 ログはテキスト ベースで、下から読み上げされます。 任意のテキスト ベースのエディターを使用して読み取り、クライアントにログインするときに新しいログが作成されます。

デバッグ ログには次のデータ フローが表示されます。

-   ログイン

-   中層サービスへの接続要求

-   通話/会話

デバッグ ログは、次の OS 固有のメソッドを使用して生成されます。

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

メディア ログには、Teams 会議での音声、ビデオ、画面共有に関する診断データが含まれます。 これらは、通話関連の問題にリンクされているサポート ケースに必要です。

メディア ログは既定で無効になっています。 Teams 会議の診断データをログに記録するには、ユーザーが Teams クライアントでオプションを有効にする必要があります。 [設定全般 **]** に移動し、[会議の診断のログを有効にする (Teams の再起動が必要) ] チェック ボックスをオンにし、Teams を再起動して、  >  問題を再現します。  

次の表に、メディア ログの場所の概要を示します。 ログ ファイルを Microsoft サポートに送信する場合は、ログ ファイルのタイムスタンプを確認して、問題を再現したログの時間枠を確実にカバーしてください。

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
|Teams.msrtc-0-s1039525249.blog     | メディア スタックに関連する情報が含まれている。 これには、解像度、デコーダーとエンコーダー、送信および受信したフレーム数、カメラとビデオベースの画面共有 (VBSS) セッションの状態などのチャネルの状態が含まれます。         |
|rtmcontrol.msrtc-0-2415069487.blog      |コントロールを指定した場合のタイム スタンプ、マウス ポインター情報など、リモート コントロールの操作に関連する情報を記録します。          |
|Teams_MediaStackETW-2-U-xr-U.etl      |メディア スタックトレース イベントを記録します。         |
|Debug-0-s2790420889.blog    | メディア エージェントに関連する情報 (レンダリング品質など) が含まれている。          |
|tscalling-0-2061129496.blog   |ts 呼び出し API のイベントを記録します。       |

<a name="desktop-logs"></a>デスクトップ ログ
---------------------

デスクトップ ログ (bootstrapper ログとも呼ばれる) には、デスクトップ クライアントとブラウザーの間で発生するログ データが含まれます。 メディア ログと同様に、これらのログは Microsoft から要求された場合にのみ必要です。 ログはテキスト ベースであり、トップダウン形式の任意のテキスト ベースのエディターを使用して読み取り可能です。

Windows:

 - システム トレイの **Microsoft Teams** アイコンを右クリックし、[ログの取得] を **選択します**。

Mac OsX:

 - [ヘルプ **] プルダウン メニュー** から **[ログ** の取得] を選びます。

Linux:

 - システム トレイの **Microsoft Teams** アイコンをクリックし、[ログの取得] **を選択します**。

|クライアント |場所 |
|---------|---------|
|Windows     |%appdata%\Microsoft\Teams\logs.txt         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/logs.txt         |
|Linux       |~/.config/Microsoft/Microsoft Teams/logs.txt         |


## <a name="related-topics"></a>関連トピック

[Teams のトラブルシューティング](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
