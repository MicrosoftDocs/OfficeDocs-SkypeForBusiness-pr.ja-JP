---
title: Microsoft Teams のアイテム保持ポリシー
author: cabailey
ms.author: cabailey
ms.reviewer: prvijay
manager: laurawi
ms.topic: conceptual
ms.service: msteams
audience: admin
description: この記事では、アイテム保持ポリシーと、Microsoft Teams でアイテムの作成と管理を行う方法について説明します。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: efa11a5ca91be13508ab518ab5be504743825b68
ms.sourcegitcommit: a5276a713697e089d0eb0d80bba83a7af8d48251
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2020
ms.locfileid: "45202956"
---
# <a name="retention-policies-in-microsoft-teams"></a>Microsoft Teams のアイテム保持ポリシー

アイテム保持ポリシーは、組織内の情報をより効果的に管理するのに役立ちます。 アイテム保持ポリシーは、組織の社内ポリシー、業界の規制、法的要件に準拠するために必要なデータを保持したり、負債と考えられるデータ、保存する必要がなくなったデータ、法的またはビジネス上の価値がないデータを削除したりするために使用できます。

既定では、アイテム保持ポリシーを使用してコンテンツを削除しようとした場合や、ユーザーが削除した場合、管理者が削除した場合を除き、チームチャット、チャネル、ファイルのデータは無期限に保持されます。管理者として、チャットやチャネルメッセージ用にチームのアイテム保持ポリシーを設定し、データを保持するか削除するか、特定の期間に保持するかを決定してから、削除することができます。

