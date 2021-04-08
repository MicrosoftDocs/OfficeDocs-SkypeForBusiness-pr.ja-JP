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
description: Microsoft Teams のアイテム保持ポリシーを使用して、組織が内部ポリシー、業界の規制、または法的要件に準拠する必要があるメッセージを保持し、責任と見なされたメッセージまたは法的なビジネス価値がないメッセージを削除します。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ec6b257f91c7e5003a4a69079e37b20b5f338528
ms.sourcegitcommit: b52b6aba289396c4fc10dd856817137eb1bc1f67
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/07/2021
ms.locfileid: "51617759"
---
# <a name="manage-retention-policies-for-microsoft-teams"></a>Teams のアイテム保持ポリシーを管理する

> [!NOTE]
> チャットまたはメッセージがアイテム保持ポリシーによって削除されたというメッセージが Teams に表示されている場合は、「[アイテム保持ポリシーに関する Teams メッセージ](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)」を参照してください。
> 
> このページの情報は、これらのアイテム保持ポリシーを管理する IT 管理者向けです。

Microsoft 365 のアイテム保持ポリシーと保持ラベルは、組織内の情報をより効果的に管理するのに役立ちます。 保持設定を構成して、組織の内部ポリシー、業界の規制、または法的要件に準拠するために必要なデータを保持できます。 保持設定を構成して、責任があると見なされたデータ、保持する必要がなくなったデータ、または法的価値やビジネス価値のないデータを削除するためにも使用されます。

Teams では、チャットやチャネルのメッセージ用にアイテム保持ポリシーを設定するサポートを行い、管理者としてデータを保持するか、削除するか、特定の期間保持した後に削除するかを前もって決定できます。 これらのアクションの保持期間の開始は、常にメッセージの作成日に基づいて行います。 Teams のアイテム保持ポリシーは、組織全体に適用することも、特定のユーザーやチームに適用することもできます。 保持ラベルは、Teams ではサポートされていません。

Microsoft 365 の保持ソリューションの詳細については、「アイテム保持ポリシーとアイテム保持ラベル [について」を参照してください](/microsoft-365/compliance/retention)。

Teams のアイテム保持ポリシーの適用対象となるユーザーは、Office 365 E3 や Office 365 A3 などの適切なライセンスを持っている必要があります。 これらのアイテム保持ポリシーのその他のライセンス オプションについては[、Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance)のライセンス ガイダンスの情報ガバナンスのセクションを参照して、セキュリティとコンプライアンス&してください。 [](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) Teams のライセンスの詳細については、Microsoft Teams サービスの [説明を参照してください](/office365/servicedescriptions/teams-service-description)。

## <a name="how-teams-retention-policies-support-retain-and-delete-actions"></a>Teams アイテム保持ポリシーが保持アクションと削除アクションをサポートする方法

チャットまたはチャネル メッセージを保持する Teams アイテム保持ポリシーを構成した場合でも、ユーザーは Teams アプリでメッセージを編集および削除できます。 ユーザーは Teams で事前に編集または削除されたメッセージを表示しなくなりましたが、これらのメッセージのデータは、コンプライアンス管理者による電子情報開示検索用に設計されたセキュリティで保護された場所に保存されます。 このデータの完全な削除は、構成済みの保持期間が終了する前に行わないか、このデータを保持するように別のアイテム保持ポリシーが構成されている場合、または電子情報開示の保留の対象になる場合[です。](/microsoft-365/compliance/retention#when-to-use-retention-policies-and-retention-labels-or-ediscovery-holds)

アイテム保持ポリシーがチャットおよびチャネル メッセージを削除するように構成されている場合、これらのメッセージは自動削除の対象になります。 メッセージが引き続き Teams アプリに表示されている場合、メッセージはそこから消え、アイテム保持ポリシーによってこれらのメッセージが削除されたという [通知がユーザーに送信されます](#end-user-experience)。 メッセージが以前に保持アクションの対象であり、ユーザーによって編集または削除された場合、これらのメッセージはセキュリティで保護された場所から削除され、電子情報開示検索で返されなくなりました。

ポリシーの構成とユーザーの操作に応じてこれらのポリシーがどのように機能し、Teams アイテム保持ポリシーに含まれるメッセージ データと除外されるメッセージ データの詳細については [、「Microsoft Teams](/microsoft-365/compliance/retention-policies-teams)の保持について」を参照してください。 このページでは、アイテム保持ポリシーがメッセージを削除するときに遅延が発生する場合がある理由も説明します。 たとえば、アイテム保持ポリシーで構成した有効期限の 7 日後まで、Teams アプリのユーザーにメッセージを表示できます。

異なる保持設定を持つ複数の Teams アイテム保持ポリシーを設定した場合、保持の原則によって競合が解消されます。 次に例を示します。

- 同じコンテンツの保持と削除の間に競合がある場合、コンテンツはセキュリティで保護された場所に常に保持され、コンプライアンス管理者の電子情報開示で検索可能なままです。
    
    この原則は、法的または調査的な理由で電子情報開示の保留にされているメッセージにも適用されます。

- 同じコンテンツを保持する期間に競合がある場合、最長の保持期間は、セキュリティで保護された場所に保持されます。

この 2 つの保持の原則は、Teams に複数のアイテム保持ポリシーがある場合に発生する可能性のあるほとんどの矛盾を解決しますが、詳細については「[保持するための原則、または優先順位](/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)」を参照してください。

## <a name="when-to-use-retention-policies-for-teams"></a>Teams のアイテム保持ポリシーを使用すべき状況

組織は多くの場合、プライベート チャットのデータの方が、一般にプロジェクトとの関連性がより高い会話であるチャネル メッセージよりも負債になりやすいものとみなします。

管理者は、プライベート チャット (1 対 1 または 1 対多数チャット) のアイテム保持ポリシーとチャネル メッセージのアイテム保持ポリシーを別個に設定できます。 さらに、組織内の特定のユーザーやチームに適用される固有のポリシーを構成することもできます。 Teams のチャットの場合、ポリシーが適用されるユーザーを選択できます。 Teams のチャネル メッセージの場合は、ポリシーが適用されるチームを選択できます。

たとえば、チャネル メッセージの場合、組織内の特定のチームにアイテム保持ポリシーを適用し、そのポリシーは 1 年後に削除アクションで構成されます。 その後、他のすべてのチームに別のアイテム保持ポリシーを適用し、そのポリシーは 3 年後に削除アクションで構成されます。

## <a name="create-and-manage-retention-policies-for-teams"></a>Teams 向けアイテム保持ポリシーの作成と管理

Teams チャットおよびチャネル メッセージのアイテム保持ポリシーを作成または編集するには、Teams の場所のアイテム保持 [ポリシーの手順を使用します](/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations)。

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
