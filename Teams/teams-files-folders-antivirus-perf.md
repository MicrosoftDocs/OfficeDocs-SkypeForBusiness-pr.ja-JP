---
title: ウイルス対策スキャンから除外する Teams のファイルとフォルダー
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: 定期的なウイルススキャンから特定のファイルやフォルダーを除外することで、チームのパフォーマンスを向上させます。
localization_priority: Normal
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: a1e890509428b3bfba19f6bfb01916e8ea837147
ms.sourcegitcommit: 0fa50d1cf354d79fbaf16b6aaec60e8d3ab852e8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43579593"
---
<a name="teams-files-and-folders-to-exclude-from-antivirus-scanning"></a>ウイルス対策スキャンから除外する Teams のファイルとフォルダー
=================================

ウイルス対策プログラムによって特定の Teams のファイルやフォルダーがスキャンされないようにすることで、チーム展開の全体的なパフォーマンスを向上させることができます。 これにより、スキャンする必要がないファイルやフォルダーのスキャンに関するシステムリソースの経費を回避することができます。

> [!NOTE]
> ユーザーがファイルをダウンロードしたり、ファイルを共有したりするとき、これらのファイルは、次のセクションに記載されている場所を通過しません。 ユーザーがファイルをアップロード、ダウンロード、または共有する場所は、ウイルス対策プログラムによって定期的にスキャンされます。

## <a name="files-and-folders-to-add-to-your-antivirus-safe-lists"></a>ウイルス対策の安全なリストに追加するファイルとフォルダー

ウイルス対策プログラムでサポートされている手順を使用して、次のファイルとフォルダーをセーフリストに追加します。 こうすることで、これらの場所のウイルススキャンを回避して、システムリソースを節約できます。

### <a name="programs"></a>アプリケーション

ウイルス対策の安全なリストに次の Teams プログラムを追加します。

**%localappdata%\Microsoft\Teams\current\Teams.exe**

**%localappdata%\Microsoft\Teams\Update.exe**

