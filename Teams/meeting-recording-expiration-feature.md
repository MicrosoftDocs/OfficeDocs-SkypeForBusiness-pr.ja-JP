---
title: 会議のレコーディングの有効期限機能
author: cichur
ms.author: v-cichur
ms.reviewer: ''
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: 会議のレコーディングの有効期限機能については、Microsoft Teams。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cfbbc8602044c0429de414b94b88d0e0e5aa8b19
ms.sourcegitcommit: 11a803d569a57410e7e648f53b28df80a53337b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2021
ms.locfileid: "60889527"
---
# <a name="meeting-recording-expiration-feature---frequently-asked-questions"></a>会議のレコーディングの有効期限機能 - よく寄せられる質問

**変更とは?**

新しく作成された会議記録 (TMRs) に対して、既定の 60 日間Teams設定が導入されています。 これはすべてのテナントで既定でオンになっています。この機能が必要ない場合はオフにする必要があります。 OneDriveおよびSharePointシステムは、すべての TMRs で設定された有効期限を監視し、その有効期限に自動的に TMRs をごみ箱に移動します。

**この変更を導入する理由は何ですか?**

会議記録の有効期限機能に関するご要望にお答えしました。 これは、コールド TMR から作成されたストレージの低優先メールを軽減する軽量の家事処理メカニズムです。 平均すると、60 日後に 99% の TMRs が再表示されません。

**既定でオンになっている理由は何ですか?**

60 日後に再び視聴される可能性がほとんどない記録を削除することで、テナントのストレージ負荷が軽減されることは、ほぼすべてのお客様にとってメリットになります。 既定では、すべてのお客様に可能な限りクリーンなエクスペリエンスを提供することです。

**有効期限日はどのように計算しますか?**

有効期限は、作成日に加えて、管理者がポリシーに設定した既定の日数Teams計算されます。

**管理者が有効期限を変更する方法**

管理者は、ポリシー コンソールで既定の有効期限Teams編集できます。 この変更は、その時点から新しく作成された TMRs にのみ影響します。 その日付より前のレコーディングには影響を与えはありません。

管理者は、既存の TMRs の有効期限を変更できない。 これは、TMR を所有するユーザーの決定を保護するために行われます。

**これはだれに影響しますか?**

TMRs をOneDriveまたはSharePoint。

**この機能はどのように使用しますか?**

この機能は既定で有効になっています。 無効にするには、ポリシー コンソールの既定の有効期限Teams を [有効期限なし]**に変更します**。
これを使用して、会議レコードによってOneDriveクラウド ストレージの使用量を制限Teams必要があります。 一般的な会議記録では、1 時間あたり約 400 MB の記録が消費されます。

**セキュリティとコンプライアンスの厳格な準拠のために、この機能に依存する必要がありますか?**

いいえ。エンド ユーザーが制御する記録の有効期限を変更できるので、法的保護のためにこれを利用してはならない。

**Security & コンプライアンス センターで設定したアイテム保持ポリシーや削除ポリシーは、会議Teamsの有効期限設定を上書きしますか?**

はい。コンプライアンス センターで設定したポリシーが完全に優先されます。

次に例を示します。

- サイト内のすべてのファイルを 100 日間保持し、Teams 会議の記録の有効期限設定が 30 日間であるポリシーがある場合、記録は 100 日間保持されます。
- Teams 会議のすべての記録が 5 日後に削除され、Teams 会議記録の有効期限設定が 30 日後に設定されている削除ポリシーがある場合、記録は 5 日後に削除されます。

**TMR の有効期限が切れるとどうなるでしょうか。**

有効期限の日付に、記録がごみ箱に移動され、[有効期限] フィールドがオフになります。 ごみ箱から記録を回復した場合、有効期限がクリアされたため、この機能によって再び削除されません。

**ファイルの有効期限の通知はどのように行われますか?**

- すべてのユーザーに、有効期限に関する通知が[チャット] ウィンドウの記録チェックリストTeams表示されます。
- 閲覧権限のあるすべてのユーザーは、ファイルの有効期限切れ 14 日前になると、OneDrive や SharePoint のフォルダ内のファイルの横に赤いアイコンが表示されます。
- 記録の有効期限が切れると、ファイル所有者は電子メール通知を受け取り、記録を回復するためにごみ箱に移動されます。

**この機能に必要な SKU は何ですか?**

- すべての SKU にこの機能が既定で搭載されます。

- すべてのユーザーは既定で 30 日間の有効期限に設定され、有効期限を変更する必要はありません。

**ファイルの失効は監査イベントになり、監査ログに記録されますか?**

はい。これらは監査ログにシステム削除イベントとして表示されます。

**管理者が会議の記録のライフサイクルを完全に制御し、エンド ユーザーに有効期限を上書きする機能を与えたくない場合は、どうしますか。**

E5 コンプライアンス SKU の一部として使用できるセキュリティおよびコンプライアンスの保持ポリシーまたは削除ポリシーを使用することをお勧めします。 このサービスは、複雑なポリシーや SLA 駆動型の管理的な法的問題を解決することを目的としています。

この機能は、コールド セッションや会議の記録から作成されたストレージの低Teams専用です。

**いつファイルを削除しますか?**

ファイルは有効期限から 5 日以内に削除されます。しかし、これは厳密な保証ではありません。