---
title: Microsoft Teams 保持ポリシーに関するよくある質問
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: prvijay
audience: admin
description: Microsoft Teams のアイテム保持ポリシーについてよく寄せられる質問。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a0eb556f53c617636f9169dbf0358455860c46b6
ms.sourcegitcommit: 6b73b89f29a0eabbd9cdedf995d5325291594bac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2019
ms.locfileid: "37018792"
---
# <a name="microsoft-teams-retention-policies-faq"></a>Microsoft Teams 保持ポリシーに関するよくある質問

### <a name="what-types-of-policies-can-i-set-up-in-retention-policies-and-how-do-they-work"></a>アイテム保持ポリシーでセットアップできるポリシーの種類とその機能について

セキュリティ & のコンプライアンスセンターでは、アイテム保持ポリシーを設定するときに、Teams またはその他のワークロードについて、次の2種類のポリシーを設定できます。 
- 保持: これらのポリシーによって、エンドユーザーツールで行われる処理に関係なく、一定の期間、データは保持されます。 これにより、コンプライアンス上の理由でデータが保護され、この時間が経過するまで eDiscovery で利用できるようになります。 有効期限が切れると、何も行わないか、データを削除するかをポリシーで指定できます。 Teams では、保持ポリシーを7年にわたって作成した場合でも、エンドユーザーがそのチームのメッセージを削除した場合でも、これらのメッセージは7年の電子情報開示のために保持されたままになります。
- 削除: これらのポリシーにより、データは組織の責任を負わないものとします。 指定した期間が経過すると、チーム内のすべての関連ストレージからデータが削除されます。 

### <a name="can-we-include-teams-in-org-wide-policies"></a>チームを組織全体のポリシーに含めることはできますか? 

いいえ、現在はサポートされていません。 Teams の位置情報行または次のチームコマンドレットを使用して、チームチャットとチャネルメッセージ用の特定のポリシーを作成する必要があります。 [TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps) & の[新規 TeamsComplianceRetentionRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps)。 これらのコマンドレットには、バージョンの取得と設定も含まれています。

### <a name="are-these-retention-policies-retroactive"></a>これらのアイテム保持ポリシーは遡及的なですか? 

はい、です。 60日より前のデータを削除するアイテム保持ポリシーを作成すると、60日以上前に作成された Teams データが削除されます。 

### <a name="what-is-the-default-retention-policy"></a>既定のアイテム保持ポリシーとは 

既定では、Teams のチャット、チャネル、ファイルのデータは永久に保持されます。 ユーザーは何かを削除することはできますが、アイテム保持ポリシーがない場合は、チームデータは常に Exchange online のメールボックス (ユーザーとグループ) にアーカイブされ、電子情報開示のために残ります。 

### <a name="can-i-target-sets-of-users-or-teams-in-a-policy"></a>ポリシーでユーザーまたはチームのセットをターゲットにすることはできますか? 

はい。 ポリシーの作成ウィザードの [場所] ステップでは、チーム (チーム**チャネルメッセージ**) またはユーザー (**チームチャット**) を含めたり除外したりすることができます。また、組織の対象ポリシーを作成することもできます。 

### <a name="what-is-the-main-difference-between-using-the-group-mailbox-location-row-and-teams-channel-messages-location-row-in-retention-policies"></a>アイテム保持ポリシーの [グループメールボックスの場所] 行と [チームチャネルメッセージの場所] 行を使用する主な違いは何ですか。 

Exchange Online のグループメールボックスとユーザーのメールボックスの場所の行を使用すると、チームのデータは指定したメールボックスから削除されます。 ただし、この方法ではメールボックスからデータが削除されるだけです。 他の Teams データ (チャットサービスなど) は削除されません。 チームのアイテム保持ポリシーを使用して、すべてのチームデータを適切に管理することをお勧めします。 チームアイテム保持ポリシーは、すべてのストレージの場所から teams データ (メールボックス、チャットサービス、チームクライアント) を削除します。 

注: Teams のアイテム保持ポリシー機能を起動すると、Exchange メールボックスの場所 (ユーザーまたはグループ) 内に保存されている Teams アイテムが、Teams のポリシーだけで削除されます。 メールボックスに設定されている他のポリシーは、Teams のアイテムには影響しません。 これは過去にも当てはまりましたが、アイテム保持ポリシー機能の起動によって修正されました。 

### <a name="what-happens-to-skype-for-business-online-and-teams-interop-chats--are-they-affected-by-retention-policies"></a>Skype for Business Online と Teams の相互運用機能のチャットはどうなりますか。アイテム保持ポリシーが影響を受けていますか?

はい。 Skype for Business Online と Teams の相互運用機能のチャットは、同じように動作します。 Skype for Business Online のチャットが Teams に届くと、Teams チャットスレッド内のメッセージとなり、適切なメールボックスに毎回が表示されます。 同じフローが機能すると、チームの削除ポリシーによって、これらのメッセージが Teams のスレッドから削除されます。 ただし、Skype for Business Online と skype for Business Online クライアント側からメールボックスに保存されている会話履歴が有効になっている場合は、このチャットデータは Teams のアイテム保持ポリシーによって処理されません。

### <a name="can-i-do-these-through-security--compliance-center-cmdlets-what-should-i-use"></a>セキュリティ & コンプライアンスセンターのコマンドレットを使用して行うことはできますか? 何を使用したらよいですか? 

そうですよ。 [セキュリティ & コンプライアンスセンターの Powershell コマンドレット]( https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)を使用して、チームのアイテム保持ポリシーを作成できます。 これらは Exchange Online のコマンドレットではないことに注意してください。 Teams 用に作成したコマンドレットを次に示します。 セキュリティ & コンプライアンスセンターで現在利用可能な保持コマンドレットには、既存の用語とスタイルが適用されます。

|ポリシー|ルール|
|---|---|
|[新規-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps)| [新規-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps)|
|[Get-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancepolicy?view=exchange-ps)| [Get-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancerule?view=exchange-ps)|
|[Set-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancepolicy?view=exchange-ps)| [Set-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancerule?view=exchange-ps)|
|[Remove-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancepolicy?view=exchange-ps)| [Remove-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancerule?view=exchange-ps)|

### <a name="if-there-are-multiple-retention-policies-for-teams-with-varying-durations-which-one-wins"></a>異なる期間を持つ Teams の複数のアイテム保持ポリシーがある場合、それは1つの wins ですか?

ここでは、[アイテム保持ポリシーの原則](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)に従っていますが、これを行うことをお勧めします。 簡単な答えは次のとおりです。 
-   常に wins 経由での保存が削除
-   最長保持期間は常に wins
-   場所に関する暗黙的な追加による明示的な追加の wins
-   最短の削除期間 wins
