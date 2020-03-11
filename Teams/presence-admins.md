---
title: Teams でのユーザーのプレゼンス
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Teams でのプレゼンスに関する管理者向け情報。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7e0d7ef2fa7ae12f660bf6b77ba7c45a8c49ab10
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "41863198"
---
# <a name="user-presence-in-teams"></a>Teams でのユーザーのプレゼンス

プレゼンスは、Microsoft Teams (および Office 365 全体) のユーザーのプロファイルの一部であり、ユーザーの現在の空き状況や状態を他のユーザーに示します。 既定では、組織内で Teams を使用しているすべてのユーザーは、他のユーザーがオンラインの場合、(ほぼリアルタイムで) 確認できます。

> [!IMPORTANT]
> ユーザーを [**Teams のみ**] モードに移動した後に Skype for Business クライアントをアンインストールすると、Outlook および Office アプリでプレゼンスが機能しなくなります。 プレゼンスは Teams では正常に機能します。 回避策: Outlook (および他の Office アプリ) でプレゼンスを表示させるには、Teams を [**Teams のみ**] モードで実行している場合であっても、Skype for Business をインストールする必要があります。 Microsoft はこの問題を把握しており、現在修正に向けて取り組んでいます。

Outlook での Teams のプレゼンスは、Outlook 2013 デスクトップ版アプリ以降でサポートされています。

## <a name="presence-states-in-teams"></a>Teams でのプレゼンス状態

Teams で利用できるユーザーのプレゼンス状態は次のとおりです。

|ユーザーが設定|アプリが設定|
|:--- |:---|
| ![塗りつぶした緑のチェックマークは、連絡可能な状態を示す](media/Presence_Available.png) 連絡可能|![塗りつぶした緑のチェックマークは、連絡可能な状態を示す](media/Presence_Available.png) 連絡可能|
|| ![緑枠のチェックマークは、連絡可能な外出中の状態を示す](media/Presence_Available_OOF.png) 連絡可能、外出中 |
|  ![塗りつぶした赤い丸は、取り込み中を示す](media/Presence_Busy.png) 取り込み中 |  ![塗りつぶした赤い丸は、取り込み中を示す](media/Presence_Busy.png) 取り込み中  |
|| ![塗りつぶした赤い丸は、通話のための取り込み中を示す](media/Presence_Busy.png) 通話中|
|| ![塗りつぶした赤い丸は、会議のための取り込み中を示す](media/Presence_Busy.png) 会議中 |
|| ![赤枠の丸は、取り込み中を示す](media/Presence_Busy_OOF.png) 通話中、外出中|
|  ![白線の入った赤い丸は、応答不可を示す](media/Presence_DND.png) 応答不可 ||
|| ![白線の入った赤い丸は、発表中を示す](media/Presence_DND.png) 発表中|
|| ![白線の入った赤い丸は、フォーカスを示す](media/Presence_DND.png) フォーカス|
| ![黄色の時計アイコンは、退席中を示す](media/Presence_Away.png) 退席中| ![黄色の時計アイコンは、退席中を示す](media/Presence_Away.png) 退席中|
|| ![黄色の時計アイコンは、退席中を示す*前回の退席中表示](media/Presence_Away.png)時刻*|
|![黄色の時計アイコンは、一時退席中を示す](media/Presence_Away.png) 一時退席中| |
|| ![黄の時計アイコンは、退席中、業務時間外を示す](media/Presence_Away.png)  業務時間外|
|| ![X マーク付き灰色の丸は、オフラインを示す](media/Presence_Offline.png) オフライン |
|| ![灰色枠の丸は、状態不明を示す](media/Presence_Unknown.png) 状態不明|
||![斜線の入った赤枠の丸は、ブロックされたことを示す](media/Presence_Blocked.png) ブロックされました |
|| ![矢印付き紫色の丸は、外出中を示す](media/Presence_OOF.png) 外出中|
|||
 
ユーザーは、現在のプレゼンス状態をいくつかのオプションから手動で設定できます。その状態が他のすべてのユーザーに対して表示されます。 ユーザーのプレゼンスの他の詳細情報も自動的に更新されます。 ユーザーのアクティビティ (連絡可能、退席中)、Outlook カレンダーの状態 (会議中)、Teams アプリの状態 (通話中、発表中) などに基づいて、このリストの右側の状態に変更されます。 15 分間休止状態が続くとタイムアウトが発生し、現在のプレゼンス状態は「退席中」にリセットされます。

プレゼンス状態に関係なく、ユーザーは、Teams で送信されたすべてのチャット メッセージを受信します。 他者がメッセージを送信したときにユーザーがオフラインだった場合は、次回ユーザーがオンラインになったときに Teams にチャット メッセージが表示されます。 「応答不可」状態にある場合でもユーザーはチャット メッセージを受信できますが、バナー通知は表示されません。

ユーザーは、「応答不可」状態 (着信呼び出しがボイスメールに配信される) を除き、すべてのプレゼンス状態で通話を受信します。 受信者が発信者をブロックした場合、通話は配信されず、発信者には受信者のプレゼンスが「オフライン」と表示されます。

ユーザーを優先順位の高いアクセス リストに追加するには、Teams の **[設定]** > **[プライバシー]** に移動します。 ユーザーが「応答不可」状態にある場合でも、優先アクセス権が付与されている発信者は、ユーザーと連絡を取ることができます。

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a>Skype for Business と Teams の管理設定の比較

Skype for Business と Teams では、次の管理設定が異なります。

- Teams では、組織内ユーザーに対してプレゼンス共有が常に有効になります。 プライバシー (プレゼンスを表示できるユーザーを定義する) 構成は、Teams では利用できません。
- すべてのユーザー (フェデレーション サービスを含む) とのプレゼンス共有は、Teams ユーザーに対して常に有効になっています。 連絡先リスト (Skype for Business に含まれている場合) は、**[チャット] > [連絡先]** または **[通話] > [連絡先]** で表示できます。
- クライアントの「応答不可」と「重要な連絡先」機能は、Teams ユーザーに対して常に有効になっています。
- カレンダー (不在およびその他のカレンダー情報を含む) は、Teams が Outlook と統合されている場合、ユーザーに対して常に有効になっています。
- 組織で Skype for Business を使用している場合は、*[最終ログイン]* または *[退席中]* インジケータ―が、Teams ユーザーに対して常に有効になっています。

> [!NOTE]
> Teams 管理者がこれらの設定をカスタマイズする機能は、現在サポートされていません。

## <a name="coexistence-with-skype-for-business"></a>Skype for Business との共存

組織で Skype for business も使用している場合の Teams のプレゼンス機能の詳細については、「[Skype for Business との共存](coexistence-chat-calls-presence.md)」を参照してください。
