---
title: PSTN 接続のオプション
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
ms.openlocfilehash: 2c53b553a83349c3d4fd20a926f29b4c727175c73aba5ba0f5e352cf19a53f9e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54285943"
---
# <a name="pstn-connectivity-options"></a>PSTN 接続のオプション

Microsoft は、組織に完全Exchangeプライベート ブランチ サービス (PBX) 機能を提供電話システム。 ただし、ユーザーが組織外で通話を行う場合は、公衆交換電話網 (PSTN) 電話システムに接続する必要があります。

この記事では、PSTN 接続オプションについて説明します。 Microsoft 音声ソリューションの詳細については、「音声ソリューションの計画」を電話システム Teams詳細を[参照してください](cloud-voice-landing-page.md)。

PSTN に電話システム接続するには、次のオプションから選択できます。

- [**通話プラン**](#phone-system-with-calling-plan). MICROSOFT を PSTN キャリアとして使用する、クラウド内のオール イン ザ クラウド ソリューション。

- [**演算子Connect、**](#phone-system-with-operator-connect)現在パブリック プレビューでのみ **使用できます。**  Operator Connectを使用すると、既存の通信事業者が Microsoft Operator Connect プログラムの参加者である場合、PSTN 通話とセッション ボーダー コントローラー (SPC) を管理できます。 

- [**直接ルーティング**](#phone-system-with-direct-routing):セッション ボーダー コントローラー (SBC) を接続して、独自の PSTN キャリアを使用電話システム。


オプションの組み合わせを選択して、複雑な環境向けソリューションを設計したり、複数ステップの移行を管理したりできます。

選択するオプションまたはオプションは、一部の機能の構成電話システムに影響します。 詳細については、この記事 [の「構成に関する考慮事項](#configuration-considerations) 」を参照してください。


## <a name="phone-system-with-calling-plan"></a>通話プランが設定された電話システム。 

電話システムプランを使用する方法は、Microsoft のクラウド内音声ソリューションで、ユーザーをTeamsします。 これは、PSTN に接続する最も電話システムオプションです。 このオプションを使用すると、次の図に示すように、Microsoft は PSTN キャリアとして機能します。

![図 1 に、通話プラン電話システムを示します。](media/voice-solutions-simple.png)

次に対して yes と答えた場合は、電話システムプランを使用して設定を行うのが適切なソリューションです。

- 通話プランは地域で利用できます。
- 現在の PSTN 通信事業者を保持する必要はない。
- PSTN への Microsoft 管理アクセスを使用する場合。

このオプションを使用する場合: 

- Microsoft 通話プランに国内および国際通話プランを追加することにより、世界中の電話機に電話をかけることができます (ライセンス対象サービスのレベルによって異なります)。 

- 通話プランは一部のサーバーから動作しないので、オンプレミス展開の展開や &mdash; メンテナンスはMicrosoft 365。

- 注: 必要に応じて、サポートされているセッション ボーダー コントローラー (SBC) をダイレクト ルーティング経由で接続して、SBC でサポートされるサードパーティ製 PBX、アナログ デバイス、その他のサードパーティテレフォニー 機器との相互運用性を選択できます。

このオプションを使用するには、Microsoft 365 に継続的に接続することが必要です。

通話プランの詳細については、次の記事を参照してください。

- [どの通話プランが適していますか?](calling-plan-landing-page.md)
- [通話プランを購入する方法](calling-plans-for-office-365.md)
- [通話プランの国と地域の可用性](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [通話プランのセットアップ](set-up-calling-plans.md)


## <a name="phone-system-with-operator-connect"></a>電話システム演算子を使用Connect

現在パブリック プレビュー中のオペレーター Connect では、既存の通信事業者が Microsoft Operator Connect プログラムの参加者である場合、PSTN 通話を Teams に持ち込むサービスを管理できます。 通信事業者は PSTN 通話サービスとセッション ボーダー コントローラー (SPC) を管理し、ハードウェアの購入と管理を節約できます。

オペレーター Connect、次の場合に組織に適切なソリューションになる可能性があります。

- Microsoft 通話プランは地理的な場所では利用できません。
- お客様の希望する通信事業者は、Microsoft Operator Connect参加者です。
- 通話を有効にする新しい通信事業者を検索する場合は、Teams。

Operator Connect の利点と要件、およびこのプログラムに参加している通信事業者の一覧については[、「Plan Operator Connect」を参照してください](operator-connect-plan.md)。 演算子の構成方法の詳細については、「Configure Operator Connect」[を参照Connect。](operator-connect-configure.md)


## <a name="phone-system-with-direct-routing"></a>電話システムルーティングの使用

このオプションは、電話システムに示すように、ダイレクト ルーティングを使用してテレフォニー ネットワークに接続します。 

![図 5 に、ダイレクト ルーティング電話システムを示します。](media/voice-solution-with-direct-routing.png)

以下の質問に対して「はい」と答えた場合は、ダイレクト ルーティング機能を設定した電話システムが最適です。

- 電話システムによって Teams を使用する場合。
- 現在の PSTN 通信事業者を維持する必要がある。
- 一部の通話は通話プランを経由し、一部の通話は通信事業者を経由する、ミックス ルーティングにします。
- サードパーティ製の PBX や、オーバーヘッド ページ、アナログ デバイスなどの機器と相互運用する必要があります。

このオプションを使用する場合:

- 追加のオンプレミス ソフトウェアを必要とせずに、サポートされている独自のセッション ボーダー コントローラー (SBC) 電話システムに接続します。

- 仮想的に任意のテレフォニー キャリアを使用して、電話システム。

- このオプションを構成して管理するか、または通信事業者やパートナーが構成して管理するかを選択することができます (通信事業者またはパートナーがこのオプションを提供するかどうかを尋ねます)。

- サード パーティ製 PBX やアナログ デバイスなどのテレフォニー機器とデバイス間の相互運用性を &mdash; &mdash; 電話システム。

このオプションを実行するには、以下が必要です。

- Microsoft 365 に継続的に接続する必要があります。

- サポートされている SBC の展開および保守。

- サード パーティの通信事業者との契約。(通話プランが設定されている電話システムのユーザーが、サード パーティ PBX、アナログ デバイス、またはその他のテレフォニー機器との接続を提供するオプションとして展開されている場合を除きます。)

ダイレクト ルーティングの詳細については、次の記事を参照してください。

- [ダイレクト ルーティングを計画する](direct-routing-plan.md)
- [ダイレクト ルーティングを構成する](direct-routing-configure.md)
- [ダイレクト ルーティングで使用する音声ルーティング ポリシーの管理](manage-voice-routing-policies.md)
- [ダイレクト ルーティングの場所に基づくルーティングを計画する](location-based-routing-plan.md)
- [ダイレクト ルーティングに対応する認定済みセッション ボーダー コントローラーのリスト](direct-routing-border-controllers.md)



## <a name="configuration-considerations"></a>構成に関する考慮事項

ほとんどの電話システムは、選択した PSTN 接続オプションに関係なく同じです。 たとえば、未応答の通話と転送設定、通話転送、保留音のカスタム音楽、通話パーク、共有回線、音声アプリはすべて利用できます。 この機能の完全な電話システムについては、「次の機能を使用して取得する情報」[を電話システム。](here-s-what-you-get-with-phone-system.md)

ただし、特定の機能の構成方法に影響を与える機能にはいくつかの電話システムがあります。 たとえば、ダイレクト ルーティングでは、通話ルーティングを構成するための追加の手順が必要です。 別の例として、ダイレクト ルーティングは場所ベースルーティング (LBR) を提供します。そのため、許可されていない特定の地理的な場所で有料バイパスを制限できます。 

次の表に、主な構成の違いを示します。 表に続くセクションでは、詳細情報と詳細へのリンクを提供します。

| オプション | 説明 | 電話番号管理 | 通話ルーティング | 緊急通話の可用性 |
| :------------| :-------| :-------| :-------| :-------| 
| 通話プラン | -Microsoft は PSTN キャリアとして機能します。<br>-SPC を購入または管理する必要はない。| Microsoft を介して取得します。| -Microsoft によって管理されます。 <br> -Admin は、番号変換用のユーザー ダイヤル プランを構成します。 | -Microsoft によって有効になります。 <br> -Admin はアドレスを登録します。 <br> -Dynamic 呼び出しがサポートされています。 |
| オペレーター 接続 | -Carrier は PSTN 接続と SPC を管理します。 <br> -SPC を購入または管理する必要はない。 | -キャリア経由で取得。 <br> - 通信事業者が管理する緊急アドレスに関連付けられている番号。  | -通信事業者によって管理されます。 <br>-Admin は、番号変換用のユーザー ダイヤル プランを構成します。 | -通信事業者が有効です。 <br> -Admin はアドレスを登録します。 <br> -Dynamic 呼び出しがサポートされています。 |
| ダイレクト ルーティング | -サード パーティ ベンダーから購入した認定 SBC が必要です。<br>-Connectに SBC を電話システム。<br> -既存の PSTN 通信事業者を使用します。 | キャリアを介して取得します。 | -管理者による追加の構成が必要です。<br>-Admin は、番号変換用にトランク ダイヤル プランを構成します。 <br>-LBR を使用して、有料バイパスを制限できます。 | -管理者による追加の構成が必要です。 <br>-登録済みのアドレスはサポートされていません。 <br>-動的呼び出しはサポートされますが、追加の構成が必要です。 |
|||||


### <a name="phone-number-management"></a>電話番号管理

Microsoft には、組織内のユーザーに割り当て可能なサブスクライバー (ユーザー) 番号と、有料サービス番号とフリーダイヤル サービス番号の 2 種類の電話番号があります。 サービス番号は、サブスクライバー番号よりも高い同時通話容量を持ち、電話会議、自動応答、通話キューなどのサービスに割り当てることができます。

次の条件を決定する必要があります。

- Microsoft の新しい電話番号が必要なユーザーの場所
- どの種類の電話番号 (サブスクライバーまたはサービス) が必要ですか?
- 既存の電話番号を既存の電話番号に移植Teams?

電話番号の取得および管理方法は、PSTN 接続オプションによって異なります。

- 通話プランの電話番号の管理については、「組織の電話番号を [管理する」を参照してください](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。

- Operator Connect を使用して電話番号を管理する方法については、「Operator Connect を使用して電話番号[を設定する」を参照してください](operator-connect-configure.md#set-up-phone-numbers)。

- ダイレクト ルーティングの電話番号の管理の詳細については、「電話番号を構成し、エンタープライズボイスとボイスメールを有効 [にする」を参照してください](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail-online)。


### <a name="call-routing-and-dial-plans"></a>通話ルーティングとダイヤル プラン

通話ルーティングの構成方法は、PSTN 接続オプションによって異なります。  

- 通話プランの場合、通話ルーティングの大部分は Microsoft 通話プラン インフラストラクチャによって処理されます。 通話承認と通話ルーティングの番号変換を目的として、ユーザー ダイヤル プランを構成します。 詳細については、「ダイヤル プラン [とは」を参照してください](what-are-dial-plans.md)。

- Operator Connectでは、ほとんどの通話ルーティングは通信事業者によって管理されます。  通話承認と通話ルーティングの番号変換を目的として、ユーザー ダイヤル プランを構成します。 詳細については、「ダイヤル プラン [とは」を参照してください](what-are-dial-plans.md)。

- ダイレクト ルーティングの場合は、音声ルートを指定し、ユーザーに音声ルーティング ポリシーを割り当て、通話ルーティングを構成する必要があります。 トランク レベルで番号変換のダイヤル プランを構成して、セッション ボーダー コントローラー (SPC) との相互運用性を確保できます。 詳細については、「ダイレクト ルーティングの[音声ルーティングの構成](direct-routing-voice-routing.md)[」、「音声](manage-voice-routing-policies.md)ルーティング ポリシーの管理」、および「電話番号の変換[」を参照してください](direct-routing-translate-numbers.md)。 


### <a name="location-based-routing-for-direct-routing"></a>ダイレクト ルーティングの場所に基づくルーティングを有効にする

一部の国や地域では、長距離通話コストを削減するために PSTN キャリアをバイパスする方法は違法です。 Location-Basedルーティング (LBR) を使用すると、地理的な場所に基づいて、ユーザーのTeamsバイパスを制限できます。 LBR を計画および構成する方法の詳細については、次の記事を参照してください。

- [ダイレクト ルーティングの場所に基づくルーティングを計画する](location-based-routing-plan.md)
- [場所に基づくルーティングのネットワーク設定を構成する](location-based-routing-configure-network-settings.md)
- [ダイレクト ルーティングの場所に基づくルーティングを有効にする](location-based-routing-enable.md)
- [Contoso のケース スタディ: Location-Based ルーティング](voice-case-study-location-based-routing.md)<br>
  架空の多国籍企業 Contoso 社が組織のルーティングLocation-Based実装する方法について説明します。


### <a name="emergency-calling"></a>緊急通話

緊急通話の構成方法は、PSTN 接続オプションによって異なります。

- 通話プランの場合、各ユーザーは自動的に緊急通話を有効にし、割り当てられた電話番号に関連付けられた登録済みの緊急アドレスを持っている必要があります。 動的緊急通話 (クライアントの場所にTeams) がサポートされています。  

- Operator Connectでは、各ユーザーは緊急通話を自動的に有効にし、割り当てられた電話番号に関連付けられた登録された緊急住所を持っている必要がありますが、通信事業者パートナーによってのみ設定できます。 動的緊急通話 (クライアントの場所にTeams) がサポートされています。

- ダイレクト ルーティングの場合は、Teams 緊急通話ルーティング ポリシー (TeamsEmergencyCallRoutingPolicy) を使用して緊急電話番号と関連するルーティング先を定義することで、ユーザーの緊急通話ポリシーを定義する必要があります。 登録されている緊急の場所は、ダイレクト ルーティング ユーザーではサポートされていません。 動的緊急通話の場合、緊急通話のルーティングやパートナー接続の場合は、追加の構成が必要です。

緊急通話の概念と用語、および緊急通話と動的緊急通話を構成する方法の詳細については、次の記事を参照してください。

- [緊急通報を管理する](what-are-emergency-locations-addresses-and-call-routing.md)
- [動的な緊急通報を計画して構成する](configure-dynamic-emergency-calling.md)
- [緊急時通話ポリシーを管理する](manage-emergency-calling-policies.md)
- [ダイレクト ルーティングの緊急通話のルーティング ポリシーを管理する](manage-emergency-call-routing-policies.md)
- [Contoso のケース スタディ: 緊急通話](voice-case-study-emergency-calling.md)<br>
  架空の多国籍企業 Contoso 社が組織に対して緊急電話を実施した方法について説明します。


### <a name="network-topology-for-voice-features"></a>音声機能のネットワーク トポロジ

動的緊急通話または直接ルーティングLocation-Basedを展開する場合は、これらの機能で使用するネットワーク設定を構成する必要Microsoft Teams。 ネットワーク地域、ネットワーク サイト、ネットワーク サブネット、および信頼できる IP アドレスのネットワーク設定を構成する方法については、次の記事を参照してください。

- [クラウド音声機能のネットワーク設定 -Microsoft Teams概念と用語](cloud-voice-network-settings.md)
- [Microsoft Teams でクラウド ボイス機能のネットワーク トポロジを管理する](manage-your-network-topology.md)



