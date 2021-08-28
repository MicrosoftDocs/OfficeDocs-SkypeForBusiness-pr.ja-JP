---
title: EDU 管理者向け Microsoft Teams ポリシーおよびポリシーパッケージ
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.reviewer: prkuch
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.policypackages.overview
ms.localizationpriority: high
search.appverid: MET150
description: 教育機関におけるポリシーや EDU 設定、および Microsoft Teams でポリシー パッケージを使用および管理する方法について説明します。
ms.openlocfilehash: 8120000599f2e0406d80a7e61b2e5720ffe2fd71
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58608864"
---
# <a name="teams-policies-and-policy-packages-for-education"></a>教育機関向け Teams ポリシーおよびポリシー パッケージ

[!INCLUDE [policy-wizard-edu](includes/policy-wizard-edu.md)]

> [!NOTE]
> Microsoft Teams のポリシーの大規模な事例については、「[Microsoft Teams でユーザーにポリシーを割り当てる](assign-policies.md)」をご確認ください。

## <a name="admins-getting-started-with-microsoft-teams-policy-management"></a>管理者: Microsoft Teams のポリシー管理の概要

Microsoft Teams を使用すると、ユーザーはオンライン会議やライブ イベントへの参加、チャット、通話、アプリの使用などを行うことができます。 適切な Microsoft Teams 管理ポリシーを設定することは、Teams が学生にとって安全な学習環境であることを保証するための重要なステップです。 管理者は、ポリシーを使用して、教育機関のユーザーが利用できる Teams 機能を制御できます。 ほとんどの場合、環境を安全に保つために、学生と教師の両方のポリシーを調整する必要があります。  

Microsoft Teams 内の主なポリシー領域の一覧は次のとおりです。 各領域のポリシーとそれらが制御する機能の詳細については、以下のリンクを使用してください:

- [会議](meeting-policies-in-teams.md)
- [ライブ イベント](teams-live-events/configure-teams-live-events.md)
- [通話](teams-calling-policy.md) 
- [メッセージング](messaging-policies-in-teams.md) 
- [Teams](teams-policies.md)
- [アプリのアクセス許可](teams-app-permission-policies.md)

:::image type="content" source="media/edu-admin-center-users.png" alt-text="ポリシーが適用されているユーザーのスクリーンショット。":::

