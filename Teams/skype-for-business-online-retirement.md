---
title: Skype for Business Online のサポート終了
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Skype for Business Online の廃止計画と、Microsoft が Teams への移行をどのように支援しているかについて説明します。
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
ms.openlocfilehash: 07d5e443075a80ddad8bda2e490cdd906c3900bf
ms.sourcegitcommit: 9de6b0b03f433e71fe239d292387eed33c11b531
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2022
ms.locfileid: "67657237"
---
# <a name="skype-for-business-online-retirement"></a>Skype for Business Online のサポート終了

2021 年 7 月 31 日、Microsoft はSkype for Business Online を廃止しました。 この廃止は 2019 年 7 月に発表され、Microsoft Teams へのアップグレードを計画するための 2 年前の通知が顧客に提供されました。 Teams は、Microsoft 365 のコミュニケーションとコラボレーションのためのコア アプリです。 Skype for Business Online が廃止された場合、Microsoft は Teams へのアップグレードを計画して実行するために必要な情報とリソースを顧客に確実に提供したいと考えています。  Skype コンシューマー サービスは、この廃止の影響を受けられません。 Skype for Business Online が廃止された理由の背景については、「[FAQ - Skype for Businessから Microsoft Teams へのアップグレード](FAQ-journey.yml)」を参照してください。

Microsoft は、Skype for Business Online インフラストラクチャの使用停止を 2022 年 6 月 30 日以降に開始します。 この記事には、任意のバージョンのSkype for Businessからアップグレードされた TeamsOnly ユーザーを持つ組織向けのガイダンスが含まれています。


## <a name="organizations-with-on-premises-deployments-of-skype-for-business-server"></a>Skype for Business Serverのオンプレミス展開を持つ組織

