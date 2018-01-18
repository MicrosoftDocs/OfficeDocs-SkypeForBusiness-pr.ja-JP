---
title: "Skype for Business および Microsoft Teams の電話会議のセットアップ"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: O365P_DialInConfDesc
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
- LIL_Placement
description: "電話を使用して会議に参加する必要のあるビジネスで、ユーザーのダイヤルインまたはオーディオ会議を設定する方法について説明します。 "
ms.openlocfilehash: 6d8fae08a5dc8e6a1cf6bc05b458840c47fc83ed
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2017
---
# <a name="set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams"></a>Skype for Business および Microsoft Teams の電話会議のセットアップ

組織内のユーザーは、会議へのコールに電話を使用する必要があります。 Skype ビジネスおよびマイクロソフトのチームには、これだけのオーディオ会議機能を搭載! 人は、ビジネスまたはマイクロソフトのチームのアプリケーションをモバイル デバイスまたは PC 上で、Skype を使用する代わりに、電話を使用するビジネスまたはマイクロソフトのチームの会議、Skype を呼び出すことができます。 
  
のみ、スケジュールや会議を計画している人の電話会議を設定する必要があります。 ダイヤルイン会議の参加者、ライセンスを取得、またはその他の設定に割り当てられている必要はありません。
  
オーディオ会議についてよく寄せられる質問は、[オーディオ会議のよく寄せられる質問](audio-conferencing-common-questions.md)を参照してください。
  
## <a name="step-1-buy-and-assign-licenses"></a>手順 1: ライセンスを購入して割り当てる
<a name="__top"> </a>

この手順を実行するのには、 [Office 365 の管理者の役割](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)をする必要があります。
  
1. Office 365 のオーディオ会議は、国/地域で利用可能なかどうかを確認します。 [オーディオ会議や予定を呼び出すための国および地域の可用性](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)です。 
    
2. オーディオ会議、およびかかる費用は購入する必要がありますライセンスについて説明します。 [Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)を参照してくださいし、ライセンスを購入します。 
    
3. [割り当てまたはビジネスのための Office 365 のライセンスを削除する](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)人に、組織の会議のスケジュール、または潜在顧客を購入しました。
    
4. **オーディオ会議**のアドオン ライセンスおよび通信のクレジットのライセンスを購入した場合も割り当てます。 手順については、[ビジネスおよびマイクロソフトのチームのライセンスを Skype を割り当てる](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)を参照してください。
    
## <a name="step-2-decide-on-your-audio-conferencing-provider"></a>手順 2: は、オーディオ会議プロバイダーを決定します。
<a name="__top"> </a>

オーディオ会議プロバイダーは、*オーディオ会議用ブリッジ*を提供します。 会議用ブリッジは、ダイヤルインの電話番号、Pin、および会議の会議 Id を設定します。 Microsoft またはサード パーティ製のオーディオ会議プロバイダーを使用するかどうかを決定します。
  
> [!NOTE]
> マイクロソフトのチームのユーザーには、サード ・ パーティ製のオーディオ会議プロバイダーのユーザーことはできません。 
  
- **オーディオ会議プロバイダーとして Microsoft**: オーディオ会議の最も簡単なソリューションをする場合は、オーディオ会議プロバイダーとして Microsoft を選択します。
    
- **オーディオ会議プロバイダーとして、サード パーティ製**: サード ・ パーティ製のオーディオを選択する場合、Office 365 での音声会議を使用できないための場所では、優れたサービスの品質はありません、既存の契約がある国で、会議プロバイダーです。 プロバイダーを検索するには、[マイクロソフトの特定](http://go.microsoft.com/fwlink/?LinkId=797530)に移動します。
    
> [!TIP]
> 組織では、することが、オーディオ会議プロバイダーでは、Microsoft を使用している人や他のユーザー、サード パーティ プロバイダーを使用します。 設定および管理するために複雑になります。 
  
オーディオのプロバイダーは、Microsoft およびサード パーティ プロバイダーの間で詳細に比較は、[オーディオ会議プロバイダーの比較](compare-audio-conferencing-providers.md)を参照してください。 
  
## <a name="step-3-assign-the-audio-conferencing-provider-to-people-who-lead-or-schedule-meetings"></a>手順 3: オーディオ会議プロバイダーをリードしたり、会議をスケジュールするユーザーに割り当てる
<a name="__top"> </a>

オーディオ会議プロバイダーを決定したら、これでは、プロバイダーをリードしたり、会議をスケジュールする、組織内のユーザーに割り当てる必要があります。 次のいずれかの操作を行います。 
  
- [オーディオ会議プロバイダーとしてマイクロソフトを割り当てます](assign-microsoft-as-the-audio-conferencing-provider.md)。
    
- [オーディオ会議プロバイダーとしてサードパーティ製の割り当て](assign-a-third-party-as-the-audio-conferencing-provider.md)を。
    
## <a name="step-4-set-up-meeting-invitations"></a>手順 4: 会議出席依頼の設定
<a name="__top"> </a>

次の手順**オプション**ですが、管理者の多くがそれらを行いたいです。
  
1. [ミーティングの招待状をカスタマイズ](../set-up-skype-for-business-online/customize-meeting-invitations.md)します。 ユーザーに設定されているダイヤルの番号は、出席者に送信される会議出席依頼に自動的に追加されます。 ただし、独自のヘルプおよび法律上のリンク、テキスト メッセージ、および小規模な会社のグラフィックを追加することができます。
    
2. [ミーティングの開催者の招待に収録されている電話会議の電話番号を設定](set-the-phone-numbers-included-on-invites.md)します。 これは、ユーザーがスケジュールされている会議で表示される電話番号です。
    
3. [オーディオ会議の自動応答の言語設定](set-auto-attendant-languages-for-audio-conferencing.md)で、電話会議の電話番号にダイヤルするときに、呼び出し元を呼びかけられるように設定するのには、オーディオ会議自動アテンダントを使用します。 この手順は、Microsoft のオーディオのプロバイダーとして使用する場合にのみ適用されます。
    
4. [オーディオ会議の会議の暗証番号 (pin) の長さを設定](set-the-pin-length-for-audio-conferencing-meetings.md)します。
    
> [!NOTE]
> この機能はまだ顧客に利用可能な Office 365 を使用して運用している中国で 21Vianet。 詳細については、 [21Vianet によって運営されて Office 365 について](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE)を参照してください。 
  
[!INCLUDE [LinkedIn Learning Info](../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>関連トピック

[オーディオ会議の一般的な質問](audio-conferencing-common-questions.md)
  
[Skype for Business Online のセットアップ](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[オーディオ会議用電話番号](phone-numbers-for-audio-conferencing.md)
  
[オンライン会議、電話会議のオプションを設定します。](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)

