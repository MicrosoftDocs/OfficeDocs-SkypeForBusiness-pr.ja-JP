---
title: ライブ イベント記録ポリシー
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: christi.balaki
audience: admin
search.appverid: MET150
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
description: ライブ イベント記録ポリシーについて説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5ae98255edf26843e59839192a9f20096182bfa2
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2022
ms.locfileid: "66794115"
---
# <a name="live-event-recording-policies-in-microsoft-teams"></a>Microsoft Teams のライブ イベント記録ポリシー

Microsoft Teams ライブ イベントを記録するには、いくつかのオプションがあります。 記録オプションは、記録ポリシーを使用して設定されます。 この記事では、さまざまな設定について説明します。

記録オプションは、PowerShell コマンド [Set-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy) を使用して設定されます。

## <a name="scheduling-and-option-behaviors"></a>スケジュールとオプションの動作

ライブ イベントの記録をスケジュールする際には、次の 2 つのオーガナイザー オプションがあります。

- プロデューサーと発表者が利用できるレコーディング

  - 記録ファイル: プロデューサーと発表者がイベントの終了後にダウンロードできる記録ファイルを提供します。

- 出席者が利用できる記録

  - DVR: デジタル ビデオ レコーダー (DVR) を使用すると、出席者はイベント中に巻き戻しと一時停止を行うことができます

  - VOD: ビデオ オンデマンド (VOD) を使用すると、イベントの終了後に出席者が視聴できます

## <a name="broadcast-recording-policy-setting"></a>ブロードキャスト記録ポリシー設定

ブロードキャスト ポリシーの一部として、ライブ イベントの記録をオンまたはオフに切り替えることができる設定があります。

| &nbsp;| プロデューサーと発表者が利用できるレコーディング | 出席者が利用できる記録 |
| ------------------------------- | ---------------------------------------------------- | ------------------------------------- |
| 常に記録する               | 無効で選択済み                                | 有効および選択済み         |
| 開催者が記録できるかどうか | 既定で有効および選択されている                  | 既定で有効および選択されている   |
| レコードを記録しない               | 無効で選択されていません                            | 無効で選択されていません      |

## <a name="storage-and-persistence-behavior"></a>ストレージと永続化の動作

| オプション                                       | 都道府県   | DVR                                                   | VOD                                                     | 記録                |
| ------------------------------------------------ | ------------ | --------------------------------------------------------- | ----------------------------------------------------------- | ---------------------------- |
| 出席者が利用できる記録 | 選択済み     | DVR を使用でき、Azure Media Services (AMS) 資産は 180 日間保存されます | 出席者はイベントにアクセスして視聴できます                     |                              |
|                                                  | [選択されていません] | DVR を使用でき、AMS 資産は 180 日間保存されます | 出席者は、イベントが終了した後にイベントにアクセスできなくなります。 |                              |
||無効 (選択されていません)|DVR が使用可能で、イベントの後に AMS 資産が削除される|出席者は、イベントが終了した後にイベントにアクセスできなくなります。||
| プロデューサーと発表者が利用できる記録 | 選択済み     |                                                           |                                                             | MP4 が作成され、180 日間保存される |
|                                                  | [選択されていません] |                                                           |                                                             | ファイルが作成されない           |

### <a name="related-topics"></a>関連項目

- [Teams のライブ イベントについて](what-are-teams-live-events.md)
- [Teams のライブ イベントの計画](plan-for-teams-live-events.md)
- [Teams でライブ イベント設定を構成する](configure-teams-live-events.md)
- [Teams クラウド会議の記録](../cloud-recording.md)
