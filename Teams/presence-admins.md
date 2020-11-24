---
title: Teams でのユーザーのプレゼンス
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Teams のプレゼンス状態と、プレゼンス機能の管理設定について説明します。
ms.custom: seo-marvel-apr2020
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: d2949ef0defec37ce674fb8d7a94250d29fe0a3a
ms.sourcegitcommit: bac9aa29074ef32387dc05b3918e87d4c38d195d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2020
ms.locfileid: "49385644"
---
# <a name="user-presence-in-teams"></a>Teams でのユーザーのプレゼンス

プレゼンスは、Microsoft Teams (および Microsoft 365 または Office 365 全体) のユーザーのプロファイルの一部です。 [プレゼンス] は、ユーザーの現在の可用性と状態を他のユーザーに表示します。 既定では、組織内で Teams を使用しているすべてのユーザーは、他のユーザーがオンラインの場合、(ほぼリアルタイムで) 確認できます。 モバイルでページを更新すると、web とデスクトップのバージョンでプレゼンスがリアルタイムで更新されます。

 > [!Note]
 > さまざまなプラットフォームの Teams ユーザープロファイルの詳細については、「 [プラットフォームごとの teams の機能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)」を参照してください。

## <a name="presence-states-in-teams"></a>Teams でのプレゼンス状態

|ユーザーが設定|アプリが設定|
|:--- |:---|
| ![塗りつぶした緑のチェックマークは、連絡可能な状態を示す](media/Presence_Available.png) 連絡可能|![塗りつぶした緑のチェックマークは、連絡可能な状態を示す](media/Presence_Available.png) 連絡可能|
|| ![緑枠のチェックマークは、連絡可能な外出中の状態を示す](media/Presence_Available_OOF.png) 外出中でもご利用いただけます。 注: ユーザーが "自動応答" を設定した期間、[不在時の自動応答] が自動的に設定されます。 この期間中にユーザーがアプリを使用している場合は、"外出中、利用可能" などの2つのプレゼンスが表示されることがあります。 |
|  ![塗りつぶした赤い丸は、取り込み中を示す](media/Presence_Busy.png) 取り込み中 |  ![塗りつぶした赤い丸は、取り込み中を示す](media/Presence_Busy.png) 取り込み中  |
|| ![塗りつぶした赤い丸は、通話のための取り込み中を示す](media/Presence_Busy.png) 通話中|
|| ![塗りつぶした赤い丸は、会議のための取り込み中を示す](media/Presence_Busy.png) 会議中 |
|| ![赤枠の丸は、取り込み中を示す](media/Presence_Busy_OOF.png) 通話中、外出中|
|  ![白線の入った赤い丸は、応答不可を示す](media/Presence_DND.png) 応答不可 ||
|| ![白線の入った赤い丸は、発表中を示す](media/Presence_DND.png) 発表中|
|| ![白線の入った赤い丸は、フォーカスを示す](media/Presence_DND.png) 焦点. ユーザーが自分の予定表の MyAnalytics/インサイトでフォーカス時間をスケジュールすると、フォーカスが設定されます。|
| ![黄色の時計アイコンは、退席中を示す](media/Presence_Away.png) 退席中| ![黄色の時計アイコンは、退席中を示す](media/Presence_Away.png) 退席中|
|| ![黄色の時計アイコンは、退席中を示す *前回の退席中表示](media/Presence_Away.png)時刻*|
|![黄色の時計アイコンは、一時退席中を示す](media/Presence_Away.png) 一時退席中| |
|![X マーク付き灰色の丸は、オフラインを示す](media/Presence_Offline.png) オフラインとして表示する|![X マーク付き灰色の丸は、オフラインを示す](media/Presence_Offline.png) で.  ユーザーが何分もデバイスにログインしていない場合は、オフラインとして表示されます。 | |
|| ![灰色枠の丸は、状態不明を示す](media/Presence_Unknown.png) 状態不明|
|| ![矢印付き紫色の丸は、外出中を示す](media/Presence_OOF.png) 外出中です。 不在時の自動応答が設定されている場合に使用されます。 (Outlook でのみ利用できます。) |
|||

