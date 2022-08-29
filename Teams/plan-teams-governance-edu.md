---
title: IT 管理者向けの Microsoft Education FAQ
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Teamsを使用している Microsoft Education グループの管理者からよく寄せられる質問にお答えします。
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6970cb95ff85ace99cc70cb81620e7a5de322496
ms.sourcegitcommit: c19ac3be42cc4b8409c8d512bbe3156736af0309
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/24/2022
ms.locfileid: "67426854"
---
# <a name="microsoft-education-faq-for-it-admins"></a>IT 管理者向けの Microsoft Education FAQ

> [!Tip]
> Microsoft Teams での管理の詳細については、次のセッションをご覧ください。[Microsoft Teams でのガバナンス、管理、およびライフサイクル](https://aka.ms/teams-governance)

## <a name="how-do-i-control-team-creation-im-worried-students-are-going-to-create-inappropriate-teams"></a>チームの作成を制御するにはどうすればよいですか? 学生が不適切なチームを作成することを心配していますか?

不適切な名前や誤解を招く名前を避けるため、またはチームの名前付け方法の構造を増やすために、Microsoft 365 グループ名前付けポリシー (現在プレビュー段階) を使用できます。

- **プレフィックス/サフィックスの名前付けポリシー** プレフィックスまたはサフィックスを使用して、チーム (グループ) の名前付け規則を定義できます (例: **GRP_US_My Group_Engineering**) プレフィックスとサフィックスには、チームを作成しているユーザーに基づいて名前に追加される固定文字列またはユーザー属性 ( **[部門]** など) を指定できます。
- **カスタムのブロックする単語** 特定の組織のユーザーが作成したチームの名前で使用をブロックする単語のセットをアップロードできます。 たとえば、**CEO**、**給与、****人事** という用語が、適用されていないグループのチーム名で使用されないようにブロックできます。
- **分類** 組織内のユーザーが Microsoft 365 グループを作成するときに設定できる分類を作成できます。

> [!IMPORTANT]
> Microsoft 365 グループ名前付けポリシーを使用するには、1 つ以上の Microsoft 365 グループのメンバーである一意のユーザーごとに、Azure Active Directory Premium P1 ライセンスまたは Azure AD Basic EDU ライセンスが必要です。

詳しい手順については、「[Office グループの名前付けポリシー](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)」を参照してください。

> [!NOTE]
> 別のシステムからの入力 (学校データ同期など) を使用してチームが自動的に作成される場合は、入力データが構成した名前付けポリシーに準拠していることを確認します。そうでない場合、チームの作成は失敗します。

## <a name="can-i-see-who-created-a-team"></a>チームを作成したユーザーを確認できますか?

特定のチームの作成者を確認するには、「[Microsoft Teams でイベントの監査ログを検索する](audit-log-events.md)」を参照してください。

## <a name="can-i-control-who-can-create-teams"></a>チームを作成できるユーザーを制御できますか?

一般的に、誰もチームを作成できないようにすることをお勧めします。 すべてのユーザーがチームを作成できるのであれば、Teams はより広く導入されるでしょう。 教職員、教師、生徒は Teams を使用して研究グループや特別な目的のグループを作成できます。 この機能は、Teams を教室の内外で受け入れるのに役立ちます。

私たちの経験では、ユーザー教育は責任ある Teams の使用を確実にするのに役立ちます。 ユーザーは、チームの作成が匿名ではないことを理解するとすぐに、不注意にチームを作成することの影響を理解し、ツールの悪用を敬遠する傾向があります。

チームを作成できるユーザーを制御する必要がある場合は、「Microsoft 365 グループを[作成できるユーザーを管理する」](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)を参照してください。

## <a name="how-do-i-automatically-create-a-team-for-each-course-at-the-beginning-of-the-semester-or-quarter"></a>学期または四半期の開始時にコースごとにチームを自動的に作成するにはどうすればよいですか?

各半期または四半期の開始時に、新しいチームが必要になります。 これらのチームを自動的に作成し、適切なユーザーを選択し、適切な権限を設定するという自動化されたアプローチは適切かもしれません。

- School Data Sync では、Exchange Onlineと SharePoint Online のMicrosoft 365 グループ、Microsoft Teams および OneNote クラス ノートブックのクラス チーム、教育機関向けのIntune用の学校グループ、その他多くのサードパーティ アプリケーションの名簿とシングル Sign-On (SSO) の統合を作成できます。 詳細については、「[School Data Sync の概要](/schooldatasync/overview-of-school-data-sync)」を参照してください。
- PowerShell を使用すると、チームやチャネルを作成して、設定を自動的に構成できます。 詳細については、 [Microsoft Teams PowerShell に関するページを](/powershell/module/teams/?view=teams-ps)参照してください。
- Microsoft Graph API (現在プレビュー段階) を使用して、チームの作成、構成、複製、アーカイブを行うことができます。 詳細については、「[Microsoft Graph APIを使用して Microsoft Teams を操作する」を参照してください](/graph/api/resources/teams-api-overview)。

> [!TIP]
> School Data Sync は、同期されたクラスごとに Microsoft 365 グループを作成し、 [非表示のグループ メンバーシップを有効にして](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945) 、クラス内の教師と学生だけがそのクラスのメンバーを表示できるようにします。 別のプロセスを使用してクラス グループを作成している場合は、New-UnifiedGroup コマンドレットの HiddenGroupMembershipEnabled パラメーターを使用して、同じプライバシー要件を満たすことができます。

## <a name="how-do-i-deal-with-teams-when-the-semester-or-quarter-ends"></a>学期や四半期が終わったときにチームにどのような対処すればよいですか?

最初に、学校の半期または四半期が終わったときに Teams データを処理する方法について検討することをお勧めします。コースを完了した後でも、削除するか、学生が利用できるようにしておくかを検討することをお勧めします。 設定したポリシーが休日と競合しないように、学校の予定表を念頭に置いておく必要があります。 戦略の実装には次のツールを使用できます。

- **アイテム保持ポリシー:** このポリシーを使用して、指定した年齢より古いデータをすべて削除して、古いデータがチャット (すべてまたは一部のユーザー) およびチャネルから確実に削除されるようにします。 削除できないように、コンテンツを保持するように Teams を構成することもできます。 詳細については、「[Microsoft Teams の保持ポリシー](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011)」を参照してください。
- **有効期限ポリシー:** 設定した日の後に有効期限が切れるチームを構成します。 有効期限が切れる 30 日前に、チームのすべての所有者にチームの更新が必要であることが通知され、それ以外の場合は削除されます。 ただし、管理者は削除されたチームをさらに 30 日間回復できます。 この設定は、未使用のチームが廃止されることを確認するのに役立ちます。 詳細については、 [Microsoft 365 グループの有効期限ポリシー](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733)を参照してください。

- **チームをアーカイブする:** この設定で、チームは読み取り専用モードになります。 参照して検索することはできますが、新しい投稿を追加することはできません。 [チームのアーカイブまたは復元では、チーム](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)の所有者がチームをアーカイブする方法について説明します。チームの所有者は、[Graph API (プレビュー)](/graph/api/resources/teams-api-overview) を使用してチームをアーカイブまたは復元することもできます。

> [!IMPORTANT]
> Microsoft 365 グループ有効期限ポリシーを使用するには、1 つ以上の Microsoft 365 グループのメンバーである一意のユーザーごとに、Azure Active Directory Premium P1 ライセンスが必要です。

## <a name="are-there-team-templates-for-my-faculty-members-to-use-when-creating-a-team"></a>チームを作成するときに教職員用に使用できるチームのテンプレートはありますか?

はい。 ユーザーは新しいチームを作成するときに **既存のテンプレートから** チームの作成を選択でき、Teams の所有者は [Graph API (プレビュー)](/graph/api/resources/teams-api-overview) を使用して、使用可能なテンプレートから新しいチームを作成することもできます。

## <a name="what-tasks-can-i-automate-via-powershell-or-graph"></a>PowerShell や Graph を介して自動化できるタスクは何がありますか?

[Microsoft Graph API (プレビュー)](/graph/api/resources/teams-api-overview) では、次のタスクを実行できます。

- チームの作成。
- メンバーおよび所有者の追加。
- チャネルの追加。
- アプリの追加。
- 既存のチームを複製してこれらのステップを短縮し、そのタブも取得。
- 作成したチームへのリンクをユーザーに付与します。
- 不要になったメンバー、所有者、チャネル、アプリの削除。
- アクティブでなくなったチームのアーカイブ。
- チームの削除。
- チャネル スレッドの作成

[PowerShell](/powershell/module/teams/?view=teams-ps) では、次のタスクを実行できます。

- チームの作成。
- メンバーおよび所有者の追加。
- チャネルの追加。
- 不要になったメンバー、所有者、チャネルの削除。
- チームの削除。

> [!TIP]
> Graph API と PowerShell コマンドレットで継続的に機能を追加。 機能拡張については、[Microsoft Graph API (プレビュー)](/graph/api/resources/teams-api-overview) と [PowerShell](/powershell/module/teams/?view=teams-ps) の記事をよく確認してください。  

## <a name="can-i-control-what-teams-features-my-faculty-and-students-have-access-to"></a>教職員と学生がどの Teams の機能にアクセスできるかを制御できますか?

はい。 ポリシーを使用して、ユーザーがアクセスする特定のメッセージ、会議、通話、ライブ イベント機能を制御できます。 テナント全体の設定を使用して、すべてのユーザーに同じ設定を適用したり、必要に応じてユーザー レベルのポリシーを適用したりできます。

Teams ポリシーの詳細については、「 [組織の Microsoft Teams 設定の管理」を参照してください](enable-features-office-365.md)。

## <a name="can-i-control-what-external-parties-my-faculty-and-students-collaborate-with"></a>教職員と学生が共同作業を行う外部関係者を制御できますか?

ゲスト アクセスを使用すると、テナント外のユーザーを招待することができます。これは、研究の共同作業や来客の講義に便利です。

- ドメイン の許可リストを使用して、ドメインに基づいてゲストを許可またはブロックします。
- 特定のMicrosoft 365 グループとチームのゲスト アクセスを有効または無効にして、ゲストを招待できる (および招待できない) チームを制御します。
- 監査ログを使用して、招待されたゲストに送信された警告を確認します。

詳細については、「[Microsoft 365 グループでのゲスト アクセス](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage)」を参照してください。

## <a name="what-information-can-i-review-about-existing-teams"></a>既存のチームについてどのような情報を確認できますか?

監査ログを確認すると、次の事項を確認できます。

- 誰がどのチームにゲストとして招待されたか。
- 誰がどのチームを作成したのか。

詳細については、「[Microsoft Teams でイベントの監査ログを検索する](audit-log-events.md)」を参照してください。

## <a name="teams-evolves-so-quickly-how-can-i-stay-up-to-date"></a>Teams は急速に進化しています。 最新の状態を維持するにはどうすればよいですか?

Teams の最新の更新プログラムを取得するには、次のリソースをお勧めします。

- [Microsoft Teams の新機能](https://support.office.com/article/What-s-new-in-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
- [Microsoft Teams のブログ](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)
