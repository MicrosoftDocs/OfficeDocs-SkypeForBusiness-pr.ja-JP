---
title: Teams でのユーザーのプレゼンス
author: jambirk
ms.author: jambirk
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Teams のプレゼンスに関する管理者向けの情報です。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: f6b64a54a2a6f198c893894dc0302c81c1bff5da
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837337"
---
# <a name="user-presence-in-teams"></a>Teams でのユーザーのプレゼンス

プレゼンスは、Microsoft Teams (および Office 365 全体) のユーザーのプロファイルの一部であり、ユーザーの現在の可用性と他のユーザーの状態を示します。 既定では、他のユーザーがオンラインで利用できる場合、チームを使っているすべてのユーザーに (ほぼリアルタイムで) 表示できます。

> [!IMPORTANT]
> ユーザーを [**Teams のみ**] モードに移動した後に Skype for Business クライアントをアンインストールすると、Outlook および Office アプリでプレゼンスが機能しなくなります。 プレゼンスは Teams では正常に機能します。 回避策: Outlook (および他の Office アプリ) でプレゼンスを表示させるには、Teams を [**Teams のみ**] モードで実行している場合であっても、Skype for Business をインストールする必要があります。 Microsoft はこの問題を把握しており、現在修正に向けて取り組んでいます。

Outlook での Teams のプレゼンスは、Outlook 2013 デスクトップ版アプリ以降でサポートされています。

## <a name="presence-states-in-teams"></a>Teams のプレゼンス状態

Teams で利用できるユーザーのプレゼンス状態は次のとおりです。

|ユーザー構成済み|構成済みのアプリ|
|:--- |:---|
| ![正常に機能していることを示す緑色のチェックマーク](media/Presence_Available.png) 利用可能|![正常に機能していることを示す緑色のチェックマーク](media/Presence_Available.png) 利用可能|
|| ![使用可能な oof を示す緑のチェックマークを開く](media/Presence_Available_OOF.png) 利用可能、外出中 |
|  ![赤い丸で塗りつぶし、取り込み中](media/Presence_Busy.png) 少ない |  ![赤い丸で塗りつぶし、取り込み中](media/Presence_Busy.png) 少ない  |
|| !["通話中" であることを示す赤色の丸](media/Presence_Busy.png) 通話中|
|| ![赤い丸で囲まれるので、会議中に取り込み中であることを示します。](media/Presence_Busy.png) 会議中 |
|| ![赤い丸で囲まれる、取り込み中であることを示す](media/Presence_Busy_OOF.png) 通話中、外出中|
|  ![白の丸で囲まれた赤い円。 [応答不可] を示します。](media/Presence_DND.png) 応答不可 ||
|| ![赤い円に白線を付け、プレゼンテーションを示します。](media/Presence_DND.png) 発表|
|| ![赤の丸 (白の線) は、フォーカスがあることを示します。](media/Presence_DND.png) 焦点|
| ![黄色の時計アイコン。退席中であることを示します。](media/Presence_Away.png) 位置| ![黄色の時計アイコン。退席中であることを示します。](media/Presence_Away.png) 位置|
|| ![黄色の時計アイコン。 [](media/Presence_Away.png)最終版]*が表示さ*れていないことを示します。|
|![黄色の時計アイコン。退席中として表示されます。](media/Presence_Away.png) 一時退席中| |
|| ![黄色の時計アイコン、[退席中]、[勤務停止]](media/Presence_Away.png)  業務時間外|
|| ![灰色の丸と x (x、オフラインを示す)](media/Presence_Offline.png) で |
|| ![灰色の円を開く、状態が不明であることを示す](media/Presence_Unknown.png) 状態不明|
||![四角で囲まれた赤い円を開き、ブロックされていることを示します。](media/Presence_Blocked.png) ブロックされました |
|| ![矢印付き紫色の円は、外出中であることを示します。](media/Presence_OOF.png) 外出中|
|||
 
ユーザーは、現在のプレゼンス状態をいくつかのオプションに手動で設定することができ、その状態は他のすべてのユーザーに反映されます。 その他のユーザーのプレゼンス情報も自動的に更新されます。 変更は、ユーザーのアクティビティ (利用可能、退席中)、Outlook の予定表の状態 (会議中)、またはチームアプリの状態 (通話中、発表中) に基づいて、一覧でインデントされた状態に基づいて行われます。 現在のプレゼンス状態が [退席中] にリセットされるまでの15分間のアイドル時間のタイムアウトがあります。

ユーザーには、プレゼンス状態に関係なく、すべてのチャットメッセージが Teams で送信されます。 他のユーザーがメッセージを送信したときにユーザーがオフラインになっている場合は、次回ユーザーがオンラインになったときに、Teams にチャットメッセージが表示されます。 ユーザーが [応答不可] 状態にある場合でも、ユーザーはチャットメッセージを受け取りますが、バナー通知は表示されません。

ユーザーは、[応答不可] 状態 (着信通話がボイスメールに配信される) を除き、すべてのプレゼンス状態で通話を受信します。 受信者が発信者をブロックした場合、通話は配信されず、発信者には受信者のプレゼンスがオフラインとして表示されます。

ユーザーを優先順位の高いアクセスリストに追加するには、Teams の [**設定** > ]**プライバシー**に移動します。 ユーザーが [応答不可] の状態にある場合でも、アクセス権が付与されているユーザーに連絡できます。

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a>Skype for Business と比較した場合のチームの管理設定

Skype for Business の次の管理設定は、Teams では異なります。

- Teams では、組織内のユーザーに対してプレゼンス共有が常に有効になります。 プライバシー (プレゼンスを表示できるユーザーを定義した場合) 構成は Teams では利用できません。
- すべてのユーザー (フェデレーションサービスを含む) とのプレゼンスの共有は、Teams のユーザーに対して常に有効になっています。 連絡先リスト (Skype for Business に含まれている場合) は、**チャット >** の [連絡先] または [ **> の連絡先**への通話] の下に表示されます。
- クライアントが応答不可であり、チーム内のユーザーに対して画期的な機能が常に有効になります。
- 予定表 (不在およびその他の予定表情報が含まれています) は、Teams が Outlook と統合されている場合、ユーザーに対して常に有効になります。
- 組織で Skype for Business が使用されている場合、[*最終表示*または*退席後*の状態の後、チームのユーザーは常に有効になります。

> [!NOTE]
> チーム管理者がこれらの設定をカスタマイズできるかどうかは、現在サポートされていません。

## <a name="coexistence-with-skype-for-business"></a>Skype for Business と共存する

組織で Skype for business を使用している場合の Teams の機能の詳細については、「 [skype For business との共存](coexistence-chat-calls-presence.md)」を参照してください。
