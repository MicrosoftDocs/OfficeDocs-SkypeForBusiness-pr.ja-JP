---
title: Microsoft Teams でのストリーミング用エンコーダーのセットアップ
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: asteele
search.appverid: MET150
f1.keywords:
- NOCSH
description: この記事では、Microsoft Teams ストリーミング イベントのエンコーダー ベースの RTMP セットアップについて説明します。
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 8a31b8b0de30367401c998d17dbf59ea06fc5687
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767989"
---
# <a name="using-an-encoder-for-live-streaming-in-microsoft-teams"></a>Microsoft Teams でのライブ ストリーミングにエンコーダーを使用する

Teams エンコーダーを使用すると、ユーザーは Microsoft Teams を使用して外部のハードウェアまたはソフトウェア ベースのエンコーダーから直接ライブ イベントを生成できます。

## <a name="overview"></a>概要

エンコーダーは、カメラ、マイク、デスクトップ画面キャプチャなど、ライブ イベント中に使用するさまざまなソースからオーディオとビデオのコンテンツを取得します。 そのメディアを圧縮して適切なデジタル形式に変換し、対象ユーザーにライブ ストリーミングするために Teams に送信します。 外部エンコーダーで Teams 運用テクノロジ (NDI など) を使用する方法の詳細については、 [カスタム運用プレイブック](https://aka.ms/CustomProductionVEP) を参照してください。

## <a name="production-workflow-when-using-an-encoder"></a>エンコーダーを使用する場合の運用ワークフロー

Teams Live イベントを生成するためのワークフローは次のとおりです。

ライブ イベントは Teams または Yammer でスケジュールされ、[ **Teams エンコーダー** ] オプションが選択されています。 これにより、RTMP エンドポイントがプロビジョニングされます。このエンドポイントには、RTMP(S) URL と対応するキーが用意されています。 URL とキーは、スケジュールされたライブ イベントの RTMP エンドポイントに接続するためにエンコーダーによって使用されます。

### <a name="common-encoders-user-with-live-events"></a>ライブ イベントを持つ一般的なエンコーダー ユーザー

次の 2 つのリストのエンコーダーは、Teams でのライブ ストリーミングについて Microsoft によってテストされています。 最初の一覧は、これらのエンコーダーのサブセットであり、使いやすさと迅速なセットアップのために製品でテストされています。

#### <a name="stream-ready-encoders"></a>ストリーム対応エンコーダー

|エンコーダー                                |Web サイト  |詳細  |
|---------------------------------------|---------|---------|
|Haivision                              |[Haivision Makito X](https://www.haivision.com/microsoft/stream) |RTMP の強力な代替手段である Haivision Hub で高品質の HD ビデオを提供します。 |
|Haivision                              |[Haivision KB](https://www.haivision.com/microsoft/stream) |H.264 および HEV ビデオ エンコーダーは、最大 4K の解像度で高品質の ABR ビデオ カスケードを提供します。 |
|Open Broadcaster Software (OBS Studio) |[ブロードキャスト ソフトウェアを開く](https://obsproject.com/) |すべてのストリーミング プラットフォームをサポートする、ハイ パフォーマンスのリアルタイムのビデオ/オーディオキャプチャとミキシング。 |
|Vmix                                   |[Vmix](https://www.vmix.com/) |カメラ、ビデオ、オーディオなどの録画、ミキシング、ライブ ストリーミングを制御するソフトウェア ビジョン ミキサー。 |
|Wirecast                               |[Wirecast](https://www.telestream.net/wirecast) |すべての基本とマルチカメラの生産をカバーするWebキャストソフトウェア。 |
|Switcher Studio                        |[Switcher Studio](https://www.switcherstudio.com/microsoft-stream) |複数の Apple デバイスを 1 台以上のカメラと同期して、リアルタイムのビデオ キャプチャと編集を行います。 |
|AWS Elemental Live                     |[AWS Elemental Live](https://www.elemental.com/products/aws-elemental-appliances-software/#elemental-live) |インターネットに接続されたデバイスへのライブ ストリーミング用のリアルタイムビデオとオーディオ録音 |
|XSplit Broadcaster                     |[XSplit Broadcaster](https://www.xsplit.com/) |ライブ ストリーミング用のゲームプレイなど、豊富なビデオ コンテンツを生成、ミックス、配信します。 |
|Ffmpeg                                 |[Ffmpeg](https://ffmpeg.org/) |ビデオ、オーディオ、およびその他のマルチメディア ファイルとライブ ストリームを処理するためのソフトウェアのオープン ソース スイート。 |
|生産トラック          |[生産トラック](https://www.blueframetech.com/productiontruck) |モバイルバンやトラックから場所でイベントを映画やストリーミング。 |
|ライブ アリーナ AI プロデューサー                 |AI プロデューサー |会議アプリとして Microsoft Teams に統合された運用スタジオ。|
|StreamYard                             |StreamYard |ブラウザーのライブ ストリーミング スタジオ。|
|Socialive                              |Socialive |クラウド ビデオ制作プラットフォーム。スタジオ品質のビデオ コンテンツを作成および配布するためのオールインワンエクスペリエンスを提供します。|
|Brandlive                              |BrandLive |クラウドベースの運用プラットフォーム。|

### <a name="haivision-makito-x-encoder-and-makito-kb-encoder"></a>Haivision Makito X エンコーダーと Makito KB エンコーダー

既存の Haivision X または Makito KB エンコーダーがある場合は、ドロップダウン リストから適切なオプションを選択し、指示の一覧に従います。

1. [ **セットアップの開始]** を選択して、ライブ ストリーミング用のチャネルを作成します。 セットアップが完了するまで待ちます。 画面に [ **接続の準備完了** ] メッセージが表示されます。
1. 完了したら、取り込み URL とイベント名を含むすべてのエンコード パラメーターを含むプリセットをダウンロードします。 プリセットをエンコーダーにインポートし、エンコーダーを起動します。
1. Teams に戻るします。 エンコーダーからプレビューを表示できたら、[ **イベントの開始** ] を選択してライブに移行し、対象ユーザーがライブ イベントを表示できるようにします。

> [!NOTE]
> RTMPS に対する Haivision KB Encoder のサポートはまだテストされていません。 Haivision Makito X Encoder は RTMPS をサポートしていません。 両方のエンコーダーのダウンロードされたプリセットには、RTMP 取り込み URL が含まれています。

### <a name="switcher-studio"></a>Switcher Studio

Switcher Studio を使用して、iPhone または iPad を使用して Teams へのストリーミングを開始できます。

1. [ **セットアップの開始]** を選択して、ライブ ストリーミング用のチャネルを作成します。 セットアップが完了するまで待ちます。 画面に [ **接続の準備完了** ] メッセージが表示されます。
2. Switcher Studio によって Switcher Studio ダッシュボードが開き、ライブ イベントがアカウントに追加されます。

> [!NOTE]
> Switcher Studio アカウントがまだない場合は、アカウントを作成する必要があります)。

3. これが完了したら、iPhone または iPad の Switcher Studio アプリに移動し、[出力] タブで [Teams] を選択し、Teams へのストリーミングを開始できます。
4. Teams に戻るします。 エンコーダーからプレビューを表示できたら、[ **イベントの開始** ] を選択してライブに移行し、対象ユーザーがライブ イベントを表示できるようにします。

> [!NOTE]
> Switcher Studio では、RTMP 取り込み URL が使用されます。

### <a name="wirecast"></a>Wirecast

Wirecast の既存のユーザーの場合は、ドロップダウン リストからこのオプションを選択して、ライブ ストリームを Teams に送信できます。 Wirecast バージョン 10 以降が必要であることに注意してください。

1. [ **セットアップの開始]** を選択して、ライブ ストリーミング用のチャネルを作成します。 セットアップが完了するまで待ちます。 画面に [ **接続の準備完了** ] メッセージが表示されます。
1. エンコーダーは、正しいエンコード パラメーターを使用して事前に構成されたコンピューターで Wirecast アプリを起動し、そのライブ イベントの URL を取り込みます。 準備ができたら、Wirecast アプリの Teams アイコンをクリックして Teams へのストリーミングを開始します。
1. Teams に戻るします。 エンコーダーからプレビューを表示できたら、[ **イベントの開始** ] を選択してライブに移行し、対象ユーザーがライブ イベントを表示できるようにします。

> [!NOTE]
> Wirecast アプリは、RTMPS 取り込み URL が事前に構成された状態で起動されます。
