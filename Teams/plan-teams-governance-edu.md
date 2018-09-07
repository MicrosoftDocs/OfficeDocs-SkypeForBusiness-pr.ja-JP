---
title: IT プロフェッショナル向けのマイクロソフトのチームの Microsoft 教育ガバナンスに関する FAQ
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 08/10/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: チームを使用して、マイクロソフトの教育グループの管理者からよく寄せられる質問への回答です。
localization_priority: Priority
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: f798d9bd18316f7a78c846e473a8a5dfbae0c6c6
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23860510"
---
# <a name="microsoft-education-governance-faq-for-admins"></a>管理者のマイクロソフト教育ガバナンスに関する FAQ

## <a name="how-do-i-control-team-creation-im-worried-students-are-going-to-create-inappropriate-teams"></a>チームの作成を制御する方法は? ない受講者は、不適切なチームを作成しようとしています。

不適切または誤解を招く名前を避けるために、またはチームに名前を付ける方法の多くの構造を提供するだけには、Office 365 グループ (プレビュー) で現在のポリシーの名前を使用できます。

-   **プレフィックス、サフィックスの名前付けポリシー**プレフィックスまたはサフィックス、チーム (グループ) の名前付け規則を定義するのには**GRP_US_My Group_Engineering**を使用することができます。 プレフィックスおよびサフィックスは文字列またはチームを作成しているユーザー名に追加されます ( **[部署]**) などのユーザー属性に固定できます。
-   **カスタム単語をブロックします。** 単語のセットをアップロードすることで作成するチームの名前を使用して、特定の組織内のユーザーがブロックされています。 などには適用しないグループの名前をチームで使用されているから**最高経営責任者**、**給与**、および**人事**の用語をブロックできます。
-   **クラス分け**組織内のユーザーが、Office 365 のグループを作成するときに設定する分類を作成します。 

> [!IMPORTANT]
> Office 365 グループ名前付けポリシーを使用すると、1 つまたは複数の Office 365 のグループのメンバーである個々 のユーザーの Azure Active Directory プレミアム P1 ライセンスまたは EDU の Azure AD の基本的なライセンスが必要です。

詳細については、 [Office のグループ ポリシーの名前を付ける](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)を参照してください。

> [!Note]
> チームは別のシステム (たとえば、学校データの同期) からの入力を使用して自動的に作成する場合は、入力データが、命名ポリシーを構成した; に準拠していることを確認します。チームには、作成は失敗します。

## <a name="can-i-see-who-created-a-team"></a>チームを作成したユーザーを表示できますか。

特定のチームを作成したユーザーについては、[マイクロソフトのチームでのイベントの監査ログの検索](audit-log-events.md)を参照してください。

## <a name="can-i-control-who-can-create-teams"></a>チームを作成できるユーザーを制御できますか。

一般に、チームを作成するを防ぐことをお勧めします。 チームを作成できるすべてのユーザーは、チームが幅広く採用される可能性が高くします。 教員、教師、または受講者は、研究グループ、または特別な関心のグループを作成するのにチームを使用できます。 教室の内外に受け入れられるチームに役立ちます。

経験では、ユーザー教育により、担当するチームの使用率です。 チームの作成ではないこと匿名のユーザーを理解するとすぐに、不注意に作成するは理解し、ツールの誤用をためらう傾向があります。

チームを作成できるユーザーを制御することを確認する場合は、 [Office 365 のグループを作成できるユーザーの管理](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)を参照してください。

## <a name="how-do-i-automatically-create-a-team-for-each-course-at-the-beginning-of-the-semester-or-quarter"></a>自動的を作成する方法各コースのチーム、半期または四半期の先頭にしますか。

、半期または四半期ごとの開始時に、多数の新しいチームを必要があります。 自動的にこれらのチームを作成して、適切なユーザーを設定して、適切なアクセス許可を設定するのには自動化されたアプローチを採用する必要があります。

