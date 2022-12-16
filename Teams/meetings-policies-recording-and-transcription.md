---
title: 記録と文字起こしの会議ポリシーを管理する
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.recordingandtranscription
description: 記録と文字起こしのために Teams で会議ポリシー設定を管理する方法について説明します。
ms.openlocfilehash: 06a05d2eb8a8c1542b79fa4c37b68ea4a3aa6d32
ms.sourcegitcommit: 00a526c5b9829302f7c4e0631d0c2dac50b7d004
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/16/2022
ms.locfileid: "69436763"
---
# <a name="meeting-policy-settings-for-recording--transcription"></a>&文字起こしを記録するための会議ポリシー設定

この記事では、Teams 会議での記録と文字起こしに固有の会議ポリシー設定について説明します。 これらの設定は、チーム管理センターの **[会議会議** > ポリシー] の下 **にあります**。

## <a name="transcription"></a>転写

これは、開催者単位とユーザーごとのポリシーの組み合わせです。 この設定は、会議の記録の再生中にキャプションと文字起こし機能を使用できるかどうかを制御します。 記録を開始したユーザーは、これらの機能で記録を操作できるようにするため、この設定を有効にする必要があります。

この設定をオンにすると、会議記録に保存されているトランスクリプトのコピーが作成されます。これにより、会議記録で **検索**、**CC**、および **トランスクリプト** を実行できるようになります。

## <a name="cloud-recording"></a>クラウド記録

この設定は、開催者ごとのポリシーとユーザーごとのポリシーの組み合わせであり、会議を記録できるかどうかを制御します。 参加者のポリシー設定が有効になっており、同じ組織の認証済みユーザーである場合、会議の開催者または別の会議参加者が記録を開始できます。

フェデレーション ユーザーや匿名ユーザーなど、組織外のユーザーは記録を開始できません。 ゲストは録音を開始または停止できません。

![記録オプションが表示されたスクリーンショット](media/meeting-policies-recording.png)

次の例を見てみましょう。

| ユーザー                 | 会議ポリシー         | クラウド記録を許可する |
|----------------------|------------------------|-----------------------|
| Daniela              | グローバル                 | オフ                   |
| Amanda               | Location1MeetingPolicy | オン                    |
| John (外部) | 該当なし         | 該当なし        |

- Daniela が開催した会議は記録できません。
- アマンダは、Daniela が主催する会議を記録できません。
- Amanda が主催する会議を記録できます。
- Daniela は、Amanda が開催した会議を記録できません。
- ジョンはアマンダが主催する会議を記録できない。

クラウド会議の記録の詳細については、「[Teams のクラウド会議の記録](cloud-recording.md)」を参照してください。

## <a name="meetings-automatically-expire"></a>会議の有効期限が自動的に切れる

この設定は、会議の記録が自動的に期限切れになるかどうかを制御します。 この設定をオンにすると、既定の有効期限を日数で設定するオプションが表示されます。

:::image type="content" source="media/meeting-expiration-policy.jpg" alt-text="自動会議の有効期限設定の Teams 管理センターのスクリーンショット。":::

この設定では、古い録音で使用されるストレージの量を減らす簡単なツールが提供されます。 OneDrive と SharePoint システムは、すべての会議記録の有効期限セットを監視し、有効期限日に記録をごみ箱に自動的に移動します。

### <a name="default-expiration-time"></a>既定の有効期限

新しく作成されたすべての会議録画の既定の有効期限は 120 日です。この機能を有効にした後に作成されたすべての録音は、作成日から 120 日後に削除されます。

> [!NOTE]
> A1 ユーザーの既定の最大有効期限は 30 日です。

#### <a name="changing-default-expiration-time"></a>既定の有効期限の変更

管理者は、PowerShell または Teams 管理センターで [既定の有効期限] 設定を編集できます。 変更は、その時点から新しく作成された会議の記録にのみ影響します。その日付より前に作成された録音には影響しません。

