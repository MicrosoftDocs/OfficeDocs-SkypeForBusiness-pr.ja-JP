---
title: チームのマイクロソフトのチームでの管理のための計画
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 08/10/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: チームでの管理機能の実装を計画する方法について説明します。
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 048b9dd09e9309c4aaaf1af3b92d7e24f280d088
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883253"
---
# <a name="plan-for-governance-in-teams"></a>チームの管理のための計画

チームは、組織が必要な場合があります、管理機能を実装するためのツールの豊富なセットを提供します。 この資料では、IT プロフェッショナルが、ガバナンス、およびそれらに対応する方法についての要件を確認するのには、正しい質問をガイドします。 

## <a name="group-and-team-creation-naming-classification-and-guest-access"></a>グループとチームの作成、名前付け、分類、およびゲスト アクセス

組織は、チームの名前し分類方法、来園者をチームのメンバーとして追加するか、およびチームを作成できるユーザーを厳密な制御を実装する必要があります。 Azure Active Directory (AD の Azure) を使用して、これらの各領域を設定できます。 

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|意思決定ポイント|<ul><li>組織はチームの特定の命名規則を必要とするか。</li><li>チーム作成者にチームを組織に固有の分類を割り当てる機能が必要ですか。</li><li>チーム別のチームにゲストを追加する機能を制限する必要がありますか。</li><li>組織は、チームを作成できるユーザーを制限することを必要ですか。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|次のステップ|<ul><li>チームの作成、名前付け、分類、およびゲスト アクセスのため、組織の要件を文書化します。</li><li>チームの展開の一部としてこれらの要件を実装するために計画します。</li><li>通信し、その動作のチームのユーザーに通知するポリシーを公開します。</li></ul>|

> [!TIP]
組織の要件をキャプチャするのにには、次の表を使用します。
|機能 |詳細 |Azure AD プレミアム <br> ライセンスが必要 |意思決定 |
|---------|---------|---------|---------|
|チームの名前付けポリシー | プレフィックス、サフィックスに基づく、カスタム ブロックの単語を使用します。 |P1 |未定 |
|チーム分類 |分類をチームに割り当てます。 |P1 |未定 |
|チームのゲスト アクセス |許可するか、来園者がチームに追加されることを防止します。 |なし |未定 |
|チームの作成 |管理者のチームの作成を制限します。 |なし |未定|
|チームの作成 |セキュリティ グループのメンバーにチームの作成を制限します。 |P1 |未定|

> [!NOTE]
> [学ぶ必要があるライセンスの詳細については、これらのポリシーを設定し、どのような](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings)事前の計画に役立ちます。

> [!NOTE]
> グループとチームの作成を制限することと、多くの Office 365 サービスは、サービスが機能するためにグループを作成することを必要とするために、ユーザーの生産性が低下することが。 詳細についてに移動し、 [Office 365 のグループを作成したユーザーを制御する理由](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why)を展開します。


#### <a name="additional-information"></a>追加情報

お客様の要件を決定した後は、Azure AD コントロールを使用して実装できます。 これらの設定を実装する方法についての技術的なガイダンスを参照してください。

-   [Azure Active Directory グループの設定を構成するコマンドレット](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)です。

-   [Azure Active Directory 内の Office 365 のグループの名前付けポリシーを適用します](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy)。

-   [Office 365 のグループ ポリシーに名前を付ける](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)。


## <a name="group-and-team-expiration-retention-and-archiving"></a>グループとチームの有効期限、保存、およびアーカイブ

保持、有効期限ポリシーを設定するための追加要件を持つ組織もあり、チームおよびチームのデータをアーカイブします。 自動的に保持するか、必要に応じて情報を削除するグループ、および保存ポリシーのライフ サイクルを管理するグループの有効期限ポリシーを構成することができ、チームをアーカイブすることができます (読み取り専用モードに設定する) チームのポイント ・ イン ・ タイム ・ ビューを保持するためのアクティブではないです。

|           |            |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>意思決定ポイント|<ul><li>組織はチームの有効期限を指定する必要がありますか。</li><li>組織に必要な特定のデータ ・ リテンション ・ ポリシーは、チームに適用するか。</li><li>組織は、読み取り専用状態でコンテンツを保持するためにチームを非アクティブにアーカイブする機能を必要とする予定ですか。</li></ul>|
| ![](media/audio_conferencing_image9.png)<br/>次のステップ|<ul><li>チームの有効期限、データの保存、アーカイブに関する組織の要件を文書化します。</li><li>チームの展開の一部としてこれらの要件を実装するために計画します。</li><li>通信し、その動作のチームのユーザーに通知するポリシーを公開します。</li></ul>|

