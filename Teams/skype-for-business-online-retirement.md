---
title: Skype for Business Online のサポート終了
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Skype for Business Online の廃止計画と、Microsoft が顧客のTeamsへの移行をどのように支援しているかについて説明します。
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dcd2148a3f939bd8799b7b3f8b86118359936b7c
ms.sourcegitcommit: d3d3d5a70a69359fc71f072ad6c651556f4eda00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2022
ms.locfileid: "63783906"
---
# <a name="skype-for-business-online-retirement"></a>Skype for Business Online のサポート終了

2021 年 7 月 31 日、Microsoft はSkype for Business Online を廃止しました。 この廃止は、2019 年 7 月に発表され、Microsoft Teamsへのアップグレードを計画するための 2 年前の通知を顧客に提供しました。 Teamsは、Microsoft 365におけるコミュニケーションとコラボレーションのためのコア アプリです。 Skype for Business Online が廃止されると、Microsoft は、Teamsへの正常なアップグレードを計画して実行するために必要な情報とリソースを顧客に確実に提供したいと考えています。  Skypeコンシューマー サービスは、この廃止の影響を受けられません。 Skype for Business Online が廃止された理由の背景については、「[よく寄せられる質問 - Skype for BusinessからMicrosoft Teamsへのアップグレード](FAQ-journey.yml)」を参照してください。

Microsoft は、Skype for Business Online インフラストラクチャの使用停止を 2022 年 6 月 30 日以降に開始します。 この記事には、任意のバージョンのSkype for Businessからアップグレードされた TeamsOnly ユーザーを持つ組織向けのガイダンスが含まれています。


## <a name="organizations-with-on-premises-deployments-of-skype-for-business-server"></a>Skype for Business Serverのオンプレミス展開を持つ組織

