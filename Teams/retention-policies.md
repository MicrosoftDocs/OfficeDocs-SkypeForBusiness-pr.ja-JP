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
description: Microsoft Teams のアイテム保持ポリシーを使用して、組織の内部ポリシー、業界規制、または法的要件に準拠するために組織が必要とするメッセージを保持し、負債とみなされるメッセージや法的にビジネス価値のないメッセージを削除します。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c99fc4bfb185ec291a98a96572167b389b3e6252
ms.sourcegitcommit: 28b83243411b54760875e7fd137549d5d2182c7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2021
ms.locfileid: "53252652"
---
# <a name="manage-retention-policies-for-microsoft-teams"></a>Teams のアイテム保持ポリシーを管理する

> [!NOTE]
> チャットまたはメッセージがアイテム保持ポリシーによって削除されたというメッセージが Teams に表示されている場合は、「[アイテム保持ポリシーに関する Teams メッセージ](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)」を参照してください。
> 
> このページの情報は、これらのアイテム保持ポリシーを管理する IT 管理者向けです。

Microsoft 365 のアイテム保持ポリシーと保持ラベルは、組織内の情報をより効果的に管理するのに役立ちます。 保持設定を構成して、組織の内部ポリシー、業界規制、または法的要件に準拠する必要のあるデータを保持します。 保持設定を構成して、責任があると見なされたデータ、保持する必要がなくなったデータ、または法的価値やビジネス価値のないデータを削除するためにも使用されます。

Teams では、チャットやチャネルのメッセージ用にアイテム保持ポリシーを設定するサポートを行い、管理者としてデータを保持するか、削除するか、特定の期間保持した後に削除するかを前もって決定できます。 これらのアクションの保持期間の開始は、常にメッセージが作成されるタイミングに基づきます。 Teams のアイテム保持ポリシーは、組織全体に適用することも、特定のユーザーやチームに適用することもできます。 保持ラベルは、Teams ではサポートされていません。

Microsoft 365 での保持ソリューションに関する詳細については、「[保持ポリシーと保持ラベルの詳細](/microsoft-365/compliance/retention)」を参照してください。

Teams でのアイテム保持ポリシーの対象となるユーザーは、Office 365 E3 や Office 365 A3 などの適切なライセンスを所有している必要があります。 これらのアイテム保持ポリシーへのその他のライセンス オプションについては、[[セキュリティとコンプライアンス向け Microsoft 365 ライセンス ガイド]](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) で [[情報ガバナンス]](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) セクションを参照してください。 Teams のライセンスの詳細については、「[Microsoft Teams サービスのサービスの説明](/office365/servicedescriptions/teams-service-description)」を参照してください。

## <a name="how-teams-retention-policies-support-retain-and-delete-actions"></a>Teams のアイテム保持ポリシーが保持と削除のアクションをサポートする方法

