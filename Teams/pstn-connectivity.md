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
- highpri
ms.reviewer: crowe
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
- seo-marvel-may2020
search.appverid: MET150
description: Teams 通話 (PSTN 接続) オプションと、組織に対して行う決定の詳細について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: f547528f39e92be1660f670cad44c66726fe3ef2
ms.sourcegitcommit: 401cee68d4f6f9470d614dda12b9cb023f382ff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2022
ms.locfileid: "67999642"
---
# <a name="pstn-connectivity-options"></a>PSTN 接続オプション

Microsoft は、電話システムを使用して組織に完全なプライベート ブランチ Exchange (PBX) 機能を提供します。 ただし、ユーザーが組織外で通話できるようにするには、電話システムを公衆交換電話網 (PSTN) に接続する必要があります。

この記事では、PSTN 接続オプションについて説明します。 電話システム機能の詳細など、Microsoft 音声ソリューションの詳細については、「 [Teams 音声ソリューションを計画する](cloud-voice-landing-page.md)」を参照してください。

電話システムを PSTN に接続するには、次のオプションから選択できます。

- [**プランの呼び出し**](#phone-system-with-calling-plan)。 MICROSOFT を PSTN 通信事業者として使用する、クラウド内のオール イン ソリューション。

- [**オペレーター接続**](#phone-system-with-operator-connect)。 オペレーター接続を使用すると、既存の通信事業者が Microsoft Operator Connect プログラムに参加している場合、PSTN 通話とセッション ボーダー コントローラー (SBC) を管理できます。

- [**オペレーター コネクト モバイル**](#phone-system-with-operator-connect-mobile)。 オペレーター コネクト モバイルでは、ユーザーの SIM 対応電話番号は Teams の電話番号でもあります。 既存の通信事業者が Microsoft オペレーター コネクト モバイル プログラムに参加している場合は、PSTN 通話を Teams に呼び出すためのサービスを管理できます。  **オペレーター コネクト モバイルはパブリック プレビュー リリースです。**

- [**直接ルーティング**](#phone-system-with-direct-routing)。これにより、セッション ボーダー コントローラー (SBC) を電話システムに接続して、独自の PSTN 通信事業者を使用できます。

オプションの組み合わせを選択することもできます。これにより、複雑な環境のソリューションを設計したり、複数ステップの移行を管理したりできます。

選択するオプションは、一部の電話システム機能の構成方法に影響します。 詳細については、この記事の後半の [「構成に関する考慮事項」を](#configuration-considerations) 参照してください。

## <a name="phone-system-with-calling-plan"></a>通話プランを使用した電話システム

通話プランを使用した電話システムは、Teams ユーザー向けの Microsoft のオールインクラウド音声ソリューションです。 このソリューションは、電話システムを PSTN に接続する最も簡単なオプションです。 このオプションを使用すると、次の図に示すように、Microsoft は PSTN 通信事業者として機能します。

![図 1 は、通話プランを使用した電話システムを示しています。](media/voice-solutions-simple.png)

次に対して [はい] と答える場合は、通話プランを使用した電話システムが最適なソリューションです。

- 通話プランはリージョンで利用できます。
- 現在の PSTN 通信事業者を保持する必要はありません。
- PSTN への Microsoft マネージド アクセスを使用する必要があります。

このオプションを使用すると、次のようになります。

- 電話システムには、(ライセンスが付与されているサービスのレベルに応じて) 世界中の電話への通話を可能にする国内通話プランまたは国際通話プランが追加されています。

- 通話プランは Microsoft 365 から動作するため、オンプレミス展開の展開&mdash;やメンテナンスは必要ありません。

- 注: サポートされているセッション ボーダー コントローラー (SBC) をダイレクト ルーティングを介して接続して、SBC でサポートされているサードパーティの PBX、アナログ デバイス、およびその他のテレフォニー機器との相互運用性を実現できます。

このオプションには、Microsoft 365 への中断のない接続が必要です。

通話プランの詳細については、次の記事を参照してください。

- [どの通話プランが適していますか?](calling-plan-landing-page.md)
- [通話プランを購入する方法](calling-plans-for-office-365.md)
- [通話プランが利用可能な国と地域](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [通話プランを設定する](set-up-calling-plans.md)

## <a name="phone-system-with-operator-connect"></a>オペレーターが接続された電話システム

オペレーター接続を使用すると、既存の通信事業者が Microsoft Operator Connect プログラムに参加している場合、PSTN 通話を Teams に呼び出すためのサービスを管理できます。 通信事業者は PSTN 通話サービスとセッション ボーダー コントローラー (SBC) を管理し、ハードウェアの購入と管理を節約できます。

次の場合は、オペレーター接続が組織に適したソリューションである可能性があります。

- Microsoft 通話プランは、地理的な場所では利用できません。
- お好みの通信事業者は、Microsoft Operator Connect プログラムの参加者です。
- Teams で通話を有効にする新しい通信事業者を見つける必要があります。

オペレーター接続の利点と要件、およびこのプログラムに参加している通信事業者の一覧については、「 [オペレーター接続の計画](operator-connect-plan.md)」を参照してください。 オペレーター接続を構成する方法については、「オペレーター接続の [構成」を](operator-connect-configure.md)参照してください。

## <a name="phone-system-with-operator-connect-mobile"></a>オペレーター コネクト モバイルを使用した電話システム

**オペレーター コネクト モバイルはパブリック プレビュー リリースです。**

既存の通信事業者が Microsoft オペレーター コネクト モバイル プログラムに参加している場合は、PSTN 通話を Teams に呼び出すためのサービスを管理できます。 オペレーター コネクト モバイルでは、ユーザーの SIM 対応電話番号は Teams の電話番号でもあります。  ユーザーは、モバイル サービスとデスクの両方の回線で Microsoft Teams で 1 つの電話番号を使用できます。  

サービスの組み合わせを検討する場合があります。 たとえば、モバイル サポートを必要とする営業組織とフィールド組織のオペレーター コネクト モバイルを選択できますが、デスクフォンに依存するオンサイト コール センター組織の別のソリューションを選択できます。 

オペレーター コネクト モバイルは、次の場合に組織に適したソリューションである可能性があります。

- Teams Phone の主要な会社所有の SIM 対応携帯電話番号を 1 つの番号ソリューションとして使用する必要があります。
- 優先演算子は、Microsoft オペレーター コネクト モバイル プログラムの参加者です。
- Teams で呼び出しを有効にする新しいオペレーターを見つける必要があります。

オペレーター コネクト モバイルの利点と要件、およびこのプログラムに参加している通信事業者へのリンクについては、「[プラン オペレーター コネクト モバイル](operator-connect-mobile-plan.md)」を参照してください。 オペレーター コネクト モバイルを構成する方法については、「[オペレーター コネクト モバイルの構成」を](operator-connect-mobile-configure.md)参照してください。

## <a name="phone-system-with-direct-routing"></a>ダイレクト ルーティングを使用した電話システム

このオプションは、次の図に示すように、直接ルーティングを使用して電話システムをテレフォニー ネットワークに接続します。 

![図 5 は、直接ルーティングを使用した電話システムを示しています。](media/voice-solution-with-direct-routing.png)

次の質問に対して [はい] と答える場合は、直接ルーティングを使用した電話システムが最適なソリューションです。

- 電話システムで Teams を使用する場合。
- 現在の PSTN 通信事業者を保持する必要があります。
- 一部の通話は通話プランを経由し、一部は通信事業者を介してルーティングを混在させたいと考えています。
- オーバーヘッド ポケットベル、アナログ デバイスなどのサードパーティの PBX や機器と相互運用する必要があります。

このオプションを使用すると、次のようになります。

- 追加のオンプレミス ソフトウェアを必要とせずに、サポートされている独自のセッション ボーダー コントローラー (SBC) を Phone System に接続します。

- 電話システムでは、実質的に任意のテレフォニー通信事業者を使用できます。

- このオプションを構成および管理することも、通信事業者またはパートナーによって構成および管理することもできます (通信事業者またはパートナーがこのオプションを提供しているかどうかを確認してください)。

- サードパーティ製 PBX やアナログ デバイス&mdash;、電話システムなどのテレフォニー機器&mdash;間の相互運用性を構成できます。

このオプションには、次のものが必要です。

- Microsoft 365 への中断のない接続。

- サポートされている SBC のデプロイと保守。

- サード パーティの通信事業者との契約。
  (通話プランを使用して電話システムを使用しているユーザーに対して、サードパーティの PBX、アナログ デバイス、またはその他のテレフォニー機器への接続を提供するオプションとして展開されていない場合)。

ダイレクト ルーティングの詳細については、次の記事を参照してください。

- [ダイレクト ルーティングを計画する](direct-routing-plan.md)
- [ダイレクト ルーティングを構成する](direct-routing-configure.md)
- [ダイレクト ルーティングで使用する音声ルーティング ポリシーを管理する](manage-voice-routing-policies.md)
- [ダイレクト ルーティングの場所に基づくルーティングを計画する](location-based-routing-plan.md)
- [ダイレクト ルーティングに対応する認定済みセッション ボーダー コントローラーのリスト](direct-routing-border-controllers.md)

## <a name="configuration-considerations"></a>構成に関する考慮事項

ほとんどの電話システム機能は、選択した PSTN 接続オプションに関係なく同じです。 たとえば、未応答の通話と転送の設定、通話転送、保留状態のカスタム音楽、コール パーク、共有回線、音声アプリはすべて利用できます。 電話システムの機能の完全な一覧については、 [電話システムで入手できる機能を次に示します](here-s-what-you-get-with-phone-system.md)。

ただし、特定の電話システム機能の構成方法に影響を与える機能には、いくつかの違いがあります。 たとえば、ダイレクト ルーティングでは、呼び出しルーティングを構成するための追加の手順が必要です。 別の例として、ダイレクト ルーティングは場所ベースのルーティング (LBR) を提供します。 LBR を使用すると、許可されていない特定の地理的な場所で有料バイパスを制限できます。 

次の表は、主な構成の違いを示しています。 この表に続くセクションでは、詳細情報と詳細へのリンクを示します。

| オプション | 説明 | 電話番号の管理 | 通話ルーティング | 緊急通話の可用性 |
| :------------| :-------| :-------| :-------| :-------| 
| 通話プラン | -Microsoft は PSTN 通信事業者として機能します。<br>-SBC を購入または管理する必要はありません。| Microsoft を通じて取得。| -Managed by Microsoft。 <br> -管理は、番号変換用のユーザー ダイヤル プランを構成します。 | -Microsoft によって有効になっています。 <br> -管理 アドレスを登録します。 <br> -Dynamic 呼び出しがサポートされています。 |
| オペレーター接続 | -Carrier は PSTN 接続と SBC を管理します。 <br> -SBC を購入または管理する必要はありません。 | -キャリアを介して取得します。 <br> - キャリアによって管理される緊急対応アドレスに関連付けられている番号。 | -Managed by Carrier。 <br>-管理は、番号変換用のユーザー ダイヤル プランを構成します。 | -Carrier によって有効になっています。 <br> -管理 アドレスを登録します。 <br> -Dynamic 呼び出しがサポートされています。 |
| オペレーター コネクト モバイル | -Carrier は、携帯電話番号、PSTN 接続、および SBC SIM-Enabled管理します。 <br> -SBC を購入または管理する必要はありません。 | -キャリアを介して取得します。 <br> -キャリアによって管理される緊急対応アドレスに関連付けられている番号。 | -Managed by Carrier。 <br> 管理番号変換のユーザー ダイヤル プランを構成します。 |- キャリアによって有効になります。 <br> - 管理アドレスを登録します。 <br> - 動的呼び出しがサポートされています。 <br> - キャリアでサポートされているネイティブ ダイヤラー緊急通話。 |
| ダイレクト ルーティング | -サード パーティベンダーから購入した認定 SBC が必要です。<br>-SBC を電話システムに接続します。<br> -既存の PSTN 通信事業者を使用します。 | キャリアを介して取得されます。 | -管理者による追加の構成が必要です。<br>-管理は、番号変換用のトランク ダイヤル プランを構成します。 <br>-LBR は有料バイパスを制限するために使用できます。 | -管理者による追加の構成が必要です。 <br>-登録済みのアドレスはサポートされていません。 <br>-動的呼び出しはサポートされていますが、追加の構成が必要です。 |


### <a name="phone-number-management"></a>電話番号の管理

Microsoft には、組織内のユーザーに割り当てることができるサブスクライバー (ユーザー) 番号と、有料および無料のサービス番号として使用できるサービス番号の 2 種類の電話番号があります。 サービス番号は、サブスクライバー番号よりも高い同時通話容量を持ち、電話会議、自動応答、通話キューなどのサービスに割り当てることができます。

次のことを決定する必要があります。

- Microsoft からの新しい電話番号が必要なのはどのユーザー ロケーションですか?
- どの種類の電話番号が必要ですか (サブスクライバーまたはサービス)?
- どんな方法で既存の電話番号を Teams に移植しますか?

電話番号を取得および管理する方法は、PSTN 接続オプションによって異なります。

- 通話プランの電話番号の管理については、「通話プラン [の電話番号を管理する](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)」を参照してください。

- Operator Connect で電話番号を管理する方法については、「オペレーター接続 [を使用して電話番号を設定する](operator-connect-configure.md#set-up-phone-numbers)」を参照してください。

- オペレーター コネクト モバイルで電話番号を管理する方法については、「[オペレーター コネクト モバイルで電話番号を設定](operator-connect-mobile-configure.md#set-up-phone-numbers)する」を参照してください。

- ダイレクト ルーティングの電話番号の管理の詳細については、「電話番号 [を構成してエンタープライズ音声を有効にする](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice)」を参照してください。

### <a name="call-routing-and-dial-plans"></a>通話ルーティングとダイヤル プラン

通話ルーティングの構成方法は、PSTN 接続オプションによって異なります。  

- 通話プランの場合、ほとんどの通話ルーティングは Microsoft 通話プラン インフラストラクチャによって処理されます。 通話承認と通話ルーティングの番号変換を目的として、ユーザー ダイヤル プランを構成します。 詳細については、「 [ダイヤル プランとは」](what-are-dial-plans.md)を参照してください。

- Operator Connect とオペレーター コネクト モバイルの場合、ほとんどの通話ルーティングは通信事業者によって管理されます。 通話承認と通話ルーティングの番号変換を目的として、ユーザー ダイヤル プランを構成します。 詳細については、「 [ダイヤル プランとは」](what-are-dial-plans.md)を参照してください。

- ダイレクト ルーティングの場合は、音声ルートを指定し、音声ルーティング ポリシーをユーザーに割り当てることで、通話ルーティングを構成する必要があります。 番号変換のダイヤル プランをトランク レベルで構成して、セッション ボーダー コントローラー (SBC) との相互運用性を確保できます。 詳細については、「 [ダイレクト ルーティングの音声ルーティングの構成](direct-routing-voice-routing.md)、 [音声ルーティング ポリシーの管理](manage-voice-routing-policies.md) 、 [および電話番号の変換](direct-routing-translate-numbers.md)」を参照してください。 

### <a name="location-based-routing-for-direct-routing"></a>ダイレクト ルーティングのLocation-Based ルーティング

一部の国と地域では、PSTN 通信事業者をバイパスして、長距離通話コストを削減することは違法です。 ダイレクト ルーティングのLocation-Based ルーティング (LBR) を使用すると、地理的な場所に基づいて Teams ユーザーの有料バイパスを制限できます。 LBR を計画および構成する方法の詳細については、次の記事を参照してください。

- [ダイレクト ルーティングの場所に基づくルーティングを計画する](location-based-routing-plan.md)
- [場所に基づくルーティングのネットワーク設定を構成する](location-based-routing-configure-network-settings.md)
- [ダイレクト ルーティングの場所に基づくルーティングを有効にする](location-based-routing-enable.md)
- [Contoso のケース スタディ: Location-Based ルーティング](voice-case-study-location-based-routing.md)<br>
  架空の多国籍企業 Contoso が組織のルーティングLocation-Based実装した方法について説明します。

### <a name="emergency-calling"></a>緊急通話

緊急通報の構成方法は、PSTN 接続オプションによって異なります。

- 通話プランの場合、各ユーザーは緊急通話に対して自動的に有効になります。 Ths ユーザーには、割り当てられた電話番号に関連付けられている緊急対応の登録アドレスが必要です。 (Teams クライアントの場所に基づいて) 動的緊急通報がサポートされています。 詳細については、「[プランの呼び出しに関する考慮事項」を](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)参照してください。 

- Operator Connect の場合、各ユーザーは緊急通話に対して自動的に有効になります。 ユーザーには、割り当てられた電話番号に関連付けられた緊急対応の登録アドレスが必要です。 (Teams クライアントの場所に基づいて) 動的緊急通報がサポートされています。 詳細については、「 [オペレーター接続に関する考慮事項」を](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-operator-connect)参照してください。 

- オペレーター コネクト モバイルの場合、各ユーザーは緊急通報に対して自動的に有効になります。 緊急通報は、特定の番号のオペレーター コネクト モバイル運送業者に自動的にルーティングされます。 (Teams クライアントの場所に基づいて) 動的緊急通報がサポートされています。 詳細については、「[オペレーター コネクト モバイルに関する考慮事項」を](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-operator-connect-mobile)参照してください。 

- ダイレクト ルーティングの場合は、Teams 緊急通話ルーティング ポリシー (TeamsEmergencyCallRoutingPolicy) を使用して、ユーザーの緊急通話ポリシーを定義する必要があります。 ポリシーでは、緊急電話番号とそれに関連するルーティング先が定義されます。 登録された緊急対応の場所は、ダイレクト ルーティング ユーザーではサポートされていません。 動的緊急通報の場合、緊急通報をルーティングしたり、パートナー接続を行う場合は、追加の構成が必要です。 詳細については、「 [ダイレクト ルーティングに関する考慮事項」を](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing)参照してください。

#### <a name="for-more-information"></a>関連情報

緊急通報の概念と用語、および緊急通報と動的緊急通報を構成する方法の詳細については、次の記事を参照してください。

- [緊急通報を管理する](what-are-emergency-locations-addresses-and-call-routing.md)
- [動的な緊急通話を計画して構成する](configure-dynamic-emergency-calling.md)
- [緊急通話ポリシーを管理する](manage-emergency-calling-policies.md)
- [ダイレクト ルーティングの緊急通話ルーティング ポリシーを管理する](manage-emergency-call-routing-policies.md)
- [Contoso のケース スタディ: 緊急通話](voice-case-study-emergency-calling.md)<br>
  架空の多国籍企業 Contoso が、組織の緊急呼び出しを実装した方法について説明します。

### <a name="network-topology-for-voice-features"></a>音声機能のネットワーク トポロジ

動的緊急通報またはダイレクト ルーティングのLocation-Basedルーティングを展開する場合は、Microsoft Teams でこれらの機能のネットワーク設定を構成する必要があります。 ネットワーク リージョン、ネットワーク サイト、ネットワーク サブネット、信頼された IP アドレスのネットワーク設定を構成する方法については、次の記事を参照してください。

- [Microsoft Teams のクラウド音声機能のネットワーク設定 - 概念と用語](cloud-voice-network-settings.md)
- [Microsoft Teams でクラウド音声機能のネットワーク トポロジを管理する](manage-your-network-topology.md)
