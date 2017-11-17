---
title: "Microsoft Teams のトラブルシューティングでログ ファイルを使用する | Microsoft サポート"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Microsoft Teams によって生成されるデバッグ ログ、メディア ログ、デスクトップ ログ、これらのログの場所、トラブルシューティングでのログの活用について説明します。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: a014e33df7587aee94a751e2a057f421655009fc
ms.sourcegitcommit: 9756856140ea56a94e986c134c5c04e53e5c0fa6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2017
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
|Windows Phone     |-         |-         |-         |

サポートされるオペレーティング システムとブラウザーの完全なリストについては、次の「[Microsoft Teams FAQ](https://support.office.com/en-US/article/Frequently-asked-questions-about-Microsoft-Teams-%E2%80%93-Admin-Help-05cbe533-2181-4e95-a4b0-52cd7695fafc)」をご覧ください。

<a name="debug-logs"></a>デバッグ ログ
---------------------------

デバッグ ログは最も一般的なログで、すべての Microsoft サポート ケースで必要とされます。このログは Window と Mac デスクトップ クライアント、ブラウザー ベースのクライアントで生成されます。ログはテキストベースで、下から上に読み取られます。ログは任意のテキストベースのエディタで読み取ることができます。クライアントにログインすると、新規のログが作成されます。

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
|Windows     |%appdata%\Roaming\Microsoft\Teams\media-stack\*.etl         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/media-stack\*.blog         |


<a name="desktop-logs"></a>デスクトップ ログ
---------------------

bootstrapper ログとも呼ばれるデスクトップ ログには、デスクトップ クライアントとブラウザー間で発生するログ データが含まれます。メディア ログと同様に、このログは Microsoft から要求された場合にのみ必要です。テキスト ベースのログで、任意のテキストベース エディタを使用して上から下の形式で読み取ることができます。

|クライアント |場所 |
|---------|---------|
|Windows     |%appdata%\Roaming\Microsoft\Teams\logs.txt         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/logs.txt         |