Skype for Business Online の廃止は、Skype for Business Serverと Lync Server 2013 のオンプレミス展開のサポートには影響しません。 ただし、オンラインユーザーとオンプレミスユーザーが混在するハイブリッド顧客は、 *オンライン* ユーザーをアップグレードする必要があります。 オンライン ユーザーは、TeamsUpgradePolicy を使用して TeamsOnly モードを割り当てる必要があります。 Microsoft では、TeamsOnly モードへの残りのSkype for Businessオンライン ユーザーのアップグレードを自動化するために、支援されたアップグレードを提供しています。 ハイブリッド組織は、この廃止の結果、*オンプレミス* のSkype for Business ユーザーをクラウドに移行する必要はありません。 Microsoft では、TeamsOnly ユーザーとオンプレミス Skype for Business ユーザーが混在するハイブリッド組織を完全にサポートしています。 Skype for Business Serverまたは Lync Server 2013 のハイブリッド展開をお持ちのお客様は、[Skype for Business Online の提供終了](/skypeforbusiness/hybrid/plan-hybrid-connectivity#implications-of-the-upcoming-retirement-of-skype-for-business-online)を確認する必要があります。

## <a name="what-to-expect-post-retirement"></a>退職後の予定

クラウドに所属するユーザーに TeamsOnly 以外のモードを割り当てることはできなくなります。 これはですね：

 - オンプレミス Skype for Business Serverに所属していない新しいユーザーにライセンスを付与すると、テナントの TeamsUpgradePolicy のグローバル ポリシーに関係なく、ユーザーには TeamsOnly モードが自動的に割り当てられます。
 - ハイブリッド組織では、オンプレミスのホーム ユーザーをクラウドに移動すると、スイッチが `MoveToTeams` [ `Move-CsUser`.
 - クラウドに所属するユーザーは、TeamsOnly 以外のモードを割り当てることはできません。 オンラインホームユーザーは、オンプレミスSkype for Businessサーバーを使用 *しません*。

お客様には、Skype for Business Online に所属していて、TeamsOnly モードがまだ割り当てられていないユーザーが残っている可能性があります。 お客様は、できるだけ早く TeamsOnly モードをこれらのユーザーに割り当てる必要があります。 Microsoft は、TeamsOnly モードではないSkype for Business Online ユーザーに対して、サポートされるアップグレードを提供します。 アップグレードを支援するエクスペリエンスは、組織が純粋なオンライン組織であるか、オンプレミスのSkype for Business ユーザーを持つ組織であるかによって異なります。 詳細については、「[Skype for Business Online から Microsoft Teamsへのアップグレードの支援」を](upgrade-assisted.md)参照してください。

支援されたアップグレードが完了すると、すべての *オンライン* ユーザーは TeamsOnly モードになります。 TeamsOnly モードのユーザーは、Teamsで受信チャットや通話を受け取り、Teamsで会議をスケジュールすることもできます。 チャットや通話を開始したり、Skype for Business Online で会議をスケジュールしたりすることはできません。  ただし、TeamsOnly ユーザーは、今後既に開催または受信している会議Skype for Business参加できます。 最後に、 *オンプレミスに所属するすべてのユーザーはオンプレミスのままであり、TeamsOnly にはされません*。

## <a name="actions-to-take-before-june-30-2022"></a>2022 年 6 月 30 日までに実行するアクション
Skype for Business Online が廃止されたので、Microsoft は 2022 年 6 月 30 日より間もなく、サポート インフラストラクチャの使用停止を開始します。  任意のバージョンのSkype for Businessからアップグレードされた TeamsOnly ユーザーを持つすべての組織では、次のいずれかの状況に該当する場合は、アクションを実行する必要があります。

- previoulsy がSkype for Businessに連絡先を持っていて、アップグレード後にまだTeamsにログインしていない TeamsOnly ユーザーがいる場合。 
- TeamsOnly にアップグレードする前に開催した Skype for Business Online 会議を引き続き持つ TeamsOnly ユーザーがいる場合。

これらの状況のいずれかが組織に適用される場合は、以下に説明するように、2022 年 6 月 30 日までにアクションを実行する必要があります。

 - **Skype for Business オンライン連絡先:** ユーザーが TeamsOnly モードにアップグレードされると、ユーザーが初めてTeamsにログオンすると、そのユーザーのSkype for Business Online アカウント内の既存の連絡先はすべてTeamsに移行されます。 Microsoft が Skype for Business Online インフラストラクチャを削除した後、*まだログオンしていないユーザーの連絡先をTeamsに* 移行できなくなります。 Skype for BusinessからTeamsに連絡先を移行するには、以前にログオンSkype for Businessすべてのユーザーが、2022 年 6 月 30 日までに少なくとも 1 回Teamsにログオンすることをお勧めします。

 - **Skype for Business オンライン会議:** 組織が TeamsOnly にアップグレードされると、ユーザーはすべての新しい会議をTeams会議として作成します。 TeamsOnly ユーザーは、以前に開催したSkype for Businessオンライン会議を引き続き開催している場合があります。 現在、アップグレードされた TeamsOnly ユーザーと招待された出席者は、Skype for Business クライアントを使用して、これらのSkype for Business Online 会議に参加できます。 ただし、Microsoft が特定の TeamsOnly ユーザーのSkype for Business Online インフラストラクチャを削除した後、そのユーザーが開催した残りの Skype for Business Online 会議は存在しなくなります。 開催者と出席者は、これらの会議に参加できません。 TeamsOnly 組織のユーザーに、組織したオンライン会議Skype for Business残っている場合は、これらの会議をTeams会議としてスケジュール変更することをお勧めします。 または、管理者は[会議移行サービス](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms#trigger-meeting-migration-manually-via-powershell-cmdlet)を使用して、これらの会議をTeams会議に変換することもできます。 いずれの場合も、2022 年 6 月 30 日までにこれらのアクションを完了します。  


## <a name="how-microsoft-is-helping-customers-upgrade-to-teams"></a>Microsoft が顧客のTeamsへのアップグレードを支援する方法

Skype for Business Online から Teams へのアップグレードを今すぐ開始することを強くお勧めします。 TeamsのデプロイとSkype for Businessからのアップグレードの計画に役立つリソースを利用します。

- [Teams展開とアップグレードに関するドキュメント](upgrade-start-here.md) – IT 管理者向けの無料の技術ガイダンス。

- [Teamsアップグレード計画ワークショップ](./upgrade-workshops-landing-page.yml) – 無料の対話型アップグレード計画ワークショップでは、Teamsへのアップグレードの計画と実装に役立つガイダンス、ベスト プラクティス、リソースを受け取ることができます。

- [Skype for Business Online から Microsoft Teamsへのアップグレードの支援](upgrade-assisted.md) – オンライン ユーザーのTeamsへのアップグレードを支援Skype for Business自動化されたプログラム。

- [Microsoft 365のFastTrack](https://www.microsoft.com/fasttrack/microsoft-365) – Teams展開のサポートは、対象プランで利用できます。

- [Teamsライブ トレーニング](./instructor-led-training-teams-landing-page.yml) – Teamsを使用して組織を稼働させるために設計された無料のオンライン トレーニング クラス。

- [Teamsの白書き講演](./chalk-talks-landing-page.yml) – it 担当者と意思決定者向けの無料オンライン ワークショップ。Teamsの主要なシナリオのベスト プラクティスについて説明します。

- [Microsoft パートナー](https://www.microsoft.com/solution-providers/home) – Microsoft ソリューション プロバイダーは、Teamsを最大限に活用するのに役立ちます。

- [Microsoft Teamsブログ](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog) – 新機能、導入と使用状況のリソース、Teamsデバイス、その他のビジネス アプリケーションとの統合に関するニュースをTeamsします。

現在のSkype for Business Online のお客様の場合は、Teamsへのアップグレードの計画を今すぐ開始してください。 強力なコミュニケーションとコラボレーション機能を体験できることを楽しみにしています。また、その過程で支援することに取り組んでいます。  Skype for Business Online の廃止の詳細については、「[よく寄せられる質問 - Skype for BusinessからMicrosoft Teamsへのアップグレード」を](FAQ-journey.yml)参照してください。





