---
title: Microsoft Teams 保持ポリシーに関するよく寄せられる質問
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: prvijay
audience: admin
description: Microsoft Teams の保持ポリシーに関するよく寄せられる質問です。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9b3d2ed05459c6866c73b0f49b128eea3980605f
ms.sourcegitcommit: 4a22bf77f529cfc2e68a6498a0c4aa9030ee2168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2019
ms.locfileid: "37968308"
---
# <a name="microsoft-teams-retention-policies-faq"></a>Microsoft Teams 保持ポリシーに関するよく寄せられる質問

> [!NOTE]
> プライベートチャネルメッセージの保持の構成はまだサポートしていません。 プライベートチャネルで共有されているファイルの保持はサポートされています。

### <a name="what-types-of-policies-can-i-set-up-in-retention-policies-and-how-do-they-work"></a>保持ポリシーで設定できるポリシーの種類と、それらがどのように機能するのかを教えてください。

セキュリティ/コンプライアンス センターにおいて保持ポリシーを設定する場合、Teams または他のワークロードに対しては、次の 2 つの主な種類のポリシーを設定できます。 
- 保持: このポリシーは、エンド ユーザーのツールにどのような状況が発生しても、指定された期間におけるデータの保持を保証します。 この期間が終了するまで、データはコンプライアンス上の理由により保持され、電子情報開示で利用できることが保証されます。 期間の終了後、ご利用のポリシーで何も操作を行わないか、データを削除するかが示されます。 Teams で、7 年間の保持ポリシーを作成すると、エンド ユーザーがそ自分たちの Teams メッセージを削除しても、それらのメッセージは電子情報開示のために ７ 年間保持されます。
- 削除: このポリシーは、データが自分の組織での責任負担となるものではないことを保証します。 指定の期間後に、データは Teams 内のすべての関連するストレージから削除されます。 

### <a name="can-we-include-teams-in-org-wide-policies"></a>Teams を組織全体のポリシーに含めることはできますか? 

現時点ではできません。 Teams の場所の行または次の Teams のコマンドレットを使用して、Teams のチャットおよびチャネルのメッセージに対する特定のポリシーを作成する必要があります。[New-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps) & [New-TeamsComplianceRetentionRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps) これらのコマンドレットは、バージョンの取得と設定も行います。

### <a name="are-these-retention-policies-retroactive"></a>これらのポリシーはさかのぼって適用されますか? 

はい、適用されます。 60 日より古いデータを削除する保持ポリシーを作成すると、60 日以上前に作成された Teams データが削除されます。 

### <a name="what-is-the-default-retention-policy"></a>既定の保持ポリシーとは何ですか? 

既定では、Teams チャット、チャネル、ファイルのデータは永続的に保持されます。

### <a name="can-i-target-sets-of-users-or-teams-in-a-policy"></a>ユーザーやチームのセットをポリシーの対象にすることはできますか? 

はい、できます。 ポリシー作成ウィザードの [場所] の手順で、チーム (**Teams のチャネル メッセージ**) またはユーザー (**Teams のチャット**) を含めたり除外したりして、自分の組織を対象としたポリシーを作成することができます。 

### <a name="what-is-the-main-difference-between-using-the-group-mailbox-location-row-and-teams-channel-messages-location-row-in-retention-policies"></a>保持ポリシーでグループ メールボックスの場所の行と Teams のチャネル メッセージの場所の行を使用することの主な違いを教えてください? 

Exchange Online のグループ メールボックスとユーザー メールボックスの場所の行を使用すると、Teams のデータは指定されたメールボックスから削除されます。 ただし、この操作ではメールボックスからデータを削除するだけです。 チャット サービスなどのその他の Teams のデータは削除されません。 すべての Teams データを適切に管理するには、Teams の保持ポリシーを使用することをお勧めします。 Teams の保持ポリシーにより、チームのデータは、メールボックス、チャット サービス、Teams のクライアントなどのすべてのストレージ場所から削除されます。 

注: Teams の保持ポリシー機能の導入に伴い、Exchange メールボックスの場所 (ユーザーまたはグループ) 内に格納されている Teams のアイテムを削除するのは Teams のポリシーのみになります。 メールボックスに設定されたその他のポリシーは、Teams のアイテムには影響しません。 この内容は以前は正しかったのですが、保持ポリシー機能の導入により、修正されています。 

### <a name="what-happens-to-skype-for-business-online-and-teams-interop-chats--are-they-affected-by-retention-policies"></a>Skype for Business Online と Teams の相互運用チャットはどのようになっていますか? 保持ポリシーによって影響を受けますか?

はい、Skype for Business Online と Teams の相互運用チャットは同じように機能します。 Skype for Business Online のチャットが Teams に入ると、Teams のチャット スレッドのメッセージとなり、適切なメールボックスに取り込まれます。 このため、Teams の削除ポリシーがそれらのメッセージを Teams のスレッドから削除するという、同じフローが機能します。 ただし、Skype for Business Online に対して会話履歴がオンになっていて、Skype for Business Online のクライアント側からこれらがメールボックスに保存されている場合、このチャット データは Teams の保持ポリシーでは処理されません。

### <a name="can-i-do-these-through-security--compliance-center-cmdlets-what-should-i-use"></a>セキュリティ/コンプライアンス センターのコマンドレットを介してこれらの操作を実行できますか? どのコマンドレットを使用すればよいか教えてください。 

はい、コマンドレットを使用することができます。 [セキュリティ/コンプライアンス センターの Powershell コマンドレット]( https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)を使用して Teams の保持ポリシーを作成することができます。 これらは Exchange Online のコマンドレットではありませんのでご注意ください。 Teams のために作成したコマンドレットを以下に示します。 これらは、現在セキュリティ/コンプライアンス センターで利用可能な保持コマンドレットの既存の命名法と書式に従っています。

|ポリシー|ルール|
|---|---|
|[New-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps)| [New-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps)|
|[Get-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancepolicy?view=exchange-ps)| [Get-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancerule?view=exchange-ps)|
|[Set-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancepolicy?view=exchange-ps)| [Set-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancerule?view=exchange-ps)|
|[Remove-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancepolicy?view=exchange-ps)| [Remove-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancerule?view=exchange-ps)|

### <a name="if-there-are-multiple-retention-policies-for-teams-with-varying-durations-which-one-wins"></a>Teams で期間が異なる複数の保持ポリシーがある場合に、どのポリシーが優先されるかを教えてください。

「[保持ポリシーの原則](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)」に従います。お客様もそれに従うことをお勧めします。 簡単に答えると、次のようになります。 
-   保持が常に削除よりも優先されます
-   最長の保持期間が常に優先されます
-   場所に関しては、明示的な包含が暗黙的な包含より優先されます
-   最短の削除期間が優先されます
