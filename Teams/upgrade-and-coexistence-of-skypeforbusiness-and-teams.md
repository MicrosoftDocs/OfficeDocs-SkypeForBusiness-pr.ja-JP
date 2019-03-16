---
title: Skype for Business から Microsoft Teams へのアップグレード| モード、共存
author: lsomi
ms.author: lsomi
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: dearbeen, bjwhalen
description: Skype for Business と Microsoft Teams の共存オプションおよびモードの詳細と、いくつかのシナリオ例での Skype for Business から Teams へのアップグレード手順。
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
f1keywords:
- ms.teamsadmincenter.orgwidesettings.teamsfeatures.upgradetoteamsarticle
- ms.teamsadmincenter.upgradeoverride.learnmore
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 22bd17ffbb29695f69aa4eff8581821a882f1614
ms.sourcegitcommit: a589b86520028d8751653386265f6ce1e066818b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "30649197"
---
![展開と実装の段階に重点を置いた、アップグレード手順の各段階](media/upgrade-banner-deployment.png "展開と実装の段階に重点を置いた、アップグレード手順の各段階")

This article is part of Deployment and Implementation stage of your upgrade journey. Before proceeding, confirm that you’ve completed the following activities:

- [プロジェクトの関係者をリスト化した](upgrade-enlist-stakeholders.md)
- [プロジェクトの対象範囲を定義した](https://aka.ms/SkypetoTeams-Scope)
- [Skype for Business と Teams の共存と相互運用を理解した](https://aka.ms/SkypeToTeams-Coexist)

# <a name="choose-your-upgrade-journey-from-skype-for-business-to-teams"></a>Skype for Business から Teams へのアップグレード手順を選択する

As an existing Skype for Business customer, your complete transition to Teams might take some time. However, you can begin realizing the value of Teams today, by enabling your users to use Teams alongside Skype for Business. Given that there’s some overlapping functionality between the two apps, we recommend that you review the available coexistence and upgrade modes to help determine which path is right for your organization. For example, you might opt to enable all workloads on both solutions without interoperability. Or, you might decide to manage the user experience, either by gradually introducing Teams capabilities or by targeting groups of users for select capabilities, until your organization is ready to upgrade everyone to Teams. Use the outcome of your pilot to help assess the right upgrade journey for your organization.

> [!IMPORTANT]
> This article outlines the various modes that enable you to manage which modalities in Skype for Business and Teams are available to your users. As with any deployment, we strongly encourage you to [pilot your intended plan](pilot-essentials.md) with a selected group of users before upgrading your organization to Teams. Remember, introducing new technology can be disruptive for users. Take time to assess user readiness and implement a communication and training plan prior to implementing any of the modes outlined herein.

## <a name="upgrade-journey-building-blocks"></a>アップグレード手順の構成単位

お客様の組織を Teams に移行するために正式に準備するためには、最終的に組織が Teams を唯一のコミュニケーションとコラボレーションのソリューションとして完全に受け入れられるようになるアップグレード シナリオ計画を開始する必要があります。

To help guide your decision-making process, familiarize yourself with the various modes, concepts, and terminology relevant to upgrading from Skype for Business to Teams. For more information, see [Microsoft Teams and Skype for Business coexistence and interoperability](https://aka.ms/SkypeToTeams-Coexist)

日常のコミュニケーションおよびコラボレーションの必要性に応じて、一部のユーザーが Teams のみを使用する準備が整っている場合、**Teams Only** モードを有効にすることによって、それらのユーザーの Teams へのアップグレードを開始することができます。

If it’s not feasible for your whole organization to move to Teams, you can start by piloting Teams alongside Skype for Business in **Islands** coexistence mode. As the additional coexistence modes, (i.e. **Skype for Business with Teams collaboration** and **Skype for Business with Teams collaboration and meetings**), are become progressively fully available in the next few months, you can also start by fully adopting Teams as a group collaboration solution first while keeping Skype for Business as your organization’s unified communications solution. That is Microsoft’s recommended path for customers using Skype for Business Server (on-premises or hybrid) and customers with significant complexity whose trajectory to Teams will include a long coexistence period.

![Skype for Business と Teams でのコラボレーションのみのモード、Skype for Business と Teams でのコラボレーションおよび会議モード、アイランド モード、Teams のみのモード、Skype for Businessのみのモードから成る、Skype for Business から Teams へのアップグレードの構成単位のスクリーンショット。](media/upgrade_journeys_building_block.png)

次の表で、共存モードとアップグレード モードを比較します。

|モード |状況 |推奨される使用状態 |利点 |注意事項 |
|---|---|---|---|---|
|アイランド |より小規模またはシンプルな Skype for Busness の展開<br><br>いくつかの短期的な複雑な状況を管理して、Teams により速やかに移行するための能力と意思。 |できるだけ早く完全な Teams エクスペリエンスに移動する<br><br>Teams の概念実証 (PoC) の実施<br><br>Skype for Business Online を導入した組織に対して推奨されるアップグレード パス |運用が簡単<br><br>すべての機能において傑出した、最も豊かな Teams エクスエぺリエンス |混乱を排除し、Teams の使用を推進するためには、良好なユーザー コミュニケーションが必須<br><br>出口戦略において、Teams Only フェーズへのアップグレードを開始する前にユーザーが完全に Teams を導入することが必須<br><br>アイランド モードのユーザーに対する相互運用性はなし。また、ユーザーの Skype for Business アカウントがオンプレミスで所属している場合は Teams からのフェデレーションもなし|
|Skype for Business と Teams でのコラボレーション |Skype for Business の展開で、Teams ではまだ満たされていない要件がある (たとえば、先進的なコンプライアンスなど)<br><br>Skype for Business に対する長期的な必要性や、コミットメント|グループでの共同作業について最初に焦点をあてながら、Teams の導入を速やかに開始する<br><br>Skype for Business 上で、すべての統合コミュニケーション ワークロードを維持する<br><br>オンプレミス (またはハイブリッド) の Skype for Business からの移行を開始する組織の開始点としての使用を推奨|Teams と Skype for Business との間に重複する機能なし	<br><br>インスタント メッセージング チャットおよび会議のスケジュールが (通話に結びついている) Skype for Business に存在する<br><br>Teams Only のユーザーとの相互運用性|
|Skype for Business と Teams でのコラボレーションおよび会議 |エンタープライズ VoIP を頻繁に使用し、Teams 通話では適合しない要件がある Skype for Business の展開<br><br>Skype for Business に対する長期的な必要性や、コミットメント<br><br>サードパーティの会議サービスを使用する可能性|グループでの共同作業にとどまらず、Teams の導入を速やかに開始<br><br>ユーザーの会議のエクスペリエンスを改善<br><br>(一般的にエンタープライズ VoIP オンプレミスのために) 完全にアップグレードする準備が整う前に、Teams 会議を十分に活用することを望んでいる、オンプレミスの組織に対して推奨される使用 |重複する機能なし<br><br>Superior meetings on Teams. Features roadmap, UX and cross platform, quality and reliability<br><br>Skype for Business と Teams との間での「より良い連携作業」エクスペリエンス<br><br>Teams Only の相互運用性ユーザー。|インスタント メッセージング およびチャットが (通話に結びついている) Skype for Business に存在する|
|Teams Only |Skype for Business の使用を継続する必要がある一部のユーザー<br><br>Skype for Business Online ユーザーを Teams にアップグレートしている一方で、Skype for Business オンプレミス ユーザーは Skype for Business Server 上にとどめている<br><br>展開済みのユーザーを既にアイランド モードにしており、ユーザーのグループでの Skype for Business の使用を廃止する準備が整っている |Skype for Business のさまざまな費用 (オンプレミス サーバーの運用、外注契約など) の削減<br><br>できるだけ早く、少なくとも一部のユーザーにおいて、完全な Teams エクスペリエンスに移行する|Skype for Business のみ、Skype for Business と Teams でのコラボレーション、Skype for Business と Teams でのコラボレーション、Skype for Business と Teams でのコラボレーションおよび会議において、ユーザーとの相互運用性で機能するクライアントを 1 つのみ提供して、ユーザーの混乱を抑制する|相互運用性のサポート範囲は、Skype for Business と Teams との間での基本的なチャットと通話、およびデスクトップ共有や複数パーティでのチャットおよび通話のための相互運用性のエスカレーション シナリオに限られる|
|Skype for Business のみ |Skype for Business の使用を継続する必要がある一部のユーザー<br><br>|ユーザーとの相互運用性で機能するクライアントを 1 つのみ提供して、ユーザーの混乱を抑制する<br><br>ユーザーは招待された場合に Teams 会議に参加することができる|現時点で Skype for Business によってのみ適合しているビジネス要件に適合する<br><br>Teams Only のユーザーとの相互運用性|相互運用性のサポート範囲は、Skype for Business と Teams との間での基本的なチャットと通話、およびデスクトップ共有や複数パーティでのチャットおよび通話のための相互運用性のエスカレーション シナリオに限られる|

## <a name="upgrade-journeys"></a>アップグレード手順

オンラインでもオンプレミスでも、Skype for Business から Teams へのアップグレードは、複数のアプローチで行うことができます。

- In a direct upgrade journey, you first deploy Teams alongside Skype for Business in **Islands** mode as part of evaluation and early adoption, and then upgrade your users to **Teams Only** mode with the goal of quickly retiring Skype for Business from the environment for all users in the organization. This is the recommended journey for Skype Business online customers, unless they are concerned their users will be confused with having two tools to conduct the same action (chat, calling, meeting scheduling).
- A gradual upgrade journey delivers a specific coexistence and upgrade mode to a specific group of users (also called a *cohort*), depending on their communications and collaboration requirements. Over time, the entire organization can converge into using Teams Only and eventually replace Skype for Business. However, if your organization has compelling business reasons to keep Skype for Business—such as a dependency on a Unified Communications Managed API (UCMA)–based solution that integrates with line-of-business applications, or an ethical wall solution currently available for Skype for Business only, or a complex Enterprise Voice deployment that will take time to upgrade to **Teams Only**—you can upgrade a portion of users to **Teams Only** mode while retaining Skype for Business users in one of the coexistence modes for a portion of your user population. Gradual upgrade journey is the recommended approach for on-premises (and hybrid) customers starting with Skype for Business with Teams Collaboration coexistence mode and moving from there to Teams Only mode when requirement for the users met (possibly through the Skype for Business with Teams Collaboration and Meetings coexistence mode).

> [!IMPORTANT]
> For both types of upgrade journey, if your organization is currently a Skype for Business on-premises deployment only, you need to start planning to implement Skype for Business hybrid before upgrading your users to **Teams Only** mode. This will also help facilitate interoperability with Teams.
>
> Skype for Business のハイブリッド実装をガイドするために、[MyAdvisor](https://myadvisor.fasttrack.microsoft.com/) を使用します。

> [!NOTE]
> **Teams Only** mode requires that the users who are part of cohorts be homed in Skype for Business Online, and a hybrid relationship between your Skype for Business on-premises deployment and your Skype for Business Online tenant is required to facilitate the interoperability between Skype for Business and Teams. The move to Skype for Business Online must be completed for users who are part of the cohorts before they’re upgraded to **Teams Only** mode. Skype for Business Server 2019, and Skype for Business Server 2015 with CU8 update can simplify the mechanics of upgrading on-premises users to Teams by managing the migration to Skype for Business Online and upgrading the users to **Teams Only** mode in one step.

### <a name="direct-upgrade-journey"></a>直接的なアップグレード手順

直接的なアップグレード手順は次の図に示されています。

![A screenshot of the direct upgrade journey. All users initially use Teams in Islands mode, then transition to Teams-only mode, with the end state of the entire organization upgraded to Teams.](media/upgrade_journey_direct_upgrade.png)

Teams is deployed to all users in the organization and configured in **Islands** mode. When your organization determines that Teams is ready to fulfill all of your communications and collaboration needs, notify the users and upgrade them to **Teams Only** mode. At that point, Skype for Business can be retired from the environment.

### <a name="gradual-upgrade-journey"></a>段階的なアップグレード手順

段階的なアップグレード手順の例は次の図に示されています。

![In the gradual upgrade journey, cohorts of users initially use Teams in Islands mode for evaluation and then in a variety of upgrade modes for early adoption, side by side with Skype for Business. Some cohorts transition to Teams-Only mode, while one group of users stays with Skype for Business with Teams collaboration and meetings mode.](media/upgrade_journey_gradual_upgrade.png)

Teams is deployed in the organization in **Islands** mode for evaluation and then move to different coexistence and upgrade modes for different groups of users. For example, a group of users can be enabled for **Islands** mode, another enabled for **Skype for Business with Teams collaboration and meetings** mode, while a third group of users might initially be enabled for **Skype for Business with Teams collaboration only** mode.

Over time, groups of users can be upgraded to **Teams Only** mode, followed by the rest of the organization. Eventually, the entire organization will be ready to retire Skype for Business and use only Teams for communications and collaboration, or—if business requirements dictate that Skype for Business be retained for a specific group—the majority of users in the organization can use Teams Only. <br><br>
<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>判断ポイント</td><td><ul> どのアップグレード手順が組織のビジネス要件に適してますか?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>次のステップ</td><td><ul> お客様の組織での現在の展開モデル、ユース ケースのシナリオ、および主な考慮事項を特定することにより、組織に最も適した Teams への移行手順がわかるようになります。<br><br></ul></td></tr>
</table>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>判断ポイント</td><td><ul> お客様の組織に該当するアップグレード シナリオはどれですか?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>次のステップ</td><td><ul> メッセージング、会議、および通話のビジネス要件に基づいて、お客様の組織のアップグレード手順のタイムラインを決定します。<br><br> アップグレード手順を完了するために必要な追加作業を決めます。<br><br></ul></td></tr>
</table>

組織にとって最高のアップグレード手順を選んだ後、[Teams に対するアップグレードを実行します](https://aka.ms/SkypeToTeams-Upgrade)。
