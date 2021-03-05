---
title: Microsoft Teams のアイテム保持ポリシーを管理する
author: cabailey
ms.author: cabailey
ms.reviewer:
- anwara
- prvijay
manager: laurawi
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Microsoft Teams のアイテム保持ポリシーを使用して、内部ポリシー、業界の規制、または法的なニーズに準拠するために必要なメッセージを保持し、責任と見なされたメッセージまたは法的なビジネス価値がないメッセージを削除します。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9422fd2b47ac3d460ee10e8933c45964d78282c1
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460657"
---
# <a name="manage-retention-policies-for-microsoft-teams"></a>Microsoft Teams のアイテム保持ポリシーを管理する

> [!NOTE]
> アイテム保持ポリシーによってチャットまたはメッセージが削除されたというメッセージが Teams に表示される場合は、アイテム保持ポリシーに関する Teams メッセージ [を参照してください](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)。
> 
> このページの情報は、これらのアイテム保持ポリシーを管理する IT 管理者向けです。

Microsoft 365 のアイテム保持ポリシーと保持ラベルは、組織内の情報を効果的に管理するのに役立ちます。 保持設定を構成して、組織の内部ポリシー、業界の規制、または法的なニーズに準拠するために必要なデータを保持できます。 また、責任と見なされるデータ、保持する必要がなくなったデータ、法的価値またはビジネス価値がないデータを削除する保持設定を構成することもできます。

Teams はチャットおよびチャネル メッセージのアイテム保持ポリシーをサポートし、管理者は、このデータを保持するか、削除するか、特定の期間保持してから削除するかどうかを積極的に決定できます。 Teams のアイテム保持ポリシーは、組織全体に適用することも、特定のユーザーやチームに適用することもできます。 保持ラベルは、Teams ではサポートされていません。

