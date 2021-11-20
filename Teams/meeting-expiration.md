---
title: 会議ポリシーと会議の有効期限 (Microsoft Teams
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: nej
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom: ''
description: 会議ポリシー設定を使用して、会議の有効期限を制御する方法についてMicrosoft Teams。
ms.openlocfilehash: 7912c57e12de83f112bb1c80b1c44d81d9d6b857
ms.sourcegitcommit: 32ba2ed0343e19f56e62fb3c507923c95f11b1bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2021
ms.locfileid: "61124264"
---
# <a name="meeting-policies-and-meeting-expiration-in-microsoft-teams"></a>会議ポリシーと会議の有効期限 (Microsoft Teams

[](meeting-policies-overview.md) Microsoft Teams の会議ポリシーは、組織内のユーザーが会議を開始およびスケジュールできるかどうかと、ユーザーがスケジュールした会議に対して会議参加者が使用できる機能を制御するために使用されます。 グローバル (組織全体の既定) ポリシーを使用ことも、カスタム ポリシーを作成して割り当てることもできます。 Microsoft Teams 管理センターで、または Get [、New、Set、Remove、Grant](/powershell/module/skype/new-csteamsmeetingpolicy)-CsTeamsMeetingPolicy PowerShell コマンドレットを使用して、会議ポリシーを管理します。 [](/powershell/module/skype/get-csteamsmeetingpolicy) [](/powershell/module/skype/set-csteamsmeetingpolicy) [](/powershell/module/skype/remove-csteamsmeetingpolicy) [](/powershell/module/skype/grant-csteamsmeetingpolicy)

ユーザーが会議を開始およびスケジュールできるかどうかを制御し、ユーザーがスケジュールした会議の有効期限を制御する会議ポリシー設定。 会議の参加リンクと会議 ID の有効期限が切れると、誰も会議に参加できます。 次の会議ポリシー設定は、ユーザーが会議を開始してスケジュールできるかどうかを決定Teams。 この記事では、会議の設定について説明します。

- [[チャネルで今すぐ](meeting-policies-in-teams-general.md#allow-meet-now-in-channels)会議を許可する]: ユーザーがチャネルで一時会議を開始できるかどうかを制御します。
- [チャネル会議のスケジュール設定](meeting-policies-in-teams-general.md#allow-channel-meeting-scheduling)を許可する: ユーザーがチャネルで会議をスケジュールできるかどうかを制御します。
- [[プライベート会議のスケジュール設定](meeting-policies-in-teams-general.md#allow-scheduling-private-meetings)を許可する]: ユーザーがプライベート会議をスケジュールできるかどうかをTeams。 チームのチャネルに公開されていない会議はプライベートです。
- [[ユーザーのOutlookを許可](meeting-policies-in-teams-general.md#allow-the-outlook-add-in)する: ユーザーが会議からプライベート会議をスケジュールできるかどうかをOutlook。 チームのチャネルに公開されていない会議はプライベートです。
- [[プライベート会議で今すぐ](meeting-policies-in-teams-general.md#allow-meet-now-in-private-meetings)会議を許可する]: ユーザーが一時プライベート会議を開始できるかどうかを制御します。

既定では、これらの設定はオンになっています。 これらの設定が無効になっている場合、ポリシーが割り当てられているユーザーは、その種類の新しい会議を開始またはスケジュール設定できます。 同時に、ユーザーが以前に開始またはスケジュールした、その種類のすべての既存の会議の会議参加リンクと会議 ID が期限切れになります。

たとえば、これらの会議ポリシー設定が **[** オン] に設定されている会議ポリシーがユーザーに割り当てられている場合、[チャネルで今すぐ会議を許可する] 設定をオフにすると、そのユーザーはチャネルで即日の会議を開始できなくなりました。また、[会議] チャネルでは、以前に作成したリンクが期限切れになります。 ユーザーは、他の種類の会議を開始してスケジュールを設定し、他のユーザーが開催した会議に参加できます。

## <a name="what-happens-when-the-meeting-join-link-and-conference-id-expire"></a>会議参加リンクと会議 ID の有効期限が切れると、どうなるでしょうか。

会議の参加リンクと会議 ID の有効期限が切れると、誰も会議に参加できます。 ユーザーがリンクまたは電話で会議に参加しようとすると、会議が利用できなくなったというメッセージが表示されます。 会話、ファイル、ホワイトボード、レコーディング、トランスクリプト、会議に関連するその他のコンテンツは保持され、ユーザーは引き続きアクセスできます。

## <a name="what-happens-when-you-turn-on-and-turn-off-a-meeting-policy-setting"></a>会議ポリシー設定をオンまたはオフにすると、何が起こりますか?

### <a name="switch-a-meeting-policy-setting-from-on-to-off"></a>会議ポリシー設定をオンからオフに切り替える

会議ポリシー設定が [オン]に設定されている場合、ポリシーが割り当てられているユーザーは、その種類の会議を開始またはスケジュールできます。すべてのユーザーが参加できます。 会議ポリシー設定を **[** オフ] に切り替えた場合、ポリシーが割り当てられているユーザーは、その種類の新しい会議を開始またはスケジュールできないので、ユーザーが以前にスケジュールした既存の会議の会議参加リンクと会議 ID が期限切れになります。

ユーザーは、他のユーザーが開催した会議に引き続き参加できます。

### <a name="switch-a-meeting-policy-setting-from-off-to-on"></a>会議ポリシー設定をオフからオンに切り替える

会議ポリシー設定を [オフ]から **[オン**] に切り替える場合、ポリシーが割り当てられているユーザーは、その種類の会議を開始またはスケジュールできます。 ユーザーに対して会議ポリシー設定がオフになってから再度有効にした場合、ユーザーが開催した以前にスケジュールされた会議 (および期限切れ) はすべてアクティブになり、ユーザーは会議参加リンクまたは電話を使用して会議に参加できます。  

## <a name="meeting-expiration-scenarios"></a>会議の有効期限のシナリオ

この記事で説明する各会議ポリシー設定について、会議の有効期限のしくみの概要を次に示します。

|必要な場合...&nbsp;&nbsp; |これを行う&nbsp;&nbsp;&nbsp;&nbsp;  |会議参加の動作&nbsp;&nbsp;&nbsp;&nbsp;  |
|---------------------------|---------------------|---------|
|ユーザーが開始したプライベート会議の有効期限を切る&nbsp;&nbsp;|プライベート会議 **で [今すぐ会議を許可する] をオフにします**。&nbsp;&nbsp;|ユーザーが開始した **プライベート会議に** 誰も参加できます。|
|ユーザーがスケジュールしたプライベート会議の有効期限を切る&nbsp;&nbsp;|[プライベート **会議のスケジュール設定を許可する**] をオフにし、[Outlook **アドインを許可する] をオフにします**。 &nbsp;&nbsp;|ユーザーがスケジュールした非公開の会議に誰も参加できます。 これにより、ユーザーは次の会議に参加できます。<ul><li>過去に発生したプライベート会議。</li><li>将来予定され、まだ発生していないプライベート会議。</li><li>定期的なプライベート会議の今後のインスタンス。</li></ul><br>[**プライベート会議のスケジュール** を **許可** する] と [Outlookを許可する] は、ユーザーがスケジュールしたプライベート会議の有効期限が切れるには、オフにする必要があります。 1 つの設定がオフで、もう 1 つの設定がオンになっている場合、既存の会議の会議参加リンクと会議の数はアクティブなままであり、有効期限が切れはされません。|
|期限切れチャネル **ユーザーが開始** した会議を今すぐ満たす&nbsp;&nbsp;|チャネルで **[今すぐ会議を許可する] をオフにし**_、[_ チャネル会議 **のスケジュールを許可する] をオフにします**。&nbsp;&nbsp;|ユーザーが開始した [ **今すぐ会議]** チャネルに参加できるユーザーはいます。|
|ユーザーがスケジュールしたチャネル会議の有効期限を切る&nbsp;&nbsp;|[チャネル会議 **のスケジュール設定を許可する] をオフにします**。&nbsp;&nbsp;|ユーザーがスケジュールしたチャネル会議に誰も参加できます。 これにより、ユーザーは次の会議に参加できます。<ul><li>過去に発生したチャネル会議。</li><li>将来予定され、まだ発生していないチャネル会議。</li><li>定期的なチャネル会議の今後のインスタンス。</li></ul>|

特定のユーザーが以前にスケジュールまたは開始した会議にユーザーがアクセスする場合は、次の方法があります。

- そのユーザーの会議ポリシー設定を有効にします。
- そのユーザーの会議ポリシー設定をオフにし、ポリシー設定を有効にしている別のユーザーに、期限切れの会議を置き換える新しい会議を作成します。

> [!NOTE]
> 会議が代理人によって送信された場合(管理者など、他のユーザーの代わりに会議出席依頼を送信するアクセス許可が与えられた場合)、会議ポリシー設定は、アクセス許可を付与したユーザー (マネージャー) に適用されます。

## <a name="changes-to-meeting-expiration"></a>会議の有効期限の変更

新しく作成Teams記録 (TMRs) には、既定で 60 日間の有効期限が設定されます。 これは、すべてのテナントで既定でオンになっています。 つまり、既定では、この機能を有効にした後に作成された TMRs はすべて、作成日から 60 日後に削除されます。 管理者は、会議を自動期限切れに **しないに設定できます**。 OneDriveおよびSharePointシステムは、すべての TMRs で設定された有効期限を監視し、その有効期限に自動的に TMRs をごみ箱に移動します。

自動会議の有効期限は、古い TMRs によって作成されたストレージの低優先メールを減らす軽量の家事処理メカニズムです。 平均すると、すべてのお客様に対して、60 日後に 99% の TMRs が監視されません。 ほぼすべてのお客様が、60 日後に再び視聴されなくなる可能性が高い記録を削除することで、テナントのストレージ負荷の削減の恩恵を受けると考えています。 既定では、すべてのお客様に可能な限りクリーンなエクスペリエンスを提供することです。

会議の有効期限を使用して、OneDriveレコードSharePointによって駆動されるクラウド ストレージの使用量に対するTeams制限します。 一般的な会議記録では、1 時間あたり約 400 MB の記録が消費されます。

> [!NOTE]
> A1 ユーザーの既定の有効期限の最大値は 30 日です。

### <a name="expiration-date"></a>有効期限

- 有効期限は、作成日に加えて、管理者がポリシーに設定した既定Teams **として計算されます**。
- 再生は有効期限に影響を与えはありません。

### <a name="change-the-default-expiration-date"></a>既定の有効期限を変更する

管理者は、PowerShell または管理センターで既定の有効期限Teams編集できます。 変更は、その時点から *新しく作成* された TMRs にのみ適用されます。 その日付より前に作成された記録には影響を与えされません。 管理者は、既存の TMRs の有効期限を変更できない。 これは、TMR を所有するユーザーの決定を保護するために行われます。 この設定では、会議と通話の両方を制御できます。

有効期限の値は、次のように設定できます。

- 最小値: **1 日**
- 最大値: **99,999 日**
- また、有効期限を **-1** に設定して、記録の有効期限が切れることはありません。

PowerShell コマンドの例は、以下のとおりです。

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -NewMeetingRecordingExpirationDays 50
```

有効期限は、管理センターの [会議ポリシー Teams設定 **できます。** 会議を自動的に **有効にすると、** 記録の有効期限を設定するオプションが表示されます。

![会議の有効期限ポリシーの管理センターのスクリーンショット。](media/meeting-expiration-policy.jpg)

### <a name="security-and-compliance"></a>セキュリティとコンプライアンス

#### <a name="should-i-rely-on-this-feature-for-strict-security-and-compliance-adherence"></a>セキュリティとコンプライアンスの厳格な準拠のために、この機能に依存する必要がありますか?

いいえ。エンド ユーザーが制御する記録の有効期限を変更できるので、法的保護のためにこれを利用してはならない。

#### <a name="will-a-retention-andor-deletion-policy-ive-set-in-the-security--compliance-center-override-the-teams-meeting-recording-expiration-setting"></a>Security & コンプライアンス センターで設定したアイテム保持ポリシーや削除ポリシーは、会議Teamsの有効期限設定を上書きしますか?

はい。コンプライアンス センターで設定したポリシーが完全に優先されます。

次に例を示します。

- サイト内のすべてのファイルを 100 日間保持し、Teams 会議の記録の有効期限設定が 30 日間であるポリシーがある場合、記録は 100 日間保持されます。
- Teams 会議のすべての記録が 5 日後に削除され、Teams 会議記録の有効期限設定が 30 日後に設定されている削除ポリシーがある場合、記録は 5 日後に削除されます。

### <a name="will-this-feature-enforce-file-retention"></a>この機能はファイルの保持を強制しますか?

いいえ。この機能や設定により、ファイルは保持されません。 削除権限を持つユーザーが、有効期限が設定された TMR を削除しようとした場合、そのユーザーの削除アクションが実行されます。

### <a name="what-skus-are-required-for-this-feature"></a>この機能に必要な SKU は何ですか?

- すべての SKU にこの機能が既定で搭載されます。
- A1 ユーザーは既定で最大 30 日間の有効期限に設定されますが、必要に応じて有効期限を変更できます。

### <a name="what-if-i-want-the-admin-to-have-full-control-over-the-lifecycle-of-meeting-recordings-and-dont-want-to-give-end-users-the-ability-to-override-the-expiration-date"></a>管理者が会議の記録のライフサイクルを完全に制御し、エンド ユーザーに有効期限を上書きする機能を与えたくない場合は、どうしますか。

セキュリティポリシーとコンプライアンス 保持ポリシーまたは削除ポリシーを使用することをお勧めします。 このサービスは、複雑なポリシーや SLA 駆動型の管理的な法的問題を解決することを目的としています。

自動有効期限機能は、古い会議記録から作成されたストレージの煩雑を軽減する軽量のTeams専用です。

### <a name="will-future-tmrs-migrated-from-classic-stream-after-this-feature-is-released-have-auto-expiration-applied-to-them-too"></a>この機能のリリース後、クラシック ストリームから移行した将来の TMR にも自動失効が適用されますか?

いいえ。移行した TMR には有効期限が設定されません。 その代わりに、管理者には、保持したい TMR のみを移行することをお勧めします。 詳細は移行ドキュメントに記録されます。

### <a name="how-is-this-feature-different-from-the-expiration-message-i-see-when-a-tmr-upload-to-onedrive-and-sharepoint-fails"></a>この機能は、TMR アップロードが失敗した場合に表示される有効期限メッセージOneDrive違SharePointですか。

記録を OneDrive または SharePoint にアップロードできない場合、Teams アプリケーションは、ユーザーが Teams サーバーから完全に削除される前に TMR をダウンロードするために最大 21 日間のメッセージをチャットに表示します。 TMR アップロードの失敗によるこの既存の有効期限エクスペリエンスは、ヘルプ ドキュメントで説明されている OneDrive および SharePoint の自動有効期限機能とは関係はありません。

## <a name="related-topics"></a>関連項目

[会議の有効期限を変更する - エンド ユーザーのコントロール](https://support.microsoft.com/office/record-a-meeting-in-teams-34dfbe7f-b07d-4a27-b4c6-de62f1348c24#bkmk_view_change_expiration_date)

[Teams での会議ポリシーを管理する](meeting-policies-overview.md)

[ Teams でユーザーにポリシーを割り当てる](policy-assignment-overview.md)

[Teams での PowerShell の概要](teams-powershell-overview.md)


