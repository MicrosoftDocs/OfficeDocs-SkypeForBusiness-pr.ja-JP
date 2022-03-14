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
ms.openlocfilehash: 6c18871756c8081b7013666d98d1599cfec4117f
ms.sourcegitcommit: b635f3765498ae23f535a33fa9ffea5068eecb14
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2022
ms.locfileid: "63463740"
---
# <a name="skype-for-business-online-retirement"></a>Skype for Business Online のサポート終了

2021 年 7 月 31 日に、Microsoft は Skype for Business提供を終了しました。 この提供の提供が 2019 年 7 月に発表されました。お客様は 2 年前に、お客様が新しいサービスへのアップグレードを計画Microsoft Teams。 Teamsは、コミュニケーションとコラボレーションのためのコア アプリであり、Microsoft 365。 Skype for Business Online の提供終了に向け、Microsoft は、お客様がプランを立て、アップグレードを正常に実行するために必要な情報とリソースを確実Teams。  コンシューマー Skypeこの提供の影響を受け取る必要があります。

## <a name="why-is-skype-for-business-online-retiring"></a>Skype for Business Online が廃止される理由

導入以来、Skype for Business Online は世界中の何百万人ものユーザーにとって貴重なツールでした。 インスタント メッセージング、通話、ビデオを組み合わせることで、Skype for Business Online はビジネスコミュニケーションの新しい可能性を確立しました。 Teamsは、そのビジョンの次の章です。 

この機能は、Microsoft Teams Online の機能Skype for Business超えるものです。 継続的なプラットフォームの革新と開発は、Teams、機能、柔軟性、およびセキュリティの恩恵を受けるユーザーを意味します。 次の機能を 1 つのエクスペリエンスに組み合わせることでTeams新しい作業方法が可能になります。

- チャット
- ビデオ
- 通話
- ドキュメントコラボレーション
- アプリケーション統合

