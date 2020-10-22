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
ms.openlocfilehash: 2ff24ddb8aaf63b539959119138aebf2f5d4e81f
ms.sourcegitcommit: 3a577c07b4f399c81d8650a2bba8cfc00b695b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "48650830"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a>Microsoft Teams のトラブルシューティングでログ ファイルを使用する
=================================================

クライアントによって自動的に生成されるログは 3 種類あり、これらのログを使用して Microsoft Teams のトラブルシューティングに役立てることができます。

-   デバッグ ログ

-   メディア ログ

-   デスクトップ ログ

Microsoft サポートでサポート リクエストを作成する際、サポート エンジニアによってデバッグ ログが要求されます。サポート リクエストを作成する前にこのログを手元に用意しておくと、Microsoft はすばやく問題解決を開始することができます。メディア ログやデスクトップ ログは Microsoft によって要求された場合のみ必要です。

次の表にクライアントとそれに関連付けられたログの概要を示します。ログ ファイルの格納場所は、クライアントとオペレーティング システムによって異なります。


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

これらは最も一般的なログであり、Microsoft のすべてのサポート案件に必要です。 デバッグログは、Windows と Mac のデスクトップクライアントだけでなく、ブラウザーベースのクライアントによって生成されます。 ログはテキストベースであり、最後から読み取られます。 テキストベースのエディターを使って読むことができます。また、クライアントにログインすると、新しいログが作成されます。

デバッグ ログには次のデータ フローが表示されます。

-   ログイン

-   中間層サーバーへの接続要求

-   通話/会話

デバッグ ログは OS 依存の方法により生成できます。

-   Windows:

      キーボード ショートカット: Ctrl + Alt + Shift + 1

-   Mac OSX:

      キーボード ショートカット: Option + Command + Shift + 1

-   走ら

      キーボード ショートカット: Ctrl + Alt + Shift + 1

デバッグ ログは次のフォルダーに自動的にダウンロードされます。

-   Windows: %userprofile%\\Downloads

-   Mac OSX: ~/ダウンロード

-   Linux: ~/ダウンロード

-   ブラウザー: 既定の保存場所にデバッグ ログを保存するように求められます

<a name="media-logs"></a>メディア ログ
---------------------------

メディアログには、Teams 会議でのオーディオ、ビデオ、画面共有に関する診断データが含まれています。 これは、通話関連の問題にリンクされているサポートケースに必要です。

メディアログは既定で無効になっています。 Teams 会議の診断データをログに記録するには、ユーザーは Teams クライアントでオプションをオンにする必要があります。 [**設定**全般] に移動し、[  >  **General****会議の診断のためのログを有効にする (チームの再起動が必要**)] チェックボックスをオンにして、チームを再起動し、問題を再現します。 

次の表に、メディアログの場所の概要を示します。 ログファイルを Microsoft サポートに送信する場合は、ログファイルのタイムスタンプを確認して、問題を再現したときにログがその期間に対応していることを確認してください。

|クライアント |場所 |
|---------|---------|
|Windows     |%appdata%\Microsoft\Teams\media-stack \\ *. ブログ         |
|            |%appdata%\Microsoft\Teams\skylib \\ *. ブログ
|            |%appdata%\Microsoft\Teams\media-stack \\ * .etl         |
|Mac OSX     |~/Library/application support Support/Microsoft/Teams/media-stack/*. ブログ         |
|            |~/Library/application support Support/Microsoft/Teams/skylib/*. ブログ         |
|Linux       |~/.config/Microsoft/Microsoft Teams/media-stack/*. ブログ         |
|            |~/.config/Microsoft/Microsoft Teams/skylib/*. ブログ         |

生成されるログファイルとそれらに含まれる情報の一覧を次に示します。

|ログファイル名  |説明  |
|---------|---------|
|Teams. msrtc-0-s1039525249     | メディアスタックに関連する情報が含まれています。 これには、解像度、デコーダー、使用されるエンコーダー、送受信されたフレーム数、カメラおよびビデオベースの画面共有 (VBSS) セッション状態などのチャネル状態が含まれます。         |
|rtmcontrol. msrtc-0-2415069487      |コントロールが指定されているときのタイムスタンプやマウスポインター情報など、リモートコントロールの操作に関連する情報を記録します。          |
|-2-U-xr-U の Teams_MediaStackETW      |メディアスタックトレースイベントを記録します。         |
|Debug-0-s2790420889    | レンダリング品質など、メディアエージェントに関連する情報が含まれています。          |
|tscalling-0-2061129496   |Ts API のイベントを記録します。       |

<a name="desktop-logs"></a>デスクトップ ログ
---------------------

bootstrapper ログとも呼ばれるデスクトップ ログには、デスクトップ クライアントとブラウザー間で発生するログ データが含まれます。メディア ログと同様に、このログは Microsoft から要求された場合にのみ必要です。テキスト ベースのログで、任意のテキストベース エディタを使用して上から下の形式で読み取ることができます。

Windows:

1.  システムトレイで**Microsoft Teams**アイコンを右クリックし、[**ログの取得**] を選択します。

Mac OsX:

1.  [**ヘルプ**] プルダウン メニューで [**Get Logs (ログを取得)**] を選択する

走ら

1.  システムトレイの**Microsoft Teams**アイコンをクリックし、[**ログの取得**] を選択します。

|クライアント |場所 |
|---------|---------|
|Windows     |% appdata% \Microsoft\Teams\logs.txt         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/logs.txt         |
|Linux       |~/.config/Microsoft/Microsoft Teams/logs.txt         |


## <a name="related-topics"></a>関連トピック

[Teams のトラブルシューティング](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