> [!TIP]
組織の要件をキャプチャするのにには、次の表を使用します。
|機能 |詳細 |Azure AD プレミアム <br>ライセンスが必要 |意思決定 |
|---------|---------|---------|---------|
|有効期限ポリシー |有効期限ポリシーを設定することにより、Office 365 のグループのライフ サイクルを管理します。 |P1 |未定|
|リテンション ・ ポリシー |保持または、セキュリティとコンプライアンスの中心でチームのリテンション ・ ポリシーを設定することによって、特定の期間 (チームのチャネル メッセージ、チャネル ファイル) のデータを削除します。 **注**: この機能を使用するには、Office 365 エンタープライズ E3 以上のライセンスが必要です。 |なし |未定 |
|アーカイブと復元 |チームは、アクティブになっていませんが、参照を保持するか、将来的に再アクティブ化するときにアーカイブします。 |なし |未定 |

> [!Note]
> グループの有効期限は、Azure AD プレミアム機能です。 できるようにするには、この機能に、テナントは設定し、影響を受けるグループのメンバーを設定する管理者の Azure AD プレミアムとライセンスのサブスクリプションが必要です。

#### <a name="additional-information"></a>追加情報

これらの設定を実装する方法についての技術的なガイダンスを参照してください。

-   [Office 365 のグループの有効期限を設定](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle)します。

-   [チーム ・ リテンション ・ ポリシーを設定](security-compliance-overview.md#retention-policies)します。

-   [アーカイブまたはチームを復元](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)します。


## <a name="teams-feature-management"></a>チーム機能の管理

ガバナンスとチームのライフ サイクル管理のもう 1 つの重要な側面は、どのような機能、ユーザーがへのアクセスを制御する機能です。 メッセージング、会議、および Office 365 のテナントのレベルまたはユーザーごとのいずれかで、機能の呼び出しを管理することができます。 


|         |         |
|---------|---------|
| ![](media/audio_conferencing_image7.png) <br/>意思決定ポイント|<ul><li>組織は、全体のテナントのチームの機能を制限する必要ですか。</li><li>組織が特定のユーザーのチームの機能を制限する必要ですか。</li></ul>|
| ![](media/audio_conferencing_image9.png)<br/>次のステップ|<ul><li>テナントとユーザー レベルのチームの機能を制限するため、組織の要件を文書化します。</li><li>チームの展開の一部として、特定の要件を実装するために計画します。</li><li>通信し、その動作のチームのユーザーに通知するポリシーを公開します。</li></ul>|

### <a name="teams-feature-management-focus-areas"></a>チーム機能の管理の重点分野

チームでは、メッセージング、会議、呼び出し、およびライブ イベントの機能と詳細については、ポリシーを使用して制御するための詳細な機能を提供します。 デフォルトで、または組織内で必要に応じてユーザーごと、すべてのユーザーに異なるポリシーを適用できます。 

組織では、それらを実装する方法についての技術的なガイダンスを含む、すべての設定の詳細なリストは、以下の資料を参照してください。

-   [Office 365 組織でマイクロソフトのチーム機能を管理します。](enable-features-office-365.md)
-   [新しいマイクロソフトのチームとビジネス管理センターの Skype に移行する際のチームを管理します。](manage-teams-skypeforbusiness-admin-center.md)
-   [チームでミーティングのポリシーを管理します。](meeting-policies-in-teams.md)


## <a name="security-and-compliance"></a>セキュリティとコンプライアンス

チームでは、高度なセキュリティおよびコンプライアンス機能を Office 365 の上に構築された、監査およびレポート作成、コンプライアンス ・ コンテンツの検索、電子的証拠開示、法的保持義務、および保存ポリシーをサポートしています。 

> [!Important]
> 組織は、コンプライアンスおよびセキュリティの要件は、[セキュリティとマイクロソフトのチームでのコンプライアンスの概要](security-compliance-overview.md)の資料では、このトピックに関する詳細な内容を確認してください。

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->