Teamsは、Skype for Business Online のアップグレード以上のものです。 これは、学校や組織の俊敏性を高め、主要なワークフローの効率を向上させる強力なツールです。 詳細については、「Forrester[™](https://www.microsoft.com/microsoft-365/blog/wp-content/uploads/sites/2/2019/04/Total-Economic-Impact-Microsoft-Teams.pdf?rtc=1) の総経済的影響」Teamsホワイト ペーパーを参照してください。このホワイト ペーパーでは、Microsoft Teams。

Skype for Business Online の提供Skype for Businessについては、「FAQ - Skype for Business から Microsoft Teams」[を参照してください](FAQ-journey.yml)。

## <a name="organizations-with-skype-for-business-online"></a>Skype for Business Online を使用している組織

Microsoft は、組織がオンライン ユーザーの残りのユーザーを [オンラインのみ] Skype for Business移行するための支援Teams提供しています。 Teamsは、ほとんどの Microsoft 365 Business プランと Enterprise プランで利用できます。また、既存のライセンス投資はビジネス プランにTeams。 現在 Skype for Business Online に含まれるプレミアム ワークロードの機能は Teams のプレミアム ワークロードとしても継続的に利用できます。 たとえば、電話会議をスタンドアロンで購入した場合、または Skype for Business を使用して E5 の一部として購入した場合、電話会議は Teams で有効になります。

## <a name="organizations-with-on-premises-deployments-of-skype-for-business-server"></a>オンプレミスにデプロイされた組織Skype for Business Server

Skype for Business Online の提供が完了しても、Skype for Business Server Lync Server 2013 のオンプレミス 展開のサポートには影響しません。 ただし、オンラインとオンプレミスのユーザーが混在するハイブリッド顧客は、オンライン ユーザーをアップグレードする *必要* があります。 これらのオンライン ユーザーには、TeamsUpgradePolicy Teamsのみモードで割り当てる必要があります。 Microsoft は、オンライン ユーザーの残りのユーザーのアップグレードを自動化するための支援Skype for BusinessのみモードTeams提供しています。 ハイブリッド組織では、この提供が取 *り* やSkype for Business、オンプレミスのユーザーをクラウドに移行する必要があります。 Microsoft は、ハイブリッド組織とハイブリッド組織を完全にサポートTeamsユーザーとオンプレミスのユーザーのみをSkype for Businessしています。 Skype for Business Server または Lync Server 2013 のハイブリッド展開をお持ちのお客様は、「Skype for Business Online の提供が近日提供が予定されている場合の影響[」を確認する必要があります](/skypeforbusiness/hybrid/plan-hybrid-connectivity#implications-of-the-upcoming-retirement-of-skype-for-business-online)。

## <a name="what-to-expect-post-retirement"></a>提供提供後に期待する情報

クラウドにホームされたユーザーに TeamsOnly 以外のモードを割り当てはできなくなりました。 これはですね：
 - (オンプレミスの Skype for Business Server にホームされているユーザーを除く) 新しいユーザーにライセンスを与え、テナントの TeamsUpgradePolicy のグローバル ポリシーに関係なく、ユーザーには TeamsOnly モードが自動的に割り当てられます。
 - ハイブリッド組織では、オンプレミスのユーザーをクラウドに移動すると、ユーザーには自動的に TeamsOnly モードが割り当てられます (`MoveToTeams``Move-CsUser`スイッチが で指定されたかどうかの変更)。
 - クラウドにホームされているユーザー (オンプレミスの Skype for Business サーバーを使用しないなど) には、Teams のみ以外のモードを割り当てすることはできません。

ユーザー人口の残りの部分が Skype for Business Online にホームされ、まだ [のみ] モードで割り当てられていないTeamsがあります。  顧客は、できるだけ早Teamsユーザーに [のみ] モードを割り当てる必要があります。  さらに、Microsoft では、オンライン ユーザーが Skype for Business モードではない場合は、Teamsアップグレードを提供します。  アップグレードの支援を受け取るエクスペリエンスは、組織が純粋なオンライン組織か、オンプレミスのユーザーが所属する組織Skype for Business異なります。  詳細については、「オンラインからオンラインへの支援Skype for Business[アップグレード」をMicrosoft Teams](upgrade-assisted.md)。

支援されたアップグレードが完了すると、すべての *オンライン* ユーザーが [のみ] Teamsされます。 [Teams モードのユーザーは、Teams で着信チャットと通話を受信し、Teams で会議をスケジュールします。 Skype for Business Online でチャットや通話を開始したり、会議をスケジュールしたりすることはできません。  ただし、Teams既にSkype for Businessまたは受信した会議に参加できるのは、ユーザーのみです。 最後に *、オンプレミスに持* ち込むすべてのユーザーはオンプレミスのままであり、Teamsされません。


## <a name="how-microsoft-is-helping-customers-upgrade-to-teams"></a>Microsoft が顧客のアップグレードを支援する方法Teams

現在は、Skype for Business Online から Teams開始することを強Teams勧めします。

デプロイの計画とアップグレードに役立つリソースを活用TeamsからアップグレードSkype for Business。

- [Teamsおよびアップグレードのドキュメント](upgrade-start-here.md) – IT 管理者向け無料の技術ガイダンス。

- [Teams](./upgrade-workshops-landing-page.yml)計画のワークショップ – 無料の対話型アップグレード計画ワークショップ。このワークショップでは、Teams へのアップグレードを計画して実装するのに役立つガイダンス、ベスト プラクティス、リソースを受け取る予定です。

- [Skype for Business Online から Microsoft Teams](upgrade-assisted.md) への支援付きアップグレード – Skype for Business Online ユーザーを Teams にアップグレードする支援を受けています。

- [FastTrackのMicrosoft 365](https://www.microsoft.com/fasttrack/microsoft-365) – Teamsプランで利用できるデプロイ サポートを提供します。

- [Teamsライブ トレーニング](./instructor-led-training-teams-landing-page.yml) – 組織を稼働するように設計された無料のオンライン トレーニング クラスTeams。

- [Teams講演](./chalk-talks-landing-page.yml) – IT のプロや意思決定者向け無料のオンライン ワークショップで、Teams の主要なシナリオのベスト プラクティスについて説明します。

- [Microsoft パートナー](https://www.microsoft.com/solution-providers/home) – Microsoft ソリューション プロバイダーは、お客様がマイクロソフトのソリューションをフルに活用Teams。

- [Microsoft Teamsブログ](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog) - 新機能Teams導入と使用リソース、Teamsデバイス、他のビジネス アプリケーションとの統合に関するニュースを紹介します。

現在オンラインのお客様の場合は、Skype for Businessにアップグレードする計画をTeamsしてください。 お客様が強力なコミュニケーション機能とコラボレーション機能を体験できると共に、お客様の支援に取り組み、取り組み中です。




