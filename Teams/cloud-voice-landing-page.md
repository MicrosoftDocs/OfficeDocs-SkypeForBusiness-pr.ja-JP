---
title: 音声ソリューションの計画を立Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/29/2020
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
description: クラウド音声機能のMicrosoft Teams、および組織に対して行うデプロイの決定について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 391b8e2f30aa5e64fcb4b9e418af49341c2b9042
ms.sourcegitcommit: 31c5b9cd3d4f500e1f9d7823052dae8f8c298b1e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2021
ms.locfileid: "52901934"
---
# <a name="plan-your-teams-voice-solution"></a>音声ソリューションTeams計画する 

この記事は、組織に最適な Microsoft 音声ソリューションを決定するのに役立ちます。 決定したら、この記事では、選択したソリューションを実装できるコンテンツのロードマップを提供します。

> [!NOTE]
> Skype for Business Server から Teams にアップグレードする全体的な計画の一部として Teams 音声ソリューションを計画する方法のガイダンスについては、「Teams から Skype for Business オンプレミス へのアップグレードに関する[PSTN](upgrade-to-teams-on-prem-pstn-considerations.md)の考慮事項」を参照してください。

最も簡単なソリューションを通話 &mdash; プラン電話システム必要な場合があります。 これは、次の図に示すように、プライベート ブランチ Exchange (PBX) 機能と公衆交換電話網 (PSTN) への呼び出しを提供する Microsoft のクラウド内すべてソリューションです。 このソリューションでは、Microsoft は PSTN 通信事業者です。

![図 1 は、通話プラン電話システムを示しています](media/voice-solutions-simple.png)

次に対して 「はい」と答える場合は、電話システムプランを使用する方法が適切なソリューションです。

- 通話プランは、お客様のリージョンで利用できます。
- 現在の PSTN 通信事業者を保持する必要はない。
- PSTN への Microsoft が管理するアクセスを使用する場合。

ただし、状況は複雑になる可能性があります。 たとえば、通話プランが利用できない場所にオフィスがある場合があります。 または、地理的な場所ごとに異なる要件を持つ、複雑で多国籍のデプロイをサポートする組み合わせソリューションが必要な場合があります。 Microsoft では、次のソリューションの組み合わせをサポートしています。 

- 電話システムプランの使用
- 電話システムオペレーター サービスを使用して、独自の PSTN Connect (現在パブリック プレビュー **でのみ利用可能**)
- 電話システムルーティングを使用して独自の PSTN 通信業者と通信する
- 通話プランで電話システムを使用する組み合わせ電話システムオペレーター Connect、直接ルーティング電話システムを使用する


## <a name="what-do-you-need-to-read"></a>何を読む必要がありますか?

**すべてのユーザーに必須です。** この記事のセクションの一部は、すべての組織に関連します。 たとえば、すべてのユーザーは、電話システムについて読み、公衆交換電話網 (PSTN) に接続するためのオプションを理解する必要があります。 


