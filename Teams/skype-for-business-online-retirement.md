---
title: Skype for Business Online のサポート終了
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Skype for Business Online の提供提供Skype for Business、Microsoft が顧客の移行を支援する方法についてTeams。
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

2021 年 7 月 31 日に、Microsoft は Skype for Business提供を終了しました。 この提供の提供が 2019 年 7 月に発表されました。お客様は 2 年前に、お客様が新しいサービスへのアップグレードを計画Microsoft Teams。 Teamsは、コミュニケーションとコラボレーションのためのコア アプリであり、Microsoft 365。 Skype for Business Online の提供終了に向け、Microsoft は、お客様がプランを立て、アップグレードを正常に実行するために必要な情報とリソースを確実Teams。  コンシューマー Skypeサービスは、この提供が提供されなされた場合には影響を受け取らない。 Skype for Business Online が廃止された理由の背景については、「FAQ - SKYPE FOR BUSINESS から Microsoft Teams」[を参照してください](FAQ-journey.yml)。

Microsoft は、2022 年 6 月 30 日Skype for Businessオンライン インフラストラクチャの使用停止を開始します。 この記事では、TeamsOnly ユーザーが任意のバージョンのバージョンからアップグレードされた組織のガイダンスをSkype for Business。


## <a name="organizations-with-on-premises-deployments-of-skype-for-business-server"></a>オンプレミスにデプロイされた組織Skype for Business Server