管理者の資格情報でサインインすることにより、[Microsoft Teams 管理センター](https://admin.teams.microsoft.com) で、Teams のすべてのポリシーを管理できます。

### <a name="where-to-find-microsoft-teams-policies"></a>Microsoft Teams ポリシーへのアクセス方法

Teams 管理センターにログインすると、Teams 管理センターの左側のナビゲーションにある [ポリシー] オプションをクリックして、管理する必要がある Teams のあらゆる領域のポリシー設定に移動できます。メッセージング ポリシーの場所のスクリーンショットが含まれています。

:::image type="content" source="media/edu-messaging-policies.png" alt-text="Teams 管理センター内のメッセージング ポリシーの場所。":::

### <a name="how-to-create-and-update-a-policy-definition"></a>ポリシー定義を作成して更新する方法

ユーザーにポリシーを割り当てる前に、Teams を使って、各機能領域のポリシー定義を追加および作成する必要があります。

> [!NOTE]
> 学生と教師には、異なるポリシー定義を設定することをお勧めします。

既定では、すべての新しいユーザー (学生または教師) に各機能領域に対してグローバル (組織全体の既定) ポリシー定義が割り当てられます。 最も厳密なポリシー定義のセットには、グローバル （組織全体の既定） を使用することをお勧めします。 ほとんどの場合、このより厳密なポリシー セットは学生により適しています。 このようにグローバル （組織全体の既定） ポリシー定義を使用すると、新しいユーザーがテナントに追加されたときに最も厳しい制限が適用されます。 このガイダンスに従うには、次の手順に従うことをお勧めします:

1. チームの機能領域ごとに、教師のニーズに合ったポリシー値を使用してカスタム ポリシー定義を作成します （これがないと、教師は、グローバル （組織全体の既定） ポリシー定義で定義されているのと同じ制限付きアクセスを学生に与えることになります）。

1. これらの新しいカスタム ポリシー定義を教師に割り当てます。

1. 学生に適した値を使用して、各機能領域のグローバル （組織全体の既定） ポリシー定義を編集します。

1. グローバル （組織全体の既定） ポリシー定義は、他のポリシー定義が割り当てられていない限り、学生に適用されます。


ポリシー定義を作成または編集するには、作業するポリシー機能領域 (メッセージング ポリシーなど) に移動します。 **[追加]** を選択して、新しいカスタム ポリシー定義を作成します。 既存のポリシー定義を変更するには、**[編集]** を選択します。

:::image type="content" source="media/edu-messaging-policies-add-closeup.png" alt-text="[追加] ボタンを表示した状態での [メッセージング ポリシー] セクションのクローズアップ。":::

ポリシー定義を追加するか編集するかを選択したどうかにかかわらず、このポリシー領域に関連付けられているすべてのポリシー オプションが一覧表示されるビューに移動します。 このリストを使用して、ポリシー定義に設定する値を選択します。

![選んだポリシー領域に関連付けられているポリシー オプションを含むページ。](media/edu-global-policy-definition.png)

> [!IMPORTANT]
> ページから移動する前に、**[保存]** を必ず選択してください。

### <a name="assigning-policy-definitions"></a>ポリシー定義の割り当て 
ポリシー定義をユーザーに割り当てるために使用できる方法は複数あります。 各方法には、独自の利点と欠点があります。これは、お客様の機関のニーズによって異なります。  

ほとんどの場合、グループ ポリシーの割り当てを使用して、ユーザーにポリシーを割り当てることをお勧めします。 この方法を使用すると、より迅速かつシームレスにポリシーを適用することができます。  ポリシー定義が割り当てられているグループにユーザーを追加すると、新しいユーザーはグループのポリシーを自動的に継承します。  これにより、たとえば学期の開始時や終了時に、環境に多数のユーザーが追加および削除された場合に、ポリシー管理が容易になります。  

大規模な組織では、多数のユーザーにポリシーを割り当てる必要がある場合に最適なバッチ ポリシーの割り当てもお勧めします。 これらの適用方法の詳細については、「[学校の多数のユーザーにポリシーを割り当てる](batch-group-policy-assignment-edu.md)」を参照してください。

小規模な機関の場合、または個々の学生または教師のポリシー設定を更新する必要がある場合は、次の手順に従います。  

> [!IMPORTANT]
> 個々のユーザー レベルで指定されたポリシーの割り当ては、ユーザーに割り当てられたグループ ポリシーを上書きします。 グループ ポリシー設定を上書きする場合にのみ、個別のポリシー割り当てを使用していることを確認してください。 

#### <a name="how-to-assign-a-policy-definition-to-a-user"></a>ユーザーにポリシー定義を割り当てる方法

> [!NOTE]
> ポリシー定義を割り当てると、すべてのユーザーとクライアントに反映されるのにしばらく時間がかかる場合があります。 Azure/M365 にユーザー アカウントを初めて作成するとき、教育機関に新しい学生が参加するときに、この操作を行うことが必要となる場合があります。


ポリシー定義を作成または更新した後、ポリシー ページの **[ユーザーの管理]** を選択し、希望のユーザーを検索して、ポリシーを割り当てることにより、ユーザーにポリシー定義を割り当てることができます。

![[メッセージング ポリシー] ページの上部の右側にあるユーザー パネルを管理します。](media/edu-manage-users-pane.png)

また、**[ユーザー]** に移動し、ポリシーを更新するユーザーを選択し、**[ポリシー]** を選択してから **[編集]** を選択することにより、ユーザーにポリシーを割り当てることができます。 ここから、各機能領域に対してユーザーに割り当てるポリシー定義を選択できます。

![[割り当てられているポリシー] ページの右側にある [ユーザー ポリシーの編集] ウィンドウ。](media/edu-edit-user-policies-pane.png)

### <a name="policy-packages-in-microsoft-teams"></a>Microsoft Teams のポリシー パッケージ
> [!NOTE]
> 詳細については、「[Microsoft Teams でポリシー パッケージを管理する](manage-policy-packages.md)」をご確認ください。1 人のユーザーにパッケージを割り当てる方法、最大 5000 人のユーザーにパッケージを一括で割り当てる方法、各パッケージに関連付けられたポリシーの管理と更新を行う方法を紹介しています。

Teams 内のポリシー パッケージは、上記で説明したように事前に定義されたポリシーおよびポリシー設定を収集し、それらを教育機関内の同様の役割を持つユーザーに割り当てます。 ポリシー パッケージにより、ポリシー管理を簡素化し、合理化し、一貫性を高めることができます。 通常の方法では、各ユーザーにポリシーパッケージを割り当て、そのユーザー グループのニーズに合わせて、各パッケージのポリシーを再定義します。 パッケージの設定を更新すると、そのパッケージに割り当てられているすべてのユーザーが一括更新として変更されます。

一般に、教育機関には、学生の年齢や成熟度によって異なる固有のニーズを持つ多くのユーザーが存在します。 たとえば、教師やスタッフが Microsoft Teams にフルアクセスできるようにする一方で、安全で集中できる学習環境を構築するために、学生に対する Microsoft Teams の機能を制限したい場合があります。 教育機関コミュニティにおける異なるコーホートのニーズに基づいて、ポリシー パッケージを使用して設定を調整できます。

> [!IMPORTANT] 
> 最初に、ポリシー パッケージの代わりに、学生に対してグローバル (組織全体の既定) ポリシー定義を使うことをお勧めします。 これにより、組織内の新しいユーザーは常に、学生に適した最も厳格なポリシーのセットを使用できます。 この勧告が機関のニーズを満たしていない場合は、次のいずれかの学生ポリシー パッケージが適している可能性があります。 

この記事で前述したポリシー一覧と同様に、ポリシーパッケージでは、次のようなポリシーが事前に定義されています。

- 会議
- ライブ イベント
- 通話
- Messaging
- アプリのアクセス許可

Microsoft Teams には現在、次のポリシー パッケージが含まれます。

|Microsoft Teams 管理センターで一覧表示されるパッケージ名 |以下の目的での使用に最適です  |説明 |
|:--- |:--- |:--- |
|**Education_Teacher**| 教師およびスタッフ| この一連のポリシーおよびポリシー設定を使用して、Microsoft Teams を通して、組織内の教師およびスタッフがチャット、通話、会議にフルアクセスできるようにします。 |
|**Education_PrimaryStudent**| 小学生  | 教育機関における小学生の場合、Microsoft Teams 内での更なる制限が必要になる場合があります。 この一連のポリシーおよびポリシー設定を使用して、会議の作成と管理、チャット管理、個人的な通話などの機能を制限します。 |
|**Education_SecondaryStudent**| 中学生 | 教育機関における中学生の場合、Microsoft Teams 内での更なる制限が必要になる場合があります。 この一連のポリシーおよびポリシー設定を使用して、会議の作成と管理、チャット管理、個人的な通話などの機能を制限します。 |
|**Education_HigherEducationStudent**| 高校生 | 教育機関における高校生の場合、小中学生に比べて制限は少なくなりますが、ある程度の制限が必要になる場合があります。 この一連のポリシーおよびポリシー設定のセットを使用して、組織内でのチャット、通話、会議へのアクセス権を与えることができます。ただし、学生が外部参加者と共に Microsoft Teams を使用する方法を制限します。 |
|**Education_PrimaryTeacher_RemoteLearning**| 教師およびスタッフ | 小学校教師に適用する一連のポリシーを作成して、学生が最大限に安心して共同でリモート学習に集中できる環境づくりを行います。 |
|**Education_PrimaryStudent_RemoteLearning**| 小学生| 小学生に適用する一連のポリシーを作成して、学生が最大限に安心して共同でリモート学習に集中できる環境づくりを行います。
|||

:::image type="content" source="media/edu-policy-packages-list.png" alt-text="ポリシー パッケージ ページと選択するポリシーパッケージの一覧。":::

ポリシー パッケージにリンクされているポリシーを識別できるように、個々のポリシーにはポリシー パッケージ名が付けられます。 たとえば、教育機関の教師に Education_Teacher ポリシー パッケージを割り当てると、パッケージ内の各ポリシーに対して Education_Teacher という名前のポリシーが作成されます。

![Education_Teacher ポリシー パッケージのスクリーンショット](media/policy-packages-education_teacher.png)

> [!NOTE]
> 教師と管理サポート スタッフが異なるポリシーを必要としていると判断した場合は、既存のパッケージを転用できます。現在使用していないパッケージを特定し、そのグループに合わせて設定を変更します。 どのグループにどのパッケージがあるかを確認することが必要になる場合がありますが、これはパッケージの転用における唯一の障害です。

## <a name="manage-policy-packages"></a>ポリシー パッケージを管理する

### <a name="view"></a>表示

パッケージを割り当てる前に、ポリシー パッケージ内の各ポリシーの設定を表示します。 Microsoft Teams 管理センターの左側のナビゲーションで、[**ポリシーパッケージ**] を選択し、パッケージ名を選択して、ポリシー名を選択します。

事前に定義された値が組織に適しているかどうか、または組織のニーズに基づいてより厳しくあるいは緩めにユーザーをカスタマイズする必要があるかどうかを判断します。

### <a name="customize"></a>カスタマイズ

組織のニーズに合わせてポリシー パッケージのポリシーの設定をカスタマイズします。 ポリシー設定の変更は、パッケージが割り当てられているユーザーに自動的に適用されます。 ポリシー パッケージ内のポリシーの設定を編集するには、Microsoft Teams 管理センターでポリシー パッケージを選び、編集するポリシーの名前を選択して、[**編集**] を選択します。

ポリシー パッケージを割り当てると、パッケージ内のポリシーの設定を変更することもできます。 詳細については、[「ポリシー パッケージのポリシーをカスタマイズする」](manage-policy-packages.md#customize-policies-in-a-policy-package)を参照してください。 

### <a name="assign"></a>割り当て

ポリシー パッケージをユーザーに割り当てます。ユーザーにポリシーが割り当てられている場合は、別のポリシーを割り当てると、最新の割り当てが優先されます。

> [!NOTE]
> カスタム ポリシー パッケージの割り当てを受け取るには、各ユーザーに Advanced Communications アドオンが必要です。 詳細については、「[Microsoft Teams 用 Advanced Communications アドオン](/microsoftteams/teams-add-on-licensing/advanced-communications)」を参照してください。

#### <a name="assign-a-policy-package-to-one-or-several-users"></a>1 人または複数のユーザーにポリシー パッケージを割り当てる

1 人または複数のユーザーにポリシー パッケージを割り当てるには、Microsoft Teams 管理センターの左側のナビゲーションから、[**ポリシー パッケージ**] に移動し、[**ユーザーの管理**] を選択します。  

![管理センターでポリシー パッケージを割り当てる方法のスクリーンショット](media/policy-packages-healthcare-assign.png)

詳細については、[「ポリシー パッケージを割り当てる」](manage-policy-packages.md#assign-a-policy-package)を参照してください。

ユーザーにポリシーが割り当てられている場合は、別のポリシーを割り当てると、最新の割り当てが優先されます。

#### <a name="assign-a-policy-package-to-a-group"></a>ポリシー パッケージをグループに割り当てる

**この機能はプライベート プレビューです**

グループにポリシー パッケージを割り当てると、セキュリティ グループや配布リストなど、ユーザーのグループに複数のポリシーを割り当てることができます。 ポリシーの割り当ては、優先規則に従ってグループのメンバーに反映されます。 グループのメンバーが追加または削除されると、それに応じて継承されたポリシーの割り当てが更新されます。 この方法は、最大 50,000 ユーザーのグループに推奨されますが、より大きなグループでも機能します。

詳細については、[「グループにポリシー パッケージを割り当てる」](assign-policies.md#assign-a-policy-package-to-a-group)を参照してください。

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a>ポリシー パッケージを多数 (一群) のユーザー セットに割り当てる

バッチ ポリシーパッケージの割り当てを使用して、多数のユーザー セットに同時にポリシーパッケージを割り当てることができます。 [New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) コマンドレットを使用して、割り当てたい一群のユーザーおよびポリシー パッケージを送信します。 割り当てはバックグラウンド操作として処理され、各バッチの操作 ID が生成されます。

バッチには最大 5,000 のユーザーを含めることができます。 ユーザーをオブジェクト ID、UPN、SIP アドレス、またはメール アドレスで指定できます。 詳細については、[「一群のユーザーにポリシー パッケージを割り当てる」](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)を参照してください。

## <a name="policies-that-should-be-assigned-for-student-safety"></a>学生の安全を確保するために割り当てるべきポリシー

環境内の学生を保護するために必要な手順の詳細については、「[遠隔教育に Teams を使用している間、学生を安全に保つ](https://support.office.com/article/keeping-students-safe-while-using-meetings-in-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8)」を注意深く確認してください。
