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
ms.openlocfilehash: 2d463034109e39920254e3f230546efe7f336af1
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2022
ms.locfileid: "61766450"
---
# <a name="plan-your-teams-voice-solution"></a>音声ソリューションTeams計画する

この記事は、組織に最適な Microsoft 音声ソリューションを決定するのに役立ちます。 決定したら、この記事では、選択したソリューションを実装できるコンテンツのロードマップを提供します。

最も簡単なソリューションを通話 &mdash; プランTeams 電話必要な場合があります。 これは、次の図に示すように、プライベート ブランチ Exchange (PBX) 機能と公衆交換電話網 (PSTN) への呼び出しを提供する Microsoft のクラウド内すべてソリューションです。 このソリューションでは、Microsoft は PSTN 通信事業者です。

![図 1 は、通話Teams 電話の概要を示しています。](media/voice-solutions-simple.png)

次に対して 「はい」と回答した場合は、Teams 電話プランを使用する方法が適切なソリューションです。

- 通話プランは、お客様のリージョンで利用できます。
- 現在の PSTN 通信事業者を保持する必要はない。
- PSTN への Microsoft が管理するアクセスを使用する場合。

ただし、状況は複雑になる可能性があります。 たとえば、通話プランが利用できない場所にオフィスがある場合があります。 または、地理的な場所ごとに異なる要件を持つ、複雑で多国籍のデプロイをサポートする組み合わせソリューションが必要な場合があります。 Microsoft では、次のソリューションの組み合わせをサポートしています。

- Teams 電話プランの使用
- Teams 電話オペレーター サービスを使用して、独自の PSTN 通信業者とConnect
- Teams 電話ルーティングを使用して独自の PSTN 通信業者と通信する
- 通話プランで Teams 電話 を使用する組み合わせソリューション、オペレーター Teams 電話 を使用Connect直接ルーティングTeams 電話を使用する組み合わせソリューション

>[!NOTE]
>中小企業 (300 人以下) の場合、Microsoft は現在、国内通話プラン電話システムをバンドルしています。 詳細については、音声ソリューション[Teams 電話、](/microsoftteams/business-voice/whats-business-voice)設定、管理に役立つ中小企業向けガイダンスに関するページを参照してください。

## <a name="what-do-you-need-to-read"></a>何を読む必要がありますか?

**すべてのユーザーに必須です。** この記事のセクションの一部は、すべての組織に関連します。 たとえば、すべてのユーザーは、TEAMS 電話について読み、公衆交換電話網 (PSTN) に接続するためのオプションを理解する必要があります。


