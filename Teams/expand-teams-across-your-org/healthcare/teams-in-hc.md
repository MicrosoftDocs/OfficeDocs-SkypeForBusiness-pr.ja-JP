---
title: 医療機関向け Teams の使用を開始する
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Microsoft Teams のテレケア、EHR 統合、firstline worker システム統合、患者アプリなどの健康ケア機能について説明します。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 7cd05039797f26cd2a6fb3fb93e9b90cc3059651
ms.sourcegitcommit: 43dc627e9fef31a2508f54acf741000551ff68b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2020
ms.locfileid: "48878711"
---
# <a name="get-started-with-teams-for-healthcare-organizations"></a>医療機関向け Teams の使用を開始する

Microsoft Teams には、病院やその他の医療機関にとって便利な多数の telemedicine 機能が用意されています。 Teams の機能は、次の機能を利用して、病院を支援します。

- 仮想アクセスと電子医療記録 (EHR) の統合
- Teams ポリシーパッケージ
- セキュリティで保護されたメッセージング
- Teams テンプレート
- ケアの調整と共同作業

この機能は、医療機関向けの Microsoft Cloud に含まれています。 このソリューションの使い方について詳しくは、Azure、Dynamics 365、Microsoft 365 の機能と、 [医療のための Microsoft Cloud の](https://docs.microsoft.com/industry/healthcare)機能がまとめられています。

医療機関向けコレクションを使用して、Microsoft Teams での正常性チームの共同作業を強化する方法について詳しくは、次のビデオをご覧ください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hqan]

> [!NOTE]
> このセクションの内容は、組織にチームを既に展開していることを前提としています。 まだチームをロールアウトしていない場合は、「 [Microsoft teams をロールアウトする方法](../../How-to-roll-out-teams.md)」を参照してください。

## <a name="virtual-visits-and-electronic-healthcare-record-ehr-integration"></a>仮想アクセスと電子医療記録 (EHR) の統合

Microsoft Teams の完全な会議プラットフォームを使用して、患者との仮想アクセスのスケジュール、管理、実施を行うことができます。

- 組織で既に電子医療レコードまたは EHR を使用している場合は、よりシームレスなエクスペリエンスを実現するために Microsoft Teams を統合することができます。 Microsoft Teams の電子医療記録 (EHR) コネクタを使用すると、clinicians は、EHR システムから直接、Teams の他のプロバイダーとの間で仮想患者のアクセスや相談を簡単に開始できます。 詳細については、「 [Teams による仮想アクセス](ehr-admin.md)」を参照してください。
- サポートされている EHR を使用していない場合は、Teams で Microsoft 予約と予約アプリを使うことができます。 詳細については、「 [Microsoft Teams での予約アプリと仮想訪問](../../bookings-app-admin.md)」を参照してください。

![Microsoft Teams を使用した仮想アクセス](../../media/virtual-visits-teams.png)

## <a name="teams-policy-packages"></a>Teams ポリシーパッケージ

Teams ポリシーパッケージを適用して、Teams で実行できるさまざまな役割を定義します。 たとえば、次のポリシーを指定します。

- 登録した看護師、通話、医師、およびソーシャルワーカーなどの臨床員が、チャット、通話、シフト管理、会議へのフルアクセス権を持つことができるようにします。
- IT 担当者、informatics スタッフ、財務担当者、コンプライアンス責任者などの、医療機関のインフォメーションワーカーは、チャット、通話、会議に完全にアクセスできます。
- 患者の会議室のデバイスの設定を制御します。

詳細については、「 [医療用の Teams ポリシーパッケージ](../../policy-packages-healthcare.md)」を参照してください。

## <a name="secure-messaging"></a>セキュリティで保護されたメッセージング

セキュリティで保護されたメッセージングは、次のような新しい機能を含む、医療チーム内での共同作業をサポート

- メッセージの送信者は、メッセージに特別な優先順位を設定できます。そのため、受信者は、メッセージが読み上げられるまで、受信者に対して繰り返し通知されます。
- メッセージの送信者は、開封確認メッセージを要求できます。そのため、送信したメッセージがメッセージの受信者によって読み上げられたときに通知されます。

これらの機能を組み合わせて使用すると、メッセージの受信と開封による信頼性が向上します。 これらの機能を使用した新しい健康チームは、患者ごとに作成することができます。 これらの機能はポリシーベースであり、個人またはチーム全体に割り当てることができます。

詳細については、「 [医療機関向けのセキュリティで保護されたメッセージングポリシーの概要](messaging-policies-hc.md)」を参照してください。

また、セキュリティで保護されたメッセージングに関連して、医療機関が他のテナントをフェデレーションし、豊富なテナント間通信を実現することができます。 (「 [Microsoft Teams で外部アクセス (フェデレーション) を管理](../../manage-external-access.md)する」を参照してください)。

## <a name="teams-templates-for-healthcare-organizations"></a>医療機関向けの Teams テンプレート

Teams を作成するための新しいテンプレートは、病院の設定に適用するために開発されたもので、近日中に対応する予定です。 これにより、医療員がさまざまな部署または wards の患者の注意を調整するために使用するチームの作成が容易になります。 詳細については、「 [医療機関向けのチームテンプレートの概要](healthcare-templates.md)」を参照してください。 Cardiology、またはケア wards などの社内部署向けにチームを開始したり、その他のテンプレートを開発中に追加したりすることができます。

## <a name="care-coordination-and-collaboration"></a>ケアの調整と共同作業

医療チームを協力して、ケアの調整と Microsoft Teams との共同作業を実現します。

