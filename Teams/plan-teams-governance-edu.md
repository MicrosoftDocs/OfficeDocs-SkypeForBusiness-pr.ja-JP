---
title: Microsoft Education のガバナンスに関するよくある質問 (管理者向け)
author: cichur
ms.author: v-cichur
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
ms.openlocfilehash: ada92509adc0f066bf957ddaa8f5de8dd0c47653
ms.sourcegitcommit: 8906fc384cd13255972df53d2a07d12589154d42
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2021
ms.locfileid: "52085849"
---
# <a name="microsoft-education-governance-faq-for-admins"></a>Microsoft Education のガバナンスに関するよくある質問 (管理者向け)

> [!Tip]
> Microsoft Teams での管理の詳細については、次のセッションをご覧ください。[Microsoft Teams でのガバナンス、管理、およびライフサイクル](https://aka.ms/teams-governance)

## <a name="how-do-i-control-team-creation-im-worried-students-are-going-to-create-inappropriate-teams"></a>チームの作成を制御するにはどうすればよいですか? 学生が不適切なチームを作成するのではないかと心配です。

不適切な名前や誤解を招く名前を避けるため、またはチームの名前の構造を高くするために、Microsoft 365 Groups 名前付けポリシー (現在プレビュー中) を使用できます。

-   **プレフィックス/サフィックスの名前付けポリシー** プレフィックスまたはサフィックスを使用して、チーム (グループ) の名前付け規則を定義できます (例: **GRP_US_My Group_Engineering**) プレフィックスとサフィックスは、チームを作成しているユーザーに基づいて名前に追加される固定文字列またはユーザー属性 **([Department]** など) です。
-   **カスタムのブロックする単語** 特定の組織のユーザーが作成したチームの名前で使用をブロックする単語のセットをアップロードできます。 たとえば、CEO、Payroll、HR という用語が、適用されないグループのチーム名で使用されるのをブロックできます。 
-   **分類** 組織内のユーザーがグループを作成するときに設定できる分類Microsoft 365できます。 

> [!IMPORTANT]
> Microsoft 365 グループ名前付けポリシーを使用するには、1 つ以上の Microsoft 365 グループのメンバーである一意のユーザーごとに、Azure Active Directory プレミアム P1 ライセンスまたは Azure AD Basic EDU ライセンスが必要です。

詳しい手順については、「[Office グループの名前付けポリシー](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)」を参照してください。

> [!Note]
> チームが別のシステムからの入力 (学校データ同期 など) を使用して自動的に作成される場合は、入力データが構成した名前付けポリシーに準拠していることを確認します。作成しない場合、チームの作成は失敗します。

## <a name="can-i-see-who-created-a-team"></a>チームを作成したユーザーを確認できますか?

特定のチームの作成者を確認するには、「[Microsoft Teams でイベントの監査ログを検索する](audit-log-events.md)」を参照してください。

## <a name="can-i-control-who-can-create-teams"></a>チームを作成できるユーザーを制御できますか?

一般的に、誰もチームを作成できないようにすることをお勧めします。 すべてのユーザーがチームを作成できるのであれば、Teams はより広く導入されるでしょう。 教職員、教師、生徒は Teams を使用して研究グループや特別な目的のグループを作成できます。 これにより、Teams は教室の内外で受け入れられるようになります。

私たちの経験では、ユーザー教育は責任ある Teams の使用を確実にするのに役立ちます。 ユーザーは、チームの作成が匿名ではないと理解するとすぐに、チームを不注意で作成した場合の影響を理解し、ツールの誤使用を敬遠する傾向があります。

チームを作成できるユーザーを制御する必要がある場合は、「グループを作成できるユーザーを管理する[」をMicrosoft 365してください](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)。

## <a name="how-do-i-automatically-create-a-team-for-each-course-at-the-beginning-of-the-semester-or-quarter"></a>学期または四半期の開始時にコースごとにチームを自動的に作成するにはどうすればよいですか?

各学期または四半期の始めには、新しいチームが必要です。 これらのチームを自動的に作成し、適切なユーザーを選択し、適切な権限を設定するという自動化されたアプローチは適切かもしれません。

-   学校データ同期 では、Exchange Online および SharePoint Online 用の Microsoft 365 グループ、Microsoft Teams および OneNote Class Notebook 用のクラス チーム、Intune for Education の学校グループ、他の多くのサード パーティ 製アプリケーションのリストおよびシングル サインオン (SSO) 統合を作成できます。 詳細については、「[School Data Sync の概要](/schooldatasync/overview-of-school-data-sync)」を参照してください。
-   PowerShell を使用すると、チームやチャネルを作成して、設定を自動的に構成できます。 詳細については、「[Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps)」を参照してください。
-   Microsoft Graph API (現在ベータ版) を使用して、チームの作成、構成、複製、アーカイブを行うことができます。 詳細については、「[Microsoft Graph API を使用して Microsoft Teams で作業する](/graph/api/resources/teams-api-overview)」を参照してください。

> [!TIP]
> 学校データ同期クラスごとに Microsoft 365 グループを作成し、非表示のグループ メンバーシップを有効[](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945)にすることで、クラス内の教師と学生だけがそのクラスのメンバーを表示できます。 別のプロセスを使用してクラス グループを作成している場合は、New-UnifiedGroup コマンドレットの HiddenGroupMembershipEnabled パラメーターを使用して、同じプライバシー要件を満たすことができます。

## <a name="how-do-i-deal-with-teams-when-the-semester-or-quarter-ends"></a>学期や四半期が終わったときにチームにどのような対処すればよいですか?

学校の学期または四半期が終了した場合に、Teams データを処理する方法を最初に考えるのをお勧めします。このデータを削除するか、コースを完了した後でも学生が利用できる状態に保つかについて考えすることをお勧めします。 設定したポリシーが祝日と競合しないので、学校の予定表を念頭に置いておきます。 戦略の実装には次のツールを使用できます。

-   **アイテム保持ポリシー:** 指定した期間を経過したすべての古いデータが削除されます。古いデータがチャット (すべてまたは一部のユーザー用) およびチャンネルから削除されます。 コンテンツを削除Teamsコンテンツを保持するアカウントを構成できます。 詳細については、「[Microsoft Teams の保持ポリシー](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011)」を参照してください。
-   **有効期限ポリシー:** 特定の日数が経過した後に、期限切れになるようにチームを構成します。 有効期限の 30 日前に、チームのすべての所有者に、チームの更新が必要であることが通知されます。それ以外の場合は、削除されます (管理者は、削除されたチームをさらに 30 日間復元できます)。 この設定は、未使用のチームが使用されていない状況を確認するのに非常に便利です。 詳細については、「Microsoft 365[ポリシー」を参照してください](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733)。

-   **チームをアーカイブする:** この設定で、チームは読み取り専用モードになります。 参照して検索することはできますが、新しい投稿を追加することはできません。 「[チームをアーカイブする、または復元する](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)」は、チームの所有者がチームをアーカイブする方法を説明します。チームの所有者は、 「[Graph API (ベータ)](/graph/api/resources/teams-api-overview)」を使用してチームをアーカイブまたは復元することもできます。
 
> [!IMPORTANT]
> Microsoft 365 グループの有効期限ポリシーを使用するには、Azure Active Directory プレミアムグループのメンバーである一意のユーザーごとに P1 ライセンスをMicrosoft 365があります。

## <a name="are-there-team-templates-for-my-faculty-members-to-use-when-creating-a-team"></a>チームを作成するときに教職員用に使用できるチームのテンプレートはありますか?

はい。 ユーザーは新しいチームを作成するときに **既存のテンプレートからチームを作成する** ことを選択でき、Teams の所有者も使用可能なテンプレートから [Graph API (ベータ版)](/graph/api/resources/teams-api-overview) を使用して新しいチームを作成することができます。

## <a name="what-tasks-can-i-automate-via-powershell-or-graph"></a>PowerShell や Graph を介して自動化できるタスクは何がありますか?

[Microsoft Graph API (ベータ版)](/graph/api/resources/teams-api-overview) で、次の操作を実行できます。

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

[PowerShell](/powershell/module/teams/?view=teams-ps) では、次の操作を実行できます。

-   チームの作成。
-   メンバーおよび所有者の追加。
-   チャネルの追加。
-   不要になったメンバー、所有者、チャネルの削除。
-   チームの削除。

> [!TIP]
> Graph API と PowerShell コマンドレットで継続的に機能を追加。 機能拡張については、「[Microsoft Graph API (ベータ版)](/graph/api/resources/teams-api-overview)」および 「[PowerShell](/powershell/module/teams/?view=teams-ps)」の記事をよく確認してください。  


## <a name="can-i-control-what-teams-features-my-faculty-and-students-have-access-to"></a>教職員と学生がどの Teams の機能にアクセスできるかを制御できますか?

はい。 ポリシーを使用して、ユーザーがアクセスする特定のメッセージ、会議、通話、ライブ イベント機能を制御できます。 テナント全体の設定を使用して、同じ設定をすべてに適用するか、必要に応じてユーザーレベルのポリシーを適用することができます。 

Teams のポリシーの詳細については、「[組織の Microsoft Teams の設定を管理する](enable-features-office-365.md)」を参照してください。
 
## <a name="can-i-control-what-external-parties-my-faculty-and-students-collaborate-with"></a>教職員と学生が共同作業を行う外部関係者を制御できますか?

ゲスト アクセスを使用すると、テナント外のユーザーを招待することができます。これは、研究の共同作業や来客の講義に便利です。

-   ドメインの許可リストを使用して、ドメインに基づいてゲストを許可またはブロックします。
-   特定のグループとチームのゲスト アクセスMicrosoft 365、ゲストを招待できる (または招待できない) チームを制御します。
-   監査ログを使用して、招待されたゲストに送信された警告を確認します。

詳細については、「グループ内の[ゲスト アクセス」をMicrosoft 365してください](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage)。

## <a name="what-information-can-i-review-about-existing-teams"></a>既存のチームについてどのような情報を確認できますか?

監査ログを確認すると、次の事項を確認できます。

-   誰がどのチームにゲストとして招待されたか。
-   誰がどのチームを作成したのか。

詳細については、「[Microsoft Teams でイベントの監査ログを検索する](audit-log-events.md)」を参照してください。

## <a name="teams-evolves-so-quickly-how-can-i-stay-up-to-date"></a>Teams は急速に進化しています。 最新の状態を維持するにはどうすればよいですか?

Teams の最新の更新プログラムを取得するには、次のリソースをお勧めします。

-   [Microsoft Teams の新機能](https://support.office.com/article/What-s-new-in-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
-   [Microsoft Teams のブログ](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)