チャットやチャネル メッセージを保持するように Teams のアイテム保持ポリシーを構成した場合でも、ユーザーは Teams アプリでメッセージを編集したり削除したりすることができます。 ユーザーは、Teams で編集前のメッセージや削除したメッセージを見ることができなくなりますが、これらのメッセージのデータは、コンプライアンス管理者によって電子情報開示検索用に設計された安全な場所に保存されます。 このデータの完全な削除は、構成された保持期間が終了する前には行われず、このデータを保持するために別のアイテム保持ポリシーが構成されているか、[電子情報開示ホールド](/microsoft-365/compliance/retention#when-to-use-retention-policies-and-retention-labels-or-ediscovery-holds)の対象となっている場合に行われます。

チャットやチャネルのメッセージを削除するようにアイテム保持ポリシーを構成した場合は、これらのメッセージは自動削除の対象となります。 メッセージがまだ Teams アプリに表示されている場合は、底場所から消え、[ユーザーにはアイテム保持ポリシーによりこれらのメッセージが削除されたことが通知されます](#end-user-experience)。 以前、メッセージが保持アクションの対象となり、ユーザーによって編集または削除された場合、これらのメッセージは保護された場所から削除され、電子情報開示の検索で返されなくなります。

ポリシー構成やユーザーの操作によってこれらのポリシーが機能する方法や、Teams のアイテム保持ポリシーに含まれるメッセージ データや含まれないメッセージ データの詳細については、「[Microsoft Teams の保持の詳細](/microsoft-365/compliance/retention-policies-teams)」を参照してください。 このページでは、アイテム保持ポリシーでのメッセージを削除する場合に延期される場合がある理由についても説明しています。 たとえば、メッセージは、アイテム保持ポリシーで設定した有効期限の 7 日後まで、Teams アプリのユーザーに表示することができます。

異なる保持設定を持つ複数の Teams アイテム保持ポリシーを設定した場合、保持の原則によって競合が解消されます。例を以下に示します。

- 同じコンテンツを保持するか削除するかで競合が生じた場合、コンテンツは常にセキュリティで保護された場所に保持されるため、コンプライアンス管理者が電子情報開示で検索可能な状態は維持されます。
    
    この原則は、法律上または調査上の理由で電子情報開示の適用対象となっているメッセージにも適用されます。

- 同じコンテンツをどのくらいの期間セキュリティで保護された場所に保持するかで競合する場合は、最も長い保持期間で保持されます。

この 2 つの保持の原則は、Teams に複数のアイテム保持ポリシーがある場合に発生する可能性のあるほとんどの矛盾を解決しますが、詳細については「[保持するための原則、または優先順位](/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)」を参照してください。

## <a name="when-to-use-retention-policies-for-teams"></a>Teams のアイテム保持ポリシーを使用すべき状況

組織は多くの場合、プライベート チャットのデータの方が、一般にプロジェクトとの関連性がより高い会話であるチャネル メッセージよりも負債になりやすいものとみなします。

すべてのメッセージに対して 1 つのアイテム保持ポリシーを非常に効率的Teamsできます。 または、よりきめ細かく制御するには、次の操作を行います。

- プライベート チャット (1:1 または 1:多のチャット)、標準チャネルからのメッセージ、またはプライベート チャネルからのメッセージに対して個別の保持ポリシーを設定します。

- ポリシーは、組織内の特定のユーザーまたはチームにのみ適用します。 チャットTeamsプライベート チャネルの場合は、ポリシーを適用するユーザーを選択できます。 Teams のチャネル メッセージの場合は、ポリシーが適用されるチームを選択できます。

たとえば、標準チャネル メッセージの場合: 組織内の特定のチームのアイテム保持ポリシーを作成し、1 年後に削除アクションを使用してそのポリシーを構成します。 その後、他のすべてのチームの標準チャネル メッセージに対して別のアイテム保持ポリシーを作成し、3 年後に削除アクションを使用してそのポリシーを構成します。

## <a name="create-and-manage-retention-policies-for-teams"></a>Teams 向けアイテム保持ポリシーの作成と管理

メッセージの保持ポリシーを作成または編集するにはTeamsのアイテム保持ポリシーに関するページの[Teams使用します](/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations)。

このページには、Microsoft 365 の他のワークロードのアイテム保持ポリシーの作成と管理に関する追加情報があります。 たとえば、Microsoft 365 グループのアイテム保持ポリシーを作成して、Teams でアクセスし、OneDrive や SharePoint に保存されたファイルを保持または削除することもできます。  

## <a name="end-user-experience"></a>エンドユーザーのエクスペリエンス

私的なチャット (1:1 のチャット) やグループのチャットの場合、ユーザーにはアイテム保持ポリシーの構成より古いチャットは削除され、"組織のアイテム保持ポリシーにより、古いメッセージを削除しました" という自動生成メッセージがまだ削除されていないメッセージの上に表示されます。例を以下に示します。

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
