---
title: Microsoft テレフォニー ソリューション
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Microsoft テレフォニー ソリューションについて説明します。
ms.openlocfilehash: 57d1abe69bc0513fa015543e8440e9d9f778b78c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "35243926"
---
# <a name="microsoft-telephony-solutions"></a>Microsoft テレフォニー ソリューション

Microsoft では、Microsoft クラウド内の Teams の使用を開始する際に使用できるいくつかのオプションをサポートしています。 この記事は、どの Microsoft テレフォニー ソリューション (クラウド内の電話システムまたはオンプレミスのエンタープライズ VoIP) が組織のユーザーに適しているかを判断し、組織を公衆交換電話網 (PSTN) に接続する方法を決定するのに役立ちます。 

この記事は、関連する技術図面と共に使用してください。この図面は、お客様の組織に適した決定を行うための視覚的な支援を提供します。

- [Microsoft テレフォニー ソリューション - PDF](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/telephony-solutions/microsoft-telephony-solutions-12-18.pdf)

- [Microsoft テレフォニー ソリューション - Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/telephony-solutions/microsoft-telephony-solutions-12-18.vsdx)




## <a name="private-branch-exchange-pbx-options"></a>構内交換機 (PBX) オプション

### <a name="phone-system-office-365"></a>電話システム (Office 365)
  
電話システムは、Microsoft Teams や Skype for Business Online を使用した Office 365 クラウドでの通話コントロールおよび構内交換機 (PBX) 機能を有効にする Microsoft の技術です。 

電話システムは、Teams または Skype for Business Online クライアントおよび認定デバイスで動作します。 電話システムを使用すると、既存の PBX システムを、Office 365 から直接提供される機能セットに置き換えて、会社のクラウドの生産性を向上させるエクスペリエンスと緊密に統合することができます。 電話システムを公衆交換電話網 (PSTN) に接続するには、Microsoft の通話プランを選択するか、独自のテレフォニー通信事業者を選択することができます。

