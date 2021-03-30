---
title: Teams のアイテム保持ポリシーを管理する
author: cabailey
ms.author: cabailey
ms.reviewer:
- anwara
- prvijay
manager: laurawi
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Microsoft Teams のアイテム保持ポリシーを使用して、内部ポリシー、業界の規制、または法的要件に準拠するために必要なメッセージを保持し、責任と見なされたメッセージまたは法的なビジネス価値がないメッセージを削除します。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 748106de5ed7e2f0147a182716ca8bce1571b82f
ms.sourcegitcommit: 6505dd1fb891ab27fcc9f36423fda67aae6fcfd7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/30/2021
ms.locfileid: "51418815"
---
# <a name="manage-retention-policies-for-microsoft-teams"></a>Teams のアイテム保持ポリシーを管理する

> [!NOTE]
> チャットまたはメッセージがアイテム保持ポリシーによって削除されたというメッセージが Teams に表示されている場合は、「[アイテム保持ポリシーに関する Teams メッセージ](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)」を参照してください。
> 
> このページの情報は、これらのアイテム保持ポリシーを管理する IT 管理者向けです。

Microsoft 365 のアイテム保持ポリシーと保持ラベルは、組織内の情報をより効果的に管理するのに役立ちます。 保持設定を構成して、組織の内部ポリシー、業界の規制、または法的要件に準拠するために必要なデータを保持できます。 保持設定を構成して、責任があると見なされたデータ、保持する必要がなくなったデータ、または法的価値やビジネス価値のないデータを削除するためにも使用されます。

Teams では、チャットやチャネルのメッセージ用にアイテム保持ポリシーを設定するサポートを行い、管理者としてデータを保持するか、削除するか、特定の期間保持した後に削除するかを前もって決定できます。 これらのアクションの保持期間の開始は、常にメッセージの作成日に基づいて行います。 Teams のアイテム保持ポリシーは、組織全体に適用することも、特定のユーザーやチームに適用することもできます。 保持ラベルは、Teams ではサポートされていません。

保持についての詳細や、Microsoft 365 の他のワークロードにアイテム保持ポリシーや保持ラベルを使用して保持設定を適用する方法については、「[アイテム保持ポリシーと保持ラベルの詳細](/microsoft-365/compliance/retention)」を参照してください。

Teams 向けのアイテム保持ポリシーの最小ライセンス要件は、Microsoft 365 E3 です。 Teams のライセンスの詳細については、「[Microsoft Teams サービスのサービスの説明](/office365/servicedescriptions/teams-service-description)」を参照してください。

## <a name="how-teams-retentiondeletion-policies-work"></a>Teams のアイテム保持/削除ポリシーのしくみ

Teams チャットのメッセージは、2 つの場所に保存されます。 プライマリ コピーは Azure に保存され、コンプライアンス ポリシーに使用されるセカンダリ コピーは、チャットに含まれる各ユーザーの Exchange オンライン メールボックスの非表示フォルダーに保存され、Teams チャネル メッセージはチームのグループ メールボックス内の同様の非表示フォルダーに保存されます。 チャット メッセージの削除ポリシーがユーザーやチームに適用された場合、セカンダリ コピーが最初に削除され、続いてプライマリ コピーが削除されます。 電子情報開示または Teams の検索は、セカンダリ コピーに保存されているメッセージに基づくため、セカンダリ コピーが削除された場合、メッセージは検出できません。 

チャット メッセージ保持ポリシーがユーザーまたはチームに適用されている場合、およびメッセージが削除された場合 (別の削除ポリシーまたはユーザー自身が削除された場合)、プライマリ コピーが削除されると、Teams クライアントはメッセージが消えますが、セカンダリ コピーは自動的に、Exchange 回復可能なアイテム フォルダーのサブフォルダーである **、"小** 谷ホールド" という名前の非表示のフォルダーに移動されます。  メッセージは SubstituteHolds フォルダ内から完全に削除されるまで、メッセージは電子情報開示ツールで検索できます。

Teams のアイテム保持ポリシーに含まれる内容や含まれない内容、また、ポリシー構成によってこれらのポリシーが機能する方法の詳細については、「[Microsoft Teams の保持の詳細](/microsoft-365/compliance/retention-policies-teams)」を参照してください。

> [!NOTE]
> このページでは、アイテム保持ポリシーでのメッセージの削除で延期される場合がある理由を説明しています。 たとえば、メッセージは、アイテム保持ポリシーで設定した有効期限の 7 日後まで見ることができます。