Microsoft 365 で他のワークロードのアイテム保持ポリシーまたはアイテム保持ラベルを使用して保持設定を適用する方法の詳細については、「アイテム[](https://docs.microsoft.com/microsoft-365/compliance/retention)保持ポリシーとアイテム保持ラベルについて」を参照してください。

Teams のアイテム保持ポリシーの最小ライセンス要件は、Microsoft 365 E3 です。 Teams のライセンスの詳細については、「[Microsoft Teams サービスのサービスの説明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)」を参照してください。

## <a name="how-teams-retentiondeletion-policies-work"></a>Teams のアイテム保持/削除ポリシーの動作

Teams チャット メッセージは 2 つの場所に保存されます。 プライマリ コピーは Azure に保存され、コンパイル ポリシーに使用されるセカンダリ コピーは、チャットに含まれる各ユーザーの Exchange オンライン メールボックスの非表示フォルダーに保存され、Teams チャネル メッセージはチームのグループ メールボックス内の同様の非表示フォルダーに保存されます。 ユーザーまたはチームにチャット メッセージ削除ポリシーを適用すると、最初にセカンダリ コピーが削除され、その後にプライマリ コピーが削除されます。 電子情報開示または Teams の検索は、セカンダリ コピーに保存されているメッセージに基づくため、セカンダリ コピーが削除された場合、メッセージは検出できません。 

チャット メッセージの保持ポアシーがユーザーまたはチームに適用されている場合、およびメッセージが削除された場合 (別の削除ポリシーまたはユーザー自身が削除された場合)、プライマリ コピーが削除されると、Teams クライアントはメッセージが消えますが、セカンダリ コピーは自動的に、Exchange の回復可能なアイテム フォルダーのサブフォルダーである **、SubfolderHolds** という名前の非表示のフォルダーに移動されます。  これらのメッセージが、電子情報開示ツールで検索可能なままになるまで、そのメッセージは、電子情報開示ツールで検索可能なままです。

Teams アイテム保持ポリシーに含まれる内容と除外される内容、およびポリシーの構成に応じてこれらのポリシーがどのように動作するのかの詳細については [、「Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)の保持について」を参照してください。

> [!NOTE]
> このページでは、アイテム保持ポリシーでメッセージを削除するときに遅延が発生する場合がある理由について説明します。 たとえば、メッセージは、アイテム保持ポリシーで構成した有効期限の 7 日後まで表示できます。

異なる保持設定で複数の Teams アイテム保持ポリシーを設定した場合、保持の原則は競合を解決します。 次に例を示します。
- 同じコンテンツの保持と削除の間に競合がある場合、コンテンツは常に保持されます。
- 同じコンテンツを保持する期間に競合がある場合、最長の保持期間は保持されます。

これら 2 つの保持原則は、Teams に複数のアイテム保持ポリシーがある場合に発生する可能性のあるほとんどの競合に対処しますが、詳細については、「保持の原則」または「優先されるルール」を参照してください [。](https://docs.microsoft.com/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)

## <a name="when-to-use-retention-policies-for-teams"></a>Teams のアイテム保持ポリシーを使用すべき状況

組織は多くの場合、プライベート チャットのデータの方が、一般にプロジェクトとの関連性がより高い会話であるチャネル メッセージよりも負債になりやすいものとみなします。

管理者は、プライベート チャット (1 対 1 または 1 対多数チャット) のアイテム保持ポリシーとチャネル メッセージのアイテム保持ポリシーを別個に設定できます。 さらに、組織内の特定のユーザーやチームに適用される固有のポリシーを構成することもできます。 Teams のチャットの場合、ポリシーが適用されるユーザーを選択できます。 Teams のチャネル メッセージの場合は、ポリシーが適用されるチームを選択できます。

たとえば、チャネル メッセージの場合、組織内の特定のチームには 1 年間の削除ポリシーを適用し、その他のすべてのチームには 3 年間の削除ポリシーを適用することができます。

## <a name="create-and-manage-retention-policies-for-teams"></a>Teams のアイテム保持ポリシーを作成および管理する

Teams チャットおよびチャネル メッセージのアイテム保持ポリシーを作成するには、Teams の場所のアイテム保持 [ポリシーの手順を使用します](https://docs.microsoft.com/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations)。

このページには、Microsoft 365 の他のワークロードのアイテム保持ポリシーの作成と管理に関する追加情報があります。 たとえば、Microsoft 365 グループのアイテム保持ポリシーを作成して、Teams にアクセスし、OneDrive または SharePoint に保存されているファイルを保持および削除することもできます。  

## <a name="end-user-experience"></a>エンド ユーザーのエクスペリエンス

プライベート チャット (1 対 1 のチャット) またはグループ チャットの場合、ユーザーには、アイテム保持ポリシーの構成よりも古いチャットが削除され、まだ削除されていないメッセージの上に "組織のアイテム保持ポリシーにより古いメッセージが削除されました" というメッセージが自動的に生成されます。 次に例を示します。

:::image type="content" source="media/retention-policies-image1.png" alt-text="Teams のアイテム保持ポリシーのためにチャット メッセージが削除されたという通知を受け取ったユーザー":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="Teams アイテム保持ポリシーの結果としてメッセージが削除されたと説明する Teams のユーザー":::

チャネル メッセージの場合、ユーザー (チャネル メンバー) は、メッセージの有効期限が切れると、削除されたメッセージがビューから消えます。 削除されたメッセージがスレッド会話の親メッセージであった場合、親メッセージの代わりに "アイテム保持ポリシーに従い、このメッセージは削除されました。" というメッセージが表示されます。 次に例を示します。

:::image type="content" source="media/retention-policies-image3.png" alt-text="保持前のチャネルのスクリーンショット":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="保持後のチャネルのスクリーンショット":::

> [!NOTE]
> 削除されたメッセージの結果としてユーザーに表示されるメッセージは、現時点では構成できません。

表示されるメッセージ内のリンクは、 [アイテム保持ポリシーに関する Teams メッセージに移動します](https://support.microsoft.com/en-us/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)。 エンド ユーザー向けこのドキュメントは、メッセージが削除された理由に関する基本的な質問に答えるのに役立ちます。 ただし、アイテム保持ポリシーの展開の一環として、設定した設定の影響をユーザーとヘルプ デスクに伝えます。

## <a name="related-topics"></a>関連トピック

- [アイテム保持ポリシーとアイテム保持ラベルの使用を開始する](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-retention)
- [Microsoft Teams の保持について](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)
- [アイテム保持ポリシーを作成および構成する](https://docs.microsoft.com/microsoft-365/compliance/create-retention-policies)
