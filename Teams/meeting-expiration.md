---
title: Microsoft Teams での会議ポリシーと会議の有効期限
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: nej, brgussin
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
description: 会議ポリシー設定を使用して、Microsoft Teams で会議の有効期限を制御する方法について説明します。
ms.openlocfilehash: 3d79041cf6e8e16ed4ebd680cf5f4370e04cd62a
ms.sourcegitcommit: f5d784df59a8010b390691bbb20c4ea66c46280b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/26/2022
ms.locfileid: "67005337"
---
# <a name="meeting-policies-and-meeting-expiration-in-microsoft-teams"></a>Microsoft Teams での会議ポリシーと会議の有効期限

Microsoft Teams の[会議ポリシー](meeting-policies-overview.md)は、組織内のユーザーが会議を開始およびスケジュールできるかどうかを制御するために使用されます。また、ユーザーがスケジュールした会議の会議参加者が利用できる機能を制御します。 グローバル (組織全体の既定) ポリシーを使用ことも、カスタム ポリシーを作成して割り当てることもできます。 会議ポリシーは、Microsoft Teams 管理センターで管理するか、 [Get](/powershell/module/skype/get-csteamsmeetingpolicy)、 [New](/powershell/module/skype/new-csteamsmeetingpolicy)、 [Set](/powershell/module/skype/set-csteamsmeetingpolicy)、 [Remove](/powershell/module/skype/remove-csteamsmeetingpolicy)、 [Grant](/powershell/module/skype/grant-csteamsmeetingpolicy) -CsTeamsMeetingPolicy PowerShell コマンドレットを使用して管理します。

ユーザーが会議を開始およびスケジュールできるかどうかを制御し、ユーザーがスケジュールした会議の有効期限を制御する会議ポリシー設定。 会議の参加リンクと会議の会議 ID の有効期限が切れた場合、誰も会議に参加できません。 次の会議ポリシー設定は、ユーザーが Teams で会議を開始およびスケジュールできるかどうかを決定します。 この記事では、会議の設定について説明します。

