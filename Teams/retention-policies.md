---
title: Microsoft Teams の保持ポリシー
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: prvijay
description: アイテム保持ポリシーと Teams での作成と管理の方法について説明します。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 86cbb37b46bca606e7225ce0267a49c709fc9619
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2020
ms.locfileid: "42160751"
---
# <a name="retention-policies-in-microsoft-teams"></a>Microsoft Teams の保持ポリシー

アイテム保持ポリシーは、組織内の情報をより効果的に管理するのに役立ちます。 アイテム保持ポリシーを使用して、組織の社内ポリシー、業界規制、法的要件に準拠する必要があるデータを維持し、負債と見なされるデータを削除したり、法的またはビジネス価値を持たせたりすることができます。

既定では、Teams チャット、チャネル、ファイルのデータは永続的に保持されます。 管理者として、チャットやチャネルメッセージ用にチームのアイテム保持ポリシーを設定し、データを保持するか削除するか、特定の期間に保持するかを決定してから、削除することができます。

[Office 365 セキュリティ & コンプライアンスセンター](https://protection.office.com/)で、またはセキュリティ & コンプライアンスセンターの PowerShell コマンドレットを使用して、チームおよびその他のワークロードのアイテム保持ポリシーを作成および管理します。 チームのアイテム保持ポリシーは、組織全体または特定のユーザーやチームに適用できます。

> [!NOTE]
> プライベートチャネルメッセージの保持の構成はまだサポートしていません。 プライベートチャネルで共有されているファイルの保持はサポートされています。

Office 365 のアイテム保持ポリシーの詳細については、「[アイテム保持ポリシーの概要](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)」を参照してください。

## <a name="what-are-retention-policies-for-teams"></a>Teams のアイテム保持ポリシーとは

Teams またはその他のワークロードのアイテム保持ポリシーを設定すると、次のように設定できます。

- **データの保持**: ユーザーアプリで何が発生したかに関係なく、アイテム保持ポリシーを使用して、指定した期間、データが保持されるようにします。 データはコンプライアンス上の理由で保持されます。また、保持期間が終了するまで eDiscovery で利用可能になります。その後、何も行わないか、データを削除するかをポリシーで指定します。 たとえば、7年のチャネルメッセージを保持するためにチームのアイテム保持ポリシーを作成すると、ユーザーが Teams でメッセージを削除した場合でも、7年間は電子情報開示用にメッセージを保持します。
- **データの削除**: アイテム保持ポリシーを使用してデータを削除し、組織の責任を負わないことを確認します。 チームアイテム保持ポリシーを使用して、データを削除すると、Teams サービスのすべてのストレージの場所から完全に削除されます。

Teams のアイテム保持ポリシーを使用すると、次のことができます。

- 指定した期間、チームのチャットやチャネルのメッセージを保持して、何もしない。
- 指定した期間のチームチャットとチャネルメッセージを保持し、データを削除します。
- 指定した期間が経過した後に Teams のチャットやチャネルのメッセージを削除します。

> [!NOTE]
> Teams では、ユーザーがプライベートチャットで共有するファイルは、ファイルを共有したユーザーの OneDrive for Business アカウントに保存されていることに注意してください。 また、チームメンバーがチャネル会話にアップロードしたファイルは、チームの SharePoint サイトに保存されます。 そのため、Teams のファイルを保持または削除するには、OneDrive for Business および SharePoint Online に適用されるアイテム保持ポリシーを作成します。

データの保持ポリシーが適用される場合、データは元の場所に保持されるため、ユーザーはそのデータを使用し続けることができます。 ポリシーが適用されているデータをユーザーが編集または削除した場合、コピーはセキュリティで保護された場所に保存され、ポリシーが有効になっている間は保持されます。

アイテム保持ポリシーの最小のライセンス要件は、Office 365 E3 です。 ライセンスの詳細については、「 [Teams の Office 365 ライセンス](Office-365-licensing.md)」を参照してください。

## <a name="how-teams-retention-policies-work"></a>チームのアイテム保持ポリシーのしくみ

チームのチャットは、チャットの各ユーザーのメールボックス内の非表示の SubstrateHolds フォルダーに保存され、チームチャネルのメッセージは、チームのグループメールボックス内の非表示の SubstratesHolds フォルダーに格納されます。 チームでは、このデータが保存されている Azure powered チャットサービスも使用します。既定では、このサービスはデータを永続的に保存します。 チームアイテム保持ポリシーを使用すると、データを削除すると、Exchange メールボックスと基礎となるチャットサービスの両方からデータが完全に削除されます。

チームチャットとチャネルメッセージにアイテム保持ポリシーを適用すると、次のような処理が行われます。

- 保持期間中にユーザーがチャットまたはチャネルメッセージを編集または削除した場合、メッセージはコピーされ (編集された場合)、または (削除された場合) SubstrateHolds フォルダーに移動され、保持期間が終了するまで保存されます。 保持期間の経過時にデータを削除するようにポリシーが構成されている場合、メッセージは保持期間が終了した日に完全に削除されます。
- 保持期間中にユーザーがチャットまたはチャネルメッセージを削除していない場合、保存期間が終了してから1日以内にメッセージが SubstrateHolds フォルダーに移動されます。 保持期間が経過したときにデータを削除するようにポリシーが構成されている場合、メッセージはフォルダーに移動された後1日に完全に削除されます。

> [!NOTE]
> 同じフローは、Skype for Business Online と Teams の相互運用機能のチャットにも対応しています。 Skype for Business Online のチャットが Teams に届くと、Teams チャットスレッド内のメッセージとなり、適切なメールボックスに毎回されます。 チームアイテム保持ポリシーは、これらのメッセージを Teams スレッドから削除します。 ただし、Skype for Business Online および skype for Business Online クライアント側からメールボックスに保存されている会話履歴が有効になっている場合は、そのチャットデータはチームのアイテム保持ポリシーによって処理されません。

Teams のアイテム保持ポリシーは、チャットまたはチャネルメッセージの作成日に基づいて遡及的なされます。 つまり、90日より前のデータを削除するアイテム保持ポリシーを作成すると、90日以上前に作成されたチームデータは削除されます。

SharePoint Online または OneDrive for Business に適用されているアイテム保持ポリシーで、チームチャットまたはチャネルメッセージで参照されているファイルを削除した後に、それらのメッセージが削除される可能性があります。 このシナリオでは、ファイルは Teams メッセージに表示されますが、ユーザーがそのファイルをクリックすると、"ファイルが見つかりません" というエラーが表示されます。 この問題は、他のユーザーが SharePoint Online または OneDrive for business からファイルを手動で削除した場合にも、ポリシーがない場合に発生する可能性があります。

### <a name="considerations-and-limitations"></a>考慮事項と制限事項

チームのアイテム保持ポリシーを使用する際の注意事項と制限事項を次に示します。

- チームには、他のワークロードとは別のアイテム保持ポリシーが必要です。 つまり、チームチャットやチャネルメッセージには、特定のアイテム保持ポリシーを作成する必要があります。 このため、チームを組織全体のアイテム保持ポリシーに含めることはできません。

- プライベートチャネルメッセージはサポートされていません。 この時点では、Teams のアイテム保持ポリシーは標準のチャネルメッセージにのみ適用されます。

- チームは、キーワードまたは機密情報を含むコンテンツにポリシーを適用する機能などの、詳細な保持設定をサポートしていません。 現在、Teams のアイテム保持ポリシーは、すべてのチャットとチャネルメッセージの内容に適用されます。

- 有効期限が切れたメッセージをクリーンアップするには、チームは最長3日間かかることがあります。 アイテム保持ポリシーによって、保存期間が経過すると、チャットとチャネルのメッセージが削除されます。 ただし、これらのメッセージをクリーンアップして完全に削除するまでに、最大3日かかる場合があります。 また、チャットやチャネルメッセージは、保存期間が終了してから、メッセージが完全に削除されるまでの間の電子情報開示ツールで検索可能になります。

### <a name="multiple-retention-policies-and-the-principles-of-retention"></a>複数のアイテム保持ポリシーと保持の原則

期間が異なる複数の Teams アイテム保持ポリシーを設定すると、[アイテム保持ポリシーの原則](https://docs.microsoft.com/microsoft-365/compliance/retention-policies#the-principles-of-retention-or-what-takes-precedence)が適用されます。 優先される機能の概要を次に示します。

- 保持が常に削除よりも優先されます
- 最長の保持期間が常に優先されます
- 場所に関しては、明示的な包含が暗黙的な包含より優先されます
- 最短の削除期間が優先されます

## <a name="when-to-use-retention-policies-for-teams"></a>Teams のアイテム保持ポリシーを使用する状況

多くの場合、組織はチャネルメッセージよりも負債の多い方法としてプライベートチャットデータを検討していますが、通常はプロジェクト関連の会話がより多く行われます。

プライベートチャット用に個別のアイテム保持ポリシー (1:1 または 1: 多くのチャット) とチャネルメッセージを設定することができます。 また、組織内の特定のユーザーまたはチームに適用する固有のポリシーを構成することもできます。 Teams のチャットの場合は、ポリシーを適用するユーザーを選択できます。 Teams チャネルメッセージの場合は、ポリシーを適用するチームを選択できます。

たとえば、チャネルメッセージの場合は、組織内の特定のチームに1年の削除ポリシーを適用し、他のすべてのチームに3年の削除ポリシーを適用することができます。

## <a name="manage-retention-policies-for-teams"></a>Teams のアイテム保持ポリシーを管理する

### <a name="using-the-security--compliance-center"></a>セキュリティ & コンプライアンスセンターを使用する

#### <a name="create-a-retention-policy"></a>アイテム保持ポリシーを作成する

チームチャットとチャネルメッセージのアイテム保持ポリシーを作成するには、次の操作を行います。

1. セキュリティ & コンプライアンスセンターの左のナビゲーションで、[**情報ガバナンス** > の**保持**] に移動します。
2. [**作成**] を選びます。
3. [**ポリシーの名前**を入力してください] ページで、ポリシーの名前と説明を入力し、[**次へ**] をクリックします。
4. [**設定**] ページで、データを保持するか、削除するか、または両方を保持するかを指定し、[**次へ**] をクリックします。
5. [**場所の選択**] ページで、次の操作を行い、[**次へ**] をクリックします。

    - ポリシーをチャネルメッセージに適用するには、 **Teams チャネルメッセージ**を有効にします。  組織内の特定のチームにポリシーを適用する場合は、[**チームの選択**] を選択し、目的のチームを選択します。
    - チャットにポリシーを適用するには、 **Teams のチャット**をオンにします。 組織内の特定のユーザーにポリシーを適用する場合は、[**ユーザーの選択**] を選択し、目的のユーザーを選びます。
      > [!NOTE]
      > **Teams のチャネルメッセージ**や**チームチャット**をオンにすると、他のすべての場所が自動的に無効になります。 Teams アイテム保持ポリシーに含めることができるのは、Teams の場所だけです。

        ![[場所の選択] ページの [チームチャネルメッセージ] と [チームチャット] オプションのスクリーンショット](media/retention-policies-create.png)

      > [!IMPORTANT]
      > **Exchange メール**または**Office 365 グループ**の場所で、ユーザーまたはグループのメールボックスに適用されるアイテム保持ポリシーの影響を受けることはありません。 チームのチャットとチャネルメッセージは Exchange に保存されていますが、チームの場所に適用されているアイテム保持ポリシーによって影響を受けます。

6. 設定を確認し、準備ができたら、[**このポリシーを作成**する] を選びます。

#### <a name="edit-a-retention-policy"></a>アイテム保持ポリシーを編集する

Teams のアイテム保持ポリシーを編集するには、次の操作を行います。

1. セキュリティ & コンプライアンスセンターの左のナビゲーションで、[**情報ガバナンス** > の**保持**] に移動します。
2. アイテム保持ポリシーの一覧で、編集するアイテム保持ポリシーの横にあるチェックボックスをオンにします。
3. 編集する内容の横にある [**編集**] を選択し、変更を加え、[**保存**] をクリックして、[**閉じる**] をクリックします。

    ![[場所の選択] ページの [チームチャネルメッセージ] と [チームチャット] オプションのスクリーンショット](media/retention-policies-edit.png)

#### <a name="delete-a-retention-policy"></a>アイテム保持ポリシーを削除する

Teams アイテム保持ポリシーを削除するには、次の操作を行います。

1. セキュリティ & コンプライアンスセンターの左のナビゲーションで、[**情報ガバナンス** > の**保持**] に移動します。
2. アイテム保持ポリシーの一覧で、削除するアイテム保持ポリシーの横にあるチェックボックスをオンにします。
3. [**ポリシーの削除**] を選びます。

### <a name="using-powershell"></a>PowerShell を使用する場合

PowerShell を使用してチームのアイテム保持ポリシーを作成および管理するには、次のコマンドレットを使用します。

|ポリシー|ルール|
|---|---|
|[New-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps)| [New-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps)|
|[Get-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancepolicy?view=exchange-ps)| [Get-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancerule?view=exchange-ps)|
|[Set-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancepolicy?view=exchange-ps)| [Set-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancerule?view=exchange-ps)|
|[Remove-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancepolicy?view=exchange-ps)| [Remove-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancerule?view=exchange-ps)|

## <a name="known-issues"></a>既知の問題

現在追跡および調査されている Teams の保持ポリシーに関する既知の問題を以下に示します。

- [チーム**チャネルメッセージ**の場所] 行の [**チームの選択**] で、teams にも含まれていない Office 365 グループが表示されることがあります。 この問題は、今後解決される予定です。

- [ **Teams のチャット**の場所] 行の [**ユーザーの選択**] で、ゲストとメールボックス以外のユーザーが表示されることがあります。 アイテム保持ポリシーはゲストに設定するものではありません。これらは、一覧から削除されます。

- Exchange Life Cycle アシスタント (ELC) は毎日実行しますが、その SLA は 7 日間です。 このため、60 日以上経過したアイテムを削除する Teams の保持ポリシーを設定している場合、それらのアイテムは最大 67 日間保持される可能性があります。 これは新しい状況ではなく、Exchange の様式によるものです。 もちろん、ほとんどの場合、遅延は生じません。

## <a name="related-topics"></a>関連トピック

- [アイテム保持ポリシーの概要](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)