管理者は、既存の会議の記録の有効期限を変更できません。 これは、記録を所有するユーザーの決定を保護するために行われます。 会議と通話の両方をこの設定で制御できます。

有効期限の値は、日数の整数です。  これは次のように設定できます。

- 最小値: **1**
- 最大値: **99999**
- PowerShell で有効期限を **-1** に設定して、記録の有効期限が切れないようにすることもできます。

PowerShell コマンドの例は、以下のとおりです。

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -NewMeetingRecordingExpirationDays 50
```

### <a name="compliance"></a>コンプライアンス

エンド ユーザーは制御するすべての録音の有効期限を変更できるため、法的保護のために会議の有効期限設定に依存しないでください。

#### <a name="recording-expiration-settings-and-microsoft-365-retention-policies-in-microsoft-purview"></a>Microsoft Purview で有効期限の設定とMicrosoft 365 の保持ポリシーを記録する

ファイルの保持は、ファイルの削除よりも優先されます。 Purview アイテム保持ポリシーを使用した Teams 会議の記録は、保持期間が完了するまで、Teams 会議記録の有効期限ポリシーによって削除できません。 たとえば、ファイルが 5 年間保持され、Teams 会議記録の有効期限ポリシーが 60 日間設定されていることを示す Purview アイテム保持ポリシーがある場合、Teams 会議記録の有効期限ポリシーは 5 年後に記録を完全に削除します。

削除日が異なる Teams 会議記録の有効期限ポリシーと Purview 削除ポリシーがある場合、ファイルは 2 つの日付の早い時点で削除されます。 たとえば、1 年後にファイルが削除され、Teams 会議記録の有効期限が 120 日間に設定されていることを示す Purview 削除ポリシーがある場合、Teams 会議記録の有効期限ポリシーは 120 日後にファイルを削除します。

ユーザーは、有効期限の前に記録を手動で削除できます。ただし、それを妨げる Purview アイテム保持ポリシーがない限りです。 保持期間内の記録がユーザーによって手動で削除された場合、記録は保持保持ライブラリに保持されます。 ただし、記録はエンド ユーザーに対して削除済みとして表示されます。 詳細については、「 [SharePoint と OneDrive の保持について」を](/microsoft-365/compliance/retention-policies-sharepoint#how-retention-works-for-sharepoint-and-onedrive)参照してください。

### <a name="deletion-of-recordings"></a>記録の削除

通常、記録は有効期限から 1 日以内に削除されますが、まれに 5 日ほどかかる場合があります。 ファイル所有者は、記録の有効期限が切れると電子メール通知を受け取り、記録を回復するためにごみ箱に送られます。

> [!NOTE]
> 有効期限日に、記録がごみ箱に移動され、有効期限フィールドがクリアされます。 ごみ箱から記録を回復した場合、有効期限がクリアされているため、この機能によって再び削除されることはありません。

### <a name="expiration-of-migrated-recordings-from-stream-classic"></a>Stream (クラシック)から移行された記録の有効期限

Stream (クラシック)から移行された録音には有効期限が設定されません。 代わりに、管理者は保持するレコーディングのみを移行することをお勧めします。 詳細については、[Stream (クラシック)移行に関するドキュメントを参照してください](/stream/streamnew/stream-classic-to-new-migration-overview)。

## <a name="store-recordings-outside-of-your-country-or-region"></a>国または地域以外の録音を保存する

このポリシーは、会議レコードを別の国または地域に永続的に保存できるかどうかを制御します。 有効になっている場合、記録を移行できません。 クラウド会議と記録の保存場所の詳細については、「 [Teams クラウド会議の記録](cloud-recording.md)」を参照してください。

## <a name="related-topics"></a>関連項目

- [Teams での会議ポリシーを管理する](meeting-policies-overview.md)
- [Teams のユーザーにポリシーを割り当てる](policy-assignment-overview.md)
- [クラウド会議の記録](cloud-recording.md)
- [会議をスケジュールできるユーザーを管理する](manage-who-can-schedule-meetings.md)