異なる保持設定を持つ複数の Teams アイテム保持ポリシーを設定した場合、保持の原則によって競合が解消されます。 次に例を示します。
- 同じコンテンツを保持するか削除するかで競合する場合、そのコンテンツは常に保持されます。
- 同じコンテンツをどのくらいの期間保持するかで競合する場合は、最も長い保持期間で保持されます。

この 2 つの保持の原則は、Teams に複数のアイテム保持ポリシーがある場合に発生する可能性のあるほとんどの矛盾を解決しますが、詳細については「[保持するための原則、または優先順位](/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)」を参照してください。

## <a name="when-to-use-retention-policies-for-teams"></a>Teams のアイテム保持ポリシーを使用すべき状況

組織は多くの場合、プライベート チャットのデータの方が、一般にプロジェクトとの関連性がより高い会話であるチャネル メッセージよりも負債になりやすいものとみなします。

管理者は、プライベート チャット (1 対 1 または 1 対多数チャット) のアイテム保持ポリシーとチャネル メッセージのアイテム保持ポリシーを別個に設定できます。 さらに、組織内の特定のユーザーやチームに適用される固有のポリシーを構成することもできます。 Teams のチャットの場合、ポリシーが適用されるユーザーを選択できます。 Teams のチャネル メッセージの場合は、ポリシーが適用されるチームを選択できます。

たとえば、チャネル メッセージの場合、組織内の特定のチームには 1 年間の削除ポリシーを適用し、その他のすべてのチームには 3 年間の削除ポリシーを適用することができます。

## <a name="create-and-manage-retention-policies-for-teams"></a>Teams 向けアイテム保持ポリシーの作成と管理

Teams のチャットやチャネル メッセージのアイテム保持ポリシーを作成するには、「[Teams の場所にアイテム保持ポリシーを作成する](/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations)」での説明を活用してください。

このページには、Microsoft 365 の他のワークロードのアイテム保持ポリシーの作成と管理に関する追加情報があります。 たとえば、Microsoft 365 グループのアイテム保持ポリシーを作成して、Teams でアクセスし、OneDrive や SharePoint に保存されたファイルを保持または削除することもできます。  

## <a name="end-user-experience"></a>エンド ユーザー エクスペリエンス

私的なチャット (1:1 のチャット) やグループのチャットの場合、ユーザーにはアイテム保持ポリシーの構成より古いチャットは削除され、"組織のアイテム保持ポリシーにより、古いメッセージを削除しました" という自動生成メッセージがまだ削除されていないメッセージの上に表示されます。 次に例を示します。

:::image type="content" source="media/retention-policies-image1.png" alt-text="Teams アイテム保持ポリシーにより、チャット メッセージが削除されることが Teams でユーザーに通知される":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="Teams のユーザーが説明するメッセージが、Teams のアイテム保持ポリシーの結果として削除される":::

チャネル メッセージの場合、ユーザー (チャネル メンバー) には、メッセージの有効期限が切れた後に、削除したメッセージが表示されなくなります。 削除されたメッセージがスレッド会話の親メッセージであった場合、親メッセージの代わりに "アイテム保持ポリシーに従い、このメッセージは削除されました。" というメッセージが表示されます。 次に例を示します。

:::image type="content" source="media/retention-policies-image3.png" alt-text="保持前のチャネルのスクリーンショット":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="保持後のチャネルのスクリーンショット":::

> [!NOTE]
> 削除済みメッセージの結果としてユーザーに表示されるメッセージは、この時点では構成できません。

これらの表示されたメッセージ内のリンクは、[アイテム保持ポリシーに関する Teams メッセージ](https://support.microsoft.com/en-us/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)に移動します。 エンド ユーザー向けのこのドキュメントは、メッセージが削除された理由に関する基本的な質問に答えるのに役立ちます。 ただし、アイテム保持ポリシーの展開の一環として、構成した設定の影響をユーザーやヘルプ デスクに連絡するようにしてください。

## <a name="related-topics"></a>関連項目

- [アイテム保持ポリシーおよび保持ラベルの使用を開始する](/microsoft-365/compliance/get-started-with-retention)
- [Microsoft Teams の保持の詳細](/microsoft-365/compliance/retention-policies-teams)
- [アイテム保持ポリシーを作成して構成する](/microsoft-365/compliance/create-retention-policies)