| すべてのユーザーに必須 | 説明 |
| :------------|:-------|
| [**Teams 電話**](#teams-phone) | クラウドとクラウドで通話制御とプライベート ブランチ Exchange (PBX) 機能を有効にするための Microsoft のMicrosoft 365テクノロジMicrosoft Teams。 |
| [**公衆交換電話網 (PSTN) 接続オプション**](#public-switched-telephone-network-connectivity-options) | テレフォニー キャリアとして Microsoft を使用するか、オペレーター Microsoft Teams または直接ルーティングを使用して、Microsoft Teams Connect に接続するかの選択。 PSTN 接続Teams 電話と組み合わせると、ユーザーは世界中で電話を発信できます。|

**要件に応じて異なる。** この記事と関連記事の一部のセクションは、既存のデプロイと要件に応じて関連します。 たとえば、Location-Basedルーティングは、有料バイパスを許可しない地理的な場所のダイレクト ルーティングのお客様にのみ必要です。

次の追加構成の中から、必要な構成を検討してください。

![図 2 は、Microsoft からの電話番号、ダイヤル プラン電話通話ルーティングなど、追加の音声コンポーネントを示しています。](media/voice-consider-additional-components.png)

| 要件に応じて | 説明 |
| :------------|:-------|
| [**電話番号の管理**](pstn-connectivity.md#phone-number-management) | 電話番号を取得および管理する方法は、PSTN 接続オプションによって異なります。 電話番号の取得、既存の番号の転送、サービス番号の取得が必要な場合は、このセクションをお読みください。 |
| [**通話ルーティングとダイヤル プラン**](pstn-connectivity.md#call-routing-and-dial-plans) | ダイヤルされた電話番号を別の形式 (通常は E.164 形式) に変換して通話承認と通話ルーティングを行うダイヤル プランを構成および管理する方法。 ダイヤル プランの詳細と、組織のダイヤル プランを指定する必要があるかどうかを理解する必要がある場合は、このセクションを参照してください。|
| [**緊急通話**](pstn-connectivity.md#emergency-calling) | 緊急通話を管理および構成する方法は、PSTN 接続オプションによって異なります。 組織の緊急通話を管理する方法を理解する必要がある場合は、このセクションを参照してください。 |
| [**直接ルーティングのための場所ベースのルーティング**](pstn-connectivity.md#location-based-routing-for-direct-routing) |ローカル ルーティング (LBR) Location-Basedを使用して、地理的な場所に基づいてユーザーのMicrosoft Teamsバイパスを制限する方法。 組織が有料バイパスを許可しない場所で直接ルーティングを使用している場合は、このセクションをお読みください。
| [**クラウド音声機能のネットワーク トポロジ**](pstn-connectivity.md#network-topology-for-voice-features) | 組織が直接ルーティングまたは動的緊急通話用に Location-Based ルーティング (LBR) を展開している場合は、Microsoft Teams でこれらの機能で使用するネットワーク設定を構成する必要があります。 直接ルーティング用に LBR を実装している場合、または通話プランまたは直接ルーティングを使用して動的緊急通話を実装している場合は、このセクションを参照してください。 |
| [**既存の音声ソリューションを移行する**](#migrate-your-existing-voice-solution-to-teams) | 音声ソリューションを新しい音声ソリューションに移行する際にTeams。  既存の音声ソリューションから既存の音声ソリューションに移行する場合は、このセクションをTeams。 

> [!Important]
> この記事では、音声ソリューションと音声ソリューションについてMicrosoft Teams。 2021 年 7 月 31 日に Skype for Business Online が提供終了されたので、Skype for Business Server または Cloud Connector Edition と Skype for Business Online の間のオンプレミス環境間の PSTN 接続はサポートされなくなりました。 &mdash; &mdash; この記事では、Teams 音声ソリューションと、オペレーター Connect または直接ルーティングを使用して、必要に応じてオンプレミスのテレフォニー ネットワークを Teams に接続する方法について説明します。


## <a name="teams-phone"></a>Teams 電話

Teams 電話は、通話制御とプライベート ブランチ Exchange (PBX) の機能を、Microsoft 365 クラウドと Microsoft Teams で有効にするための Microsoft のテクノロジです。

Teams 電話クライアントと認定Teamsデバイスで動作します。 Teams 電話既存の PBX システムを、既存の PBX システムから直接配信された一連の機能に置き換Microsoft 365。 

組織内のユーザー間の呼び出しは、Teams 電話 内で処理され、公衆交換電話網 (PSTN) には移動しません。 これは、地理的にさまざまな場所にいる組織内のユーザー間の通話にも当てはまるため、このような長距離の社内通話にかかるコストが解消されます。

この記事では、次のTeams 電話機能と、考慮する必要があるデプロイの決定について説明します。

- [自動応答と呼び出しキュー](#auto-attendants-and-call-queues)
- [クラウド ボイスメール](#cloud-voicemail)
- [通話 ID](#calling-identity)

![図 3 は、電話応答と通話クエリ、クラウド ボイスメール、通話 ID を含むシステムを示しています。](media/phone-system-contains.png)

すべての機能の詳細Teams 電話設定方法については、次Teams 電話記事を参照してください。

- [次の方法で利用Teams 電話](here-s-what-you-get-with-phone-system.md)
- [組織でTeams 電話を設定する](setting-up-your-phone-system.md)<br>
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

クラウド ボイスメール Azure ボイスメール サービスを利用する場合、ボイスメールによるメールボックスへのExchangeをサポートしています。 サード パーティのメール システムはサポートされていません。 

クラウド ボイスメールでは、組織内のすべてのユーザーに対してボイスメールの文字起こしが既定で有効になっています。 会社のニーズに応じて、特定のユーザーまたは組織全体の全ユーザーに対してボイスメールの文字起こしを無効にすることができます。

クラウド ボイスメールは、ユーザーに対して自動的に設定Teamsされます。  

構成とその構成のクラウド ボイスメール、次の記事を参照してください。

- [クラウド ボイスメールのセットアップ](set-up-phone-system-voicemail.md)
- [組織内のボイスメール ポリシーを設定する](manage-voicemail-policies.md)


### <a name="calling-identity"></a>通話 ID

既定で、すべての発信通話は、割り当てられた電話番号を通話 ID (発信者 ID) として使用します。 通話の受信者は、発信者をすばやく特定して、通話を承諾または拒否するかどうかを決定できます。 発信者番号の構成または発信者番号の変更またはブロックについては、「ユーザーの発信者番号を設定する」 [を参照してください](set-the-caller-id-for-a-user.md)。 

## <a name="public-switched-telephone-network-connectivity-options"></a>公衆交換電話網接続オプション

Teams 電話は、組織に完全な PBX 機能を提供します。 ただし、ユーザーが組織外で通話を発信するには、ユーザーをパブリック Teams 電話 (PSTN) に接続する必要があります。 PSTN Teams 電話接続するには、次のいずれかのオプションを選択できます。

- [**Teams 電話 プラン を使用して行います**](pstn-connectivity.md#teams-phone-with-calling-plan)。 MICROSOFT を PSTN 通信事業者として使用する、クラウド内のすべてソリューション。

- [**Teams 電話 を使用して、独自の PSTN 通信業者と通信Connect。**](operator-connect-plan.md) オペレーター Connectを使用すると、既存のオペレーターが Microsoft Operator Connect プログラムに参加している場合、PSTN 通話を Teams に持ち込むサービスを管理できます。 オペレーター サービスの利点と要件については、「プラン オペレーター」Connectを参照[Connect。](operator-connect-plan.md)

- [**Teams 電話ルーティングを使用して**](pstn-connectivity.md#teams-phone-with-direct-routing)オンプレミス環境を接続し、PSTN 通信業者と接続Teams。

オプションの組み合わせを選択することもできます。このオプションを使用すると、複雑な環境向けソリューションを設計したり、複数ステップの移行を管理したりすることもできます (移行の詳細については後で説明します)。

選択Teams 電話 PSTN 接続オプションに関係なく、ほとんどの機能は同じです。 ただし、通話ルーティングや緊急通話など、特定の Teams 電話機能の構成方法に影響する機能にはいくつかの違いがあります。 PSTN 接続オプションとこれらの構成に関する考慮事項の詳細については、「PSTN 接続オプション」 [を参照してください](pstn-connectivity.md)。


## <a name="migrate-your-existing-voice-solution-to-teams"></a>既存の音声ソリューションを既存の音声ソリューションに移行Teams

> [!NOTE]
> Skype for Business Server から Teams にアップグレードする全体的な計画の一部として Teams 音声ソリューションを計画する方法のガイダンスについては、「Teams から Skype for Business へのアップグレードに関する[PSTN](upgrade-to-teams-on-prem-pstn-considerations.md)の考慮事項」を参照してください。

アプリケーションにアップグレードする組織Teams最終的な目標は、すべてのユーザーを TeamsOnly モードに移行する方法です。 このTeams 電話は、ユーザーが TeamsOnly モードの場合にのみサポートされます。 アプリケーションへのアップグレードに関する基本情報が必要な場合Teams開始します。

- [Microsoft Teams へのアップグレードを開始する](upgrade-start-here.md)
- [アップグレードのフレームワークについて](upgrade-framework.md)
- [IT 管​​理者向けのアップグレード戦略](upgrade-to-teams-on-prem-implement.md)

音声ソリューションを移行する場合、TeamsOnly モードに移行するときに、次の 4 つの呼び出しシナリオが考えられます。

- [**Microsoft 通話プラン Skype for Business Online のユーザー**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)。 アップグレード後も、このユーザーは引き続き Microsoft 通話プランを利用できます。

- Skype for Business Online のユーザー。オンプレミスまたは Cloud Connector Edition を介してSkype for Business音声 **[](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)機能を使用します**。 このユーザーの Teams へのアップグレードは、その TeamsOnly ユーザーが確実に PSTN 機能を持てるようにするため、ユーザーのダイレクト ルーティングへの移行に合わせた調整が必要になります。

- **[を使用Skype for Business](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)** オンプレミスのユーザーエンタープライズ VoIP、オンラインに移行し、オンプレミスの PSTN 接続を維持します。 このユーザーを Teams に移行するには、そのユーザーのオンプレミスの Skype for Business アカウントをクラウドに移行し、移行をそのユーザーのダイレクト ルーティングへの移行に合わせて調整する必要があります。 

- **[オンプレミスで Skype for Business](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)** を使用しているユーザーエンタープライズ VoIP、オンラインに移行し、Microsoft 通話プラン を使用します。  このユーザーを Teams に移行するには、そのユーザーのオンプレミスの Skype for Business アカウントをクラウドに移行し、移行を A) Microsoft 通話プランへのユーザーの電話番号のポートに合わせて調整するか、B) 利用可能な地域から新しいサブスクライバー番号を割り当てる必要があります。

ハイブリッド接続を設定する必要がある場合や、オンプレミスの音声機能を持つユーザーを直接ルーティングに移行する方法に関する情報など、これらのシナリオごとに音声移行を実装する方法の詳細については、次の記事 &mdash; &mdash; を参照してください。

- [IT 管理者向け Teamsアップグレード時の PSTN に関する考慮事項](upgrade-to-teams-on-prem-pstn-considerations.md)

- [Contoso 音声移行のケース スタディ](voice-case-study-overview.md)<br>
  このケース スタディでは、架空の多国籍企業 Contoso が、組織に対してTeams音声ソリューションを実装した方法について説明します。 次の記事が含まれます。

  - [Teamsアップグレード プラン](voice-case-study-migration-plan.md)
  - [Teams 電話 PSTN 接続オプション](voice-case-study-phone-system.md)
  - [場所ベースのルーティングの実装](voice-case-study-location-based-routing.md)
  - [緊急通話](voice-case-study-emergency-calling.md)
  - [自動応答と呼び出しキュー](voice-case-study-call-queues.md)
  - [電話会議](voice-case-study-audio-conferencing.md)
