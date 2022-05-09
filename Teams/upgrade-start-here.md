---
title: Skype for BusinessをTeamsにアップグレードする概要
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: この記事は、Skype for BusinessからMicrosoft Teamsへのアップグレードの開始に役立ちます。
ms.localizationpriority: medium
search.appverid: MET150
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
- seo-marvel-may2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
f1.keywords:
- ms.teamsadmincenter.dashboard.helparticle.journeyskypeforbusinessteams
- ms.teamsadmincenter.dashboard.trainingvideos.journeytoteams
- ms.teamsadmincenter.dashboard.widget.upgrade.planning
- ms.teamsadmincenter.dashboard.widget.upgrade.pause
- ms.teamsadmincenter.dashboard.widget.upgrade.rolledback
- ms.teamsadmincenter.users.teamsupgradestatuscolumn
- ms.teamsadmincenter.users.teamsupgradepage
- ms.teamsadmincenter.dashboard.helparticle.quickstartteamsadmin
- ms.teamsadmincenter.dashboard.helparticle.upgradetoteams
- CSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: b581f509655327c944876306cee666f39e07ef6c
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58589413"
---
# <a name="get-started-on-your-upgrade-from-skype-for-business-to-microsoft-teams"></a>Skype for BusinessからMicrosoft Teamsへのアップグレードに関する概要

Skype for Business から Microsoft Teams へのアップグレードが予定されています。 Teams を始めたばかりでも、既に Skype for Business とともに Teams を使用している場合でも、アップグレードの準備ができている場合でも、Teams への旅を成功させるために必要なもののすべてが揃っていることを確認したいと思います。

Skype for Business Online から Teams にアップグレードする場合でも、Skype for Business オンプレミス環境から Teams にアップグレードする場合でも、アップグレード フレームワークは、ビジネス シナリオに基づいたプロセスをガイドします。 また、Skype for BusinessからTeamsへのアップグレードを正常に実装するための追加のトレーニングとリソースについては、[アップグレード ハブ](upgrade-skype-teams.yml)にアクセスすることをお勧めします。

[!INCLUDE [sfbo-retirement](../Skype/Hub/includes/sfbo-retirement.md)]

アップグレードに関してよく寄せられる質問については、こちらをご覧ください。

## <a name="why-upgrade-to-microsoft-teams"></a>Microsoft Teams にアップグレードする理由

