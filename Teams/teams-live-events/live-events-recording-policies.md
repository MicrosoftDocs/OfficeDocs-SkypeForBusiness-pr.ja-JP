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
ms.openlocfilehash: 77bfb6f3d57b885a11574f08f21da5f8c1c488a9832aeae1ffe602c4a922d227
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54319660"
---
# <a name="live-event-recording-policies-in-microsoft-teams"></a>ライブ イベント記録ポリシー (Microsoft Teams

ライブ イベントを記録するためのオプションMicrosoft Teamsがあります。 記録オプションは、記録ポリシーを使用して設定されます。 この記事では、さまざまな設定について説明します。

記録オプションは、PowerShell コマンド [Set-CsTeamsMeetingBroadcastPolicy を使用して設定されます](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy)。

## <a name="scheduling-and-option-behaviors"></a>スケジュールとオプションの動作

ライブ イベントの記録をスケジュールする場合、開催者のオプションは 2 つがあります。

- プロデューサーと発表者が使用できるレコーディング

  - レコーディング ファイル: プロデューサーと発表者がイベントの終了後にダウンロードできる録音ファイルを提供します。

- 出席者が利用できる記録

  - DVR: デジタル ビデオ レコーダー (DVR) を使用すると、出席者はイベント中に巻き戻して一時停止できます。

  - VOD: ビデオ オン デマンド (VOD) を使用すると、イベントが終わった後に出席者が視聴できます。

## <a name="broadcast-recording-policy-setting"></a>ブロードキャスト録画ポリシーの設定

ブロードキャスト ポリシーの一部として、ライブ イベントの記録をオンまたはオフに切り替える設定があります。

| &nbsp;| プロデューサーと発表者が使用できるレコーディング | 出席者が利用できる記録 |
| ------------------------------- | ---------------------------------------------------- | ------------------------------------- |
| 常に記録する               | 無効で選択されている                                | 有効で選択されている         |
| オーガナイザーは記録可能か記録しないか | 既定で有効および選択されている                  | 既定で有効および選択されている   |
| 記録しない               | 無効で選択されていない                            | 無効で選択されていない      |

## <a name="storage-and-persistence-behavior"></a>Storageと永続化の動作

| オプション                                       | 都道府県   | DVR                                                   | VOD                                                     | 記録                |
| ------------------------------------------------ | ------------ | --------------------------------------------------------- | ----------------------------------------------------------- | ---------------------------- |
| 出席者が利用できる記録 | 選択済み     | DVR が使用可能で、Azure Media Services (AMS) 資産は 180 日間保存されます。 | 出席者はイベントにアクセスして視聴できます。                     |                              |
|                                                  | 選択されていない | DVR が使用可能で、AMS 資産が 180 日間保存される | イベントが終わった後、出席者はイベントにアクセスできない |                              |
||無効 (選択されていない)|DVR が使用可能で、イベントの後に AMS 資産が削除される|イベントが終わった後、出席者はイベントにアクセスできない||
| プロデューサーと発表者が使用できるレコーディング | 選択済み     |                                                           |                                                             | MP4 が作成され、保存される |
|                                                  | 選択されていない |                                                           |                                                             | ファイルが作成されません           |

### <a name="related-topics"></a>関連項目

- [Teams のライブ イベントについて](what-are-teams-live-events.md)
- [Teams のライブ イベントの計画](plan-for-teams-live-events.md)
- [Teams でライブ イベント設定を構成する](configure-teams-live-events.md)
- [Teamsクラウド会議の記録](../cloud-recording.md)
