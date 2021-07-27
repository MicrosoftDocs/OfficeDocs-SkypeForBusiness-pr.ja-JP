---
title: PSTN 接続オプション
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 07/08/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
ms.reviewer: crowe
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
- seo-marvel-may2020
search.appverid: MET150
description: 通話 (PSTN Teams) オプションと、組織に対して行う決定の詳細について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 57327c408331acb3deb4d2269d87a2a30de13a75
ms.sourcegitcommit: 79d20fa2c45173d5a990551e79571caff06d7f82
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2021
ms.locfileid: "53486257"
---
# <a name="pstn-connectivity-options"></a>PSTN 接続オプション

Microsoft は、お客様の組織Exchangeプライベート ブランチ サービス (PBX) 機能を提供電話システム。 ただし、ユーザーが組織外で通話を発信するには、PSTN (Public Switched Telephone Network) 電話システムに接続する必要があります。

この記事では、PSTN 接続オプションについて説明します。 Microsoft 音声ソリューションの詳細については、「音声ソリューションを計画する」を電話システム詳細については、「音声ソリューションを計画するTeams[参照してください](cloud-voice-landing-page.md)。

PSTN 電話システム接続するには、次のオプションから選択できます。

- [**通話プラン**](#phone-system-with-calling-plan)。 MICROSOFT を PSTN 通信事業者として使用する、クラウド内のすべてソリューション。

- [**オペレーター Connect、**](#phone-system-with-operator-connect)現在パブリック プレビューでのみ **使用できます。**  オペレーター サービスConnect、既存の通信事業者が Microsoft Operator Connect プログラムに参加している場合は、PSTN 通話とセッション ボーダー コントローラー (SBC) を管理できます。 

- [**ダイレクト ルーティング**](#phone-system-with-direct-routing): セッション ボーダー コントローラー (SBC) を接続して、独自の PSTN 通信業者を使用電話システム。


オプションの組み合わせを選択して、複雑な環境向けソリューションを設計したり、複数ステップの移行を管理したりすることができます。

選択したオプションは、一部の機能の構成方法電話システム注意してください。 詳細については、この記事の [後半の「構成に関](#configuration-considerations) する考慮事項」を参照してください。


## <a name="phone-system-with-calling-plan"></a>電話システムプランの使用 

電話システムプランを使用する方法は、ユーザーをサポートする Microsoft のクラウド内音声Teamsです。 これは、PSTN に接続する最も電話システムオプションです。 このオプションを使用すると、次の図に示すように、Microsoft は PSTN 通信事業者として機能します。

![図 1 は、通話プラン電話システムを示しています](media/voice-solutions-simple.png)

次に対して 「はい」と答える場合は、電話システムプランを使用する方法が適切なソリューションです。

- 通話プランは、お客様のリージョンで利用できます。
- 現在の PSTN 通信事業者を保持する必要はない。
- PSTN への Microsoft が管理するアクセスを使用する場合。

このオプションでは、次のオプションを使用します。 

- (ライセンスMicrosoft 電話に応じて) 世界中の電話への通話を可能にする国内通話プランまたは国際通話プランが追加された新しいシステムを利用できます。

- 通話プランは、オンプレミスのデプロイまたはメンテナンスを必要と &mdash; Microsoft 365。

- 注: 必要に応じて、サード パーティの PBX、アナログ デバイス、SBC でサポートされているその他のサードパーティのテレフォニー機器との相互運用性を確保するために、サポートされているセッション ボーダー コントローラー (SBC) を直接ルーティング経由で接続できます。

このオプションを使用するには、アプリケーションへの接続が中断Microsoft 365。

通話プランの詳細については、次の記事を参照してください。

- [どの通話プランが適していますか?](calling-plan-landing-page.md)
- [通話プランを購入する方法](calling-plans-for-office-365.md)
- [通話プランが利用可能な国と地域](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [通話プランを設定する](set-up-calling-plans.md)


## <a name="phone-system-with-operator-connect"></a>電話システム 演算子を使用Connect

オペレーター Connect では、現在パブリック プレビュー中です。既存の通信事業者が Microsoft Operator Connect プログラムに参加している場合は、PSTN 通話を Teams に持ち込むサービスを管理できます。 通信事業者が PSTN 通話サービスとセッション ボーダー コントローラー (SBC) を管理し、ハードウェアの購入と管理を節約できます。

オペレーター Connectは、次の場合に組織に適切なソリューションになる可能性があります。

- Microsoft 通話プランは、地理的な場所では利用できません。
- お好みの運送業者は、Microsoft Operator Connectです。
- 通話を有効にする新しい通信事業者を探Teams。

Operator Connect の利点と要件、およびこのプログラムに参加している通信事業者の一覧については、「プラン オペレーターサービス」を[Connect。](operator-connect-plan.md) オペレーター アカウントを構成する方法の詳細についてはConnectを構成する[」をConnect。](operator-connect-configure.md)


## <a name="phone-system-with-direct-routing"></a>電話システムルーティングの使用

このオプションは、電話システムに示すように、ダイレクト ルーティングを使用して、ネットワークをテレフォニー ネットワークに接続します。 

![図 5 は、直接ルーティング電話システムを示しています](media/voice-solution-with-direct-routing.png)

次の質問に対して 「はい」と回答した場合は、電話システム ルーティングを使用する方法が適切なソリューションです。

- このコマンドを使用してTeamsを電話システム。
- 現在の PSTN 通信事業者を保持する必要があります。
- 通話プランを経由する通話と、運送業者を介した通話を組み合わせ、ルーティングを混在したい場合。
- サードパーティの PBX や、オーバーヘッド ページ、アナログ デバイスなどの機器と相互運用する必要があります。

このオプションでは、次のオプションを使用します。

- サポートされている独自のセッション ボーダー コントローラー (SBC) を、追加の電話システムソフトウェアを必要とせずに、ネットワーク に接続します。

- 事実上、任意のテレフォニー キャリアを使用して、電話システム。

- このオプションの構成と管理を選択するか、通信事業者またはパートナーが構成および管理できます (運送業者またはパートナーにこのオプションが提供されていないか確認してください)。

- サードパーティの PBX やアナログ デバイスなどのテレフォニー機器とデバイス間の相互運用性を &mdash; &mdash; 電話システム。

このオプションには、次が必要です。

- ネットワークへの接続が中断Microsoft 365。

- サポートされている SBC のデプロイと保守。

- サード パーティの運送業者との契約。
  (サード パーティ製 PBX、アナログ デバイス、その他のテレフォニー機器への接続を提供するオプションとして、通話プランを利用しているユーザーに電話システムしない限り)。

ダイレクト ルーティングの詳細については、次の記事を参照してください。

- [ダイレクト ルーティングを計画する](direct-routing-plan.md)
- [ダイレクト ルーティングを構成する](direct-routing-configure.md)
- [ダイレクト ルーティングで使用する音声ルーティング ポリシーを管理する](manage-voice-routing-policies.md)
- [ダイレクト ルーティングの場所に基づくルーティングを計画する](location-based-routing-plan.md)
- [ダイレクト ルーティングに対応する認定済みセッション ボーダー コントローラーのリスト](direct-routing-border-controllers.md)



## <a name="configuration-considerations"></a>構成に関する考慮事項

選択電話システム PSTN 接続オプションに関係なく、ほとんどの機能は同じです。 たとえば、未応答の通話と転送設定、通話転送、保留のカスタム音楽、コール パーク、共有回線、音声アプリはすべて使用できます。 すべての機能の完全な電話システムについては、次[の](here-s-what-you-get-with-phone-system.md)ページを参照電話システム。

ただし、特定の機能の構成方法に影響を与える機能には、いくつかの電話システムがあります。 たとえば、ダイレクト ルーティングでは、通話ルーティングを構成するための追加の手順が必要です。 別の例として、ダイレクト ルーティングは場所ベースのルーティング (LBR) を提供します。そのため、許可されていない特定の地理的な場所で有料バイパスを制限できます。 

次の表は、主な構成の違いを示しています。 表の後のセクションには、詳細情報と詳細へのリンクが示されています。

| オプション | 説明 | 電話番号の管理 | 通話ルーティング | 緊急通話の利用可 |
| :------------| :-------| :-------| :-------| :-------| 
| 通話プラン | - Microsoft は PSTN 通信事業者として機能します。<br>- SBC を購入または管理する必要はない。| Microsoft を通じて取得。| -Microsoft によって管理されます。 <br> -Admin は、番号変換用にユーザー ダイヤル プランを構成します。 | - Microsoft によって有効になります。 <br> -Admin はアドレスを登録します。 <br> -動的呼び出しがサポートされています。 |
| 演算子Connect | -Carrier は PSTN 接続と SBC を管理します。 <br> - SBC を購入または管理する必要はない。 | -通信事業者を通じて取得します。 <br> - 運送業者によって管理される緊急対応の住所に関連付けられている番号。  | -通信事業者によって管理されます。 <br>-Admin は、番号変換用にユーザー ダイヤル プランを構成します。 | -通信事業者によって有効になります。 <br> -Admin はアドレスを登録します。 <br> -動的呼び出しがサポートされています。 |
| ダイレクト ルーティング | - サード パーティ ベンダーから購入した認定 SBC が必要です。<br>-Connectに SBC を電話システム。<br> - 既存の PSTN 通信事業者を使用します。 | 運送業者を通じて取得されます。 | - 管理者による追加の構成が必要です。<br>-Admin は、番号変換用にトランク ダイヤル プランを構成します。 <br>-LBR を使用して有料バイパスを制限できます。 | - 管理者による追加の構成が必要です。 <br>-登録済みのアドレスはサポートされていません。 <br>-動的呼び出しはサポートされますが、追加の構成が必要です。 |
|||||


### <a name="phone-number-management"></a>電話番号の管理

Microsoft には、組織内のユーザーに割り当て可能なサブスクライバー (ユーザー) 番号と、有料サービス番号と無料サービス番号として利用できるサービス番号の 2 種類があります。 サービス番号は、サブスクライバー番号よりも高い同時通話容量を持ち、電話会議、自動応答、通話キューなどのサービスに割り当てることができます。

次の条件を決定する必要があります。

- Microsoft からの新しい電話番号が必要なのはどのユーザー ロケーションですか?
- どの種類の電話番号が必要ですか (サブスクライバーまたはサービス)?
- どんな方法で既存の電話番号を Teams に移植しますか?

電話番号を取得および管理する方法は、PSTN 接続オプションによって異なります。

- 通話プランの電話番号の管理については、「組織の電話番号を管理 [する」を参照してください](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。

- オペレーター アカウントを使用して電話番号を管理する方法についてはConnect演算子を使用して電話番号を[設定する」をConnect。](operator-connect-configure.md#set-up-phone-numbers)

- ダイレクト ルーティングの電話番号の管理については、「電話番号を構成し、エンタープライズ音声とボイスメールを有効 [にする」を参照してください](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail-online)。


### <a name="call-routing-and-dial-plans"></a>通話ルーティングとダイヤル プラン

通話ルーティングの構成方法は、PSTN 接続オプションによって異なります。  

- 通話プランの場合、通話ルーティングの大部分は Microsoft 通話プラン インフラストラクチャによって処理されます。 ユーザー ダイヤル プランは、通話承認と通話ルーティングの番号変換の目的で構成します。 詳細については、「ダイヤル プラン [とは」を参照してください](what-are-dial-plans.md)。

- オペレーター サービスConnect、ほとんどの通話ルーティングは通信事業者によって管理されます。  ユーザー ダイヤル プランは、通話承認と通話ルーティングの番号変換の目的で構成します。 詳細については、「ダイヤル プラン [とは」を参照してください](what-are-dial-plans.md)。

- ダイレクト ルーティングの場合は、音声ルートを指定し、ユーザーに音声ルーティング ポリシーを割り当て、通話ルーティングを構成する必要があります。 番号変換のダイヤル プランをトランク レベルで構成して、セッション ボーダー コントローラー (SBC) との相互運用性を確保できます。 詳細については、「ダイレクト ルーティングの音声ルーティング[の構成」、音声ルーティング](direct-routing-voice-routing.md)[ポリシー](manage-voice-routing-policies.md)の管理、電話番号の翻訳に関[するページを参照してください](direct-routing-translate-numbers.md)。 


### <a name="location-based-routing-for-direct-routing"></a>Location-Based ルーティングの詳細

一部の国や地域では、PSTN 通信事業者をバイパスして、遠距離通話コストを削減する方法は違法です。 Location-Based ルーティング (LBR) を使用すると、地理的な場所に基づいて、ユーザーのTeamsバイパスを制限できます。 LBR を計画および構成する方法の詳細については、次の記事を参照してください。

- [ダイレクト ルーティングの場所に基づくルーティングを計画する](location-based-routing-plan.md)
- [場所に基づくルーティングのネットワーク設定を構成する](location-based-routing-configure-network-settings.md)
- [ダイレクト ルーティングの場所に基づくルーティングを有効にする](location-based-routing-enable.md)
- [Contoso のケース スタディ: Location-Based ルーティング](voice-case-study-location-based-routing.md)<br>
  架空の多国籍企業 Contoso が、組織に対して Location-Based ルーティングを実装した方法について説明します。


### <a name="emergency-calling"></a>緊急通話

緊急通話の構成方法は、PSTN 接続オプションによって異なります。

- 通話プランの場合、各ユーザーは自動的に緊急通話を有効にし、割り当てられた電話番号に関連付けられている登録済みの緊急対応の住所を持っている必要があります。 動的緊急通話 (クライアントの場所に基Teams) がサポートされています。  

- オペレーター Connectでは、各ユーザーは緊急通話を自動的に有効にし、割り当てられた電話番号に関連付けられた登録済みの緊急対応の住所を持っている必要がありますが、設定できるのは運送業者パートナーのみです。 動的緊急通話 (クライアントの場所に基Teams) がサポートされています。

- 直接ルーティングの場合は、Teams 緊急通話ルーティング ポリシー (TeamsEmergencyCallRoutingPolicy) を使用して緊急電話番号と関連するルーティング先を定義することで、ユーザーの緊急通話ポリシーを定義する必要があります。 登録済みの緊急対応の場所は、ダイレクト ルーティング ユーザーではサポートされていません。 動的緊急通話の場合は、緊急通話をルーティングし、場合によってはパートナーの接続用に追加の構成が必要です。

緊急通話の概念と用語、および緊急通話と動的緊急通話を構成する方法の詳細については、次の記事を参照してください。

- [緊急通話を管理する](what-are-emergency-locations-addresses-and-call-routing.md)
- [動的な緊急通話を計画して構成する](configure-dynamic-emergency-calling.md)
- [緊急通話ポリシーを管理する](manage-emergency-calling-policies.md)
- [ダイレクト ルーティングの緊急通話ルーティング ポリシーを管理する](manage-emergency-call-routing-policies.md)
- [Contoso のケース スタディ: 緊急通話](voice-case-study-emergency-calling.md)<br>
  架空の多国籍企業 Contoso が組織の緊急呼び出しを実装した方法について説明します。


### <a name="network-topology-for-voice-features"></a>音声機能のネットワーク トポロジ

動的緊急通話または直接ルーティング用の Location-Based ルーティングをデプロイする場合は、これらの機能で使用するネットワーク設定を構成する必要Microsoft Teams。 ネットワーク リージョン、ネットワーク サイト、ネットワーク サブネット、信頼済み IP アドレスのネットワーク設定を構成する方法については、次の記事を参照してください。

- [Microsoft Teams のクラウド音声機能のネットワーク設定 - 概念と用語](cloud-voice-network-settings.md)
- [クラウド音声機能のネットワーク トポロジを管理する Microsoft Teams](manage-your-network-topology.md)



