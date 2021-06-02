---
title: Teams でのユーザーのプレゼンス
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: チームのプレゼンス状態とプレゼンス機能の管理設定について学習します。
ms.custom: seo-marvel-apr2020
localization_priority: Priority
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 82d9f152dbba345f876ac166bcf6833e53bab799
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2021
ms.locfileid: "52718038"
---
# <a name="user-presence-in-teams"></a>Teams でのユーザーのプレゼンス

プレゼンスは、Microsoft Teams (および Microsoft 365 または Office 365 全体) のユーザー プロフィールの一部です。 プレゼンスは、ユーザーが現在の連絡可能かどうか、またそのユーザーの状態を他のユーザーに示します。 既定では、組織内で Teams を使用しているすべてのユーザーは、他のユーザーがオンラインの場合、(ほぼリアルタイムで) 確認できます。 モバイルでページを更新すると、Web バージョンとデスクトップ バージョンでプレゼンスがリアルタイムで更新されます。

 > [!NOTE]
 > 別のプラットフォームでの Teams のユーザー プロフィールについての詳細は、 [プラットフォームごとの Teams の機能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)を参照してください。

 > [!NOTE]
 > Teams はプライバシー設定を尊重しますので、プライバシー モードを有効にしている場合は、あなたの存在が外部のユーザーには表示されません。
## <a name="presence-states-in-teams"></a>Teams でのプレゼンス状態

|ユーザーが設定|アプリが設定|
|:--- |:---|
| ![塗りつぶした緑のチェックマークは、連絡可能な状態を示す](media/Presence_Available.png) 連絡可能|![塗りつぶした緑のチェックマークは、連絡可能な状態を示す](media/Presence_Available.png) 連絡可能|
|| ![緑枠のチェックマークは、連絡可能な外出中の状態を示す](media/Presence_Available_OOF.png) 連絡可能、外出中。 注: 「外出中」は、ユーザーが「自動返信」を設定した期間に自動的に設定されます。 ユーザーがこれらの期間中にアプリを使用している場合、「外出中、連絡可能」などの二重のプレゼンスが表示される場合があります。 |
|  ![塗りつぶした赤い丸は、取り込み中を示す](media/Presence_Busy.png) 取り込み中 |  ![塗りつぶした赤い丸は、取り込み中を示す](media/Presence_Busy.png) 取り込み中  |
|| ![塗りつぶした赤い丸は、通話のための取り込み中を示す](media/Presence_Busy.png) 通話中|
|| ![塗りつぶした赤い丸は、会議のための取り込み中を示す](media/Presence_Busy.png) 会議中 |
|| ![赤枠の丸は、取り込み中を示す](media/Presence_Busy_OOF.png) 通話中、外出中|
|  ![白線の入った赤い丸は、応答不可を示す](media/Presence_DND.png) 応答不可 ||
|| ![白線の入った赤い丸は、発表中を示す](media/Presence_DND.png) 発表中|
|| ![白線の入った赤い丸は、フォーカスを示す](media/Presence_DND.png) フォーカスは、ユーザーがカレンダーの MyAnalytics / Insights でフォーカス時間をスケジュールしたときに表示されます。|
| ![黄色の時計アイコンは、退席中を示す](media/Presence_Away.png) 退席中| ![黄色の時計アイコンは、退席中を示す](media/Presence_Away.png) 退席中|
|| ![黄色の時計アイコンは、退席中を示す *前回の退席中表示](media/Presence_Away.png)時刻*|
|![黄色の時計アイコンは、一時退席中を示す](media/Presence_Away.png) 一時退席中| |
|![X マーク付き灰色の丸、オフラインを示す](media/Presence_Offline.png) オフライン表示|![X マーク付き灰色の丸、オフラインを示す](media/Presence_Offline.png) オフライン。ユーザーがどのデバイスにも数分間ログインしていない場合、ユーザーはオフラインとして表示されます。 | |
|| ![灰色枠の丸は、状態不明を示す](media/Presence_Unknown.png) 状態不明|
|| ![矢印付き紫色の丸、外出中を示す](media/Presence_OOF.png) 外出中。自動応答が設定されている場合、外出中が使用されます。 |
|||
 > [!NOTE]
 > メールボックスをオンプレミスで運用しているユーザーの場合、プレゼンスは最大 1 時間程度の遅延が予想されます。

アプリで構成されたプレゼンス状態は、ユーザーのアクティビティ (連絡可能、退席中)、Outlook カレンダーの状態 (会議中)、Teams アプリの状態 (通話中、発表中) などに基づいています。 カレンダーに基づいてフォーカス モードになっている場合、**フォーカ** スは Teams で表示される状態になります。 フォーカス モードは、他の製品では **応答不可** と表示されます。

