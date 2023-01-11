---
title: Microsoft Teams でのストリーミングのエンコーダー構成
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
description: この記事では、Microsoft Teams ストリーミング イベントのエンコーダー ベースの RTMP 構成について説明します。
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 8fd5feffe328083d9e7d5fa6e14cdbdac2ae5ffc
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767980"
---
# <a name="configuring-encoders-for-live-event-streaming-in-microsoft-teams"></a>Microsoft Teams でのライブ イベント ストリーミング用のエンコーダーの構成

Teams は、RTMP または RTMPS を出力するさまざまなエンコーダーからのライブ フィードを受け入れます。 各エンコーダーは異なるため、Teams に送信するときは、エンコーダー構成のガイドラインに従ってください。

Teams で Live イベントを設定する方法については、ライブ イベントの作成に関するページを参照してください。 Teams と統合されたエンコーダーを既に使用している場合は、 [ライブ ストリーミング用のエンコーダーの構成に関する記事](teams-encoder-setup.md)を参照してください。

## <a name="configuration-steps"></a>構成手順

Teams または Yammer を使用してライブ イベントをスケジュールし、[ **Teams Encoder]** オプションを選択すると、会議出席依頼から RTMP URL とキーを取得し、それらを使用して Teams プロデューサー UI にフィードを送信できます。

### <a name="gather-the-rtmp-information"></a>RTMP 情報を収集する

#### <a name="scheduled-in-teams"></a>Teams でスケジュール

1. Teams クライアントを開き、[予定表] に移動 **します**。
1. スケジュールされたライブ イベントを選択し、二重矢印ボタンを選択して招待の詳細を表示します。
1. 詳細セクションの **RTMP に** 移動します。
1. [ **RTMP の取得** ] リンクを選択して、RTMP 取り込み URL をクリップボードにコピーします。
1. **GET RTMP キー** を選択して、RTMP キーをクリップボードにコピーします。

#### <a name="scheduled-in-yammer"></a>Yammer でスケジュール

1. イベントがスケジュールされた Yammer コミュニティに移動します。
1. [ **イベント** ] タブを選択して、予定されている予定のイベントを表示します。
1. 目的のイベントを選択して詳細ページを表示します。
1. 右側の [ **生成**] で、[ **RTMP 情報** ] リンクを選択して、RTMP URL とキーを公開します。

## <a name="encoder-setup"></a>エンコーダーのセットアップ

1. RTMP 情報を収集したら、以下の推奨エンコーダー設定に従ってエンコーダーが正しい設定で構成されていることを確認します。
1. エンコーダーのストリーミング設定に RTMP URL とキーを入力します (詳細については、製造元のドキュメントを参照してください)。
1. 目的のオーディオおよびビデオ ソースを使用してエンコーダーを構成します。
1. Teams クライアントを開き、プロデューサーとしてライブ ベントに参加します。
1. エンコーダーから Teams RTMP 取り込み URL へのストリーミングを開始します。
1. [Teams プロデューサー] ウィンドウで、数秒後にエンコーダーの RTMP フィードが発表者領域に表示されます。
1. 発表者領域の RTMP フィードをクリックして、左側のキューに配置します。
1. フィードに問題がなければ、[ **ライブ送信** ] を選択すると、フィードはプロデューサー ウィンドウの右側にも表示されます。
1. [ **開始] を** 選択してストリームを開始します。

## <a name="recommended-encoder-settings"></a>推奨されるエンコーダー設定

### <a name="ingest-protocols"></a>インジェスト プロトコル

- シングル ビットレート RTMPS または RTMP

### <a name="video-format"></a>ビデオ形式

- コーデック: H.264
- プロファイル: High (レベル 4.0)
- ビットレート: 最大 5 Mbps (5000 kbps)
- 厳密な定数ビットレート (CBR)
- キーフレーム/GOP: 2 秒
  - 各 GOP の先頭に IDR フレームが必要です
  - フレーム レート: 29.97 fps または 30 fps
  - 解像度: 1280 x 720 (720P)
  - インターレース モード: プログレッシブ

### <a name="audio-format"></a>オーディオ形式

- コーデック: AAC (LC)
- ビットレート: 192 kbps
- サンプル レート: 48 kHz または 44.1 kHz (推奨 48 kHz)

### <a name="playback-requirements"></a>再生要件

- Teams でコンテンツを再生するには、オーディオ ストリームとビデオ ストリームの両方が存在する必要があります。

### <a name="configuration-tips"></a>構成に関するヒント

- 可能な限り、ハードワイヤードインターネット接続を使用してください。
- 帯域幅の要件を決定する場合は、ストリーミング ビットレートを 2 倍にすることです。 これは必須の要件ではありませんが、ネットワーク輻輳の影響を軽減するのに役立ちます。
- ソフトウェア ベースのエンコーダーを使用する場合は、不要なプログラムをすべて閉じます。
- エンコーダーの構成は、プッシュを開始した後は変更しないでください。 イベントに悪影響を及ぼし、イベントが不安定になる可能性があります。 イベントが開始される前にこれを行う場合は、Teams のプロデューサー コントロールを使用して切断し、もう一度セットアップを開始する必要があります。
- ライブ イベント中にエンコーダーが切断された場合は、続行プロセスと同じタイムスタンプを保持したまま再接続します。 中断すると、特定のブラウザーやデバイスでオーディオまたはビデオの問題が発生する可能性があります。
- イベントのセットアップに十分な時間を与えてください。 大規模なイベントの場合は、イベントの 1 時間前にセットアップを開始することをお勧めします。
