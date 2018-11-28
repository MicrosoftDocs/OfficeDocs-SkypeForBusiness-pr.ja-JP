---
title: Microsoft Teams のトラブルシューティングでログ ファイルを使用する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
description: Microsoft Teams によって生成されるデバッグ ログ、メディア ログ、デスクトップ ログ、これらのログの場所、トラブルシューティングでのログの活用について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6a14d6db6c03b540a6495b9028a4f0342ff92636
ms.sourcegitcommit: 336a9c95602d58ff069e4990b340e376a2d0d809
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26716336"
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
|iOS     |-         |-         |-         |
|Android     |-         |-         |-         |

サポートされるオペレーティング システムとブラウザーの完全なリストについては、「[Microsoft Teams のクライアントを取得する](get-clients.md)」をご覧ください。

<a name="debug-logs"></a>デバッグ ログ
---------------------------

これらは最も一般的なログであり、すべてのマイクロソフトのサポートの場合に必要な。 デバッグ ログは、Windows と Mac のデスクトップ クライアントとブラウザー ベースのクライアントによって作成されました。 ログは、テキスト ベースを下から読み終えています。 任意のテキスト ベースのエディターを使用して読み取ることができ、クライアントへのログイン時に新しいログが作成されます。

デバッグ ログには次のデータ フローが表示されます。

-   ログイン

-   中間層サーバーへの接続要求

-   通話/会話

デバッグ ログは OS 依存の方法により生成できます。

-   Windows:

    1.  アプリケーション トレイの **Microsoft Teams アイコン**をクリックし、[**Get Logs (ログを取得)**] を選択します。

    2.  [**ヘルプ**] プルダウン メニューで [**Get Logs (ログを取得)**] を選択する

    3.  キーボード ショートカット: Ctrl + Alt + Shift + 1

-   Mac OSX:

    1.  [**ヘルプ**] プルダウン メニューで [**Get Logs (ログを取得)**] を選択する

    2.  キーボード ショートカット: Option + Command + Shift + 1

デバッグ ログは次のフォルダーに自動的にダウンロードされます。

-   Windows: %userprofile%\\Downloads

-   Mac OSX: Downloads

-   ブラウザー: 既定の保存場所にデバッグ ログを保存するように求められます

<a name="media-logs"></a>メディア ログ
---------------------------

メディア ログには、音声、ビデオ、画面共有に関する診断データが含まれます。このログは要求があった場合にのみサポート ケースで必要とされ、Microsoft のみが検査できます。次の表にログの場所を示します。


|クライアント |場所 |
|---------|---------|
|Windows     |%appdata%\Microsoft\Teams\media-stack\*.etl         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/media-stack\*.blog         |


<a name="desktop-logs"></a>デスクトップ ログ
---------------------

bootstrapper ログとも呼ばれるデスクトップ ログには、デスクトップ クライアントとブラウザー間で発生するログ データが含まれます。メディア ログと同様に、このログは Microsoft から要求された場合にのみ必要です。テキスト ベースのログで、任意のテキストベース エディタを使用して上から下の形式で読み取ることができます。

|クライアント |場所 |
|---------|---------|
|Windows     |%appdata%\Microsoft\Teams\logs.txt         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/logs.txt         |