Microsoft Teams では、Skype for Business の機能を拡張して、チャット、会議、通話、共同作業、アプリの統合、ファイル ストレージを単一のインターフェイスにまとめます。 Teamsは、ユーザーの作業を効率化し、ユーザーの満足度を向上し、ビジネス成果を加速するのに役立ちます。 Microsoft では、継続的に Teams の機能を拡張することで、新しい方法でユーザーがコミュニケーションと共同作業を行えるよう、組織的および地理的な障壁を壊してプロセスと意思決定の効率性を高めます。 Teams にアップグレードする利点の詳細については、Forrester のレポート「[Microsoft Teams による総合的な経済効果](https://www.microsoft.com/microsoft-365/blog/wp-content/uploads/sites/2/2019/04/Total-Economic-Impact-Microsoft-Teams-Infographic.pdf)」を参照してください。  

## <a name="when-should-my-organization-migrate-to-teams"></a>組織はいつTeamsに移行する必要がありますか?

Skype for Business Online サービスは 2021 年 7 月 31 日まで完全に機能しますが、現在Teamsへのアップグレードを開始することを強くお勧めします。 今日アップグレードを開始すると、廃止日より前にアップグレードを完了するのに十分な時間が必要になります。 重複する機能方法 ("Islands mode") または select capabilities メソッドを使用して、Teamsにアップグレードすることを選択できます。 これらの方法の詳細については、「[Skype for BusinessからTeamsへのアップグレードの選択」](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)を参照してください。

## <a name="can-we-continue-to-use-skype-for-business-online-as-we-prepare-for-and-execute-our-upgrade-to-teams"></a>Teams の準備やアップグレードを実行しているときに、引き続き Skype for Business Online を使用することはできますか?

はい。Microsoft では、Skype for Business Online と Teams を一緒に実行するためのオプションをいくつか用意しています。 現在、この共存モードを使用すると、Teams 単独へのアップグレードを加速させながら、ユーザーは Teams に慣れ親しむことができます。 詳細については、[https://aka.ms/SkypeToTeams-Coexist](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)を参照してください。

## <a name="is-phone-system-available-for-teams-users"></a>Teams ユーザーは電話システム使用できますか?

はい。 電話システムは、TeamsOnly モードに移行した後、すべてのTeams ユーザーが使用できます。  さらに、Microsoft は、ユーザーが世界中のどこからでも電話を発信できるように、公衆交換電話網 (PSTN) に接続するためのオプションを提供しています。 詳細については、「[音声 - 電話システムおよび PSTN 接続」を](cloud-voice-landing-page.md)参照してください。

## <a name="can-we-continue-to-use-our-on-premises-telephony-infrastructure"></a>オンプレミスのテレフォニー インフラストラクチャを引き続き使用できますか?

はい。 電話システムダイレクト ルーティングを使用すると、ほぼすべてのテレフォニー通信事業者で電話システムを使用できます。 ダイレクト ルーティングでは、独自のセッション ボーダー コントローラー (SBC) を電話システムに直接接続します。 詳細については、「[電話システムのダイレクト ルーティング](direct-routing-landing-page.md)」を参照してください。

## <a name="how-is-microsoft-helping-customers-with-their-migration-to-teams"></a>Microsoft では、お客様がTeamsへの移行をどのように支援していますか?

Microsoft は、お客様が Skype for Business から Teams へ問題なく移行できるよう、貢献することに努めています。 Microsoft は、評価されたエンド ツー エンドのアップグレード成功フレームワークに基づいて構築された堅牢なガイダンスを提供しています。これは、Teams へのアップグレードを計画して実行するのに役立ちます。 このガイダンスは、計画を開始したばかりの場合、Skype for Business と共に Teams を使用している場合、Teams にアップグレードする準備ができている場合など、アップグレードのあらゆる段階に合わせて作成されています。

アップグレードの計画と実装を容易にするために、Microsoft では、アップグレード フレームワークについて理解し、アップグレードに向けたユーザーの準備に関する分析情報を共有し、Teamsに向けた組織の適切なパスを特定できるように設計された、無料のライブの対話型アップグレード計画ワークショップを開催しています。 アップグレード計画の概要セッションに参加してください。[https://aka.ms/SkypeToTeamsPlanning](./upgrade-workshops-landing-page.yml)。

Skype for Business Online を使用している組織は、2021 年 7 月 31 日にサービスを終了する前に、Skype for Business Online から正常に移行できるように、Microsoft 支援によるTeamsへのアップグレードの対象となる場合があります。 アップグレードの支援により、お客様に必要な技術的なタスクの数が減り、組織の準備、ユーザーの認識、およびTeamsトレーニングに重点を置く必要があります。

アップグレード支援を予定しているお客様は、アップグレード日の 3 か月前に、Teams管理センターとMicrosoft 365 メッセージ センターの両方で通知を受け取ります。 詳細については、「[Skype for Business Online から Microsoft Teamsへのアップグレードの支援」を](upgrade-assisted.md)参照してください。

## <a name="why-do-i-need-upgrade-guidance-cant-i-just-deletedecommission-skype-for-business"></a>アップグレード ガイダンスが必要な理由 単に Skype for Business を削除/使用停止させることはできますか?

Skype for Business から Teams へのアップグレードは、技術的な移行以上のものです。 それは、ユーザーによる連絡と共同作業の取り組み方の変革を意味するものであり、必ずしも変更は容易なものではありません。 理想的なアップグレード方法では、アップグレードの技術的な側面に対処するとともに、ユーザーの承認と Teams の導入を促して、有意義なユーザー エクスペリエンスおよびビジネス成果の実現を推進する必要があります。

## <a name="where-do-i-start-planning-for-teamsmy-upgrade-to-teams"></a>Teams の計画、Teams へのアップグレードのために最初に何をすればいいですか?

まず、アップグレードの成功フレームワークと関連リソースに精通してください。 このガイダンスは、Skype for Business から Teams へ移行するための基盤となります。

[アップグレード フレームワークの詳細](upgrade-framework.md)を参照し、[ライブ アップグレード計画の概要](./upgrade-workshops-landing-page.yml)セッションに参加してください。

> [!IMPORTANT]
> アップグレードが成功すると、技術面およびユーザー両方の準備が整ったことになります。Microsoft Teams への移行を進める際には、必ずこのガイダンスを活用してください。

> [!Tip]
> Skype for Business から Microsoft Teams へのアップグレードについては、次のセッションをご覧ください。

> - [アップグレードの概要](https://aka.ms/teams-upgrade-intro)
> - [アップグレードの計画](https://aka.ms/teams-upgrade-plan)
> - [共存と相互運用性](https://aka.ms/teams-upgrade-coexistence-interop)
> - [管理者の操作環境](https://aka.ms/teams-upgrade-admin)