- [チャネルで今すぐ会議](meeting-policies-in-teams-general.md#meet-now-in-channels)する: ユーザーがチャネルで即席会議を開始できるかどうかを制御します。
- [チャネル会議のスケジュール](meeting-policies-in-teams-general.md#channel-meeting-scheduling)設定: ユーザーがチャネルで会議をスケジュールできるかどうかを制御します。
- [プライベート会議のスケジュール](meeting-policies-in-teams-general.md#private-meeting-scheduling)設定: ユーザーが Teams でプライベート会議をスケジュールできるかどうかを制御します。 チームのチャネルに公開されていない会議はプライベートです。
- [Outlook アドイン](meeting-policies-in-teams-general.md#outlook-add-in): ユーザーが Outlook からプライベート会議をスケジュールできるかどうかを制御します。 チームのチャネルに公開されていない会議はプライベートです。
- [プライベート会議で今すぐ会議を開催する](meeting-policies-in-teams-general.md#meet-now-in-private-meetings): ユーザーが即席のプライベート会議を開始できるかどうかを制御します。

既定では、これらの設定はオンになっています。 これらの設定のいずれかがオフになっている場合、ポリシーが割り当てられているユーザーは、その種類の新しい会議を開始またはスケジュールすることはできません。 同時に、ユーザーが以前に開始またはスケジュールされた有効期限が切れた、その種類のすべての既存の会議の会議参加リンクと会議 ID。

たとえば、これらの会議ポリシー設定が **[オン]** に設定されている会議ポリシーがユーザーに割り当てられ、[ **チャネルで今すぐ会議を許可** ] 設定をオフにした場合、そのユーザーはチャネルで即席の会議を開始できなくなり、チャネル Meet は以前に作成したリンクの有効期限が切れました。 ユーザーは、他の会議の種類を開始およびスケジュールし、他のユーザーが開催した会議に参加できます。

## <a name="what-happens-when-the-meeting-join-link-and-conference-id-expire"></a>会議参加リンクと会議 ID の有効期限が切れるとどうなりますか?

会議の参加リンクと会議の会議 ID の有効期限が切れると、誰も会議に参加できません。 ユーザーがリンクまたは電話で会議に参加しようとすると、会議が利用できなくなったことを示すメッセージが表示されます。 会話、ファイル、ホワイトボード、録音、トランスクリプト、会議に関連するその他のコンテンツは保持され、ユーザーは引き続きアクセスできます。

## <a name="what-happens-when-you-turn-on-and-turn-off-a-meeting-policy-setting"></a>会議ポリシー設定をオンまたはオフにするとどうなりますか?

### <a name="switch-a-meeting-policy-setting-from-on-to-off"></a>会議ポリシー設定をオンからオフに切り替える

会議ポリシー設定が **[オン]** に設定されている場合、ポリシーが割り当てられているユーザーは、その種類の会議を開始またはスケジュールでき、全員が参加できます。 会議ポリシー設定を **オフ** に切り替えると、ポリシーが割り当てられているユーザーは、その種類の新しい会議を開始またはスケジュールすることができず、以前にスケジュールされたユーザーが以前にスケジュールした既存の会議の会議参加リンクと会議 ID が期限切れになります。

ユーザーは引き続き他のユーザーが開催した会議に参加できます。

### <a name="switch-a-meeting-policy-setting-from-off-to-on"></a>会議ポリシー設定をオフからオンに切り替える

会議ポリシー設定を **[オフ]** から **[オン]** に切り替えると、ポリシーが割り当てられているユーザーは、その種類の会議を開始またはスケジュールできます。 会議ポリシー設定がオフになっていて、ユーザーに対して再度有効になっている場合、ユーザーが開催したすべての以前にスケジュールされた (有効期限が切れた) 会議はアクティブになり、ユーザーは会議参加リンクまたは電話で参加できます。  

## <a name="meeting-expiration-scenarios"></a>会議の有効期限のシナリオ

この記事で説明する会議ポリシー設定ごとに、会議の有効期限がどのように機能するかの概要を次に示します。

|必要な場合は...&nbsp;&nbsp; |これを行う&nbsp;&nbsp;&nbsp;&nbsp;  |会議参加の動作&nbsp;&nbsp;&nbsp;&nbsp;  |
|---------------------------|---------------------|---------|
|ユーザーが開始した会議の有効期限が切れる&nbsp;&nbsp;|**プライベート会議で今すぐ会議を** オフにします。&nbsp;&nbsp;|ユーザーが開始したプライベート **会議** に誰も参加できません。|
|ユーザーがスケジュールしたプライベート会議の有効期限が切れる&nbsp;&nbsp;|**プライベート会議のスケジュール設定** をオフに _し、_**Outlook アドインを** オフにします。 &nbsp;&nbsp;|ユーザーがスケジュールしたプライベート会議に誰も参加できません。 これにより、ユーザーは次の会議に参加できなくなります。<ul><li>過去に発生したプライベート会議。</li><li>今後予定されており、まだ発生していないプライベート会議。</li><li>定期的なプライベート会議の今後のインスタンス。</li></ul><br>ユーザーが **スケジュールしたプライベート会議** を期限切れにするには、プライベート会議のスケジュール設定と **Outlook アドイン** の両方をオフにする必要があります。 一方の設定がオフになっていて、もう一方がオンになっている場合、既存の会議の会議参加リンクと会議 ID はアクティブなままで、有効期限が切れません。|
|ユーザーが開始した会議を **今すぐ会議** するチャネルを期限切れにする&nbsp;&nbsp;|**チャネルで今すぐ会議を** オフに _し、_**チャネル会議のスケジュール設定を** オフにします。&nbsp;&nbsp;|ユーザーが開始した会議を **今すぐ会議** するチャネルに参加できるユーザーはいません。|
|ユーザーがスケジュールしたチャネル会議の期限切れ&nbsp;&nbsp;|**チャネル会議のスケジュール設定を** オフにします。&nbsp;&nbsp;|ユーザーがスケジュールしたチャネル会議に誰も参加できません。 これにより、ユーザーは次の会議に参加できなくなります。<ul><li>過去に発生したチャネル会議。</li><li>今後予定されており、まだ発生していないチャネル会議。</li><li>定期的なチャネル会議の今後のインスタンス。</li></ul>|

特定のユーザーが以前にスケジュールまたは開始した会議にユーザーがアクセスできるようにする場合は、次のことができます。

- そのユーザーの会議ポリシー設定をオンにします。
- そのユーザーの会議ポリシー設定をオフにし、ポリシー設定が有効になっている別のユーザーが期限切れの会議を置き換える新しい会議を作成します。

> [!NOTE]
> 会議が代理人によって送信された場合(管理者など)、他のユーザーに代わって会議出席依頼を送信するアクセス許可が与えられた場合、会議ポリシー設定は、アクセス許可を付与したユーザー (管理者) に適用されます。

## <a name="changes-to-meeting-expiration"></a>会議の有効期限の変更

新しく作成されたすべての Teams 会議記録 (TMR) の既定の有効期限は 120 日です。 これは、すべてのテナントに対して既定でオンになっています。 つまり、既定では、 *この機能が有効になった後に* 作成されたすべての TMR は、作成日の 120 日後に削除されます。 管理者は、 **会議を自動期限切れにならないように** 設定することもできます。 OneDrive と SharePoint システムは、すべての TMR に設定された有効期限を監視し、有効期限日に TMR をごみ箱に自動的に移動します。

> [!NOTE]
> 会議のトランスクリプトの 1 つのコピーは OneDrive SharePoint に保存され、2 つ目のコピーは Exchange の一時ストレージに保存されます。 OSDP コピーは、TMR の自動有効期限が切れると期限切れになります。

会議の自動有効期限は、以前の TMR によって作成されたストレージの煩雑さを軽減する軽量のハウスキーピング メカニズムです。 平均して、すべての顧客で、TMR の 96% は 60 日後に監視されず、99% は 110 日後に監視されません。 ほぼすべてのお客様が、60 日後に再び視聴されない可能性が高い記録を削除することで、テナントのストレージ負荷の軽減の恩恵を受けると考えています。 既定では、すべてのお客様にできるだけクリーンなエクスペリエンスを提供することが目標です。

会議の有効期限を使用して、Teams 会議レコードによって駆動されるクラウド ストレージの使用に対する OneDrive または SharePoint を制限します。 一般的な会議の記録では、1 時間あたり約 400 MB の記録が消費されます。

> [!NOTE]
> A1 ユーザーの最大既定の有効期限は 30 日です。

### <a name="expiration-date"></a>有効 期限

- 有効期限は、作成 **日** に **加えて、管理者が Teams ポリシーに設定した既定の日数** として計算されます。
- 再生は有効期限に影響しません。

### <a name="change-the-default-expiration-date"></a>既定の有効期限を変更する

管理者は、PowerShell または Teams 管理センターで既定の有効期限設定を編集できます。 すべての変更は、その時点から *新しく作成された* TMR にのみ影響します。 この日付より前に作成された記録には影響しません。 管理者は、既存の TMR の有効期限を変更できません。 これは、TMR を所有するユーザーの決定を保護するために行われます。 この設定では、会議と通話の両方を制御できます。

有効期限の値は、次のように設定できます。

- 最小値: **1 日**
- 最大値: **999999 日**
- また、PowerShell で有効期限を **-1** に設定して、記録が期限切れにならないようにすることもできます。

PowerShell コマンドの例は、以下のとおりです。

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -NewMeetingRecordingExpirationDays 50
```

Teams 管理センターの [**会議ポリシー**] で有効期限を設定できます。 **会議を自動的に有効にすると、** 記録の有効期限を設定するオプションが表示されます。

![会議の有効期限ポリシーの中央のスクリーンショット管理。](media/meeting-expiration-policy.jpg)

### <a name="compliance"></a>コンプライアンス

エンド ユーザーが制御するすべての記録の有効期限を変更できるため、法的保護のために TMR の有効期限設定に依存しないでください。

#### <a name="teams-meeting-recording-expiration-settings-and-microsoft-365-retention-policies-in-microsoft-purview"></a>Microsoft Purview の Teams 会議記録の有効期限設定と Microsoft 365 アイテム保持ポリシー

ファイルの保持期間は、ファイルの削除よりも優先されます。 Purview アイテム保持ポリシーを使用した会議の記録は、保持期間が完了するまで TMR 有効期限ポリシーによって削除できません。 たとえば、ファイルが 5 年間保持され、TMR の有効期限ポリシーが 60 日間設定されるという Purview 借用ポリシーがある場合、TMR 有効期限ポリシーは 5 年後に記録を削除します。  

TMR 有効期限ポリシーと Purview 削除ポリシーに異なる削除日がある場合、ファイルは 2 つの日付の最も早い時点で削除されます。 たとえば、1 年後にファイルが削除され、TMR の有効期限が 120 日間設定されている Purview 削除ポリシーがある場合、TMR の有効期限設定は 120 日後にファイルを削除します。

### <a name="enforcement-of-file-retention-with-the-teams-meeting-recording-expiration-setting"></a>Teams 会議記録の有効期限設定を使用したファイルリテンション期間の適用

この機能またはその設定により、ファイルは保持されません。 削除アクセス許可を持つユーザーが有効期限設定を持つ TMR を削除しようとすると、そのユーザーの削除アクションが実行されます。

### <a name="what-skus-are-required-for-this-feature"></a>この機能に必要な SKU は何ですか?

- すべての SKU にこの機能が既定で搭載されます。
- A1 ユーザーは既定で最大 30 日間の有効期限が設定されますが、必要に応じて有効期限を変更できます。

### <a name="what-if-i-want-the-admin-to-have-full-control-over-the-lifecycle-of-meeting-recordings-and-dont-want-to-give-end-users-the-ability-to-override-the-expiration-date"></a>管理者が会議の記録のライフサイクルを完全に制御し、エンド ユーザーに有効期限をオーバーライドする機能を提供したくない場合はどうなりますか?

セキュリティとコンプライアンスの保持または削除ポリシーを使用することをお勧めします。 このサービスは、複雑なポリシーや SLA 駆動型の管理的な法的問題を解決することを目的としています。

自動有効期限機能は、単に、古い Teams 会議の記録から作成されたストレージの煩雑さを軽減するための軽量のハウスキーピング メカニズムとしてのみ使用されます。

### <a name="will-future-tmrs-migrated-from-classic-stream-after-this-feature-is-released-have-auto-expiration-applied-to-them-too"></a>この機能のリリース後、クラシック ストリームから移行した将来の TMR にも自動失効が適用されますか?

いいえ。移行した TMR には有効期限が設定されません。 その代わりに、管理者には、保持したい TMR のみを移行することをお勧めします。 詳細は移行ドキュメントに記録されます。

### <a name="how-is-this-feature-different-from-the-expiration-message-i-see-when-a-tmr-upload-to-onedrive-and-sharepoint-fails"></a>この機能は、OneDrive と SharePoint への TMR アップロードが失敗したときに表示される有効期限メッセージとどのように異なりますか?

記録が OneDrive または SharePoint にアップロードできない場合、Teams アプリケーションはチャットにメッセージを表示し、ユーザーが TMR をダウンロードしてから Teams サーバーから完全に削除するまでに最大 21 日間かかるというメッセージを表示します。 TMR アップロードの失敗によるこの既存の有効期限エクスペリエンスは、ヘルプ ドキュメントで説明されている OneDrive および SharePoint の自動有効期限機能とは関係ありません。

### <a name="how-do-i-know-the-distribution-of-tmr-playbacks-so-i-know-what-the-optimal-auto-expiration-default-should-be-for-my-tenant"></a>TMR 再生の分布を把握操作方法、テナントに最適な自動有効期限の既定値を把握できますか?

1. ライブラリでビデオを見つけます。
1. **[..] を選択します。** > **詳細**
1. 詳細ウィンドウの上部にあるビューの数を選択します。

次を示すファイル統計が表示されます。

- 一意のビューアーの数
- ビューの合計数
- 過去 90 日間の視聴者とビューの毎日の傾向
- 視聴率の保持 (ビデオのどの部分が表示されたか、表示されなかったか)

### <a name="when-will-the-file-be-deleted"></a>いつファイルを削除しますか?

記録は通常、有効期限の 1 日以内に削除されますが、まれに 5 日間かかる場合があります。 ファイル所有者は、記録の有効期限が切れると電子メール通知を受け取り、記録を回復するためにごみ箱に送られます。

> [!NOTE]
> 有効期限日に、記録がごみ箱に移動され、有効期限フィールドがクリアされます。 ごみ箱から記録を回復した場合、有効期限がクリアされているため、この機能によって再度削除されることはありません。

## <a name="related-topics"></a>関連項目

[会議の有効期限を変更する - エンド ユーザー コントロール](https://support.microsoft.com/office/record-a-meeting-in-teams-34dfbe7f-b07d-4a27-b4c6-de62f1348c24#bkmk_view_change_expiration_date)

[Teams での会議ポリシーを管理する](meeting-policies-overview.md)

[ Teams でユーザーにポリシーを割り当てる](policy-assignment-overview.md)

[Teams での PowerShell の概要](teams-powershell-overview.md)

[Microsoft Teams の制限事項と仕様](/microsoftteams/limits-specifications-teams)
