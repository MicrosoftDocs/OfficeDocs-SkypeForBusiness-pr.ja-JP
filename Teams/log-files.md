---
title: Teams で監視とトラブルシューティングを行うためのログ ファイルの構成
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
description: Microsoft Teams によって生成されるデバッグ、メディア、デスクトップのログについて説明します。ここでは、ログを見つけることができます。また、それらのログが監視とトラブルシューティングにどのように役立つかについて説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: ae6e6eb0c84eae8293f141940842506fa3f54142
ms.sourcegitcommit: 7a1fb6e15c21368afa34cd212865437781f721e2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67466035"
---
# <a name="configure-log-files-for-monitoring-and-troubleshooting-in-teams"></a>Teams で監視とトラブルシューティングを行うためのログ ファイルの構成

クライアントによって自動的に生成されるログ ファイルには、Teams の監視とトラブルシューティングに役立つ 3 種類のログ ファイルがあります。

-   [デバッグ ログ](#debug-logs)

-   [メディア ログ](#media-logs)

-   [デスクトップ ログ](#desktop-logs)

この記事では、これらのログとその使用方法について説明します。 特定の問題のトラブルシューティングについては、「 [Teams のトラブルシューティング](/MicrosoftTeams/troubleshoot/teams)」を参照してください。 

サポートに問い合わせる方法については、「サポートを [受ける](/microsoft-365/business-video/get-help-support)」を参照してください。

> [!NOTE]
> この記事では、 **デバッグ ログ** という用語は、トラブルシューティングに使用されるログを指します。 ただし、これらのログに対して生成されるファイルには、名前に **診断ログ** という用語が含まれます。  

## <a name="logs-overview"></a>ログの概要

問題が発生したらすぐにログを収集することが重要です。

Microsoft サポートを使用してサポート 要求を作成する場合、サポート エンジニアはデバッグ ログを必要とします。 サポート要求を作成する前にデバッグ ログを手元に置くと、Microsoft は問題のトラブルシューティングをすばやく開始できます。 **メディア** ログまたは **デスクトップ** ログは、Microsoft から要求された場合にのみ必要です。

デバッグ、デスクトップ、メディアのログは、 _MSTeams Diagnostics Log \<local date and time\>_ という名前の 1 つのフォルダーに収集されます。 このフォルダーは、Microsoft サポートでサポート要求を開くときに圧縮および共有できます。 フォルダーには、デスクトップ、会議 (メディア)、およびデバッグ (Web) 用のフォルダーが含まれます。 次のキーボード ショートカットを使用してファイルを収集できます。

- Windows: <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>

- Mac: <kbd>Option</kbd> + <kbd>Command</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>


特定の会議またはライブ イベントで問題が発生した場合は、会議に関連付けられた URL を設定すると便利です。 URL には、ログ内の正確な会議またはライブ イベントを特定するのに役立つ追加情報が用意されています。 この情報は、会議の参加者、またはライブ イベントの発表者またはプロデューサーから収集できます。 この URL は、結合 URL にマウス ポインターを合わせ、[ **ハイパーリンクのコピー**] を選択することでキャプチャできます。

> [!NOTE]
> メディア ログ記録が有効になっている場合は、オーディオとビデオの問題を調査するために必要な追加のファイルが会議フォルダーに含まれます。 メディア ログが有効になっていない場合は、使用可能なログの数に制限があります。
  
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

デバッグ ログは、Windows および Mac デスクトップ クライアントとブラウザー ベースのクライアントによって生成されます。 ログはテキスト ベースで、一番下から読み取られます。 テキスト ベースのエディターを使用して読み取ることができ、クライアントにログインするときに新しいログが作成されます。

デバッグ ログには次のデータ フローが表示されます。

-   ログイン

-   中間層サービスへの接続要求

-   通話/会話

Linux のログを収集するには:
- キーボード ショートカット: <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>  
- ファイルは次のページで使用できます。 `~/Downloads`

ブラウザーと Windows のログを収集するには:
- キーボード ショートカット: <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>  
- ファイルは次のページで使用できます。 `%userprofile%\Downloads`

Mac のログを収集するには:
- キーボード ショートカット: <kbd>Option</kbd> + <kbd>Command</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>  
- ファイルは次のページで使用できます。 `~/Downloads`

## <a name="media-logs"></a>メディア ログ

メディア ログには、Teams 会議でのオーディオ、ビデオ、画面共有に関する診断データが含まれています。 これらは、通話関連の問題にリンクされているサポート ケースに必要です。

CPU が次の場合、コンピューターのメディア ログは既定でオンになります。
- 任意の Apple M1
- 任意の Intel Xeon
- U、G7、M、MQ シリーズを除くすべての Intel i9
- U、G7、M、MQ シリーズを除く、第 6 世代以降の Intel i7

それ以外の場合は、既定でオフになっています。 Teams 会議の診断データを記録するには、次の 2 つの方法があります。

- 管理構成- エンド ユーザーのメディア ログを管理できます
- エンド ユーザーの構成- エンド ユーザーはメディア ログを有効にすることができます

### <a name="admin-configuration"></a>管理構成

エンド ユーザーのメディア ログを管理すると、特に問題が断続的な場合にシームレスなトラブルシューティング エクスペリエンスが提供されます。 管理者は TeamsMediaLoggingPolicy コマンドレットを使用して、ユーザーのメディア ログを有効および管理できます。

PowerShell コマンドレットおよび詳細については、 [Grant-CsTeamsMediaLoggingPolicy](/powershell/module/teams/grant-csteamsmedialoggingpolicy) に関する記事を参照してください。

### <a name="end-user-configuration"></a>エンド ユーザーの構成

エンド ユーザーが Teams 会議の診断データをログに記録するには、Teams クライアントでオプションを有効にする必要があります。 **[全般設定]** >  に移動 **し、[****メディア ログを有効にする] (オーディオ、ビデオ、画面共有の診断データ) を選択します。[Teams の再起動が必要]** (Teams の再起動が必要) チェック ボックスをオンにし、Teams を再起動し、問題を再現します。 ログを開始するには、Teams クライアントを再起動する必要があります。 ユーザーは、ドック (Mac) またはタスク バー (Windows) のアイコンを右クリックし、[終了] を選択して再起動できます。 終了すると、アプリ アイコンをクリックして Teams を再度開くことができます。

> [!NOTE]
> ユーザーが Teams からサインアウトすると、メディア ログは既定にリセットされます。

### <a name="collecting-and-sending-media-logs"></a>メディア ログの収集と送信

Microsoft サポートにログ ファイルを送信する前に、ログ ファイルのタイムスタンプを確認して、問題を再現したときの期間をログがカバーしていることを確認します。

Linux のログを収集するには:  
- ファイルは次の場所で使用できます。
  - `~/.config/Microsoft/Microsoft Teams/media-stack/\*\.blog`
  - `~/.config/Microsoft/Microsoft Teams/skylib/\*\.blog`

Windows のログを収集するには:  
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

デスクトップ ログ (ブートストラップ ログとも呼ばれます) には、デスクトップ クライアントとブラウザーの間で発生するログ データが含まれます。 メディア ログと同様に、これらのログは Microsoft から要求された場合にのみ必要です。 ログはテキスト ベースであり、トップダウン形式の任意のテキスト ベースのエディターを使用して読み取ることができます。

Linux のログを収集するには:
- システム トレイの Microsoft Teams アイコンをクリックし、[ **ログの取得**] を選択します。
- ファイルは .`~/.config/Microsoft/Microsoft Teams/logs.txt`

Mac のログを収集するには:
- Microsoft Teams の [ヘルプ] メニューをクリックし、[ **サポート ファイルの収集**] を選択します。
- ファイルは `logs.txt` 、 _MSTeams Diagnostics Log \<local date and time>_ フォルダー内のデスクトップ フォルダーに格納されます。

Windows のログを収集するには:
- システム トレイの Microsoft Teams アイコンをクリックし、[ **サポート ファイルの収集**] を選択します。
- ファイルは `logs.txt` 自動的にメモ帳で開きます。

Teams へのサインインに関する問題を調査する場合は、デスクトップ ログを手動で収集することが必要な場合があります。 これらのログ ファイルは、Windows の %appdata%\Microsoft\Teams にあります。

## <a name="related-topics"></a>関連項目

[Teams のトラブルシューティング](/MicrosoftTeams/troubleshoot/teams)

[Teams のブラウザー ログとトレース](/MicrosoftTeams/browser-logs-and-tracing-for-teams)