コンピューターをロックするか、コンピューターがアイドル モードまたはスリープ モードに入ると、現在のプレゼンス状態が [退席中] に変わります。 モバイル端末では、Teams アプリがバックグラウンドにあるときはいつでも、プレゼンス状態が [退席中] に変わります。

プレゼンス状態に関係なく、ユーザーは、Teams で送信されたすべてのチャット メッセージを受信します。 他者がメッセージを送信したときにユーザーがオフラインだった場合は、次回ユーザーがオンラインになったときに Teams にチャット メッセージが表示されます。 ユーザーの状態が [応答不可] に設定されている場合、ユーザーは引き続きチャットメッセージを受信しますが、バナー通知は表示されません。

ユーザーは、「応答不可」状態 (着信呼び出しがボイスメールに配信される) を除き、すべてのプレゼンス状態で通話を受信します。 受信者が発信者をブロックした場合、通話は配信されず、発信者には受信者のプレゼンスが「オフライン」と表示されます。

ユーザーを優先順位の高いアクセス リストに追加するには、Teams の **[設定]** > **[プライバシー]** に移動します。 ユーザーのステータスが「応答不可」状態に設定されている場合でも、優先アクセス権が付与されている発信者は、ユーザーと連絡を取ることができます。

### <a name="dual-presence"></a>デュアル プレゼンス

  ほとんどのユーザーにとってプレゼンスが機能する方法は、カレンダーのイベントまたは通話などのデバイス イベントに基づきます。 ユーザーは、有効期限のある状態を手動で設定することにより、UI でこのステータスを上書きできます。

## <a name="user-configured-states-expiration"></a>ユーザーが設定した状態の有効期限

ユーザーが特定のプレゼンス状態を選択すると、アプリ アクティビティの更新よりも優先されます。 たとえば、ユーザーが自分自身を「応答不可」と設定した場合、会議に出席したり電話に応答したりしても、その存在は「応答不可」のままになります。

ユーザーが構成した状態には、一定期間後に関連性がない可能性のあるステータスがユーザーに表示されないようにするために、Teams に既定の有効期限設定があります。

|ユーザーが設定した状態|既定の有効期限|
|:--- |:---|
| 多忙|1 日|
| 応答不可|1 日|
| その他|7 日間|
|||

> [!NOTE]
> ユーザーは、プレゼンスの期間を手動で構成することもできます。 たとえば、ユーザーは自分を明日の朝までオフラインで表示するように設定できます。

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a>Skype for Business と Teams の管理設定の比較

Skype for Business と Teams では、次の管理設定が異なります。

- Teams では、組織内ユーザーに対してプレゼンス共有が常に有効になります。 プライバシー (プレゼンスを表示できるユーザーを定義する場所) の構成は、Teams では使用できません。
- すべてのユーザー (フェデレーション サービスを含む) とのプレゼンス共有は、Teams ユーザーに対して常に有効になっています。 連絡先リスト (Skype for Business に含まれている場合) は、**[チャット] > [連絡先]** または **[通話] > [連絡先]** で表示できます。
- クライアントの「応答不可」と「重要な連絡先」機能は、Teams ユーザーに対して常に有効になっています。
- カレンダー (不在およびその他のカレンダー情報を含む) は、Teams が Outlook と統合されている場合、ユーザーに対して常に有効になっています。
- 組織で Skype for Business を使用している場合は、*[最終ログイン]* または *[退席中]* インジケータ―が、Teams ユーザーに対して常に有効になっています。

> [!NOTE]
> Teams 管理者がこれらの設定をカスタマイズする機能は、現在サポートされていません。

## <a name="admin-settings-in-teams-compared-to-microsoft-outlook"></a>Microsoft Outlook と Teams の管理設定の比較

Outlook でのチームのプレゼンスは、Outlook 2013 デスクトップ アプリ以降で、同じ組織内の連絡先に対してサポートされます。

ユーザー アカウントのアップグレード モード ポリシーが TeamsOnly に設定されている場合、Outlook はチームと通信してプレゼンスを取得します。 ユーザーアカウントが TeamsOnly に設定されていない場合、Outlook は Skype for Business と通信します。

## <a name="coexistence-with-skype-for-business"></a>Skype for Business との共存

組織で Skype for business も使用している場合の Teams のプレゼンス機能の詳細については、「[Skype for Business との共存](coexistence-chat-calls-presence.md)」を参照してください。