アプリで構成されたプレゼンス状態は、ユーザーアクティビティ (利用可能、退席中)、Outlook の予定表の状態 (会議中)、または Teams アプリの状態 (通話中、発表中) に基づいています。 予定表に基づいてフォーカスモードになっている場合は、チームでユーザーに表示される状態に **注目** します。 フォーカスモードは、他の製品で **は [応答不可** 」として表示されます。

コンピューターをロックした場合、またはコンピューターがアイドルまたはスリープモードに切り替わったときに、現在のプレゼンス状態が "退席中" に変わります。 モバイルデバイスでは、Teams アプリがバックグラウンドにあるときは、プレゼンス状態が [退席中] に変わります。

プレゼンス状態に関係なく、ユーザーは、Teams で送信されたすべてのチャット メッセージを受信します。 他者がメッセージを送信したときにユーザーがオフラインだった場合は、次回ユーザーがオンラインになったときに Teams にチャット メッセージが表示されます。 ユーザー状態が [応答不可] に設定されている場合でも、ユーザーはチャットメッセージを受信しますが、バナー通知は表示されません。

ユーザーは、[応答不可] (着信通話がボイスメールに転送される) を除くすべてのプレゼンス状態で通話を受信します。 受信者が発信者をブロックした場合、通話は配信されず、発信者には受信者のプレゼンスが「オフライン」と表示されます。

ユーザーを優先順位の高いアクセス リストに追加するには、Teams の **[設定]** > **[プライバシー]** に移動します。 ユーザーの状態が [応答不可] に設定されている場合でも、アクセス権が与えられているユーザーに連絡できます。

### <a name="dual-presence"></a>デュアルプレゼンス

  ほとんどのユーザーに対してプレゼンスが機能することは、予定表またはデバイスイベント (呼び出しなど) のイベントによって実現されます。 ユーザーは、有効期限がある状態を手動で設定して、UI でこの状態を上書きすることができます。

## <a name="user-configured-states-expiration"></a>ユーザー構成状態の有効期限

ユーザーが特定のプレゼンス状態を選択すると、アプリのアクティビティの更新に優先します。 たとえば、ユーザーが [応答不可] に設定した場合は、会議に出席したか、電話に応答しても、プレゼンスが [応答不可] のままになります。

ユーザーによって構成された状態には、一定期間後に関連しない可能性のある状態が表示されないようにするため、Teams に既定の有効期限の設定があります。

|ユーザーが構成した状態|既定の有効期限|
|:--- |:---|
| 取り込み中|1日|
| 応答不可|1日|
| ユーザー|7日|
|||

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a>Skype for Business と Teams の管理設定の比較

Skype for Business と Teams では、次の管理設定が異なります。

- Teams では、組織内ユーザーに対してプレゼンス共有が常に有効になります。 プライバシー (プレゼンスを表示できるユーザーを定義した場合) 構成は Teams では使用できません。
- すべてのユーザー (フェデレーション サービスを含む) とのプレゼンス共有は、Teams ユーザーに対して常に有効になっています。 連絡先リスト (Skype for Business に含まれている場合) は、**[チャット] > [連絡先]** または **[通話] > [連絡先]** で表示できます。
- クライアントの「応答不可」と「重要な連絡先」機能は、Teams ユーザーに対して常に有効になっています。
- カレンダー (不在およびその他のカレンダー情報を含む) は、Teams が Outlook と統合されている場合、ユーザーに対して常に有効になっています。
- 組織で Skype for Business を使用している場合は、*[最終ログイン]* または *[退席中]* インジケータ―が、Teams ユーザーに対して常に有効になっています。

> [!NOTE]
> Teams 管理者がこれらの設定をカスタマイズする機能は、現在サポートされていません。

## <a name="admin-settings-in-teams-compared-to-microsoft-outlook"></a>Microsoft Outlook と比較した Teams の管理設定

Outlook での Teams のプレゼンスは、Outlook 2013 デスクトップ版アプリ以降でサポートされています。

ユーザーアカウントのアップグレードモードポリシーが [Team] に設定されている場合、Outlook は、チームと話してプレゼンスを取得します。 ユーザーアカウントが Teams のみに設定されていない場合は、Outlook は Skype for Business と通信します。

## <a name="coexistence-with-skype-for-business"></a>Skype for Business との共存

組織で Skype for business を使用している場合の Teams の機能の詳細については、「 [skype For business との共存](coexistence-chat-calls-presence.md) 」を参照してください。
