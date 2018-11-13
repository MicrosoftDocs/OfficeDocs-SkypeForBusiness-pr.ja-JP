---
title: マイクロソフトのチームでのライブ イベントを構成します。
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: tonysmit
search.appverid: MET150
description: 出席者の表示/非表示を設定して、レコーディングのオプションを含む、Microsoft のチームのライブ イベントの設定を構成する方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: fcd9bc02257d67f1af959d2158042ea73545a25e
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2018
ms.locfileid: "26296106"
---
# <a name="configure-live-events-in-microsoft-teams"></a>マイクロソフトのチームでのライブ イベントを構成します。
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

## <a name="set-up-event-support-link"></a>イベントのサポートのリンクを設定します。
これは、ライブ イベントの参加者に表示されるリンクです。 

Windows PowerShell で、次の手順を実行します。
```
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
## <a name="configure-attendee-visibility-options"></a>出席者の表示/非表示のオプションを構成します。
これにより、適切な参加者の可視性を持つイベントを作成するライブ イベントを開催します。

|**値**  |**動作**  |
|---------|---------|
|全員     |ライブ イベントを次の出席者の可視性を作成するオプションをユーザーが持っている: 会社、および特定のユーザーのすべてのメンバーを公開します。 |
|EveryoneInCompany     |ユーザーは、ライブ イベントを次の出席者の可視性を作成するオプションを持っている: 会社および特定のユーザーのすべてのメンバーです。 ユーザーは、匿名ユーザーが参加できるライブ イベントを作成できません。|
|InvitedUsers |ユーザーは、イベント開催者によって入力されたとおりに、特定の人に制限されているライブのイベントのみを作成できます。 ユーザーは、公開キーと認証の会社のすべてのメンバーでライブ イベントを作成できません。 |

ユーザーが匿名の参加者を監視することができますブロードキャストのイベントのスケジュールを設定するかどうかは、PowerShell の TeamsMeetingBroadcastPolicy の BroadcastAttendeeVisibility コントロールの設定を使用します。 

カスタム ポリシーは、ユーザーに割り当てている、しない限り、ユーザーは、EveryoneInCompany に設定する既定値を保持するグローバル ポリシーを取得します。 
 
Windows PowerShell では、[グローバル ポリシーで匿名イベントを作成するユーザーを許可するのには、次を実行します。
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="configure-recording-options"></a>レコーディングのオプションを構成します。
> [!NOTE]
> このオプションは、クイック スタートの生産方法のみを使用するイベントに適用されます。

これにより、ライブ イベントは、常に記録、記録されることはないかどうか、またはイベントの開催者は、かのイベントが記録することができるかどうか制御する管理者です。  

|**値**  |**動作**  |
|---------|---------|
|常に有効になっています。 |このユーザーごとのライブ イベントは、常に記録されます。 ユーザー オプションをオーバーライドする必要はありません。 ライブのイベントが記録される場合は、イベントのチーム メンバーは、イベントの後にレコーディングをダウンロードすることと出席者は、イベント終了後のイベントを監視できます。 |
|AlwaysDisabled |このユーザーが開催するライブ イベントが記録されることはありません。 ユーザー オプションをオーバーライドする必要はありません。 ライブのイベントが記録される場合は、イベント チームのメンバーの記録は作成されず、出席者はイベントが上にあるを見ることはできません。 |
|UserOverride |ユーザーは、イベント チームのメンバーの記録ファイルを作成することができ、参加者がイベント終了後のイベントを監視するためにライブ イベントを記録するかどうかを決定できます。 |

レコーディングのライブ イベントの開催者によって作成されたライブ イベントのオプションのコントロールに、PowerShell では、 **TeamsMeetingBroadcastPolicy**で*BroadcastRecordingMode*の設定を使用します。

Windows PowerShell のでは、グローバル ポリシーでの記録モードを更新するのには次のコマンドレットを実行します。
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="configure-real-time-transcription-and-translation-in-teams-live-events-coming-soon"></a>(準備中) チームのライブ イベントのリアルタイム議事録を作成し、変換を構成します。
> [!NOTE]
> このオプションは、クイック スタートの生産方法のみを使用するイベントに適用されます。

これにより、リアルタイムのキャプションとライブ イベントの出席者に対して変換を有効にするのにはライブ イベントを開催します。 

ライブ イベントの参加者が議事録と翻訳を参照してくださいできるかどうかにコントロールする PowerShell の**TeamsMeetingBroadcastPolicy**で*AllowBroadcastTranscription*の設定を使用します。 ここで、Office 365 の PowerShell では、 **TeamsMeetingBroadcastPolicy**を管理する方法の詳細については。  

カスタム ポリシーは、ユーザーに割り当てている、しない限り、ユーザーは、議事録作成と翻訳が既定で無効にするグローバル ポリシーを取得します。

Windows PowerShell では、[グローバル ポリシーでの議事録やイベントの出席者のために翻訳を有効にするのには、次のコマンドレットを実行します。
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```
## <a name="administrative-tools"></a>管理ツール 
直接 Microsoft は、Office 365 のオンラインのすべてのデータ センターを制御し、システム全体のパフォーマンスは、ですが、Office 365 のユーザーの合計の経験を提供する要素の一部だけを制御できます。 組織自体は、データ センターでお客様のワイド エリア ネットワーク (WAN)、ネットワーク接続を担当し、お客様のローカル エリア ネットワーク (Lan)。 さらに、ユーザーのデバイスとその構成を担当しています。必要なライセンスなど、必要な機能は、ユーザーごとの管理を担当する、マイクロソフトが、ユーザーは、機能へのアクセスを必要がある限りのこれらの機能を管理することに。

お客様は、さまざまなチームのライブ イベントの関連タスクを管理するために次のツールを使用できます。
- [Microsoft Office 365 管理者センター](https://technet.microsoft.com/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_Office365admincenterl)
- [マイクロソフトのチームと Skype のオンライン ビジネスの管理センター](https://technet.microsoft.com/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_ExchangeAdministrationCenter)
- [Microsoft ストリーム管理センター](https://stream.microsoft.com)
- [リモートの Windows PowerShell の](https://technet.microsoft.com/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_RemoteWindowsPowerShell)

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報
に関して Windows PowerShell は、it のすべてのユーザーを管理するか、ユーザーの許可を許可します。 Windows PowerShell では、ビジネス オンラインを行う複数のタスクがある場合、日常的な作業を簡素化する管理の単一ポイントを使用して Office 365 と Skype を管理できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
 - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
 - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)

Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。
 - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
 - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
 - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
