---
title: Microsoft Teams で音声ソリューションを計画する
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
- highpri
ms.reviewer: crowe
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
- seo-marvel-may2020
search.appverid: MET150
description: Microsoft Teams クラウド音声機能と、組織に対して行う展開の決定の詳細について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: f1ba61d1ccbaeda26834b31a321aebfccbe23243
ms.sourcegitcommit: 401cee68d4f6f9470d614dda12b9cb023f382ff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2022
ms.locfileid: "67999352"
---
# <a name="plan-your-teams-voice-solution"></a>Teams 音声ソリューションを計画する

この記事は、組織に適した Microsoft 音声ソリューションを決定するのに役立ちます。 決定した後、この記事では、選択したソリューションを実装するためのコンテンツのロードマップを示します。

通話プランを使用した最もシンプルなソリューション&mdash;の電話システムが必要な場合があります。 このオプションは、次の図に示すように、プライベート ブランチ Exchange (PBX) 機能と公衆交換電話網 (PSTN) への呼び出しを提供する Microsoft のオール イン クラウド ソリューションです。 このソリューションを使用すると、Microsoft は PSTN 通信事業者です。

![図 1 は、通話プランを使用した電話システムを示しています。](media/voice-solutions-simple.png)

次に対して [はい] と答える場合は、通話プランを使用した電話システムが最適なソリューションです。

- 通話プランはリージョンで利用できます。
- 現在の PSTN 通信事業者を保持する必要はありません。
- PSTN への Microsoft マネージド アクセスを使用する必要があります。

ただし、状況はより複雑になる可能性があります。 たとえば、通話プランを利用できない場所にオフィスがあるとします。 または、地理的な場所ごとに異なる要件を持つ、複雑で多国籍のデプロイをサポートする組み合わせソリューションが必要な場合もあります。 Microsoft では、次のソリューションの組み合わせをサポートしています。

- 通話プランを使用した電話システム
- オペレーター接続を使用した独自の PSTN キャリアを備えた電話システム
- オペレーター コネクト モバイルを使用した独自の PSTN 携帯電話会社を使用した電話システム (パブリック プレビュー リリース)
- ダイレクト ルーティングを使用した独自の PSTN キャリアを備えた電話システム
- 通話プランを使用する電話システム、オペレーターが接続する電話システム、または直接ルーティングを使用する電話システムを使用する組み合わせソリューション

すべての音声ソリューション オプションの視覚的な概要については、音声ソリューションのポスターを参照してください。

