---
title: Microsoft テレフォニーソリューション
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/20/2018
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Microsoft テレフォニーソリューションについて説明します。
ms.openlocfilehash: c317079284c43f2578141827409655903982b79e
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221327"
---
# <a name="microsoft-telephony-solutions"></a>Microsoft テレフォニーソリューション

Microsoft は、Microsoft クラウドでの Teams への移行を開始する際に、いくつかのオプションをサポートしています。 この記事では、組織内のユーザーに適切な Microsoft テレフォニーソリューション (クラウドまたはエンタープライズボイスオンプレミスの電話システム) を決定し、組織が公衆交換電話網 (PSTN) に接続する方法を決定するのに役立つ情報を示します。 

この記事は、関連する技術ダイアグラムと一緒に使用してください。これにより、組織にとって適切な決定を行うためのビジュアルエイドが提供されます。

- [Microsoft テレフォニーソリューション-PDF](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/telephony-solutions/microsoft-telephony-solutions-12-18.pdf)

- [Microsoft テレフォニーソリューション-Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/telephony-solutions/microsoft-telephony-solutions-12-18.vsdx)




## <a name="private-branch-exchange-pbx-options"></a>構内交換 (PBX) のオプション

### <a name="phone-system-microsoft-365-or-office-365"></a>電話システム (Microsoft 365 または Office 365)
  
電話システムは、microsoft Teams または Skype for Business Online を使用して microsoft 365 または Office 365 クラウドで通話コントロールと構内交換機 (PBX) 機能を有効にするための Microsoft のテクノロジです。 

電話システムは Teams または Skype for Business Online クライアントおよび認定済みデバイスと連携して動作します。 電話システムを使用すると、既存の PBX システムを、Microsoft 365 または Office 365 から直接提供される一連の機能に置き換えて、会社のクラウドの生産性向上に密接に統合することができます。 電話システムを公衆交換電話網 (PSTN) に接続するには、Microsoft の通話プランまたは独自のテレフォニーキャリアを選択できます。

