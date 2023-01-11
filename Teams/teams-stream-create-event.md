---
title: Microsoft Teams でのストリームの作成
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
description: この記事では、Microsoft Teams ストリーミング イベントのストリームの作成について説明します。
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: b7ff5d15a08f186ae59ccef65fcd8280d84237d1
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767990"
---
# <a name="create-a-live-event-in-microsoft-teams"></a>Microsoft Teams でライブ イベントを作成する

> [!IMPORTANT]
> **中国**: 現在、中国にいるユーザーは、IT 管理者の助けを借りずに、Microsoft Teams や Yammer のライブ イベントを設定したり、参加したり、ビデオをオンデマンドで表示したりすることはできません。
>
> 開始する前に、管理者に問い合わせて、これらのアプリが組織内でシームレスに動作できるように、企業ネットワークに接続するための VPN を設定する必要があるかどうかを確認してください。

> [!IMPORTANT]
> ライブ イベントを設定するときは、最高のエクスペリエンスを得るには、イベントの少なくとも 24 時間前にビデオ、コミュニティ、ユーザーのアクセス許可を構成することをお勧めします。 これには、ユーザーの追加、ビデオのアクセス許可の更新、コミュニティのプライベートからパブリックへの変更などの設定が含まれます。 特定の変更がMicrosoft Stream、Microsoft Teams、Microsoft Yammer に反映されるまでに最大 2 時間かかることがあります。 24 時間以上を許可すると、必要に応じてテストと調整を行う時間を提供できます。

## <a name="schedule-the-live-event"></a>ライブ イベントをスケジュールする

1. Microsoft Teams クライアントを開き、予定表に移動します。
1. [ **新しい会議** ] ドロップダウンを使用します。
1. [ **ライブ イベント** ] オプションを選択します。
1. [ **新しいライブ イベント** ] ポップアップ ウィンドウで、左側にイベントの詳細 (**タイトル**、 **場所**、 **開始**、 **終了**、 **タイム ゾーン**、 **および詳細**) を入力します。
1. 同じページの右側にある [ **発表者を招待して、発表者** とプロデューサーを個別に追加するか、グループ経由で追加します。
1. すべてが入力されたら、[ **次へ**] を選択します。
1. [**ライブ イベントのアクセス許可**] **で [Peopleとグループ**、**組織全体**、または **パブリック**] を選択して、ライブ イベントを視聴できるユーザーを指定します。
1. [**ライブ イベントの生成方法**] で [**Teams Encoder (プレビュー)]** を選択します。
1. [イベント オプション] **で Q&A**、 **キャプション** などの必要なオプションを構成 **します**。
1. [ **スケジュール]** を選択して、ライブ イベントのスケジュールを完了します。

## <a name="stream-the-live-event"></a>ライブ イベントをストリーミングする

1. ライブ イベントをスケジュールすると、予定表の招待の **[詳細] セクションの** **RTMP サーバー取り込み URL** と **RTMP キー** を取得できます。このセクションを使用して、RTMP 取り込みを介して Encoder からコンテンツをプッシュできます。
1. エンコーダーを設定するには、RTMP 取り込み URL と RTMP キーをエンコーダーにコピーして、ライブ エンコーダー フィードの Team への送信を開始します。 Microsoft Teams でライブ ストリーミングにエンコーダーを使用する方法について詳しくは、以下をご覧ください。
1. Microsoft Teams クライアントを使用して、ライブ イベントにプロデューサーとして参加します。 また、RTMP 詳細については、->会議オプションを参照してください。
1. エンコーダーからサーバー取り込みポイントへのコンテンツのプッシュを開始すると、プロデューサー プレビューの更新プログラムが表示されます。
1. セットアップに満足し、プロデューサー UI でプレビューを表示したら、ソースから **RTMP フィード** を選択し、[ **ライブ送信]** を選択します。
1. [ **イベントの開始]** を選択してライブ イベントを開始し、どの対象ユーザーメンバーがイベントを表示できるかを投稿します。
1. イベントが完了したら、プロデューサー UI で [イベントの **終了** ] を選択します。 これにより、イベントが終了し、コンテンツがビデオオンデマンドですぐに利用できるようになります。

ライブ イベントのストリーミングの詳細については、「 [Teams エンコーダーを使用してライブ イベントを生成する](https://support.microsoft.com/office/produce-a-teams-live-event-using-teams-encoder-b0026c9d-fd37-4bb3-bffc-6961f221fbe9)」を参照してください。
