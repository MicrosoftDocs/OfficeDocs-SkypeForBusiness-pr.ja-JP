---
title: Teams でのユーザーのプレゼンス
author: jambirk
ms.author: jambirk
manager: serdars
ms.date: 08/21/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: rakayala
description: 情報管理者は、Teams でのプレゼンスについて理解する必要があります。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 11902a5d6ef768afa6d7bb1bba2f33b64757fef1
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2019
ms.locfileid: "35222094"
---
# <a name="user-presence-in-teams"></a>Teams でのユーザーのプレゼンス

プレゼンスは Microsoft Teams (および Office 365 全体) のユーザーのプロファイルの一部であり、ユーザーの現在の可用性と状態を組織内の他のユーザーに対して示します。 既定では、Teams を使用している組織内のすべてのユーザーは、ほぼリアルタイムで表示できます。これは、他のユーザーがオンラインで利用できるかどうかによって異なります。

## <a name="presence-states-in-teams"></a>Teams のプレゼンス状態

Teams で利用できるユーザーのプレゼンス状態は次のとおりです。

|ユーザー構成済み|構成済みのアプリ|
|:--- |:---|
| ![使用可能かどうかを示す緑色の塗りマーク](media/Presence_Available.png) 利用可能|![使用可能かどうかを示す緑色の塗りマーク](media/Presence_Available.png) 利用可能|
|| ![使用可能な oof を示す緑のボックスを開く](media/Presence_Available_OOF.png) 利用可能、外出中 |
|  ![[取り込み中] を示す赤の丸](media/Presence_Busy.png) 少ない |  ![[取り込み中] を示す赤の丸](media/Presence_Busy.png) 少ない  |
|| ![通話中にビジー状態であることを示す赤い丸](media/Presence_Busy.png) 通話中|
|| ![会議中にビジー状態であることを示す赤い丸](media/Presence_Busy.png) 会議中 |
|| ![[取り込み中] oof を示す赤い円を開く](media/Presence_Busy_OOF.png) 通話中、外出中|
|  ![[応答不可] を示す赤の丸 (白線)](media/Presence_DND.png) 応答不可 ||
|| ![プレゼンテーション中の白い線で囲まれた赤い円](media/Presence_DND.png) 発表|
| ![退席中のことを示す黄色の時計アイコン](media/Presence_Away.png) 位置| ![退席中のことを示す黄色の時計アイコン](media/Presence_Away.png) 位置|
|| ![黄色の時計アイコン。 [](media/Presence_Away.png)最終版] が表示されていない*状態*を示します。|
|![退席中であることを示す黄色の時計アイコン](media/Presence_Away.png) 一時退席中| |
|| ![退席中、作業オフを示す黄色の時計アイコン](media/Presence_Away.png)  業務時間外|
|| ![[オフライン] を示す、x の付いた灰色の円](media/Presence_Offline.png) で |
|| ![状態が不明であることを示す灰色の円を開く](media/Presence_Unknown.png) 状態不明|
||![ブロックされていることを示す斜め線の付いた赤い丸を開く](media/Presence_Blocked.png) ブロックされました |
|| ![矢印付き紫色の丸、外出中であることを示す](media/Presence_OOF.png) 外出中|
|||
 
ユーザーは、現在のプレゼンス状態をいくつかのオプションに手動で設定することができ、その状態は他のすべてのユーザーに反映されます。 また、ユーザーのプレゼンス情報は、ユーザーのアクティビティ (使用可能または退席中など)、Outlook の予定表の状態 (会議中など)、またはチームアプリの状態 (通話中、プレゼンテーション中) に基づいて、一覧でインデントされた状態に応じて自動的に更新されます。

15分間の非アクティブなタイムアウトがあります。その後、ユーザーの現在のプレゼンス状態が [退席中] にリセットされます。

ユーザーは、中断できるユーザーを指定できます (応答不可の設定を上書きすることに連絡してください)。 これらの設定は、アプリ内で利用できます。

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a>Skype for Business と比較した場合のチームの管理設定

Skype for Business の次の管理設定は、Teams では異なります。

- Teams では、組織内のユーザーに対してプレゼンス共有が常に有効になります。 [プライバシー] (プレゼンスを表示できるユーザーを決定する) 構成は、Teams では利用できません。
- すべてのユーザー (フェデレーションサービスを含む) とのプレゼンスの共有は、Teams のユーザーに対して常に有効になっています。 連絡先リスト (Skype for Business に含まれている場合) は、**チャット >** の [連絡先] または [ **> の連絡先**への通話] の下に表示されます。
- クライアントが応答不可であり、チーム内のユーザーに対して画期的な機能が常に有効になります。
- 予定表 (不在およびその他の予定表情報が含まれます) 統合は、Outlook と統合されている場合に、Teams のユーザーに対して常に有効になります。
- *最終表示*または*退席*中 (Skype for business によるデュアル環境の場合) は、Teams のユーザーに対して常に有効になっています。

> [!NOTE]
> チーム管理者がこれらの設定をカスタマイズできるかどうかは、現在サポートされていません。

## <a name="coexistence-with-skype-for-business"></a>Skype for Business と共存する

Skype for business と共存する場合の Teams のプレゼンス機能の詳細については、「 [skype For business との共存](coexistence-chat-calls-presence.md)」を参照してください。 