![医療: Teams での正常性チームとの共同作業](../../media/teams-healthcare-collaborate-in-teams.png)

Microsoft Teams を使用すると、医師、clinicians、看護師、および他のスタッフが、次のような Microsoft Teams のコラボレーション機能を活用して効率的に共同作業を行うことができます。

- 正常性チームとインフォメーションワーカー用のチームおよびチャネルをセットアップします。 作業を構造化するための手段としてタブ付きのチャネルを使用します。また、情報ソースのピン留めを行うことができるタブから追加のヘルプが用意されています。
- チャット、メッセージの投稿、通信。 チームは、注意が必要なさまざまな患者について永続的な会話を行うことができます。
- 医療チームのメンバーと通話して会議を行うことができます。 チームの音声、ビデオ、画面共有、録音、および議事録機能を使用して、個々の会議を設定するか、チャネル会議を使って日常の会議を管理します。
- ファイルとドキュメントを保存および共有します。 正常性チームは、Office ドキュメントの共同作業および共同作業を行う単一の仮想化されたチームの一部です。

さらに、チームは Teams のアプリを使用して次のことを行うことができます。

- リストアプリでリストを共有し、情報を追跡する
- タスクアプリでタスクのトラッキングと監視を行う
- 承認アプリを使用して承認を効率化する
- シフトアプリでスケジュールを作成、管理、共有する

### <a name="share-lists-and-track-information-with-the-lists-app"></a>リストアプリでリストを共有し、情報を追跡する

> [!NOTE]
> 2020年10月30日の有効な患者アプリは廃止され、Teams の [リストアプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) で置き換えられました。 リストを使用すると、医療機関のケアチームは、ラウンドやさまざまなチーム会議から一般的な患者の監視までのシナリオのために患者リストを作成できます。

Teams のリストアプリは、チームが情報を追跡し、作業を整理するのに役立ちます。 アプリは、すべての Teams ユーザー用にプレインストールされており、すべてのチームおよびチャネルのタブとして使用できます。 リストは、あらかじめ定義されたテンプレートから、または Excel にデータをインポートすることで、一から作成することができます。

正常性チームは、患者のテンプレートを使って作業を開始できます。 リストを作成して、患者のニーズと状態を追跡することができます。 Excel スプレッドシート上の既存の患者データを表示して、Teams でリストを作成することができます。 これらのリストは、ラウンドと患者のモニタリングなどの状況で、注意を調整するために使用できます。

たとえば、無料の看護師によって、チーム内にすべての正常性チームメンバーを含む患者リストが作成されます。 ラウンドの間に、正常性チームは、モバイルデバイスのチームにアクセスし、リスト内の患者情報を更新します。これは、チームの全員が同期状態を維持できるようになっています。医療チームが主要な正常性パフォーマンス指標を評価して、患者が適切なグライドパスになっていることを確認するための丸めセッションでは、大きな表示画面のチームを使ってこの情報を共有することができます。 サイトを持っていない正常性チームメンバーは、リモートで参加できます。

患者の丸め用に設定されたリストの例を次に示します。

:::image type="content" source="../../media/lists-patients-example.png" alt-text="患者の丸めの例の一覧のスクリーンショット":::

詳細については、「 [Teams で組織のリストアプリを管理](../../manage-lists-app.md)する」を参照してください。

### <a name="track-and-monitor-tasks-with-the-tasks-app"></a>タスクアプリでタスクのトラッキングと監視を行う

チームの [タスク](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070) を使用して、正常性チーム全体の項目を追跡します。 正常性チームは、チームを実行している任意のデバイスから、タスクの作成、割り当て、スケジュール、タスクの分類、状態の更新をいつでも行うことができます。

詳細については、「 [Microsoft Teams で組織のタスクアプリを管理](../../manage-tasks-app.md)する」を参照してください。

### <a name="streamline-approvals-with-the-approvals-app"></a>承認アプリを使用して承認を効率化する

[承認](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3)を使用して、チームのすべての要求とプロセスを合理化します。 チームワークのハブから直接、承認を作成、管理、共有します。 チャット、チャネルの会話、または承認アプリ自体から、承認フローを開始することもできます。 承認の種類を選択し、詳細を追加し、ファイルを添付して、[承認者] を選択するだけです。 申請が送信されると、承認者は通知を受け取り、要求を確認して行動を取ることができます。

組織の承認アプリを許可して、チームに追加することができます。 アプリの管理の詳細については、「 [Microsoft Teams 管理センターでアプリを管理](../../manage-apps.md)する」を参照してください。

### <a name="create-manage-and-share-schedules-with-the-shifts-app-and-firstline-worker-integration"></a>シフトアプリと Firstline Worker の統合を使用してスケジュールを作成、管理、共有する

Microsoft Teams は、シフトのスタッフ機能の調整に使うことができる、シフトアプリと Firstline Worker と統合されています。 たとえば、[シフト] では、看護員のスケジュールを設定して調整することができます。また、看護師はスケジュールを確認し、シフトを交換することができます。 Teams には、組織内の Firstline Worker に割り当てることができる、Firstline の組み込みのワーカーアプリセットアップポリシーが用意されています。 既定では、ポリシーにはアクティビティ、シフト、チャット、および通話の各アプリが含まれています。 このポリシーは、これらのアプリの動作を制御します。たとえば、アプリバーに [シフト] アプリを固定して、チームがすぐにアクセスできるようにします。

詳細については、「 [Microsoft Teams で組織のシフトアプリを管理](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md)する」を参照してください。
