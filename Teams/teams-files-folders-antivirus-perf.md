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
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9c1519038cb2393687a031e9b2c1ea828f999728
ms.sourcegitcommit: bb88ac0c9489bb47957e5ef1074b5df3126b6fdb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/25/2020
ms.locfileid: "42265622"
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

### <a name="folders"></a>フォルダ

ウイルス対策の安全なリストに次の Teams フォルダーを追加します。

|[カテゴリ]  |場所  |
|---------|---------|
|プログラムファイル  |%localappdata%\Microsoft\Teams|
|データファイル     |%appdata%\Microsoft\Teams\ |