詳細については、「 [Microsoft 365 または Office 365 の電話システムとは](https://docs.microsoft.com/MicrosoftTeams/what-is-phone-system-in-office-365)」を参照してください。

### <a name="enterprise-voice-skype-for-business-server"></a>エンタープライズ Voip (Skype for Business Server)

エンタープライズ Voip は、オンプレミスの Skype for Business Server で通話コントロールと構内交換機 (PBX) 機能を有効にするための Microsoft のテクノロジです。 このオプションは、独自のテレフォニーキャリアを使用して、公衆交換電話網にのみ接続できます。 

詳細については、「 [Plan For Enterprise Voice In Skype For Business Server](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/enterprise-voice-solution/enterprise-voice?toc=/SkypeForBusiness/toc.json&bc=/SkypeForBusiness/breadcrumb/toc.json)」を参照してください。

## <a name="connection-to-the-public-switched-telephone-network-pstn-options"></a>公衆交換電話網 (PSTN) オプションへの接続

公衆交換電話網 (PSTN) に接続するには、次の方法を選択できます。

- Microsoft 365 または Office 365 で Microsoft 通話プランを使用する 
- 独自のテレフォニー電話会社への接続

### <a name="calling-plan-microsoft-365-or-office-365"></a>通話プラン (Microsoft 365 または Office 365)

このオプションは、Microsoft 365 または Office 365 の電話システムを公衆交換電話網 (PSTN) に接続して、世界中の固定電話および携帯電話の通話を有効にします。 通話プランの場合、Microsoft は PSTN キャリアです。

詳細については、「 [Microsoft 365 または Office 365 の通話プラン](https://docs.microsoft.com/MicrosoftTeams/calling-plans-for-office-365)」を参照してください。

### <a name="connect-your-own-telephony-carrier-microsoft-365-or-office-365-and-skype-for-business-on-premises"></a>独自のテレフォニー電話会社 (Microsoft 365 または Office 365 と Skype for Business オンプレミス) を接続する

このオプションを使用すると、オンプレミスの Skype for Business の Microsoft 365 または Office 365 またはエンタープライズ Voip システムの電話システムがテレフォニーネットワークに接続されます。 このオプションには、サポートされているセッションボーダーコントローラー (SBC) が必要です。 場合によっては、オンプレミスで展開された追加の Microsoft ソフトウェアが必要になることがあります。

## <a name="which-solution-is-right-for-your-organization"></a>どのソリューションが自分の組織に適していますか?

クラウド内のすべてのソリューション、独自のキャリアソリューション、またはすべてのクラウドとサードパーティ製の通信事業者との間の組み合わせを選択できます。

- 通話プラン (クラウド内のすべて) を使用する電話システム

- 直接ルーティング経由で carrier を備えた電話システム

- Skype for Business Server または Cloud Connector エディションを使用した独自のキャリアを備えた電話システム

- 自分の電話会社がある Skype for Business Server のエンタープライズ Voip

選択するソリューションは、次のような現在および将来のニーズに応じて異なります。

- -または必須であるかどうか--オンプレミス展開によって提供される機能を保持します。
- ユーザー用に展開するクライアント。
- ユーザーをクラウドに移行するための計画について説明します。
- サードパーティの Pbx やその他のテレフォニー機器との相互運用が必要かどうか。

組織にとって最適なソリューションを決定するには、以下の点を考慮してください。

- 既存の Skype for Business Server の展開はありますか。
- ユーザーは、オンプレミスの Skype for Business、Skype for Business Online のクラウド、またはその両方に所属していますか。 
- オンプレミスのユーザーをクラウドに移行しますか?
- Microsoft の PSTN 通話プランは、お客様の地域で利用できますか?
- 現在のテレフォニーキャリアを維持する必要がありますか。  たとえば、既存の契約のために現在の電話会社を維持する必要があるかどうか。
- 既存のオンプレミスの従来の PBX が必要な場合、または保持する必要がある場合は、
- 現在の従来の PBX は、ビジネスに不可欠な固有の機能を提供していますか?
- 一部またはすべてのユーザーに、現在電話システムで提供されていない機能が必要かどうかを確認します。

次の点に注意してください。

- 複雑な環境のソリューションを設計したり、複数ステップの移行を管理したりする必要がある場合は、4つのオプションすべてを互いに共存させることができます。
- Skype for business Server または cloud Connector エディションを使用した独自のキャリアを備えた電話システムは、Skype for business Server または Cloud Connector を使用してのみ展開できます。 1つの会社では、Skype for Business Server と Cloud Connector の共存はサポートされていません。

## <a name="phone-system-with-calling-plan"></a>通話プランがある電話システム


通話プランが設定された電話システムは、次の図に示すように、Teams または Skype for Business Online ユーザーのすべてのクラウドオプションです。

![通話プランがある電話システム](../../sfbserver2019/media/msft-telephony-solutions-1.png)


- 国内または国際通話プランが追加された Microsoft 電話システム (ライセンス対象のサービスのレベルによって異なります)。 
- PSTN 通話プランは、Microsoft 365 または Office 365 では動作しないため、このオプションでは、オンプレミス展開の展開やメンテナンスは必要ありません。
- お客様は、直接ルーティングを使用して、サードパーティの PBX、アナログデバイス、および SBC でサポートされている他のサードパーティ製テレフォニー機器との相互運用性を実現するために、サポートされる SBC を接続できます。

| インフラストラクチャの要件                   | 必須|
| :----------------------------------------------------| ---------:|
| Microsoft 365 または Office 365 への継続的な接続は必要ありません | はい |
| 世界中で利用可能                            | いいえ  |
| サポートされているセッションボーダーコントローラー (SBC) を展開および維持する必要がある | いいえ |
| サードパーティ製の電話会社との契約が必要      | いいえ   |
| Skype for Business Server または Cloud Connector エディションの展開と保守が必要 | いいえ |

\*通話プランが利用可能な国の詳細については、「[国および地域の利用可能な電話会議と通話プラン](https://docs.microsoft.com/MicrosoftTeams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)」を参照してください。


次の質問に対して [はい] を選択した場合は、次の方法が適しています。

- 通話プランは、お客様の地域でご利用いただけます。
- 現在の PSTN キャリアを保持する必要はありません。
- Microsoft によって管理される公衆交換電話網 (PSTN) へのアクセスを使用する場合。
- セッションボーダーコントローラーを独自に管理しない場合。
- Teams または Skype for Business Online には、組織が必要とするすべての機能が含まれています。

詳細については、「 [microsoft 365 の電話システムに](https://docs.microsoft.com/MicrosoftTeams/what-is-phone-system-in-office-365)ついて」365および「 [microsoft 365 または Office 365 の通話プラン](https://docs.microsoft.com/MicrosoftTeams/calling-plans-for-office-365)」を参照してください。

## <a name="phone-system-with-own-carrier-via-direct-routing"></a>直接ルーティング経由で carrier を備えた電話システム

このオプションを使用すると、Teams ユーザーに対して、ほぼすべてのテレフォニーキャリアを備えた Microsoft Phone システムがクラウドに提供されます。

![直接ルーティングを使用して、carrier を使用する電話システム](../../sfbserver2019/media/msft-telephony-solutions-2.png)

- 追加のオンプレミスソフトウェアを必要とせずに、独自にサポートされている SBC を Microsoft Phone システムに直接接続します。  
- Microsoft Phone システムでは、ほとんどすべてのテレフォニーキャリアを使用します。
- お客様または carrier またはパートナーによって構成および管理することができます (このオプションが carrier またはパートナーから提供されているかどうかを確認してください)。
- サードパーティの PBX やアナログデバイスなどのテレフォニー機器と Microsoft Phone システムとの間の相互運用性を構成します。

| インフラストラクチャの要件                   | 必須|
| :----------------------------------------------------| ---------:|
| Microsoft 365 または Office 365 への継続的な接続は必要ありません | はい |
| 世界中で利用可能                            | はい  |
| サポートされているセッションボーダーコントローラー (SBC) を展開および維持する必要がある | はい |
| サードパーティ製の電話会社との契約が必要 *      | はい   |
| Skype for Business Server または Cloud Connector エディションの展開と保守が必要 | いいえ |

\*通話プランが設定された電話システムのユーザーのために、サードパーティの PBX、アナログデバイス、またはその他のテレフォニー機器への接続を提供するオプションとして展開されている場合を除きます。

次の質問に対して [はい] を選択した場合は、次の方法が適しています。

- 電話システムで Teams を使用する場合。
- 現在の PSTN キャリアを保持する必要があります。
- ルーティングを混在させる場合は、通話プランを経由する通話 (一部の通話は、carrier を介して行います)
- サードパーティの Pbx や機器との相互運用が必要なのは、microsoft が提供するオーバーヘッドポケットベル、アナログデバイス
- Teams には、組織に必要なすべての機能が用意されています。

詳細については、「 [Microsoft 365 の電話システムと Office 365 に](https://docs.microsoft.com/MicrosoftTeams/what-is-phone-system-in-office-365)ついて」と「 [Direct Routing を計画](https://docs.microsoft.com/MicrosoftTeams/direct-routing-plan)する」を参照してください。


## <a name="phone-system-with-own-carrier-via-skype-for-business-server-or-cloud-connector-edition"></a>Skype for Business Server または Cloud Connector エディションを使用した独自のキャリアを備えた電話システム

このオプションでは、Skype for Business Online ユーザーのオンプレミスのテレフォニーネットワークへの接続を備えた、クラウド内の Microsoft 電話システムが提供されます。

![Skype for Business Server または Cloud Connector エディションを使用して、ご利用のキャリアを備えた電話システム](../../sfbserver2019/media/msft-telephony-solutions-3.png)

 - オンプレミスで展開されている Skype for Business Server または Skype for Business Cloud Connector エディションを使用して、サポートされる SBC を Microsoft Phone システムに接続します。 
- Microsoft Phone システムでは、ほとんどすべてのテレフォニーキャリアを使用します。 
- オンプレミスの Skype for Business Server が既にインストールされている場合は、それを活用することができます。 そうしない場合は、薄いバージョンの Cloud Connector エディションを展開できます。


| インフラストラクチャの要件                   | 必須|
| :----------------------------------------------------| ---------:|
| Microsoft 365 または Office 365 への継続的な接続は必要ありません | はい |
| 世界中で利用可能                            | はい  |
| サポートされているセッションボーダーコントローラー (SBC) を展開および維持する必要がある | はい |
| サードパーティ製の電話会社との契約が必要      | はい   |
| Skype for Business Server または Cloud Connector エディションの展開と保守が必要 | はい |



次の質問に対して [はい] を選択した場合は、次の方法が適しています。

- ユーザーに Skype for Business Online を使用する場合。
- PSTN 通話プランは、お客様の地域では利用できません。
- 現在の PSTN キャリアを保持する必要があります。

詳細については、「 [Microsoft 365 の電話システムと Office 365](https://docs.microsoft.com/MicrosoftTeams/what-is-phone-system-in-office-365)、 [Skype for business Server 2019](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-server-2019)」、および「 [Plan For Skype for business Cloud Connector Edition](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition)」を参照してください。

推奨事項: ビジネス上の条件が変更された場合、たとえば、PSTN キャリアを保持する必要がなくなった場合は、オプション1または2を使用して Microsoft Teams に移行することを検討します。
- メンテナンスコストを最小限に抑える
- Microsoft によってリリースされた最新の機能にアクセスできる

## <a name="enterprise-voice-in-skype-for-business-server-with-own-carrier"></a>自分の電話会社がある Skype for Business Server のエンタープライズ Voip

このオプションを使用すると、オンプレミスのテレフォニーネットワークに接続するエンタープライズ Voip オンプレミスが、オンプレミスの Skype for Business オンプレミスユーザーに提供されます。

![自分の電話会社がある Skype for Business Server のエンタープライズ Voip](../../sfbserver2019/media/msft-telephony-solutions-4.png)

- Skype for Business オンプレミスサーバーでサポートされている SBC をエンタープライズ Voip システムに接続します。
- ローカル存続性が必要な場合に使用します。
- Microsoft Phone システムでは、ほとんどすべてのテレフォニーキャリアを使用します。 
- 展開と保守のための最も複雑なオプション。

| インフラストラクチャの要件                   | 必須|
| :----------------------------------------------------| ---------:|
| Microsoft 365 または Office 365 への継続的な接続は必要ありません | いいえ |
| 世界中で利用可能                            | はい  |
| サポートされているセッションボーダーコントローラー (SBC) を展開および維持する必要がある | はい |
| サードパーティ製の電話会社との契約が必要      | はい   |
| Skype for Business Server の展開と保守が必要 | はい |

詳細については、「 [Plan For Enterprise Voice In Skype For Business Server](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/enterprise-voice-solution/enterprise-voice?toc=/SkypeForBusiness/toc.json&bc=/SkypeForBusiness/breadcrumb/toc.json)」を参照してください。

推奨事項: ビジネス上の条件が変更された場合、たとえば、PSTN キャリアを保持する必要がなくなった場合は、オプション1または2を使用して Microsoft Teams に移行することを検討します。
- メンテナンスコストを最小限に抑える
- Microsoft によってリリースされた最新の機能にアクセスできる