Skype for Business Online の提供が完了しても、Skype for Business Server および Lync Server 2013 のオンプレミス 展開のサポートには影響しません。 ただし、オンラインとオンプレミスのユーザーが混在するハイブリッド顧客は、オンライン ユーザーをアップグレードする *必要* があります。 オンライン ユーザーには、TeamsUpgradePolicy を使用して TeamsOnly モードを割り当てる必要があります。 Microsoft では、オンライン ユーザーの残りのアップグレードを TeamsOnly モードにSkype for Business支援されたアップグレードを提供しています。 ハイブリッド組織は、この *提供がSkype for Business*、オンプレミスのユーザーをクラウドに移行する必要があります。 Microsoft は、TeamsOnly ユーザーとオンプレミスユーザーが混在するハイブリッド組織Skype for Businessサポートしています。 Skype for Business Server または Lync Server 2013 のハイブリッド展開をお持ちのお客様は、「Skype for Business Online の提供の提供の開始[」を確認する必要があります](/skypeforbusiness/hybrid/plan-hybrid-connectivity#implications-of-the-upcoming-retirement-of-skype-for-business-online)。

## <a name="what-to-expect-post-retirement"></a>提供提供後に期待する情報

クラウドにホームされたユーザーに TeamsOnly 以外のモードを割り当てはできなくなりました。 これはですね：

 - オンプレミス Skype for Business Server にホームされていない新しいユーザーにライセンスを与える場合、ユーザーには、テナントの TeamsUpgradePolicy のグローバル ポリシーに関係なく、TeamsOnly モードが自動的に割り当てられます。
 - ハイブリッド組織では、オンプレミスのユーザーをクラウドに移動すると、スイッチが で指定されたかどうかに関係なく、ユーザーには TeamsOnly `MoveToTeams` モードが自動的に割り当てられます `Move-CsUser`。
 - クラウドにホームされたユーザーには、TeamsOnly 以外のモードを割り当てできません。 オンラインで自宅のユーザー *は、オンプレミス* Skype for Businessサーバーを使用しません。

お客様には、Skype for Business Online にホームにいて、まだ TeamsOnly モードが割り当てられていないユーザーが残っている可能性があります。 お客様は、できるだけ早く TeamsOnly モードをこれらのユーザーに割り当てる必要があります。 Microsoft は、TeamsOnly モードではないオンライン ユーザー Skype for Businessアップグレードをサポートします。 アップグレードの支援を受け取るエクスペリエンスは、組織が純粋なオンライン組織か、オンプレミスのユーザーが所属する組織Skype for Business異なります。 詳細については、「オンラインからオンラインへの支援Skype for Business[アップグレード」をMicrosoft Teams](upgrade-assisted.md)。

支援されたアップグレードが完了すると、すべての *オンライン* ユーザーが TeamsOnly モードになります。 TeamsOnly モードのユーザーは、Teams で着信チャットと通話を受信し、Teams で会議をスケジュールします。 Skype for Business Online でチャットや通話を開始したり、会議のスケジュールを設定したりできない。  ただし、TeamsOnly ユーザーは、将来Skype for Businessまたは受信した会議に参加できます。 最後に、オンプレミスに自宅にいたユーザーはオンプレミスのままであり、 *TeamsOnly にはされません*。

## <a name="actions-to-take-before-june-30-2022"></a>2022 年 6 月 30 日より前に実行するアクション
Skype for Business Online が廃止されたので、Microsoft は 2022 年 6 月 30 日より早くサポート インフラストラクチャの使用停止を開始します。  任意のバージョンの Skype for Business からアップグレードされた TeamsOnly ユーザーを持つ組織では、次のいずれかの状況が該当する場合に対処する必要があります。

- アップグレード後、事前に Skype for Business に連絡先を持ち、まだ Teams にログインしていない TeamsOnly ユーザーがある場合。
- TeamsOnly にアップグレードする前に開催Skype for Businessオンライン会議に参加している TeamsOnly ユーザーが存在する場合。

このような状況が組織に適用される場合は、以下で説明するように、2022 年 6 月 30 日までに対処する必要があります。

 - **Skype for Business** オンライン連絡先: ユーザーが TeamsOnly モードにアップグレードされた後、そのユーザーが初めて Teams にログオンすると、そのユーザーの Skype for Business Online アカウント内の既存の連絡先は Teams に移行されます。 Microsoft が Skype for Business Online インフラストラクチャを削除した後、まだユーザーにログオンしていないユーザーの連絡先を移行Teams *。* Skype for Business から Teams に連絡先を移行するには、2022 年 6 月 30 日より前に Skype for Business から Teams に少なくとも 1 回ログオンしていたすべてのユーザーを推奨します。

 - **Skype for Businessオンライン会議:** 組織を TeamsOnly にアップグレードした後、ユーザーは新しい会議を新しい会議Teamsします。 場合によっては、TeamsOnly ユーザーが以前に開催Skype for Businessオンライン会議に参加している可能性があります。 現在、アップグレードされた TeamsOnly ユーザーと招待された出席者は、自分のクライアントを使用してSkype for Businessオンライン会議にSkype for Businessできます。 Microsoft が特定の TeamsOnly ユーザーの Skype for Business Online インフラストラクチャを削除した後、そのユーザーによって開催された Skype for Business Online 会議の残りは存在しなくなりました。 開催者と出席者は、これらの会議に参加できない。 TeamsOnly 組織のユーザーに、自分が開催した Skype for Business Online 会議の残りがある場合は、これらの会議を Teams勧めします。 または、管理者は、[会議](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms#trigger-meeting-migration-manually-via-powershell-cmdlet)移行サービスを使用して、これらの会議を会議にTeamsできます。 どちらの場合も、2022 年 6 月 30 日までにこれらのアクションを実行します。  


## <a name="how-microsoft-is-helping-customers-upgrade-to-teams"></a>Microsoft が顧客のアップグレードを支援する方法Teams

現在は、Skype for Business Online から Teams開始することを強Teams勧めします。 デプロイの計画とアップグレードに役立つリソースを活用TeamsからアップグレードSkype for Business。

- [Teamsおよびアップグレードのドキュメント](upgrade-start-here.md) – IT 管理者向け無料の技術ガイダンス。

- [Teams](./upgrade-workshops-landing-page.yml)計画のワークショップ – 無料の対話型アップグレード計画ワークショップ。このワークショップでは、Teams へのアップグレードを計画して実装するのに役立つガイダンス、ベスト プラクティス、リソースを受け取る予定です。

- [Skype for Business Online から Microsoft Teams](upgrade-assisted.md) への支援付きアップグレード – Skype for Business Online ユーザーを Teams にアップグレードする支援を受けています。

- [FastTrackのMicrosoft 365](https://www.microsoft.com/fasttrack/microsoft-365) – Teamsプランで利用できるデプロイ サポートを提供します。

- [Teamsライブ トレーニング](./instructor-led-training-teams-landing-page.yml) – 組織を稼働するように設計された無料のオンライン トレーニング クラスTeams。

- [Teams講演](./chalk-talks-landing-page.yml) – IT のプロや意思決定者向け無料のオンライン ワークショップで、Teams の主要なシナリオのベスト プラクティスについて説明します。

- [Microsoft パートナー](https://www.microsoft.com/solution-providers/home) – Microsoft ソリューション プロバイダーは、お客様がマイクロソフトのソリューションをフルに活用Teams。

- [Microsoft Teamsブログ](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog) - 新機能Teams導入と使用リソース、Teamsデバイス、他のビジネス アプリケーションとの統合に関するニュースを紹介します。

現在オンラインのお客様の場合は、Skype for Businessにアップグレードする計画をTeamsしてください。 お客様が強力なコミュニケーション機能とコラボレーション機能を体験できると共に、お客様の支援に取り組み、取り組み中です。  Skype for Business Online の提供Skype for Business詳細については、「FAQ- Skype for Business から Microsoft Teams」 (FAQ) [を参照してください](FAQ-journey.yml)。





