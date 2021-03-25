---
title: ライブ イベント記録ポリシー
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: christi.balaki
audience: admin
search.appverid: MET150
f1.keywords:
- CSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: ライブ イベント記録ポリシーについて説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7a5f793230798c68f0a39e2d9a3500eab9791065
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119166"
---
# <a name="live-event-recording-policies-in-microsoft-teams"></a>Microsoft Teams のライブ イベント記録ポリシー

Microsoft Teams ライブ イベントを記録するためのオプションは複数あります。 記録オプションは、記録ポリシーを使用して設定します。 この記事では、さまざまな設定について説明します。

記録オプションは、PowerShell コマンド [Set-CsTeamsMeetingBroadcastPolicy を使用して設定されます。](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)

## <a name="scheduling-and-option-behaviors"></a>スケジュールとオプションの動作

ライブ イベントの記録をスケジュールする場合、開催者の 2 つのオプションがあります。

- プロデューサーと発表者が利用できるレコーディング

  - レコーディング ファイル: プロデューサーと発表者がイベントの終了後にダウンロードできるレコーディング ファイルを提供します。

- 出席者が使用できるレコーディング

  - DVR: デジタル ビデオレコーダー (DVR) を使用すると、出席者はイベント中に巻き戻しや一時停止を行える

  - VOD: ビデオ オンデマンド (VOD) を使用すると、イベントが終わった後に出席者が視聴できます。

## <a name="broadcast-recording-policy-setting"></a>ブロードキャスト録画ポリシーの設定

ブロードキャスト ポリシーの一部として、ライブ イベントのレコーディングをオンまたはオフに切り替える設定があります。

|                                 | プロデューサーと発表者が利用できるレコーディング | 出席者が使用できるレコーディング |
| ------------------------------- | ---------------------------------------------------- | ------------------------------------- |
| 常に記録する               | 無効と選択                                | 無効と選択         |
| 開催者は記録可能または記録しない | 既定で有効で選択されていない                  | 既定で有効で選択されていない   |
| 記録しない               | 無効で選択されていない                            | 無効で選択されていない      |

ポリシーが [常に記録] **に設定されている場合**、ポリシー ページには次のオプションが選択されています。

![ライブ イベント ポリシーの設定](../media/live-event-recording-policy.png "Microsoft Teams 管理センターのライブ イベント ポリシーの設定を示すスクリーン ショット")

## <a name="storage-and-persistence-behavior"></a>記憶域と永続性の動作

| オプション                                       | 都道府県   | DVR                                                   | VOD                                                     | 記録                |
| ------------------------------------------------ | ------------ | --------------------------------------------------------- | ----------------------------------------------------------- | ---------------------------- |
| プロデューサーと発表者が利用できるレコーディング | 選択済み     | DVR が利用可能で、Azure Media Services (AMS) アセットが 180 日間保存される | 出席者はイベントにアクセスして見る                     |                              |
|                                                  | 選択されていない | DVR が利用可能で、AMS アセットが 180 日間保存される | イベントが終わった後、出席者はイベントにアクセスできない |                              |
||無効 (選択されていない)|DVR が使用可能で、イベントの後に AMS アセットが削除される|イベントが終わった後、出席者はイベントにアクセスできない||
| プロデューサーと発表者が利用できるレコーディング | 選択済み     |                                                           |                                                             | MP4 が作成および保存される |
|                                                  | 選択されていない |                                                           |                                                             | ファイルが作成されません           |

### <a name="related-topics"></a>関連項目

- [Teams のライブ イベントについて](what-are-teams-live-events.md)
- [Teams のライブ イベントの計画](plan-for-teams-live-events.md)
- [Teams でライブ イベント設定を構成する](configure-teams-live-events.md)
- [Teams クラウド会議の記録](../cloud-recording.md)