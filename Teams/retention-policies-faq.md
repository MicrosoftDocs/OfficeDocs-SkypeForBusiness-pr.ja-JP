---
title: Microsoft Teams 保持ポリシーに関するよくある質問
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: anach
description: マイクロソフトのチームでのリテンション ・ ポリシーについてよく寄せられる質問です。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 14e398908a13e621d739a5a923b52588551506f8
ms.sourcegitcommit: 3014331fff89a0842c4db0b9adf0ef32f9728ade
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2019
ms.locfileid: "30641336"
---
# <a name="microsoft-teams-retention-policies-faq"></a>Microsoft Teams 保持ポリシーに関するよくある質問

### <a name="what-types-of-policies-can-i-set-up-in-retention-policies-and-how-do-they-work"></a>どのような種類のポリシーを設定すればよいのリテンション ・ ポリシーとどのように動作するでしょうか。

セキュリティ & コンプライアンス センターでは、[セットアップするときに、保持ポリシー、またはその他のワークロードでは、チームの 2 つの主な種類のポリシーを設定できます。 
- 保存: これらのポリシーでは、エンド ユーザー ツールで何が起きても、時間の特定の期間のデータが保持されることを確認します。 これらは、コンプライアンス上の理由からデータが保存され、この時点までには、電子的証拠開示に利用可能な有効期限が切れることを確認します。 時間を経過した後、ポリシーは何もしない、またはデータを削除するかどうかを指定できます。 チームでエンド ・ ユーザー、チームのメッセージを削除する場合でも、7 年間、保持ポリシーを作成する場合これらのメッセージは保持されます電子的証拠開示の 7 年間。
- 削除: これらのポリシーでは、データが組織の負債ではないことを確認します。 、指定した期間の後は、チームに関連するすべての記憶域からデータが削除されます。 

### <a name="can-we-include-teams-in-org-wide-policies"></a>チームを組織全体のポリシーは含めることができますか。 

いいえ、されていません。 チームの場所の行またはチームのこれらのコマンドレットを使用して、チームのチャットおよびチャネルのメッセージの特定のポリシーを作成する必要があります:[新しい TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps) & [新規 TeamsComplianceRetentionRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps)。 これらのコマンドレットでは、get し、同様のバージョンを設定します。

### <a name="are-these-retention-policies-retroactive"></a>これらのアイテム保持ポリシーは、さかのぼって適用しますか。 

います。 60 日よりも古いデータを削除する保持ポリシーを作成する場合は、60 日以上前に作成したチームのデータが削除されます。 

### <a name="what-is-the-default-retention-policy"></a>デフォルトの保存ポリシーとは何ですか。 

既定では、チーム チャット、チャネル、およびファイルのデータは永久保持します。 ユーザーは、何かを削除できますが、リテンション ・ ポリシーがない場合は、チームのデータ (ユーザーおよびグループ) は、Exchange オンライン メールボックスにアーカイブが常に、電子的証拠開示のないままです。 

### <a name="can-i-target-sets-of-users-or-teams-in-a-policy"></a>ユーザーまたはチームのポリシーのセットを対象することができますか。 

はい、次のように実行します。 ポリシーの作成ウィザードのステップでは、場所では、または (**チームは、メッセージをチャネル**) のチームまたはユーザー (**チーム チャット**) を除外して組織の対象となるポリシーを作成できます。 

### <a name="what-is-the-main-difference-between-using-the-group-mailbox-location-row-and-teams-channel-messages-location-row-in-retention-policies"></a>グループのメールボックスの場所の行とチームのチャネルのメッセージの場所の行を使用して、リテンション ・ ポリシーでの主な違いは何ですか。 

Exchange Online のメールボックスのグループとユーザーのメールボックスの場所の行を使用する場合、チームのデータが指定されたメールボックスから削除されます。 ただし、メールボックスからこの、だけデータを削除します。 チャット サービスなど、他のチームのデータは、削除されません。 チーム ・ リテンション ・ ポリシーを使用して、チームのすべてのデータを適切に管理することをお勧めします。 チーム ・ リテンション ・ ポリシーは、すべてストレージの場所: メールボックス、チャット サービス、チーム クライアントからチームのデータを削除します。 

注: チームは、保持ポリシーの機能の起動、唯一のチーム ポリシーが Exchange メールボックスの場所 (ユーザーまたはグループ) 内に格納されているチームの項目を削除します。 メールボックスでは、他のポリシー設定は、チームのアイテムに適用できません。 これまでは、true ですが保持ポリシーの機能の起動が修正されています。 

### <a name="what-happens-to-skype-for-business-online-and-teams-interop-chats--are-they-affected-by-retention-policies"></a>どうなる Skype ビジネス オンラインでチームの相互運用機能チャット – のリテンション ・ ポリシーによって影響をあるか

はい、オンライン ビジネスとチームの相互運用機能のチャットの Skype 同様に動作します。 ビジネス オンライン チャットの Skype は、チームには、そのチーム チャットのスレッド内のメッセージとなり、取得、適切なメールボックスに取り込まれ。 動作: を同じフロー、チームの削除ポリシーはチームのスレッドからこれらのメッセージを削除します。 ただし、会話の履歴がオンになって Skype のオンライン ビジネスの場合は、オンライン ビジネスのクライアント側の Skype からそれらを保存しているメールボックスにこのチャットのデータはチーム ・ リテンション ・ ポリシーによって処理されません。

### <a name="can-i-do-these-through-security--compliance-center-cmdlets-what-should-i-use"></a>どうすればこれらのセキュリティ & コンプライアンス センター コマンドレットを使用しますか。 どう使用する必要がありますか。 

そうですよ。 [セキュリティ & コンプライアンス センターの Powershell コマンドレット]( https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)を使用してチーム ・ リテンション ・ ポリシーを作成できます。 オンライン Exchange コマンドレットがないことを覚えておいてください。 ここでは、コマンドレットのチームを作成しました。 従うセキュリティ & コンプライアンス センターで現在利用可能な保存管理機能のコマンドレットから既存の用語とスタイルです。

|ポリシー|ルール|
|---|---|
|[新しい-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps)| [新しい-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps)|
|[Get TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancepolicy?view=exchange-ps)| [Get TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancerule?view=exchange-ps)|
|[セット TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancepolicy?view=exchange-ps)| [セット TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancerule?view=exchange-ps)|
|[削除 TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancepolicy?view=exchange-ps)| [削除 TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancerule?view=exchange-ps)|

### <a name="if-there-are-multiple-retention-policies-for-teams-with-varying-durations-which-one-wins"></a>チームのさまざまな期間、どちらかを wins での複数の保存ポリシーがある場合ですか。

[リテンション ・ ポリシーの原則](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)に従ってし、も実行することをお勧めします。 短い答えは次のとおりです。 
-   削除を優先、常に情報を保持
-   最長の保存期間を常に優先します。
-   明示的なインクルードが場所で暗黙の信頼を優先します。
-   最短の削除期間 wins