| すべてのユーザーに必須 | 説明 |
| :------------|:-------|
| [**電話システム**](#phone-system) | クラウドとクラウドの通話制御とプライベート ブランチ Exchange (PBX) 機能を有効にするための Microsoft Microsoft 365テクノロジMicrosoft Teams。 |
| [**公衆交換電話網 (PSTN) 接続オプション**](#public-switched-telephone-network-connectivity-options) | Microsoft をテレフォニー キャリアとして使用するか、直接ルーティングまたはオペレーター サービスを使用して、Microsoft Teams に独自のテレフォニー キャリアを接続Connect。 PSTN 接続電話システムと組み合わせると、ユーザーは世界中で電話を発信できます。|

**要件に応じて異なる。** この記事のセクションの一部は、既存のデプロイと要件に応じて関連します。 たとえば、Location-Basedルーティングは、有料バイパスを許可しない地理的な場所のダイレクト ルーティングのお客様にのみ必要です。

次の追加構成の中から、必要な構成を検討してください。

![図 2 は、Microsoft からの電話番号、ダイヤル プラン電話通話ルーティングなど、追加の音声コンポーネントを示しています。](media/voice-consider-additional-components.png)

| 要件に応じて | 説明 |
| :------------|:-------|
| [**Microsoft からの電話番号**](#phone-numbers-from-microsoft) | Microsoft から電話番号を取得および管理する方法と、既存の番号を Microsoft に転送する方法。 Microsoft 通話プランの電話番号を取得したり、既存の番号を転送したり、サービス番号を取得したりする必要がある場合は、この記事をお読みください。 |
| [**ダイヤル プランと通話ルーティング**](#dial-plans-and-call-routing) | ダイヤルされた電話番号を別の形式 (通常は E.164 形式) に変換して通話承認と通話ルーティングを行うダイヤル プランを構成および管理する方法。 ダイヤル プランの詳細と、組織のダイヤル プランを指定する必要があるかどうかを理解する必要がある場合は、この記事を参照してください。|
| [**緊急通話**](#emergency-calling) | PSTN 接続オプションに応じて緊急 &mdash; 通話を管理および構成する方法。 Microsoft 通話プランまたは直接ルーティングを使用し、組織の緊急通話を管理する方法を理解する必要がある場合は、このセクションをお読みください。 |
| [**直接ルーティングのための場所ベースのルーティング**](#location-based-routing-for-direct-routing) |ローカル ルーティング (LBR) Location-Basedを使用して、地理的な場所に基づいてユーザーのMicrosoft Teamsバイパスを制限する方法。 組織が有料バイパスを許可しない場所で直接ルーティングを使用している場合は、このセクションをお読みください。
| [**クラウド音声機能のネットワーク トポロジ**](#network-topology-for-voice-features) | 組織が直接ルーティングまたは動的緊急通話用に Location-Based ルーティング (LBR) をデプロイしている場合は、Microsoft Teams でこれらの機能で使用するネットワーク設定を構成する必要があります。 直接ルーティング用に LBR を実装している場合、または通話プランまたは直接ルーティングを使用して動的緊急通話を実装している場合は、このセクションを参照してください。 |
| [**既存の音声ソリューションを移行する**](#migrate-your-existing-voice-solution-to-teams) | 音声ソリューションを音声ソリューションに移行するときに考える必要があるTeams。  既存の音声ソリューションから既存の音声ソリューションに移行する場合は、このセクションをTeams。 



> [!Important]
> この記事では、音声ソリューションと音声ソリューションについてMicrosoft Teams。 Skype for Business Online のソリューションは引き続き利用できます[(「Microsoft](/SkypeForBusiness/hybrid/msft-telephony-solutions)テレフォニー ソリューション」で説明)、Skype for Business Online は 2021 年 7 月 31 日に廃止される予定です。  その日付が終了するとSkype for Businessオンライン サービスにアクセスできなくなりました。 さらに、オンプレミス環境間の PSTN 接続は、Skype for Business Server または Cloud Connector Edition と Skype for Business Online の間では &mdash; &mdash; サポートされなくなりました。 この記事では、Teams 音声ソリューションと、必要に応じて直接ルーティングまたはオペレーター Connect を使用してオンプレミスのテレフォニー ネットワークを Teams に接続する方法について説明します。


## <a name="phone-system"></a>電話システム

電話システムは、通話制御とプライベート ブランチ Exchange (PBX) の機能を、Microsoft 365 または Office 365 クラウドと Microsoft Teams で有効にするための Microsoft のテクノロジです。

電話システムは、TeamsクライアントSkype for Business認定デバイスで動作します。 電話システムでは、既存の PBX システムを、既存の PBX システムから直接配信された一連の機能にMicrosoft 365またはOffice 365。 

組織内のユーザー間の通話は電話システムの内部で処理され、公衆交換電話網 (PSTN) に流れることは決してありません。 これは、地理的にさまざまな場所にいる組織内のユーザー間の通話にも当てはまるため、このような長距離の社内通話にかかるコストが解消されます。

この記事では、次電話システムの主な機能と、考慮する必要があるデプロイの決定について説明します。

- [自動応答と呼び出しキュー](#auto-attendants-and-call-queues)
- [クラウド ボイスメール](#cloud-voicemail)
- [通話 ID](#calling-identity)

![図 3 は、電話応答と通話クエリ、クラウド ボイスメール、通話 ID が含まれているシステムを示しています](media/phone-system-contains.png)

すべての機能と電話システム設定方法については、次電話システム記事を参照してください。

- [電話システムで利用できる機能](here-s-what-you-get-with-phone-system.md)
- [組織内の電話システムの設定](setting-up-your-phone-system.md)<br>
  無料電話番号のライセンスの購入電話システム割り当て、電話番号の管理、およびコミュニケーション クレジットの設定を行う方法について説明します。 

サポートされているデバイスの管理については、「Manage your devices [in Microsoft Teams](devices/device-management.md) and Teams Marketplace 」[を参照してください](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)。


### <a name="auto-attendants-and-call-queues"></a>自動応答と通話キュー

自動応答を使用すると、呼び出し元の入力に基づいて呼び出しをルーティングするメニュー オプションを設定できます。 呼び出しキューは、呼び出し元の待機領域です。 自動応答と通話キューを組み合わせて使用すると、組織内の適切なユーザーまたは部署に発信者を簡単にルーティングできます。

自動応答と通話キューの詳細については、次の記事を参照してください。

- [自動応答Teamsキューの計画](plan-auto-attendant-call-queue.md)
- [自動応答を設定する](create-a-phone-system-auto-attendant.md)
- [呼び出しキューを作成する](create-a-phone-system-call-queue.md) 
- [Contoso のケース スタディ: 自動応答と通話キュー](voice-case-study-call-queues.md)<br>
  架空の多国籍企業 Contoso が、音声ソリューションの自動応答と通話キューを実装した方法について説明します。

### <a name="cloud-voicemail"></a>クラウド ボイスメール

クラウド ボイスメール Azure ボイスメール サービスを利用する場合、メールボックスへのボイスメールの入金Exchangeサポートしています。 サード パーティのメール システムはサポートされていません。 

クラウド ボイスメールでは、組織内のすべてのユーザーに対してボイスメールの文字起こしが既定で有効になっています。 会社のニーズに応じて、特定のユーザーまたは組織全体の全ユーザーに対してボイスメールの文字起こしを無効にすることができます。

オンライン ユーザーの場合、ユーザークラウド ボイスメールライセンスが割り当てられた後、ユーザーに対して自動的に設定およびプロビジョニング電話システムされます。 メールボックス電話システムユーザー Exchange場合は、追加の構成手順を実行する必要があります。 

構成とその構成のクラウド ボイスメール、次の記事を参照してください。

- [クラウド ボイスメールのセットアップ](set-up-phone-system-voicemail.md)
- [組織内のボイスメール ポリシーを設定する](manage-voicemail-policies.md)


### <a name="calling-identity"></a>通話 ID

既定で、すべての発信通話は、割り当てられた電話番号を通話 ID (発信者 ID) として使用します。 通話の受信者は、発信者をすばやく特定して、通話を承諾または拒否するかどうかを決定できます。 発信者番号の構成または発信者番号の変更またはブロックについては、「ユーザーの発信者番号を設定する」 [を参照してください](set-the-caller-id-for-a-user.md)。 

## <a name="public-switched-telephone-network-connectivity-options"></a>公衆交換電話網接続オプション

電話システムは、組織に完全な PBX 機能を提供します。 ただし、ユーザーが組織外で通話を発信するには、PSTN (Public Switched Telephone Network) 電話システムに接続する必要があります。 PSTN 電話システム接続するには、次のいずれかのオプションを選択できます。

- [**電話システム プラン を使用して行います**](#phone-system-with-calling-plan)。 MICROSOFT を PSTN 通信事業者として使用する、クラウド内のすべてソリューション。

- [**電話システム直接ルーティングを**](#phone-system-with-own-pstn-carrier-with-direct-routing)使用してオンプレミス環境をオンプレミスの PSTN 通信業者に接続Teams。

- [**電話システム、現在**](operator-connect-plan.md)パブリック プレビューでのみ使用できるオペレーター Connect を使用して、独自の PSTN 通信事業者 **と通信できます。**  オペレーター Connectを使用すると、既存のオペレーターが Microsoft Operator Connect プログラムに参加している場合、PSTN 通話を Teams に持ち込むサービスを管理できます。 Operator Connect の利点と要件、およびこのプログラムに参加しているオペレーターの一覧については、「Plan [Operator Connect」を参照してください](operator-connect-plan.md)。

オプションの組み合わせを選択することもできます。これにより、複雑な環境向けソリューションを設計したり、複数ステップの移行を管理したりすることもできます (移行の詳細については後で説明します)。

### <a name="phone-system-with-calling-plan"></a>電話システムプランの使用 

この記事で前述したように、電話システムプランを使用する方法は、ユーザーが利用できる Microsoft のクラウド内音声Teamsです。 これは、世界中の固定電話Microsoft 電話携帯電話への通話を有効にするための、Microsoft 電話 System を公衆交換電話網 (PSTN) に接続する最も簡単なオプションです。 このオプションを使用すると、Microsoft は組織Exchange (PBX) 機能を提供し、次の図に示すように PSTN 通信事業者として機能します。

![図 4 は、電話システム、通話キュー、発信者番号など、PSTN 通信事業者としての Microsoft の機能を示しています。](media/voice-solution-microsoft-complete.png)

次に対して 「はい」と答える場合は、電話システムプランを使用する方法が適切なソリューションです。

- 通話プランは、お客様のリージョンで利用できます。
- 現在の PSTN 通信事業者を保持する必要はない。
- PSTN への Microsoft が管理するアクセスを使用する場合。

このオプションでは、次のオプションを使用します。 

- (ライセンスMicrosoft 電話に応じて) 世界中の電話への通話を可能にする国内通話プランまたは国際通話プランが追加された新しいシステムを利用できます。

- 通話プランは、オンプレミスのデプロイやメンテナンスを行う必要はないので、Microsoft 365 &mdash; またはOffice 365。

- 注: 必要に応じて、サード パーティの PBX、アナログ デバイス、SBC でサポートされているその他のサードパーティのテレフォニー機器との相互運用性を確保するために、サポートされているセッション ボーダー コントローラー (SBC) を直接ルーティング経由で接続できます。

このオプションを使用するには、接続または接続に中断Microsoft 365接続Office 365。

通話プランの詳細については、次の記事を参照してください。

- [どの通話プランが適していますか?](calling-plan-landing-page.md)
- [通話プランを購入する方法](calling-plans-for-office-365.md)
- [通話プランが利用可能な国と地域](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [通話プランを設定する](set-up-calling-plans.md)


### <a name="phone-system-with-own-pstn-carrier-with-direct-routing"></a>電話システムルーティングを使用して PSTN 通信業者を使用する

このオプションは、Microsoft 電話に示すように、ダイレクト ルーティングを使用して、システムをテレフォニー ネットワークに接続します。 

![図 5 は、直接ルーティング電話システムを示しています](media/voice-solution-with-direct-routing.png)

次の質問に対して 「はい」と回答した場合は、電話システム ルーティングを使用する方法が適切なソリューションです。

- このコマンドを使用してTeamsを電話システム。
- 現在の PSTN 通信事業者を保持する必要があります。
- 通話プランを経由する通話と、運送業者を介した通話を組み合わせ、ルーティングを混在したい場合。
- サードパーティの PBX や、オーバーヘッド ページ、アナログ デバイスなどの機器と相互運用する必要があります。

このオプションでは、次のオプションを使用します。

- 追加のオンプレミス ソフトウェアを必要とせずに、Microsoft 電話 SBC をシステムに接続します。

- Microsoft 電話 System では、事実上任意のテレフォニー キャリアを使用できます。

- このオプションの構成と管理を選択するか、通信事業者またはパートナーが構成および管理できます (運送業者またはパートナーにこのオプションが提供されていないか確認してください)。

- サード パーティ製 PBX やアナログ デバイスなどのテレフォニー機器と、その他のシステムとの間に相互 &mdash; &mdash; 運用性Microsoft 電話できます。


このオプションには、次が必要です。

- 接続または接続Microsoft 365接続Office 365。

- サポートされている SBC のデプロイと保守。

- サード パーティの運送業者との契約。
  (サード パーティ製 PBX、アナログ デバイス、その他のテレフォニー機器への接続を提供するオプションとして、通話プランを利用しているユーザーに電話システムしない限り)。

ダイレクト ルーティングの詳細については、次の記事を参照してください。

- [電話システムのダイレクト ルーティング](direct-routing-landing-page.md)
- [ダイレクト ルーティングを計画する](direct-routing-plan.md)
- [ダイレクト ルーティングを構成する](direct-routing-configure.md)
- [ダイレクト ルーティングで使用する音声ルーティング ポリシーを管理する](manage-voice-routing-policies.md)
- [ダイレクト ルーティングの場所に基づくルーティングを計画する](location-based-routing-plan.md)
- [ダイレクト ルーティングに対応する認定済みセッション ボーダー コントローラーのリスト](direct-routing-border-controllers.md)

## <a name="phone-numbers-from-microsoft"></a>Microsoft からの電話番号

Microsoft には、組織内のユーザーに割り当て可能なサブスクライバー *(ユーザー* ) 番号と、有料サービス番号と無料サービス番号として利用できるサービス番号の 2 種類があります。 サービス番号は、サブスクライバー番号よりも高い同時通話容量を持ち、電話会議、自動応答、通話キューなどのサービスに割り当てることができます。

次の条件を決定する必要があります。

- Microsoft からの新しい電話番号が必要なのはどのユーザー ロケーションですか?
- どの種類の電話番号が必要ですか (サブスクライバーまたはサービス)? 
- どんな方法で既存の電話番号を Teams に移植しますか?

新しい番号の取得や終了番号の転送など、組織内の電話番号の管理の詳細については、次の記事を参照してください。

- [組織の電話番号を管理する](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 
- [通話プランに使用されるさまざまな種類の電話番号](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [ユーザー用の電話番号を取得する](getting-phone-numbers-for-your-users.md)
- [電話番号を別の電話番号にMicrosoft Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)

## <a name="dial-plans-and-call-routing"></a>ダイヤル プランと通話ルーティング

ダイヤル プランは、ダイヤルされた電話番号を通話承認と通話ルーティングの代替形式 (通常は E.164 形式) に変換する正規化ルールのセットです。

次の条件を決定する必要があります。 

- 組織はダイヤル プランのカスタマイズを必要としているか?
- カスタマイズされたダイヤル プランが必要なユーザー
- どのテナント ダイヤル プランを各ユーザーに割り当てる必要がありますか。

詳細については、次の記事を参照してください。 

- [ダイヤル プランについて](what-are-dial-plans.md)
- [テナント ダイヤル プランの計画](what-are-dial-plans.md#planning-for-tenant-dial-plans)
- [ダイヤル プランを作成および管理する](create-and-manage-dial-plans.md)

## <a name="emergency-calling"></a>緊急通話

緊急通話の構成方法は、PSTN 接続オプション (Microsoft 通話プランまたは直接ルーティング) によって異なります。 Microsoft 通話プランと 電話システム ダイレクト ルーティングの動的緊急通話は、緊急通話を構成してルーティングし、Teams クライアントの現在の場所に基づいてセキュリティ担当者に通知する機能を提供します。 緊急通話の概念と用語、および動的緊急通話を構成する方法の詳細については、次の記事を参照してください。

- [緊急通話を管理する](what-are-emergency-locations-addresses-and-call-routing.md)
- [動的な緊急通話を計画して構成する](configure-dynamic-emergency-calling.md)
- [Contoso のケース スタディ: 緊急通話](voice-case-study-emergency-calling.md)<br>
  架空の多国籍企業 Contoso が組織の緊急呼び出しを実装した方法について説明します。

## <a name="location-based-routing-for-direct-routing"></a>Location-Based ルーティングの詳細

国や地域によっては、公衆交換電話網 (PSTN) プロバイダーをバイパスして、遠距離通話コストを削減する方法は違法です。 Location-Based ルーティングを使用すると、地理的な場所に基づいて、Microsoft Teamsユーザーの有料バイパスを制限できます。 ルーティング (LBR) を計画および構成する方法のLocation-Based、次の記事を参照してください。

- [ダイレクト ルーティングの場所に基づくルーティングを計画する](location-based-routing-plan.md)
- [場所に基づくルーティングのネットワーク設定を構成する](location-based-routing-configure-network-settings.md)
- [ダイレクト ルーティングの場所に基づくルーティングを有効にする](location-based-routing-enable.md)
- [Contoso のケース スタディ: Location-Based ルーティング](voice-case-study-location-based-routing.md)<br>
  架空の多国籍企業 Contoso が、組織に対して Location-Based ルーティングを実装した方法について説明します。

## <a name="network-topology-for-voice-features"></a>音声機能のネットワーク トポロジ

動的緊急通話または直接ルーティング用の Location-Based ルーティングをデプロイする場合は、これらの機能で使用するネットワーク設定を構成する必要Microsoft Teams。 ネットワーク リージョン、ネットワーク サイト、ネットワーク サブネット、信頼済み IP アドレスのネットワーク設定を構成する方法については、次の記事を参照してください。

- [Microsoft Teams のクラウド音声機能のネットワーク設定 - 概念と用語](cloud-voice-network-settings.md)
- [クラウド音声機能のネットワーク トポロジを管理する Microsoft Teams](manage-your-network-topology.md)

## <a name="migrate-your-existing-voice-solution-to-teams"></a>既存の音声ソリューションを既存の音声ソリューションに移行Teams

アプリケーションにアップグレードする組織Teams最終的な目標は、すべてのユーザーを TeamsOnly モードに移行する方法です。 ユーザー電話システムでのTeamsは、ユーザーが TeamsOnly モードの場合にのみサポートされます。 アプリケーションへのアップグレードに関する基本的な情報が必要なTeams開始します。

- [Microsoft Teams へのアップグレードを開始する](upgrade-start-here.md)
- [アップグレードのフレームワークについて](upgrade-framework.md)
- [IT 管理者向けアップグレード戦略](upgrade-to-teams-on-prem-implement.md)

音声ソリューションを移行する場合、TeamsOnly モードに移行するときに、次の 4 つの呼び出しシナリオが考えられます。

- [**Microsoft 通話プラン をSkype for Business Online のユーザー**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)。 アップグレード後も、このユーザーは引き続き Microsoft 通話プランを利用できます。

- Skype for Business Online のユーザー。オンプレミスまたは Cloud Connector Edition を介してSkype for Business音声 **[](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)機能を使用します**。 このユーザーの Teams へのアップグレードは、その TeamsOnly ユーザーが確実に PSTN 機能を持てるようにするため、ユーザーのダイレクト ルーティングへの移行に合わせた調整が必要になります。

- **[を使用Skype for Business](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)** オンプレミスのユーザーエンタープライズ VoIP、オンラインに移行し、オンプレミスの PSTN 接続を維持します。 このユーザーを Teams に移行するには、そのユーザーのオンプレミスの Skype for Business アカウントをクラウドに移行し、移行をそのユーザーのダイレクト ルーティングへの移行に合わせて調整する必要があります。 

- **[を使用Skype for Business](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)** オンプレミスのユーザーエンタープライズ VoIP、オンラインに移行し、Microsoft 通話プラン を使用します。  このユーザーを Teams に移行するには、そのユーザーのオンプレミスの Skype for Business アカウントをクラウドに移行し、移行を A) Microsoft 通話プランへのユーザーの電話番号のポートに合わせて調整するか、B) 利用可能な地域から新しいサブスクライバー番号を割り当てる必要があります。

ハイブリッド接続を設定する必要がある状況や、オンプレミスの音声機能を持つユーザーを直接ルーティングに移行する方法に関する情報など、これらのシナリオごとに音声移行を実装する方法の詳細については、次の記事 &mdash; &mdash; を参照してください。

- [IT 管理者向け Teamsアップグレード時の PSTN に関する考慮事項](upgrade-to-teams-on-prem-pstn-considerations.md)

- [Contoso 音声移行のケース スタディ](voice-case-study-overview.md)<br>
  このケース スタディでは、架空の多国籍企業 Contoso が、組織に対してTeamsソリューションを実装した方法について説明します。 次の記事が含まれます。

  - [Teamsアップグレード プラン](voice-case-study-migration-plan.md)
  - [電話システム PSTN 接続オプション](voice-case-study-phone-system.md)
  - [場所ベースのルーティングの実装](voice-case-study-location-based-routing.md)
  - [緊急通話](voice-case-study-emergency-calling.md)
  - [自動応答と呼び出しキュー](voice-case-study-call-queues.md)
  - [電話会議](voice-case-study-audio-conferencing.md)