-   学校のデータの同期は、Exchange Online と SharePoint オンライン、マイクロソフトのチームおよびクラスの OneNote ノートブックのクラスのチーム、教育、および rostering Intune と単一サインオン (SSO) の統合の他の多くの学校のグループに Office 365 のグループを作成できます。サード ・ パーティ製のアプリケーションです。 [学校のデータの同期の概要](https://docs.microsoft.com/schooldatasync/overview-of-school-data-sync)で詳しく説明します。
-   PowerShell のチームとのチャネルを作成および設定を構成する自動的にします。 詳細については、[マイクロソフト チームの PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)を参照してください。
-   (現在のベータ版) で Microsoft グラフ API を使用して、作成、構成、クローンを作成すると、およびチームをアーカイブできます。 詳細については、[マイクロソフトのチームで作業するのには Microsoft のグラフの API を使用](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)を参照してください。

> [!TIP]
> 学校のデータの同期は、唯一の先生と生徒をクラス内では、そのクラスのメンバーを参照できるように、同期クラスと[非表示のグループ メンバーシップを有効にする](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945)ごとに、Office 365 のグループを作成します。 別のプロセスを使用して作成する場合、クラスのグループは、同じプライバシーの要件を満たすために新規 UnifiedGroup コマンドレットの HiddenGroupMembershipEnabled パラメーターを使用します。

## <a name="how-do-i-deal-with-teams-when-the-semester-or-quarter-ends"></a>対処チームと共同で、半期または四半期が終了したときですか。

学校半期または四半期が上にあるとき、チームのデータを処理する方法についてまずと思われることをお勧めします。 削除するか、いつでも利用できる受講者のコースを行った後にでもするかどうか。 学校カレンダーに留意してください任意のポリシーを設定するは、祝日と競合しないようにします。 戦略を実装するのに次のツールを使用できます。

-   **リテンション ・ ポリシー:**(の一部またはすべてのユーザー) のチャットやチャンネルから古いデータが削除されるかどうかを確認するのにように指定した年齢より古いすべてのデータを削除するのにには、これを使用します。 削除できませんので、コンテンツを保持するチームを構成することもできます。 詳細については、[マイクロソフトのチームのリテンション ・ ポリシー](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011)を参照してください。
-   **の有効期限ポリシー:** 指定の日数後に期限切れにチームを構成します。 有効期限の前に 30 日間のチームは、更新する必要があることは、それ以外の場合に削除されます (ただし、管理者は、さらに 30 日間削除されたチームを回復することができます)、チームのすべての所有者に通知されます。 この設定は、未使用のチームが sunsetted であることを確認するため非常に便利です。 [Office 365 グループの有効期限ポリシー](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733)の詳細を表示します。

-   **チームのアーカイブ:** この設定は、読み取り専用モードにチームを配置します。 まだブラウズや検索しますが、誰の新しい投稿を追加できます。 [アーカイブまたは復元チーム](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)は、チームのオーナーがチームをアーカイブする方法について説明します。チームの所有者では、アーカイブまたはチームを復元するには[グラフの API (ベータ版)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)も使用できます。
 
> [!IMPORTANT]
> Office 365 のグループの有効期限ポリシーを使用して、1 つまたは複数の Office 365 のグループのメンバーである個々 のユーザーの Azure Active Directory プレミアム P1 のライセンスが必要です。

## <a name="are-there-team-templates-for-my-faculty-members-to-use-when-creating-a-team"></a>チームを作成するときに使用する自分の学部のチーム テンプレートがありますか。

はい。 新しいチームを作成するとき、ユーザーは**既存のテンプレートからチームを作成**を選択でき、チーム所有者も使用可能なテンプレートから新しいチームを作成する[グラフの API (ベータ版)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)を使用します。

## <a name="what-tasks-can-i-automate-via-powershell-or-graph"></a>どのようなタスクを自動化できます PowerShell またはグラフを使用してですか。

[Microsoft グラフ API (ベータ版)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)は、次に行うことができます。

-   チームを作成します。
-   メンバーおよび所有者を追加します。
-   チャンネルを追加します。
-   アプリケーションを追加します。
-   ショートカット既存のクローンを作成してこれらの手順は、チームとすぎるのタブを取得します。
-   ユーザーのリンクを作成したチームに与えます。
-   不要にするときは、メンバー、所有者、チャネル、およびアプリケーションを削除します。
-   チームは、アクティブでなくなったときにアーカイブします。 
-   チームを削除します。
-   チャネルのスレッドを作成します。

[PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)では、次の操作を行うことができます。

-   チームを作成します。
-   メンバーおよび所有者を追加します。
-   チャンネルを追加します。
-   不要にするときは、メンバー、所有者、およびチャネルを削除します。
-   チームを削除します。

> [!TIP]
> グラフ API および PowerShell コマンドレットは常に機能を追加します。 機能強化については、 [Microsoft グラフ API (ベータ版)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)および[PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)の記事を確認してください。  


## <a name="can-i-control-what-teams-features-my-faculty-and-students-have-access-to"></a>教職員と学生へのアクセスがあるどのようなチームの機能を制御することができますか。

はい。 ポリシーを使用してコントロール特定のメッセージ、会議、通話、およびライブ イベントの機能をユーザーがアクセスできます。 テナント全体の設定を使用して、すべてに同じ設定を適用したり、必要な場合は、ユーザー レベルのポリシーを適用できます。 

チームのポリシーの詳細については、 [Office 365 の組織での Microsoft チームの管理機能](enable-features-office-365.md)を参照してください。
 
## <a name="can-i-control-what-external-parties-my-faculty-and-students-collaborate-with"></a>どのような外部の関係者が自分の教職員と学生との共同作業を制御することができますか。

ゲスト アクセスを使用するには、テナントは、共同研究や講義のゲストの役に立ちますの外部からのユーザーを招待します。

-   許可またはブロックの来園者が自分のドメインのドメイン whitelisting を使用します。
-   特定の Office 365 のグループとチームは、来園者を招待チーム (とできることはできません) を制御するためのゲスト アクセスのオンとオフをオンにします。
-   来園者の招待を送信するアラートを表示するのにには、監査ログを使用します。

詳細については、 [Office 365 のグループでのゲスト アクセス](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage)を参照してください。

## <a name="what-information-can-i-review-about-existing-teams"></a>既存チームについて確認できる情報

監査ログを参照して確認できます。

-   ユーザーは、どのチームにゲストとして招待されました。
-   チームを作成したユーザーです。

詳細については、[マイクロソフトのチームでのイベントの監査ログの検索](audit-log-events.md)を参照してください。

## <a name="teams-evolves-so-quickly-how-can-i-stay-up-to-date"></a>チームがこれほど迅速に進化します。 最新の状態にする方法はでしょうか。

チームの最新の更新プログラムを取得するのには次のリソースをお勧めします。

-   [マイクロソフト チームの新機能](https://support.office.com/article/What-s-new-in-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
-   [マイクロソフト チームのブログ](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)