[![Microsoft Voice Solutions ポスター。](media/microsoft-voice-solutions-thumb.png)](https://download.microsoft.com/download/4/3/5/435cd4e9-ca56-4fd1-acb6-d1fda7952320/microsoft-voice-solutions.pdf) <br> [PDF](https://download.microsoft.com/download/4/3/5/435cd4e9-ca56-4fd1-acb6-d1fda7952320/microsoft-voice-solutions.pdf) <br>[Visio](https://download.microsoft.com/download/7/5/c/75c13012-e20c-48bd-a6dd-ea49d1a3420d/microsoft-voice-solutions.vsdx) 
<br>

>[!NOTE]
>小規模から中規模のビジネス (300 人以下) の場合、Microsoft は電話システムと国内通話プランをバンドルするようになりました。 詳細については、音声ソリューションの計画、設定、管理に役立つ [中小企業向けの電話システムガイダンス](/microsoftteams/business-voice/whats-business-voice) を参照してください。

## <a name="what-do-you-need-to-read"></a>何を読む必要がありますか?

**すべてで必要です。** この記事のセクションの一部は、すべての組織に関連しています。 たとえば、全員が電話システムについて読み、公衆交換電話網 (PSTN) に接続するためのオプションを理解する必要があります。


| すべてのユーザーに必須 | 説明 |
| :------------|:-------|
| [**電話システム**](#phone-system) | Microsoft Teams を使用して Microsoft 365 クラウドで通話制御とプライベート ブランチ Exchange (PBX) 機能を有効にする Microsoft のテクノロジ。 |
| [**公衆交換電話網 (PSTN) 接続オプション**](#public-switched-telephone-network-connectivity-options) | テレフォニー通信事業者として Microsoft を選択するか、オペレーター接続または直接ルーティングを使用して独自のテレフォニー通信事業者を Microsoft Teams に接続します。 電話システムと組み合わされた PSTN 接続オプションを使用すると、ユーザーは世界中で電話を発信できます。|

**要件に応じて。** この記事および関連記事の一部のセクションは、既存のデプロイと要件に応じて関連しています。 たとえば、Location-Based ルーティングは、有料バイパスを許可しない地理的な場所のダイレクト ルーティングのお客様にのみ必要です。

必要なその他の構成を検討してください。

![図 2 は、Microsoft の電話番号、ダイヤル プラン、通話ルーティングなど、他の音声コンポーネントを示しています。](media/voice-consider-additional-components.png)

| 要件に応じて | 説明 |
| :------------|:-------|
| [**電話番号の管理**](pstn-connectivity.md#phone-number-management) | 電話番号を取得および管理する方法は、PSTN 接続オプションによって異なります。 電話番号の取得、既存の番号の転送、サービス番号の取得などを行う必要がある場合は、このセクションを参照してください。 |
| [**通話ルーティングとダイヤル プラン**](pstn-connectivity.md#call-routing-and-dial-plans) | ダイヤルされた電話番号を別の形式 (通常は E.164 形式) に変換して通話承認と通話ルーティングを行うダイヤル プランを構成および管理する方法。 ダイヤル プランと組織のダイヤル プランを指定する必要があるかどうかを理解する必要がある場合は、このセクションを参照してください。|
| [**緊急通話**](pstn-connectivity.md#emergency-calling) | 緊急通話を管理および構成する方法は、PSTN 接続オプションによって異なります。 組織の緊急通報を管理する方法を理解する必要がある場合は、このセクションを参照してください。 |
| [**ダイレクト ルーティングの場所ベースのルーティング**](pstn-connectivity.md#location-based-routing-for-direct-routing) |Location-Based ルーティング (LBR) を使用して、地理的な場所に基づいて Microsoft Teams ユーザーの有料バイパスを制限する方法。 組織が有料バイパスを許可しない場所でダイレクト ルーティングを使用している場合は、このセクションを参照してください。
| [**クラウド音声機能のネットワーク トポロジ**](pstn-connectivity.md#network-topology-for-voice-features) | 組織がダイレクト ルーティングまたは動的緊急通話のLocation-Based ルーティング (LBR) を展開している場合は、Microsoft Teams でこれらの機能のネットワーク設定を構成する必要があります。 直接ルーティング用の LBR を実装している場合、または通話プランまたはダイレクト ルーティングを使用して動的緊急通話を実装している場合は、このセクションを参照してください。 |
| [**既存の音声ソリューションを移行する**](#migrate-your-existing-voice-solution-to-teams) | 音声ソリューションを Teams に移行する際に考慮する必要がある内容。  既存の音声ソリューションから Teams に移行する場合は、このセクションを参照してください。 

> [!Important]
> この記事では、Microsoft Teams での音声ソリューションに焦点を当てています。 2021 年 7 月 31 日に Skype for Business Online が廃止されたため、Skype for Business Server または Cloud Connector Edition&mdash;と Skype for Business Online を介したオンプレミス環境&mdash;間の PSTN 接続はサポートされなくなりました。 この記事では、Teams 音声ソリューションと、オペレーター接続またはダイレクト ルーティングを使用して、必要に応じてオンプレミステレフォニー ネットワークを Teams に接続する方法について説明します。


## <a name="phone-system"></a>電話システム

電話システムは、Microsoft Teams を使用して Microsoft 365 クラウドで通話制御とプライベート ブランチ交換 (PBX) 機能を有効にする Microsoft のテクノロジです。

Phone System は Teams クライアントと認定デバイスと連携します。 電話システムを使用すると、既存の PBX システムを、Microsoft 365 から直接提供される一連の機能に置き換えることができます。 

組織内のユーザー間の呼び出しは、地理的な領域に関係なく、電話システム内で内部的に処理されます。 これらの内部通話は公衆交換電話網 (PSTN) には行かないため、会社は長い距離の料金を回避します。

この記事では、次の Phone System の主な機能と、考慮する必要がある展開の決定について説明します。

- [自動応答と呼び出しキュー](#auto-attendants-and-call-queues)
- [クラウド ボイスメール](#cloud-voicemail)
- [通話 ID](#calling-identity)

![図 3 は、電話システムに自動応答と通話クエリ、クラウド ボイスメール、通話 ID が含まれていることを示しています。](media/phone-system-contains.png)

すべての電話システム機能と電話システムの設定方法については、次の記事を参照してください。

- [電話システムで利用できる機能](here-s-what-you-get-with-phone-system.md)
- [組織内の電話システムの設定](setting-up-your-phone-system.md)<br>
  電話システム ライセンスの購入と割り当て、電話番号の管理、無料電話番号の通信クレジットの設定方法について説明します。 

サポートされているデバイスの管理の詳細については、「Microsoft Teams と [Teams Marketplace](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1) [でデバイスを管理](devices/device-management.md)する」を参照してください。


### <a name="auto-attendants-and-call-queues"></a>自動応答と通話キュー

自動応答を使用すると、呼び出し元の入力に基づいて通話をルーティングするメニュー オプションを設定できます。 呼び出しキューは、呼び出し元の待機領域です。 自動応答と通話キューを組み合わせて使用すると、発信者を組織内の適切なユーザーまたは部署に簡単にルーティングできます。

自動応答と呼び出しキューの詳細については、次の記事を参照してください。

- [Teams の自動応答と通話キューを計画する](plan-auto-attendant-call-queue.md)
- [自動応答を設定する](create-a-phone-system-auto-attendant.md)
- [呼び出しキューを作成する](create-a-phone-system-call-queue.md) 
- [Contoso のケース スタディ: 自動応答と呼び出しキュー](voice-case-study-call-queues.md)<br>
  架空の多国籍企業 Contoso が、音声ソリューションの自動応答と通話キューを実装した方法について説明します。

### <a name="cloud-voicemail"></a>クラウド ボイスメール

Azure ボイスメール サービスを搭載したクラウド ボイスメールでは、Exchange メールボックスへのボイスメールの入金のみがサポートされます。 サードパーティの電子メール システムはサポートされていません。 

クラウド ボイスメールでは、組織内のすべてのユーザーに対してボイスメールの文字起こしが既定で有効になっています。 会社のニーズに応じて、特定のユーザーまたは組織全体の全ユーザーに対してボイスメールの文字起こしを無効にすることができます。

クラウド ボイスメールは、Teams ユーザー用に自動的に設定およびプロビジョニングされます。  

クラウド ボイスメールとその構成の詳細については、次の記事を参照してください。

- [クラウド ボイスメールのセットアップ](set-up-phone-system-voicemail.md)
- [組織内でボイスメール ポリシーを設定する](manage-voicemail-policies.md)


### <a name="calling-identity"></a>通話 ID

既定で、すべての発信通話は、割り当てられた電話番号を通話 ID (発信者 ID) として使用します。 通話の受信者は、発信者をすばやく特定して、通話を承諾または拒否するかどうかを決定できます。 呼び出し元 ID の構成、または呼び出し元 ID の変更またはブロックの詳細については、「 [ユーザーの呼び出し元 ID を設定する」を参照してください](set-the-caller-id-for-a-user.md)。 

## <a name="public-switched-telephone-network-connectivity-options"></a>公衆交換電話ネットワーク接続オプション

電話システムは、組織に完全な PBX 機能を提供します。 ただし、ユーザーが組織外で通話できるようにするには、電話システムを公衆交換電話網 (PSTN) に接続する必要があります。 電話システムを PSTN に接続するには、次のいずれかのオプションを選択します。

- [**通話プランを使用した電話システム**](pstn-connectivity.md#phone-system-with-calling-plan)。 MICROSOFT を PSTN 通信事業者として使用する、クラウド内のオール イン ソリューション。

- [**オペレーター接続を使用して、独自の PSTN キャリアを持つ電話システム**](operator-connect-plan.md)。 オペレーター接続を使用すると、既存のオペレーターが Microsoft Operator Connect プログラムに参加している場合、PSTN 通話を Teams に呼び出すためのサービスを管理できます。 

- **オペレーター コネクト モバイルパブリック レビュー リリース**[**を使用して、独自の PSTN 携帯電話会社を使用した電話システム**](operator-connect-mobile-plan.md)。 オペレーター コネクト モバイルでは、既存のオペレーターが Microsoft オペレーター コネクト モバイル プログラムに参加している場合、TEAMS で SIM 対応の携帯電話番号を使用するためのサービスを管理できます。 

- [**直接ルーティングを使用して**](pstn-connectivity.md#phone-system-with-direct-routing) オンプレミス環境を Teams に接続することで、独自の PSTN キャリアを備えた電話システム。


オプションの組み合わせを選択できます。これにより、複雑な環境のソリューションを設計したり、複数ステップの移行を管理したりできます。 移行の詳細については、後ほど説明します。

ほとんどの電話システム機能は、選択した PSTN 接続オプションに関係なく同じです。 ただし、機能にはいくつかの違いがあります。これは、通話ルーティングや緊急通話など、特定の電話システム機能の構成方法に影響します。 PSTN 接続オプションと構成に関する考慮事項の詳細については、「 [PSTN 接続オプション」](pstn-connectivity.md)を参照してください。


## <a name="migrate-your-existing-voice-solution-to-teams"></a>既存の音声ソリューションを Teams に移行する

> [!NOTE]
> Skype for Business Serverから Teams にアップグレードする全体的な計画の一環として Teams 音声ソリューションを計画する場合のガイダンスについては、[オンプレミスから Teams にアップグレードするための PSTN に関する考慮事項Skype for Business](upgrade-to-teams-on-prem-pstn-considerations.md)参照してください。

Teams にアップグレードする組織の場合、最終的な目標は、すべてのユーザーを TeamsOnly モードに移行することです。 電話システムの使用は、ユーザーが TeamsOnly モードの場合にのみサポートされます。 Teams へのアップグレードに関する基本的な情報が必要な場合は、ここから始めます。

- [Microsoft Teams へのアップグレードを開始する](upgrade-start-here.md)
- [アップグレードのフレームワークについて](upgrade-framework.md)
- [IT 管​​理者向けのアップグレード戦略](upgrade-to-teams-on-prem-implement.md)

音声ソリューションを移行する場合、TeamsOnly モードに移行する場合、次の 4 つの呼び出しシナリオが考えられます。

- [**Microsoft 通話プランを使用するSkype for Business Online のユーザー**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)。 アップグレード時に、このユーザーは引き続き Microsoft 通話プランを使用します。

- **[Skype for Business Online のユーザー。オンプレミス](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)または Cloud Connector Edition を通じてオンプレミスの音声機能をSkype for Business** します。 このユーザーの Teams へのアップグレードは、その TeamsOnly ユーザーが確実に PSTN 機能を持てるようにするため、ユーザーのダイレクト ルーティングへの移行に合わせた調整が必要になります。

- **[エンタープライズ VoIPを持つオンプレミスSkype for Businessユーザー](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)。オンラインに移行し、オンプレミスの PSTN 接続を維持します**。 このユーザーを Teams に移行するには、そのユーザーのオンプレミスの Skype for Business アカウントをクラウドに移行し、移行をそのユーザーのダイレクト ルーティングへの移行に合わせて調整する必要があります。 

- **[オンラインに](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)移行し、Microsoft 通話プランを使用するエンタープライズ VoIPを持つオンプレミスSkype for Businessユーザー**。  このユーザーを Teams に移行するには、そのユーザーのオンプレミスの Skype for Business アカウントをクラウドに移行し、移行を A) Microsoft 通話プランへのユーザーの電話番号のポートに合わせて調整するか、B) 利用可能な地域から新しいサブスクライバー番号を割り当てる必要があります。

これらのシナリオごとに音声移行を実装する方法の詳細については、次の記事を参照してください。

- [TEAMS にアップグレードするときの PSTN に関する考慮事項 - IT 管理者向け](upgrade-to-teams-on-prem-pstn-considerations.md)

- [Contoso 音声移行のケース スタディ](voice-case-study-overview.md)<br>
  このケース スタディでは、架空の多国籍企業 Contoso が、組織の Teams 音声ソリューションをどのように実装したかについて説明します。 次の記事が含まれています。

  - [Teams アップグレード プラン](voice-case-study-migration-plan.md)
  - [電話システムと PSTN の接続オプション](voice-case-study-phone-system.md)
  - [場所ベースのルーティングの実装](voice-case-study-location-based-routing.md)
  - [緊急通話](voice-case-study-emergency-calling.md)
  - [自動応答と呼び出しキュー](voice-case-study-call-queues.md)
  - [電話会議](voice-case-study-audio-conferencing.md)
