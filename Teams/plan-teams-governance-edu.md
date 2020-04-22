---
title: Microsoft Education のガバナンスに関するよくある質問 (管理者向け)
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Teamsを使用している Microsoft Education グループの管理者からよく寄せられる質問にお答えします。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 79b6e33c6434a1242b7d30322aff77b62f1b42fd
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780216"
---
# <a name="microsoft-education-governance-faq-for-admins"></a>Microsoft Education のガバナンスに関するよくある質問 (管理者向け)

> [!Tip]
> Microsoft Teams での管理の詳細については、次のセッションをご覧ください。[Microsoft Teams でのガバナンス、管理、およびライフサイクル](https://aka.ms/teams-governance)

## <a name="how-do-i-control-team-creation-im-worried-students-are-going-to-create-inappropriate-teams"></a>チームの作成を制御するにはどうすればよいですか? 学生が不適切なチームを作成するのではないかと心配です。

不適切な名前や誤解を招く名前がない場合、または teams の名前付けの構造を指定する場合は、Microsoft 365 グループの名前付けポリシー (現在はプレビュー) を使用できます。

-   **プレフィックス/サフィックスの名前付けポリシー** プレフィックスまたはサフィックスを使用して、チーム (グループ) の名前付け規則を定義できます (例: **GRP_US_My Group_Engineering**) プレフィックスとサフィックスは、チームを作成しているユーザーに基づいて名前に追加される、固定文字列またはユーザー属性 ( **[部署]** など) にすることができます。
-   **カスタムのブロックする単語** 特定の組織のユーザーが作成したチームの名前で使用をブロックする単語のセットをアップロードできます。 たとえば、対象となるグループのチーム名に、 **CEO**、**給与**、**人事**の使用をブロックすることができます。
-   **分類** 組織内のユーザーが Office 365 グループを作成するときに設定できる分類を作成できます。 

> [!IMPORTANT]
> Microsoft 365 グループの名前付けポリシーを使用するには、1つ以上の Microsoft 365 グループのメンバーである一意のユーザーごとに、Azure Active Directory Premium P1 ライセンスまたは Azure AD Basic EDU のライセンスが必要です。

詳しい手順については、「[Office グループの名前付けポリシー](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)」を参照してください。

> [!Note]
> 他のシステムからの入力 (School Data Sync など) を使用してチームが自動的に作成される場合は、入力データが、構成した名前付けポリシーに準拠していることを確認します。そうでない場合は、チームの作成に失敗します。

## <a name="can-i-see-who-created-a-team"></a>チームを作成したユーザーを確認できますか?

特定のチームの作成者を確認するには、「[Microsoft Teams でイベントの監査ログを検索する](audit-log-events.md)」を参照してください。

## <a name="can-i-control-who-can-create-teams"></a>チームを作成できるユーザーを制御できますか?

一般的に、誰もチームを作成できないようにすることをお勧めします。 すべてのユーザーがチームを作成できるのであれば、Teams はより広く導入されるでしょう。 教職員、教師、生徒は Teams を使用して研究グループや特別な目的のグループを作成できます。 これにより、Teams は教室の内外で受け入れられるようになります。

私たちの経験では、ユーザー教育は責任ある Teams の使用を確実にするのに役立ちます。 チームの作成が匿名ではないことをユーザーが理解したら、carelessly の作成による影響を理解し、ツールを悪用しないようにすることができます。

チームを作成できるユーザーを管理する必要がある場合は、「 [Microsoft 365 グループを作成できるユーザーを管理](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)する」を参照してください。

## <a name="how-do-i-automatically-create-a-team-for-each-course-at-the-beginning-of-the-semester-or-quarter"></a>学期または四半期の開始時にコースごとにチームを自動的に作成するにはどうすればよいですか?

各学期または四半期の最初に、いくつかの新しいチームを用意する必要があります。 これらのチームを自動的に作成し、適切なユーザーを選択し、適切な権限を設定するという自動化されたアプローチは適切かもしれません。

-   School Data Sync は、Exchange Online と SharePoint Online 用の Microsoft 365 グループ、Microsoft Teams と OneNote Class notebook のクラスチーム、他の多くのサードパーティアプリケーションの古いとシングルサインオン (SSO) 統合を作成することができます。 詳細については、「[School Data Sync の概要](https://docs.microsoft.com/schooldatasync/overview-of-school-data-sync)」を参照してください。
-   PowerShell を使用すると、チームやチャネルを作成して、設定を自動的に構成できます。 詳細については、「[Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」を参照してください。
-   Microsoft Graph API (現在ベータ版) を使用して、チームの作成、構成、複製、アーカイブを行うことができます。 詳細については、「[Microsoft Graph API を使用して Microsoft Teams で作業する](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)」を参照してください。

> [!TIP]
> School Data Sync は、同期された各クラスに Office 365 グループを作成し、[非表示のグループ メンバーシップを有効](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945)にするので、そのクラス内の教師と生徒だけがそのクラスのメンバーを見ることができます。 別のプロセスを使用してクラス グループを作成している場合は、New-UnifiedGroup コマンドレットの HiddenGroupMembershipEnabled パラメーターを使用して、同じプライバシー要件を満たすことができます。

## <a name="how-do-i-deal-with-teams-when-the-semester-or-quarter-ends"></a>学期や四半期が終わったときにチームにどのような対処すればよいですか?

学校の学期または四半期が超過した場合にチームデータをどのように処理するかについては、最初に検討することをお勧めします。削除するか、コースを完了した後でも学生が利用できるようにするかどうかを検討してください。 学校の予定表を念頭に置いて、設定したポリシーが休日と競合しないようにします。 戦略の実装には次のツールを使用できます。

-   **アイテム保持ポリシー:** 指定した期間を経過したすべての古いデータが削除されます。古いデータがチャット (すべてまたは一部のユーザー用) およびチャンネルから削除されます。 また、コンテンツを保持するようにチームを構成して、削除できないようにすることもできます。 詳細については、「[Microsoft Teams の保持ポリシー](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011)」を参照してください。
-   **有効期限ポリシー:** 特定の日数が経過した後に、期限切れになるようにチームを構成します。 有効期限の 30 日前に、チームのすべての所有者に、チームの更新が必要であることが通知されます。それ以外の場合は、削除されます (管理者は、削除されたチームをさらに 30 日間復元できます)。 この設定は、未使用のチームが使用されていない状況を確認するのに非常に便利です。 詳細については、「[Office 365 グループの有効期限ポリシー](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733)」を参照してください。

-   **チームをアーカイブする:** この設定で、チームは読み取り専用モードになります。 参照して検索することはできますが、新しい投稿を追加することはできません。 「[チームをアーカイブする、または復元する](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)」は、チームの所有者がチームをアーカイブする方法を説明します。チームの所有者は、 「[Graph API (ベータ)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)」を使用してチームをアーカイブまたは復元することもできます。
 
> [!IMPORTANT]
> Microsoft 365 グループの有効期限ポリシーを使用するには、1つ以上の Microsoft 365 グループのメンバーである個々のユーザーに対して Azure Active Directory Premium P1 ライセンスが必要です。

## <a name="are-there-team-templates-for-my-faculty-members-to-use-when-creating-a-team"></a>チームを作成するときに教職員用に使用できるチームのテンプレートはありますか?

はい。 ユーザーは新しいチームを作成するときに**既存のテンプレートからチームを作成する**ことを選択でき、Teams の所有者も使用可能なテンプレートから [Graph API (ベータ版)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) を使用して新しいチームを作成することができます。

## <a name="what-tasks-can-i-automate-via-powershell-or-graph"></a>PowerShell や Graph を介して自動化できるタスクは何がありますか?

[Microsoft Graph API (ベータ版)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) で、次の操作を実行できます。

-   チームの作成。
-   メンバーおよび所有者の追加。
-   チャネルの追加。
-   アプリの追加。
-   既存のチームを複製してこれらのステップを短縮し、そのタブも取得。
-   作成したばかりのチームへのリンクをユーザーに提供。
-   不要になったメンバー、所有者、チャネル、アプリの削除。
-   アクティブでなくなったチームのアーカイブ。 
-   チームの削除。
-   チャネル スレッドの作成

[PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) では、次の操作を実行できます。

-   チームの作成。
-   メンバーおよび所有者の追加。
-   チャネルの追加。
-   不要になったメンバー、所有者、チャネルの削除。
-   チームの削除。

> [!TIP]
> Graph API と PowerShell コマンドレットで継続的に機能を追加。 機能拡張については、「[Microsoft Graph API (ベータ版)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)」および 「[PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」の記事をよく確認してください。  


## <a name="can-i-control-what-teams-features-my-faculty-and-students-have-access-to"></a>教職員と学生がどの Teams の機能にアクセスできるかを制御できますか?

はい。 ポリシーを使用して、ユーザーがアクセスする特定のメッセージ、会議、通話、ライブ イベント機能を制御できます。 テナント全体の設定を使用して、同じ設定をすべてに適用するか、必要に応じてユーザーレベルのポリシーを適用することができます。 

Teams のポリシーの詳細については、「[組織の Microsoft Teams の設定を管理する](enable-features-office-365.md)」を参照してください。
 
## <a name="can-i-control-what-external-parties-my-faculty-and-students-collaborate-with"></a>教職員と学生が共同作業を行う外部関係者を制御できますか?

ゲスト アクセスを使用すると、テナント外のユーザーを招待することができます。これは、研究の共同作業や来客の講義に便利です。

-   ドメインに基づいてゲストを許可またはブロックするには、ドメインのホワイトリストを使用します。
-   特定の Microsoft 365 グループやチームのゲストアクセスを有効または無効にして、ゲストを招待できるチーム (およびできない) を制御します。
-   監査ログを使用して、招待されたゲストに送信された警告を確認します。

詳細については、「 [Microsoft 365 グループのゲストアクセス](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage)」を参照してください。

## <a name="what-information-can-i-review-about-existing-teams"></a>既存のチームについてどのような情報を確認できますか?

監査ログを確認すると、次の事項を確認できます。

-   誰がどのチームにゲストとして招待されたか。
-   誰がどのチームを作成したのか。

詳細については、「[Microsoft Teams でイベントの監査ログを検索する](audit-log-events.md)」を参照してください。

## <a name="teams-evolves-so-quickly-how-can-i-stay-up-to-date"></a>Teams は急速に進化しています。 最新の状態を維持するにはどうすればよいですか?

Teams の最新の更新プログラムを取得するには、次のリソースをお勧めします。

-   [Microsoft Teams の新機能](https://support.office.com/article/What-s-new-in-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
-   [Microsoft Teams のブログ](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)
