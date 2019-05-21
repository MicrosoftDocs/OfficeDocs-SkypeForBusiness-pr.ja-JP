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
ms.openlocfilehash: 0cffa4e5eef3b5b120e38b103d04adbca08bef0e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32246255"
---
# <a name="user-presence-in-teams"></a>Teams でのユーザーのプレゼンス

プレゼンスは Microsoft Teams (および Office 365 全体) のユーザーのプロファイルの一部であり、ユーザーの現在の可用性と状態を組織内の他のユーザーに対して示します。 既定では、チームを使用する組織内のすべてのユーザーは、他のユーザーがオンラインで利用できるかどうかを確認できます。

## <a name="presence-states-in-teams"></a>Teams のプレゼンス状態

Teams で利用できるユーザーのプレゼンス状態は次のとおりです。

|ユーザー構成済み|構成済みのアプリ|
|:--- |:---|
| ![プレゼンスが利用可能](media/Presence_Available.png) 利用可能|![プレゼンスが利用可能](media/Presence_Available.png) 利用可能|
|| ![利用可能な oof](media/Presence_Available_OOF.png) 利用可能、外出中 |
|  ![少ない](media/Presence_Busy.png) 少ない |  ![少ない](media/Presence_Busy.png) 少ない  |
|| ![少ない](media/Presence_Busy.png) 通話中|
|| ![少ない](media/Presence_Busy.png) 会議中 |
|| ![取り込み中 (oof)](media/Presence_Busy_OOF.png) 通話中、外出中|
|  ![応答不可](media/Presence_DND.png) 応答不可 ||
|| ![応答不可](media/Presence_DND.png) 発表|
| ![位置](media/Presence_Away.png) 位置| ![位置](media/Presence_Away.png) 位置|
|| ![](media/Presence_Away.png)退席中の最終*日時*|
|![位置](media/Presence_Away.png) 一時退席中| |
|| ![位置](media/Presence_Away.png)  業務時間外|
|| ![で](media/Presence_Offline.png) で |
|| ![未](media/Presence_Unknown.png) 状態不明|
||![さ](media/Presence_Blocked.png) ブロックされました |
|| ![外出中](media/Presence_OOF.png) 外出中|
|||
 
ユーザーは、現在のプレゼンス状態をいくつかのオプションに手動で設定することができ、その状態は他のすべてのユーザーに反映されます。 また、ユーザーのプレゼンス情報は、ユーザーのアクティビティ (使用可能または退席中など)、Outlook の予定表の状態 (会議中など)、またはチームアプリの状態 (通話中、プレゼンテーション中) に基づいて、一覧でインデントされた状態に応じて自動的に更新されます。

15分間の非アクティブなタイムアウトがあります。その後、ユーザーの現在のプレゼンス状態が [退席中] にリセットされます。

ユーザーは、中断できるユーザーを指定できます (応答不可の設定を上書きすることに連絡してください)。 これらの設定は、アプリ内で利用できます。

## <a name="teams-is-not-skype-for-business"></a>Teams は Skype for Business ではありません

Skype for Business の次の管理設定は、Teams では異なります。
- プレゼンスの共有は、組織内のユーザーに対して Teams で常に有効になっています。 [プライバシー] (プレゼンスを表示できるユーザーを決定する) 構成は、Teams では利用できません。
- すべてのユーザー (フェデレーションサービスを含む) とのプレゼンスの共有は、Teams のユーザーに対して常に有効になっています。 コンタクトリスト (SfB に含まれている場合) は、**チャット >** のコンタクトまたは「> のコンタクトに**発信**」の下に表示されます。
- クライアントが応答不可であり、チーム内のユーザーに対して画期的な機能が常に有効になります。
- 予定表 (OOF & 他の予定表の情報を含む) 統合は、Outlook と統合されている場合、Teams のユーザーに対して常に有効になります。
- *最終表示*または*退席*中 (Skype for business によるデュアル環境の場合) は、Teams のユーザーに対して常に有効になっています。

> [!NOTE]
> チーム管理者がこれらの設定をカスタマイズできるかどうかは、現在サポートされていません。


## <a name="coexistence-with-skype-for-business"></a>Skype for Business と共存する

Skype for business と共存する場合の Teams のプレゼンス機能の詳細については、「 [skype For business との共存](coexistence-chat-calls-presence.md)」を参照してください。 