Skype for Business Online の廃止は、Skype for Business Serverと Lync Server 2013 のオンプレミス展開のサポートには影響しません。 ただし、オンラインユーザーとオンプレミスユーザーが混在するハイブリッド顧客は、 *オンライン* ユーザーをアップグレードする必要があります。 オンライン ユーザーは、TeamsUpgradePolicy を使用して TeamsOnly モードを割り当てる必要があります。 Microsoft では、TeamsOnly モードへの残りのSkype for Businessオンライン ユーザーのアップグレードを自動化するために、支援されたアップグレードを提供しています。 ハイブリッド組織は、この廃止の結果、*オンプレミス* のSkype for Business ユーザーをクラウドに移行する必要はありません。 Microsoft では、TeamsOnly ユーザーとオンプレミス Skype for Business ユーザーが混在するハイブリッド組織を完全にサポートしています。 Skype for Business Serverまたは Lync Server 2013 のハイブリッド展開をお持ちのお客様は、[Skype for Business Online の提供終了](/skypeforbusiness/hybrid/plan-hybrid-connectivity#implications-of-the-upcoming-retirement-of-skype-for-business-online)を確認する必要があります。

オンプレミスの Active Directory環境で新しいユーザーを作成するときに、これらのユーザーが Azure AD に同期され、Teams のライセンスを付与する場合は、*そのユーザーにライセンスを割り当てる前に*、**まずオンプレミスのSkype for Businessデプロイでユーザーを有効にし、Azure AD 接続を使用して変更がクラウドに同期されていることを確認する必要があります**。  Get-CsOnlineUser を使用して、変更がクラウドに完全に同期されていることを確認できます。 ユーザーの HostingProvider= "SRV:" の場合、変更は同期されています。  "sipfed.online.lync.com" にしないでください。   

## <a name="what-to-expect-post-retirement"></a>退職後の予定

クラウドに所属するユーザーに TeamsOnly 以外のモードを割り当てることはできなくなります。 これはですね：

 - オンプレミス Skype for Business Serverに所属していない新しいユーザーにライセンスを付与すると、テナントの TeamsUpgradePolicy のグローバル ポリシーに関係なく、ユーザーには TeamsOnly モードが自動的に割り当てられます。
 - ハイブリッド組織では、オンプレミスのホーム ユーザーをクラウドに移動すると、スイッチが `MoveToTeams` [ `Move-CsUser`.
 - クラウドに所属するユーザーは、TeamsOnly 以外のモードを割り当てることはできません。 オンラインホームユーザーは、オンプレミスSkype for Businessサーバーを使用 *しません*。

お客様には、Skype for Business Online に所属していて、TeamsOnly モードがまだ割り当てられていないユーザーが残っている可能性があります。 お客様は、できるだけ早く TeamsOnly モードをこれらのユーザーに割り当てる必要があります。 Microsoft は、TeamsOnly モードではないSkype for Business Online ユーザーに対して、サポートされるアップグレードを提供します。 アップグレードを支援するエクスペリエンスは、組織が純粋なオンライン組織であるか、オンプレミスのSkype for Business ユーザーを持つ組織であるかによって異なります。 詳細については、「[Skype for Business Online から Microsoft Teams へのアップグレードの支援」を参照してください](upgrade-assisted.md)。 支援されたアップグレードが完了すると、すべての *オンライン* ユーザーは TeamsOnly モードになります。 *オンプレミスに所属するすべてのユーザーはオンプレミスのままであり、TeamsOnly にはされません*。

TeamsOnly モードのユーザーは、Teams で受信チャットと通話を受け取り、Teams で会議をスケジュールすることもできます。 チャットや通話を開始したり、Skype for Business Online で会議をスケジュールしたりすることはできません。 TeamsOnly ユーザーは、今後、既に開催または受信している会議Skype for Business参加できます。 ただし、Microsoft が特定の TeamsOnly ユーザーのSkype for Business Online インフラストラクチャを削除した後、TeamsOnly ユーザーは匿名で会議Skype for Business参加することしかできません。  2022 年 6 月 30 日以降、新しく作成された TeamsOnly ユーザーは、Skype for Business Online インフラストラクチャでプロビジョニングされなくなったため、Skype for Business会議に招待された場合は匿名で参加する必要があります。


## <a name="actions-to-take-before-june-30-2022"></a>2022 年 6 月 30 日までに実行するアクション
Skype for Business Online が廃止されたので、Microsoft は 2022 年 6 月 30 日より間もなく、サポート インフラストラクチャの使用停止を開始します。  任意のバージョンのSkype for Businessからアップグレードされた TeamsOnly ユーザーを持つすべての組織では、次のいずれかの状況に該当する場合は、アクションを実行する必要があります。

- previoulsy がSkype for Businessに連絡先を持っていて、アップグレード後に Teams にまだログインしていない TeamsOnly ユーザーがいる場合。 
- TeamsOnly にアップグレードする前に開催した Skype for Business Online 会議を引き続き持つ TeamsOnly ユーザーがいる場合。

これらの状況のいずれかが組織に適用される場合は、以下に説明するように、2022 年 6 月 30 日までにアクションを実行する必要があります。

 - **Skype for Business オンライン連絡先:** ユーザーが TeamsOnly モードにアップグレードされると、そのユーザーが Teams に初めてログオンすると、そのユーザーのSkype for Business Online アカウント内の既存の連絡先はすべて Teams に移行されます。 Microsoft が Skype for Business Online インフラストラクチャを削除した後は、*Teams にまだログオンしていないユーザーの連絡先を* 移行できなくなります。 Skype for Businessから Teams に連絡先を移行するには、以前にSkype for Businessしていたすべてのユーザーが、2022 年 6 月 30 日までに少なくとも 1 回 Teams にログオンすることをお勧めします。

 - **Skype for Business オンライン会議:** 組織が TeamsOnly にアップグレードされると、ユーザーはすべての新しい会議を Teams 会議として作成します。 TeamsOnly ユーザーは、以前に開催したSkype for Businessオンライン会議を引き続き開催している場合があります。 現在、アップグレードされた TeamsOnly ユーザーと招待された出席者は、Skype for Business クライアントを使用して、これらのSkype for Business Online 会議に参加できます。 ただし、Microsoft が特定の TeamsOnly ユーザーのSkype for Business Online インフラストラクチャを削除した後、そのユーザーは匿名で Skype for Business 会議に参加することしかできず、*そのユーザーが編成した* 残りの Skype for Business Online 会議は存在しなくなります。 開催者と出席者は、これらの会議に参加できません。 TeamsOnly 組織のユーザーに、組織したオンライン会議Skype for Business残っている場合は、Teams 会議としてこれらの会議のスケジュールを変更することをお勧めします。 または、管理者は [会議移行サービス](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms#trigger-meeting-migration-manually-via-powershell-cmdlet) を使用して、これらの会議を Teams 会議に変換することもできます。 いずれの場合も、2022 年 6 月 30 日までにこれらのアクションを完了します。  


## <a name="how-microsoft-is-helping-customers-upgrade-to-teams"></a>Microsoft が顧客の Teams へのアップグレードを支援する方法

Skype for Business Online から Teams へのアップグレードを今すぐ開始することを強くお勧めします。 Teams の展開を計画し、Skype for Businessからアップグレードするのに役立つリソースを利用します。

- [Teams の展開とアップグレードに関するドキュメント](upgrade-start-here.md) - IT 管理者向けの無料の技術ガイダンス。

- [Teams アップグレード計画ワークショップ](./upgrade-workshops-landing-page.yml) – 無料の対話型アップグレード計画ワークショップ。ここでは、Teams へのアップグレードの計画と実装に役立つガイダンス、ベスト プラクティス、リソースを受け取ることができます。

- [Skype for Business Online から Microsoft Teams へのアップグレードの支援](upgrade-assisted.md) – オンライン ユーザーを Teams にアップグレードする際に役立つ自動プログラムSkype for Business。

- [FastTrack for Microsoft 365](https://www.microsoft.com/fasttrack/microsoft-365) – 対象プランで利用できる Teams 展開サポート。

- [Teams ライブ トレーニング](./instructor-led-training-teams-landing-page.yml) – Teams を使用して組織を稼働させるために設計された無料のオンライン トレーニング クラス。

- [Teams の白いトーク](./chalk-talks-landing-page.yml) – It 担当者と意思決定者向けの無料オンライン ワークショップ。Teams の主要なシナリオのベスト プラクティスについて説明します。

- [Microsoft パートナー](https://www.microsoft.com/solution-providers/home) – Microsoft ソリューション プロバイダーは、Teams を最大限に活用するのに役立ちます。

- [Microsoft Teams ブログ](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog) – 新機能、導入と使用状況のリソース、Teams デバイス、およびその他のビジネス アプリケーションとの統合に関する Teams ニュース。

現在の Skype for Business Online のお客様は、今すぐ Teams へのアップグレードの計画を開始してください。 強力なコミュニケーションとコラボレーション機能を体験できることを楽しみにしています。また、その過程で支援することに取り組んでいます。  Skype for Business Online の廃止の詳細については、「[よく寄せられる質問 - Skype for Businessから Microsoft Teams へのアップグレード](FAQ-journey.yml)」を参照してください。





