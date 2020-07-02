---
title: Microsoft Teams のトラブルシューティングでログ ファイルを使用する
ms.reviewer: tejeshs
author: LolaJacobsen
ms.author: lolaj
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
ms.openlocfilehash: 7ad44af297cdfe375f28485e1c4c4e223f616666
ms.sourcegitcommit: a94a267c421a78587b0dbbea5fa167aad2882e9b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "45012193"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a>Microsoft Teams のトラブルシューティングでログ ファイルを使用する
=================================================

クライアントによって自動的に生成されるログは 3 種類あり、これらのログを使用して Microsoft Teams のトラブルシューティングに役立てることができます。

-   デバッグ ログ

-   メディア ログ

-   デスクトップ ログ

When creating a support request with Microsoft Support, the support engineer will require the debug logs. Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem. Media or desktop logs are only required if requested by Microsoft.

The following table outlines the various clients, and their associated logs. Log files are stored in locations specific to the client and operating system.


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

-   Mac OSX: Downloads

-   Linux: ~/ダウンロード

-   ブラウザー: 既定の保存場所にデバッグ ログを保存するように求められます

<a name="media-logs"></a>メディア ログ
---------------------------

Media logs contain diagnostic data about audio, video and screen sharing. They are required for support cases only upon request and can only be inspected by Microsoft. The following table outlines the log location.


|クライアント |場所 |
|---------|---------|
|Windows     |%appdata%\Microsoft\Teams\media-stack \\ *. ブログ         |
|            |%appdata%\Microsoft\Teams\skylib \\ *. ブログ
|            |%appdata%\Microsoft\Teams\media-stack \\ * .etl         |
|Mac OSX     |~/Library/application support Support/Microsoft/Teams/media-stack/*. ブログ         |
|            |~/Library/application support Support/Microsoft/Teams/skylib/*. ブログ         |
|Linux       |~/.config/Microsoft/Microsoft Teams/media-stack/*. ブログ         |
|            |~/.config/Microsoft/Microsoft Teams/skylib/*. ブログ         |



<a name="desktop-logs"></a>デスクトップ ログ
---------------------

Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser. Like media logs, these logs are only needed if requested by Microsoft. The logs are text based and can be read using any text based editor in a top down format.

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