[Microsoft 365 コンプライアンスセンター](https://protection.office.com/)で、またはセキュリティ & コンプライアンスセンターの PowerShell コマンドレットを使用して、チームおよびその他のワークロードのアイテム保持ポリシーを作成して管理します。 Teams のアイテム保持ポリシーは、組織全体に適用することも、特定のユーザーやチームに適用することもできます。

> [!NOTE]
> プライベートチャネルメッセージの保持の構成はまだサポートしていません。 プライベート チャネルで共有されているファイルの保持はサポートされています。

Microsoft 365 または Office 365 のアイテム保持ポリシーの詳細については、「[アイテム保持ポリシーの概要](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)」を参照してください。

## <a name="what-are-retention-policies-for-teams"></a>Teams のアイテム保持ポリシーとは

Teams やその他のワークロードのアイテム保持ポリシーを設定する場合、次のように設定できます。

- **データの保持**: アイテム保持ポリシーを使用すると、ユーザー アプリで何が発生するかに関係なく、指定した期間はデータが保持されるよう確認できます。 データはコンプライアンス上の理由で保持され、保持期間が終了するまで電子情報開示で利用できます。保持期間の終了後に何もしないか、データを削除するかはポリシーで指定します。 たとえば、チャネル メッセージを 7 年間保持する Teams のアイテム保持ポリシーを作成すると、ユーザーが Teams でメッセージを削除した場合でも、7 年間は電子情報開示用にそのメッセージが保持されます。
- **データの削除**: アイテム保持ポリシーを使用すると、組織の負債とならないようにデータを削除できます。 Teams のアイテム保持ポリシーでデータを削除すると、そのデータは Teams サービスのすべての保存場所から完全に削除されます。

Teams のアイテム保持ポリシーを使用すると、次のことができます。

- Teams のチャットやチャネル メッセージを指定した期間保持し、その後は何もしない。
- Teams のチャットやチャネル メッセージを指定した期間保持し、その後データを削除する。
- 指定した期間の後に、Teams のチャットやチャネル メッセージを削除する。

> [!NOTE]
> Teams では、ユーザーがプライベート チャットで共有するファイルは、ファイルを共有したユーザーの OneDrive for Business アカウントに保存されていることにご注意ください。 また、チーム メンバーがチャネルの会話にアップロードするファイルは、チームの SharePoint サイトに保存されます。 そのため、Teams のファイルを保持または削除するには、OneDrive for Business と SharePoint Online に適用されるアイテム保持ポリシーを作成します。

データにアイテム保持ポリシーが適用される場合、データは元の場所に保持されるため、ユーザーはそのデータを使用し続けることができます。 ポリシーが適用されるデータをユーザーが編集または削除する場合、安全な場所にコピーが保存され、ポリシーが有効な間はそこで保持されます。

アイテム保持ポリシーの最小ライセンス要件は、Office 365 E3 です。 ライセンスの詳細については、「 [Microsoft Teams サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)」を参照してください。

## <a name="how-teams-retention-policies-work"></a>Teams のアイテム保持ポリシーのしくみ

チームのチャットは、チャット内の各ユーザーのメールボックスの非表示フォルダー (Team・・・の) に保存され、Teams チャネルのメッセージは、チームのグループメールボックスの非表示フォルダー (Teamな) に保存されます。 Teams が使用する Azure を利用したチャット サービスでもこのデータが保存されます。既定では、このサービスはデータを無期限に保存します。 Teams のアイテム保持ポリシーでデータを削除すると、Exchange メールボックスと基になるチャット サービスの両方からデータが完全に削除されます。

チームチャットまたはチャネルメッセージに**保持保持**ポリシーを適用すると、次のような処理が行われます。

- 保持期間中にユーザーがチャットまたはチャネルメッセージを編集または削除した場合、メッセージはコピーされ (編集された場合)、または (削除された場合は) SubstrateHolds フォルダーに移動され、保持期間が終了するまで保存されます。 保持期間の終了時にデータを削除するようにポリシーが構成されている場合、メッセージは保持期間が終了した日に完全に削除されます。
- **保持**期間中にユーザーがチャットまたはチャネルメッセージを削除していない場合、保存期間が終了してから1日以内にメッセージが SubstrateHolds フォルダーに移動されます。 保持期間の終了時にデータを削除するようにポリシーが構成されている場合、メッセージはフォルダーに移動された翌日に完全に削除されます。

**アイテム保持**ポリシーをチームのチャットとチャネルメッセージに適用すると、次のような処理が行われます。

- チャットまたはチャネルメッセージの有効期限が切れた場合は、アイテム保持ポリシー (バックエンドサービス) で許可されているメッセージが、**アイテム保持**ポリシーによって制限されます。
- バックエンドストレージでメッセージが削除されると、Azure powered チャットサービスとユーザーの Teams アプリで同じメッセージを削除するためのプロセスがトリガーされます。 Teams アプリでメッセージを削除するには、アプリがインターネットに接続され、ユーザーエクスペリエンスの妨げにならないようにアイドル状態 (ユーザーアクティビティなし) にする必要があります。 1人のユーザーは複数のデバイスを持っている可能性があります。これは、状態が異なる可能性があるため、保持の削除はまったく同じタイミングでは同期されません。
- バックエンドストレージでメッセージの削除が完了すると、電子情報開示などのコンプライアンス検索レポートでそれらのメッセージが表示されなくなります。

> [!NOTE]
> Skype for Business Online と Teams の相互運用チャットでも、処理のフローは同じです。 Skype for Business Online のチャットが Teams に届くと、Teams のチャット スレッドのメッセージとなり、適切なメールボックスに取り込まれます。 Teams のアイテム保持ポリシーは、これらのメッセージを Teams のスレッドから削除します。 ただし、Skype for Business Online に対して会話履歴がオンになっていて、Skype for Business Online のクライアント側からこれらがメールボックスに保存されている場合、このチャット データは Teams のアイテム保持ポリシーでは処理されません。

> [!NOTE]
> メッセージの削除は永続的で、取り消すことはできません。

Teams のアイテム保持ポリシーは、チャットやチャネル メッセージが作成された日付に基づいて遡及的に処理されます。 つまり、90 日より前のデータを削除するアイテム保持ポリシーを作成すると、90 日より前に作成された Teams データは削除されます。

SharePoint Online や OneDrive for Business に適用されているアイテム保持ポリシーにより、Teams のチャットやチャネル メッセージで参照されているファイルが、それらのメッセージが削除されるよりも先に削除される場合があります。 このような場合、そのファイルは Teams のメッセージに依然として表示されてはいますが、ユーザーがファイルをクリックすると、"ファイルが見つかりません" というエラーが表示されます。 ポリシーはなくても、ユーザーがファイルを SharePoint Online や OneDrive for Business から手動で削除した場合、このエラーが発生することがあります。

### <a name="considerations-and-limitations"></a>考慮事項と制限事項

Teams のアイテム保持ポリシーを使用するにあたり、注意する必要のある考慮事項と制限事項を次に示します。

- Teams には、他のワークロードとは別のアイテム保持ポリシーが必要です。 つまり、Teams のチャットやチャネル メッセージ専用のアイテム保持ポリシーを作成する必要があります。 このため、Teams を組織全体のアイテム保持ポリシーに含めることはできません。

- プライベート チャネル メッセージはサポートされていません。 現時点では、Teams のアイテム保持ポリシーは標準のチャネル メッセージにのみ適用されます。

- Teams では、キーワードや機密情報を含むコンテンツにポリシーを適用する機能などの、高度な保持設定はサポートされていません。 現在、Teams のアイテム保持ポリシーは、すべてのチャットとチャネル メッセージのコンテンツに適用されます。

- チームアイテム保持ポリシーは、メッセージの作成日に基づいて、チャットとチャネルのメッセージを削除するプロセスをトリガーします。 ただし、サービスの負荷によっては、これらのメッセージがバックエンドストレージおよび Teams アプリから完全に削除されるまでに、最大7日かかる場合があります。 また、これらのメッセージは、コンプライアンスツール (電子情報開示、エンドユーザー検索) で検索可能になり、バックエンドストレージから完全に削除されます。

### <a name="multiple-retention-policies-and-the-principles-of-retention"></a>複数のアイテム保持ポリシーと保持の原則

期間が異なる複数の Teams のアイテム保持ポリシーを設定すると、[アイテム保持ポリシーの原則](https://docs.microsoft.com/microsoft-365/compliance/retention-policies#the-principles-of-retention-or-what-takes-precedence)が適用されます。 優先順位の概要を次に示します。

- 保持が常に削除よりも優先されます
- 最長の保持期間が常に優先されます
- 場所に関しては、明示的な包含が暗黙的な包含より優先されます
- 最短の削除期間が優先されます

## <a name="when-to-use-retention-policies-for-teams"></a>Teams のアイテム保持ポリシーを使用すべき状況

組織は多くの場合、プライベート チャットのデータの方が、一般にプロジェクトとの関連性がより高い会話であるチャネル メッセージよりも負債になりやすいものとみなします。

管理者は、プライベート チャット (1 対 1 または 1 対多数チャット) のアイテム保持ポリシーとチャネル メッセージのアイテム保持ポリシーを別個に設定できます。 さらに、組織内の特定のユーザーやチームに適用される固有のポリシーを構成することもできます。 Teams のチャットの場合、ポリシーが適用されるユーザーを選択できます。 Teams のチャネル メッセージの場合は、ポリシーが適用されるチームを選択できます。

たとえば、チャネル メッセージの場合、組織内の特定のチームには 1 年間の削除ポリシーを適用し、その他のすべてのチームには 3 年間の削除ポリシーを適用することができます。

## <a name="manage-retention-policies-for-teams"></a>Teams のアイテム保持ポリシーを管理する

### <a name="using-the-security--compliance-center"></a>セキュリティ/コンプライアンス センターを使用する場合

#### <a name="create-a-retention-policy"></a>アイテム保持ポリシーの作成

Teams のチャットやチャネル メッセージのアイテム保持ポリシーを作成するには、次の操作を行います。

1. セキュリティ/コンプライアンス センターの左側のナビゲーションで、**[情報ガバナンス]** > **[保持]** の順に移動します。
2. **[作成]** を選択します。
3. **[ポリシーに名前をつける]** ページで、ポリシーの名前と説明を入力して、**[次へ]** をクリックします。
4. **[設定]** ページで、データの保持、削除、またはその両方と、保持期間とを指定して、**[次へ]** をクリックします。
5. **[場所の選択]** ページで、次の操作を行い、**[次へ]** をクリックします。

    - ポリシーをチャネル メッセージに適用するには、**[Teams のチャネル メッセージ]** をオンにします。  ポリシーを組織内の特定のチームに適用する場合は、**[チームの選択]** を選択し、目的のチームを選択します。
    - ポリシーをチャットに適用するには、**[Teams のチャット]** をオンにします。 ポリシーを組織内の特定のユーザーに適用する場合は、**[ユーザーの選択]** を選択し、目的のユーザーを選択します。
      > [!NOTE]
      > **[Teams のチャネル メッセージ]** や **[Teams のチャット]** をオンにすると、その他のすべての場所が自動的にオフになります。 Teams のアイテム保持ポリシーには、Teams の場所のみを含めることができます。

        ![[場所の選択] ページの [Teams のチャネル メッセージ] オプションと [Teams のチャット] オプションのスクリーンショット](media/retention-policies-create.png)

      > [!IMPORTANT]
      > **Exchange メール**または**Microsoft 365 グループ**の場所で、ユーザーまたはグループのメールボックスに適用されるアイテム保持ポリシーの影響を受けることはありません。 Teams のチャットやチャネル メッセージは Exchange に保存されますが、それらは Teams の場所に適用されるアイテム保持ポリシーの影響のみを受けます。

6. 設定の確認し準備ができたら、**[このポリシーを作成する]** を選択します。

#### <a name="edit-a-retention-policy"></a>アイテム保持ポリシーの編集

Teams のアイテム保持ポリシーを編集するには、次の操作を行います。

1. セキュリティ/コンプライアンス センターの左側のナビゲーションで、**[情報ガバナンス]** > **[保持]** の順に移動します。
2. アイテム保持ポリシーの一覧で、編集するアイテム保持ポリシーの横にあるチェック ボックスをオンにします。
3. 編集する内容の横にある **[編集]** を選択し、変更を加えたら、**[保存]** をクリックして、**[閉じる]** をクリックします。

    ![[場所の選択] ページの [Teams のチャネル メッセージ] オプションと [Teams のチャット] オプションのスクリーンショット](media/retention-policies-edit.png)

#### <a name="delete-a-retention-policy"></a>アイテム保持ポリシーの削除

Teams のアイテム保持ポリシーを削除するには、次の操作を行います。

1. セキュリティ/コンプライアンス センターの左側のナビゲーションで、**[情報ガバナンス]** > **[保持]** の順に移動します。
2. アイテム保持ポリシーの一覧で、削除するアイテム保持ポリシーの横にあるチェック ボックスをオンにします。
3. **[ポリシーの削除]** を選択します。

### <a name="using-powershell"></a>PowerShell を使用する場合

[セキュリティ & コンプライアンスセンターの PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)を使用して、チームのアイテム保持ポリシーを作成および管理するには、次のコマンドレットを使用します。

|ポリシー|ルール|
|---|---|
|[新規-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancepolicy?view=exchange-ps)| [新規-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancerule?view=exchange-ps)|
|[Get-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancepolicy?view=exchange-ps)| [Get-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancerule?view=exchange-ps)|
|[Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancepolicy?view=exchange-ps)| [Set-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancerule?view=exchange-ps)|
|[Remove-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-retentioncompliancepolicy?view=exchange-ps)| [Remove-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-retentioncompliancerule?view=exchange-ps)|

## <a name="known-issues"></a>既知の問題

現在追跡と調査が行われている Teams のアイテム保持ポリシーに関する既知の問題を以下に示します。

- [チーム**チャネルメッセージ**の場所] 行の [**チームの選択**] で、teams にも含まれていない Microsoft 365 グループが表示されることがあります。 この問題は将来解決される予定です。

- **[Teams のチャット]** の場所の行にある **[ユーザーの選択]** の下に、ゲストや、メールボックスのユーザーではないユーザーが表示される場合がある。 アイテム保持ポリシーはゲストのために設定するものではないため、これらは一覧から削除される予定です。

- Exchange Life Cycle アシスタント (ELC) は毎日実行しますが、その SLA は 7 日間です。 このため、60 日以上経過したアイテムを削除する Teams の保持ポリシーを設定している場合、それらのアイテムは最大 67 日間保持される可能性があります。 これは新しい状況ではなく、Exchange の様式によるものです。 当然ながら、ほとんどの場合、遅延は生じません。

## <a name="related-topics"></a>関連項目

- [アイテム保持ポリシーの概要](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)
