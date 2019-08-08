---
title: IT 専門家向けの Microsoft Education のガバナンスに関するよくある質問 - Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Teams を使用する Microsoft エデュケーショングループの管理者からよく寄せられる質問に対する回答です。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b1bfa8f141f7aa8ce8dd258610ff8b510ff66aac
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237653"
---
# <a name="microsoft-education-governance-faq-for-admins"></a>Microsoft Education のガバナンスに関するよくある質問 (管理者向け)

> [!Tip]
> Microsoft Teams の管理について詳しくは、次のセッションをご覧ください。 [Microsoft teams でのガバナンス、管理、およびライフサイクル](https://aka.ms/teams-governance)

## <a name="how-do-i-control-team-creation-im-worried-students-are-going-to-create-inappropriate-teams"></a>チームの作成を管理するにはどうすればよいですか? 学生が不適切なチームを作成しようとしている心配があります。

不適切な名前や誤解を招く名前がないようにしたり、teams の名前の構造を指定したりするために、Office 365 グループの名前付けポリシー (現在はプレビュー) を使用できます。

-   **プレフィックスとサフィックスの名前付けポリシー**プレフィックスまたはサフィックスを使用して、teams (グループ) の名前付け規則 (たとえば、 **GRP_US_My Group_Engineering**) を定義できます。 プレフィックスとサフィックスは、チームを作成しているユーザーに基づいて名前に追加される、固定文字列またはユーザー属性 ( **[部署]** など) にすることができます。
-   **ユーザー設定のブロック**された単語特定の組織のユーザーが、作成したチームの名前で使用をブロックされている一連の単語をアップロードできます。 たとえば、対象となるグループのチーム名に、 **CEO**、**給与**、**人事**の使用をブロックすることができます。
-   **分類**組織内のユーザーが Office 365 グループを作成するときに設定できる分類を作成することができます。 

> [!IMPORTANT]
> Office 365 グループの名前付けポリシーを使用するには、1つ以上の Office 365 グループのメンバーである一意のユーザーごとに、Azure Active Directory Premium P1 ライセンスまたは Azure AD Basic EDU のライセンスが必要です。

詳細な手順については、「 [Office グループの名前付けポリシー](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)」を参照してください。

> [!Note]
> 他のシステムからの入力 (School Data Sync など) を使用してチームが自動的に作成される場合は、入力データが、構成した名前付けポリシーに準拠していることを確認します。そうでない場合は、チームの作成に失敗します。

## <a name="can-i-see-who-created-a-team"></a>チームを作成したユーザーを確認できますか?

特定のチームを作成したユーザーを確認するには、「 [Microsoft Teams でイベントの監査ログを検索](audit-log-events.md)する」を参照してください。

## <a name="can-i-control-who-can-create-teams"></a>チームを作成できるユーザーを管理することはできますか?

一般に、チームの作成を禁止することをお勧めします。 だれでもチームを作成できる場合、チームは広く採用されている可能性が高くなります。 教員、教師、または学生が Teams を使って、研究グループや特別な趣味のグループを作成することができます。 これにより、チームが教室の内外で受け入れられるようになります。

このエクスペリエンスでは、ユーザー教育によってチームの使用が確実に行われます。 チームの作成が匿名ではないことをユーザーが理解したら、carelessly の作成による影響を理解し、ツールを悪用しないようにすることができます。

チームを作成できるユーザーを管理する必要がある場合は、「 [Office 365 グループを作成できるユーザーを管理](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)する」を参照してください。

## <a name="how-do-i-automatically-create-a-team-for-each-course-at-the-beginning-of-the-semester-or-quarter"></a>学期または四半期の最初に各コースのチームを自動的に作成するには、どうすればよいですか。

各学期または四半期の最初に、いくつかの新しいチームを用意する必要があります。 これらのチームを自動的に作成し、適切なユーザーと一緒に入力し、適切なアクセス許可を設定するために、自動化された方法が必要になることがあります。

-   School Data Sync では、Exchange Online と SharePoint Online 用の Office 365 グループの作成、Microsoft Teams と OneNote Class notebook のクラスチーム、古いとシングルサインオン (SSO) 統合を行うことができます。サードパーティアプリケーション。 詳細について[は、「School Data Sync の概要」を](https://docs.microsoft.com/schooldatasync/overview-of-school-data-sync)参照してください。
-   PowerShell を使用すると、チームとチャネルを作成し、設定を自動的に構成することができます。 詳細については、「 [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 」を参照してください。
-   Microsoft Graph API (現在はベータ版) を使用して、チームの作成、構成、複製、アーカイブを行うことができます。 詳細については[、「Microsoft GRAPH API を使用して Microsoft Teams で作業する」を](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)参照してください。

> [!TIP]
> School Data Sync は、各クラスの Office 365 グループを作成し、[非表示のグループメンバーシップを有効](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945)にします。これにより、クラス内の教師と学生のみがそのクラスのメンバーを表示できるようになります。 別のプロセスでクラスグループを作成する場合は、同じプライバシー要件を満たすために、Get-unifiedgroup コマンドレットの HiddenGroupMembershipEnabled パラメーターを使用します。

## <a name="how-do-i-deal-with-teams-when-the-semester-or-quarter-ends"></a>半期または四半期が終了したときに teams を処理する方法を教えてください。

学校の学期または四半期が超過した場合にチームデータをどのように処理するかについては、最初に検討することをお勧めします。削除するか、コースを完了した後でも学生が利用できるようにするかどうかを検討してください。 学校の予定表を念頭に置いて、設定したポリシーが休日と競合しないようにします。 戦略を実装するには、次のツールを使用できます。

-   **アイテム保持ポリシー:** 指定した年齢より古いデータをすべて削除するには、この設定を使用して、古いデータがチャット (すべてのユーザーまたは一部のユーザー) およびチャネルから削除されるようにします。 また、コンテンツを保持するようにチームを構成して、削除できないようにすることもできます。 詳細については、「 [Microsoft Teams のアイテム保持ポリシー](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011)」を参照してください。
-   **有効期限ポリシー:** 一定の期間が経過すると、チームの有効期限が切れるように設定します。 有効期限が切れる30日前に、チームのすべての所有者にチームの更新が必要であることが通知されます。それ以外の場合は、削除されます (ただし、管理者は削除されたチームを追加で30日間復元できます)。 この設定は、未使用のチームが sunsetted であることを確認するのに非常に便利です。 詳細については、「 [Office 365 グループの有効期限ポリシー](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733)」を参照してください。

-   **アーカイブチーム:** この設定では、チームが読み取り専用モードになります。 それらのユーザーは引き続き参照して検索できますが、新しい投稿を追加することはできません。 チーム[のアーカイブまたは復元](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)チーム所有者がチームをアーカイブする方法について説明します。チーム所有者は、 [GRAPH API (ベータ)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)を使ってチームをアーカイブまたは復元することもできます。
 
> [!IMPORTANT]
> Office 365 グループの有効期限ポリシーを使用するには、1つ以上の Office 365 グループのメンバーである個々のユーザーに対して Azure Active Directory Premium P1 ライセンスが必要です。

## <a name="are-there-team-templates-for-my-faculty-members-to-use-when-creating-a-team"></a>チームの作成時に教職員のメンバーが使用するチームテンプレートはありますか。

はい。 ユーザーは、新しいチームを作成するときに、**既存のテンプレートから [チームの作成**] を選ぶことができます。また、チーム所有者は、使用可能なテンプレートから新しいチームを作成するために[Graph API (ベータ)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)を使用することもできます。

## <a name="what-tasks-can-i-automate-via-powershell-or-graph"></a>PowerShell または Graph を使用して自動化できるタスク

[Microsoft GRAPH API (ベータ版)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)では、次の操作を行うことができます。

-   チームを作成します。
-   メンバーと所有者を追加します。
-   チャネルを追加します。
-   アプリを追加します。
-   既存のチームを複製し、そのタブを表示することによって、これらの手順を実行します。
-   作成したチームへのリンクをユーザーに提供します。
-   不要になったメンバー、所有者、チャネル、アプリを削除します。
-   チームがアクティブでなくなったら、チームをアーカイブします。 
-   チームを削除します。
-   チャネルスレッドの作成

[PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)では、次の操作を行うことができます。

-   チームを作成します。
-   メンバーと所有者を追加します。
-   チャネルを追加します。
-   不要になったメンバー、所有者、チャネルを削除します。
-   チームを削除します。

> [!TIP]
> Graph API と PowerShell コマンドレットは、常に機能を追加しています。 機能拡張については、 [Microsoft GRAPH API (ベータ)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)と[PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)の記事をよく確認してください。  


## <a name="can-i-control-what-teams-features-my-faculty-and-students-have-access-to"></a>教員や学生がアクセスできる Teams を制御できますか?

はい。 ポリシーを使用して、ユーザーがアクセスできる特定のメッセージ、会議、通話、ライブイベントの機能を制御することができます。 テナント全体の設定を使用して、同じ設定をすべてに適用したり、必要に応じてユーザーレベルのポリシーを適用したりすることができます。 

チームポリシーの詳細については、「[組織の Microsoft Teams の設定を管理](enable-features-office-365.md)する」を参照してください。
 
## <a name="can-i-control-what-external-parties-my-faculty-and-students-collaborate-with"></a>教職員と学生が共同作業を行う外部関係者を管理することはできますか?

ゲストアクセスを使用すると、テナントの外部からユーザーを招待することができます。これは、グループ作業やゲストの講義に役立てることができます。

-   ドメインに基づいてゲストを許可またはブロックするには、ドメインの空白記号を使用します。
-   特定の Office 365 グループやチームのゲストアクセスを有効または無効にして、ゲストを招待できるチーム (およびできない) を制御します。
-   監査ログを使用して、招待されたゲストに送信されたアラートを確認します。

詳細については、「 [Office 365 グループのゲストアクセス](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage)」を参照してください。

## <a name="what-information-can-i-review-about-existing-teams"></a>既存のチームについてどのような情報を確認できますか?

監査ログで次の情報を確認できます。

-   誰がゲストとして招待したのかを確認します。
-   チームを作成したユーザー。

詳細については、「 [Microsoft Teams でイベントの監査ログを検索する](audit-log-events.md)」を参照してください。

## <a name="teams-evolves-so-quickly-how-can-i-stay-up-to-date"></a>チームはすばやく進化します。 最新の状態を維持するにはどうすればよいですか?

チームの最新の更新プログラムを取得するには、次のリソースをお勧めします。

-   [Microsoft Teams の新機能](https://support.office.com/article/What-s-new-in-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
-   [Microsoft Teams ブログ](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)