詳細については、「[Office 365 の電話システムとは](https://docs.microsoft.com/ja-JP/MicrosoftTeams/what-is-phone-system-in-office-365)」を参照してください。

### <a name="enterprise-voice-skype-for-business-server"></a>エンタープライズ VoIP (Skype for Business Server)

エンタープライズ VoIPは、オンプレミスの Skype for Business Serverでの通話コントロールおよび構内交換機 (PBX) 機能を有効にする Microsoft の技術です。 このオプションは、独自のテレフォニー通信事業者を使用してのみ公衆交換電話網に接続できます。 

詳細については、「[Skype for Business Server のエンタープライズ VoIP の計画](https://docs.microsoft.com/ja-JP/SkypeForBusiness/plan-your-deployment/enterprise-voice-solution/enterprise-voice?toc=/SkypeForBusiness/toc.json&bc=/SkypeForBusiness/breadcrumb/toc.json)」を参照してください。

## <a name="connection-to-the-public-switched-telephone-network-pstn-options"></a>公衆交換電話網 (PSTN) オプションへの接続

以下から公衆交換電話網（PSTN）に接続する方法を選択できます。

- Office 365 の Microsoft 通話プランを使用する 
- 独自のテレフォニー通信事業者に接続する

### <a name="calling-plan-office-365"></a>通話プラン (Office 365)

このオプションでは、Microsoft の Office 365 電話システムを公衆交換電話網 (PSTN) に接続して、世界中の固定電話や携帯電話に電話をかけることができるようにします。 通話プランでは、Microsoft が PSTN 通信事業者です。

詳細については、「[Office 365 の通話プラン](https://docs.microsoft.com/ja-JP/MicrosoftTeams/calling-plans-for-office-365)」を参照してください。

### <a name="connect-your-own-telephony-carrier-office-365-and-skype-for-business-on-premises"></a>独自のテレフォニー通信事業者(オンプレミスの Office 365 および Skype for Business) に接続する

このオプションは、Office 365 の電話システムまたはオンプレミスの Skype for Business のエンタープライズ VoIP システムのいずれかをテレフォニー ネットワークに接続します。 このオプションには、サポートされているセッション ボーダー コントローラー (SBC) が必要です。 場合によっては、このオプションでは、オンプレミスに展開された追加の Microsoft ソフトウェアが必要になることがあります。

## <a name="which-solution-is-right-for-your-organization"></a>組織に適したソリューションはどれですか?

クラウド完結型ソリューション、独自の通信事業者接続ソリューション、またはクラウド完結型とサード パーティ通信事業者の組み合わせから選択できます。

- 通話プランが設定された電話システム (クラウド完結型)

- 直接ルーティング経由の独自の通信事業者による電話システム

- Skype for Business Server または Cloud Connector エディション経由の独自の通信事業者による電話システム

- 独自の通信事業者による Skype for Business Server でのエンタープライズ VoIP

選択するソリューションは、次のような現在および将来のニーズによって異なります。

- オンプレミスの展開によって提供される機能を保持する必要があるかどうか (または必須かどうか)。
- ユーザーにどのクライアントを展開したいか。
- 計画がユーザーをクラウドに移行させることなのか。
- サードパーティの PBX や他のテレフォニー機器と相互運用する必要があるかどうか。

組織に最適なソリューションを決定するには、次の点を考慮します。

- 既存の Skype for Business Server の展開はありますか?
- ユーザーがオンプレミスの Skype for Business、Skype for Business Online のクラウド、またはその両方に所属していますか? 
- オンプレミスのユーザーをクラウドに移行しますか?
- Microsoft の PSTN 通話プランをお住まいの地域で利用できますか?
- 使用しているテレフォニー通信事業者を維持する必要がありますか?  たとえば、既存の契約があるため、現在の通信事業者を維持する必要がありますか?
- 維持を希望する、または維持する必要がある既存のオンプレミスのレガシー PBX がありますか?
- 現在のレガシー PBX は、ビジネスに不可欠な固有の機能を提供していますか?
- いずれかのユーザーまたはすべてのユーザーが電話システムで現在提供されていない機能を必要としていますか?

次の点に注意してください。

- 複雑な環境や複数の手順での移行を管理するためのソリューションを設計する必要がある場合に備えて、4 つのオプションすべてを互いに共存させることができます。
- Skype for Business Server または Cloud Connector エディション経由の独自の通信事業者による電話システムは、Skype for Business Server または Cloud Connector のいずれかでのみ展開できます。 Skype for Business Server と Cloud Connector の共存は、単一の会社ではサポートされていません。

## <a name="phone-system-with-calling-plan"></a>通話プランが設定された電話システム。


次の図に示すように、通話プランが設定された電話システムは、Teams または Skype for Business Online ユーザーにとってクラウド完結型オプションです。

![通話プランが設定された電話システム。](../../sfbserver2019/media/msft-telephony-solutions-1.png)


- Microsoft 通話プランに国内および国際通話プランを追加することにより、世界中の電話機に電話をかけることができます (ライセンス対象サービスのレベルによって異なります)。 
- PSTN 通話プランは Office 365 から動作するので、このオプションでは、オンプレミス展開の展開やメンテナンスは必要ありません。
- お客様は、サードパーティ PBX、アナログ デバイス、および SBC でサポートされている他のサードパーティ製テレフォニー機器との相互運用性のために、ダイレクト ルーティングを経由してサポートされている SBC に接続できます。

| インフラストラクチャの要件                   | 必須?|
| :----------------------------------------------------| ---------:|
| Office 365 には継続的に接続する必要がある | はい |
| 世界中で利用可能*                            | いいえ  |
| サポートされているセッション ボーダー コントローラー (SBC) を展開し、保守する必要がある | いいえ |
| サード パーティ通信事業者と契約する必要がある      | いいえ   |
| Skype for Business Server または Cloud Connector エディションを展開し、保守する必要がある | いいえ |


  \* 通話プランを利用できる国と地域については、「[国および地域ごとの電話会議および通話プランの利用可能性](https://docs.microsoft.com/ja-JP/MicrosoftTeams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)」を参照してください。


以下の質問に対して [はい] と答えた場合は、これが適切なソリューションです。

- ご使用の地域で通話プランが利用可能である。 
- 現在の PSTN 通信事業者を維持する必要はない。
- 公衆交換電話網 (PSTN) に Microsoft が管理するクセス権を使用する必要がある。
- 自分のセッション ボーダー コント ローラーの管理を希望しない。
- Teams や Skype for Business Online には、組織で必要なすべての機能が含まれている。

詳細については、「[Office 365 の電話システムとは](https://docs.microsoft.com/ja-JP/MicrosoftTeams/what-is-phone-system-in-office-365)」および「[Office 365 の通話プラン](https://docs.microsoft.com/ja-JP/MicrosoftTeams/calling-plans-for-office-365)」を参照してください。

## <a name="phone-system-with-own-carrier-via-direct-routing"></a>直接ルーティング経由の独自の通信事業者による電話システム

このオプションは、Teams ユーザー向けに、事実上あらゆるテレフォニー通信事業者をクラウド内の Microsoft 電話システムに提供します。

![直接ルーティング経由の独自の通信事業者による電話システム](../../sfbserver2019/media/msft-telephony-solutions-2.png)

- サポートされている SBC は、オンプレミスのソフトウェアを追加することなく、直接 Microsoft 電話システムに接続できます。  
- Microsoft 電話システムでは、事実上すべてのテレフォニー通信事業者を使用できます。
- 構成および管理は、顧客または通信事業者またはパートナーによって行うことができます(通信事業者またはパートナーがこのオプションを提供するかどうかを尋ねます)。
- サードパーティ PBX やアナログ デバイスなどのテレフォニー機器間の相互運用性を構成します。

| インフラストラクチャの要件                   | 必須?|
| :----------------------------------------------------| ---------:|
| Office 365 には継続的に接続する必要がある | はい |
| 世界中で利用可能                            | はい  |
| サポートされているセッション ボーダー コントローラー (SBC) を展開し、保守する必要がある | はい |
| サード パーティ通信事業者と契約する必要がある*      | はい   |
| Skype for Business Server または Cloud Connector エディションを展開し、保守する必要がある | いいえ |

\* 通話プランが設定されている電話システムのユーザーが、サード パーティ PBX、アナログ デバイス、またはその他のテレフォニー機器との接続を提供するオプションとして展開されている場合を除きます。

以下の質問に対して [はい] と答えた場合は、これが適切なソリューションです。

- 電話システムによって Teams を使用する場合。
- 現在の PSTN 通信事業者を維持する必要がある。
- ルーティングの混在を希望する場合 (一部の通話は通話プラン経由、一部の通話は通信事業者経由)
- サードパーティ PBX やオーバーヘッド ページャ、アナログ デバイスなどの機器と相互運用する必要がある
- Teams には、組織で必要なすべての機能が含まれている。

詳細については、「[Office 365 の電話システムとは](https://docs.microsoft.com/ja-JP/MicrosoftTeams/what-is-phone-system-in-office-365)」および「[ダイレクト ルーティングを計画する](https://docs.microsoft.com/ja-JP/MicrosoftTeams/direct-routing-plan)」を参照してください。


## <a name="phone-system-with-own-carrier-via-skype-for-business-server-or-cloud-connector-edition"></a>Skype for Business Server または Cloud Connector エディション経由の独自の通信事業者による電話システム

このオプションは、Skype for Business Online ユーザーのために、オンプレミス テレフォニー ネットワークへの接続をクラウド内の Microsoft 電話システムに提供します。

![Skype for Business Server または Cloud Connector エディション経由の独自の通信事業者による電話システム](../../sfbserver2019/media/msft-telephony-solutions-3.png)

 - オンプレミスに展開された Skype for Business Server または Skype for Business Cloud Connector エディション経由で、サポートされている独自の SBC を Microsoft 電話システムに接続します。 
- Microsoft 電話システムでは、事実上すべてのテレフォニー通信事業者を使用できます。 
- オンプレミスの Skype for Business Server を既に持っている場合は、それを活用できます。そうでない場合は、Cloud Connector エディションというライト バージョンを展開できます。


| インフラストラクチャの要件                   | 必須?|
| :----------------------------------------------------| ---------:|
| Office 365 には継続的に接続する必要がある | はい |
| 世界中で利用可能                            | はい  |
| サポートされているセッション ボーダー コントローラー (SBC) を展開し、保守する必要がある | はい |
| サード パーティ通信事業者と契約する必要がある      | はい   |
| Skype for Business Server または Cloud Connector エディションを展開し、保守する必要がある | はい |



以下の質問に対して [はい] と答えた場合は、これが適切なソリューションです。

- ユーザーに対して Skype for Business Online を使用する必要がある。
- 地域で PSTN 通話プランが利用できない。
- 現在の PSTN 通信事業者を維持する必要がある。

詳細については、「[Office 365 の電話システムとは](https://docs.microsoft.com/ja-JP/MicrosoftTeams/what-is-phone-system-in-office-365)」、「[Skype for Business Server 2019](https://docs.microsoft.com/ja-JP/SkypeForBusiness/skype-for-business-server-2019)」、および「[Skype for Business Cloud Connector エディションの計画](https://docs.microsoft.com/ja-JP/SkypeForBusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition)」を参照してください。

推奨事項: ビジネス状況が変化した場合 (たとえば、PSTN 通信事業者を維持する必要がなくなった場合など)、オプション 1 または 2 を使用して Microsoft Teams に移行することを検討してください。
- メンテナンス費用の最小化
- Microsoft がリリースした最新機能にアクセスできます。

## <a name="enterprise-voice-in-skype-for-business-server-with-own-carrier"></a>独自の通信事業者による Skype for Business Server でのエンタープライズ VoIP

このオプションは、Skype for Business オンプレミス ユーザーのために、オンプレミス テレフォニー ネットワークへの接続をエンタープライズ VoIP オンプレミスに提供します。

![独自の通信事業者による Skype for Business Server でのエンタープライズ VoIP](../../sfbserver2019/media/msft-telephony-solutions-4.png)

- サポートされている独自の SBC を Skype for Business オンプレミス サーバーのエンタープライズ VoIP システムに接続します。
- ローカルの存続可能性が必要な場合、使用します。
- Microsoft 電話システムでは、事実上すべてのテレフォニー通信事業者を使用できます。 
- 展開して維持するための最も複雑なオプション。

| インフラストラクチャの要件                   | 必須?|
| :----------------------------------------------------| ---------:|
| Office 365 には継続的に接続する必要がある | いいえ |
| 世界中で利用可能                            | はい  |
| サポートされているセッション ボーダー コントローラー (SBC) を展開し、保守する必要がある | はい |
| サード パーティ通信事業者と契約する必要がある      | はい   |
| Skype for Business Server を展開し、保守する必要がある | はい |

詳細については、「[Skype for Business Server のエンタープライズ VoIP の計画](https://docs.microsoft.com/ja-JP/SkypeForBusiness/plan-your-deployment/enterprise-voice-solution/enterprise-voice?toc=/SkypeForBusiness/toc.json&bc=/SkypeForBusiness/breadcrumb/toc.json)」を参照してください。

推奨事項: ビジネス状況が変化した場合 (たとえば、PSTN 通信事業者を維持する必要がなくなった場合など)、オプション 1 または 2 を使用して Microsoft Teams に移行することを検討してください。
- メンテナンス費用の最小化
- Microsoft がリリースした最新機能にアクセスできます。











  
