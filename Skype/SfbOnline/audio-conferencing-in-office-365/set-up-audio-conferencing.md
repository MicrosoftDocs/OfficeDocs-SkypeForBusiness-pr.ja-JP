---
title: "Skype for Business とチームの Microsoft の音声会議をセットアップする設定します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- O365P_DialInConfDesc
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
- LIL_Placement
description: "電話を使用して会議に参加する必要があるビジネスで他のユーザーのダイヤルインまたは音声会議を設定する方法について説明します。 "
ms.openlocfilehash: 44eaa0c7a90c0e9495eaffc81de4d9dcf9f06bbd
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams"></a>Skype for Business とチームの Microsoft の音声会議をセットアップする設定します。

組織のユーザーは、電話を使用して、会議にコールインする必要があります。Skype for Business とチームを Microsoft には、電話会議機能にはこれだけが含まれます。ユーザーが会議に参加 Skype に Business または Microsoft チーム会議が、Skype を使用して for Business または Microsoft チームのアプリをモバイル デバイスや PC ではなく、電話を使用します。 
  
のみ、スケジュールや会議を計画しているユーザーの電話会議を設定する必要があります。ダイヤルイン会議の参加者には、またはその他のセットアップに割り当てられているライセンスを必要はありません。
  
音声会議についてよく寄せられる質問は、[電話会議のよく寄せられる質問](audio-conferencing-common-questions.md)を参照してください。
  
## <a name="step-1-buy-and-assign-licenses"></a>手順 1: 購入して、ライセンスを割り当てる
<a name="__top"> </a>

この手順を実行するを[Office 365 の管理者の役割](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)があります。
  
1. Office 365 で音声会議が住んでいる国/地域で利用可能なかどうかを確認します。[電話会議とプランの呼び出しの国と地域の空き時間情報](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。 
    
2. 音声会議、およびコストはどの程度を購入する必要があります。 ライセンスについて説明します。[Skype for Business や Microsoft チーム アドオンのライセンス](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)を表示し、ライセンスを購入します。 
    
3. ユーザーが会議をスケジュールまたは潜在顧客] に、組織のユーザーを購入した[の割り当てまたは一般法人向け Office 365 のライセンスを削除](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)します。
    
4. **電話会議**アドオン ライセンスとの通信クレジット ライセンスを購入した場合も割り当てます。手順については、[ビジネスや Microsoft チームのライセンスを割り当てる Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)を参照してください。
    
## <a name="step-2-decide-on-your-audio-conferencing-provider"></a>手順 2: は、電話会議プロバイダーを決定します。
<a name="__top"> </a>

電話会議プロバイダーは、*電話会議ブリッジ*を提供します。会議ブリッジにダイヤルイン電話番号、Pin や会議の会議 Id を設定します。Microsoft またはサード パーティの電話会議プロバイダーを使用するかどうかを決定します。
  
> [!NOTE]
> Microsoft チームのユーザーには、サードパーティ電話会議プロバイダーをユーザーことはできません。 
  
- **電話会議プロバイダーとして Microsoft**: 電話会議の最も簡単に解決するには、場合は、電話会議プロバイダーとして Microsoft を選択します。
    
- **電話会議プロバイダーとしてサードパーティ**: 国、Office 365 で音声会議は使用できません、サービスの品質がない理由により、その場所では、とても便利なまたは既存の契約がある場合は、サード パーティの音声を] を選びます。会議のプロバイダーします。プロバイダーを見つけるには、 [Microsoft PinPoint](http://go.microsoft.com/fwlink/?LinkId=797530)へ移動します。
    
> [!TIP]
> 自分の組織では、自分の電話会議プロバイダーとして Microsoft を使用している一部のユーザーと他のユーザーをサードパーティ プロバイダーを使用していることができます。設定および管理するためのより複雑になります。 
  
オーディオ プロバイダーとして Microsoft およびサードパーティ プロバイダー間の詳細な比較] は、「[電話会議プロバイダーを比較する](compare-audio-conferencing-providers.md)」を参照してください。 
  
## <a name="step-3-assign-the-audio-conferencing-provider-to-people-who-lead-or-schedule-meetings"></a>手順 3: 潜在顧客、または会議をスケジュールしてきた相手に電話会議プロバイダーを割り当てる
<a name="__top"> </a>

電話会議プロバイダーを決定したら、潜在顧客、または会議をスケジュールした組織内のユーザーに、プロバイダーを割り当てる必要があります。{次のいずれかを行います。} 
  
- [電話会議プロバイダーとして Microsoft を割り当てます](assign-microsoft-as-the-audio-conferencing-provider.md)。
    
- [電話会議プロバイダーとしてサードパーティを割り当てます](assign-a-third-party-as-the-audio-conferencing-provider.md)。
    
## <a name="step-4-set-up-meeting-invitations"></a>手順 4: 会議出席依頼を設定します。
<a name="__top"> </a>

次の手順**オプション**ですが、それらを実行するなどの多くの管理者。
  
1. [会議の出席依頼をカスタマイズ](../set-up-skype-for-business-online/customize-meeting-invitations.md)します。ユーザーに設定されているダイヤルイン番号は、出席者に送信された会議出席依頼に自動的に追加されます。ただし、独自のヘルプ、法的なリンク、テキスト メッセージで、小規模企業のグラフィックを追加することができます。
    
2. [会議の開催者の招待に収録されている電話会議の電話番号を設定](set-the-phone-numbers-included-on-invites.md)します。これは、電話番号をユーザーがスケジュールされている会議が表示されます。
    
3. [電話会議の自動応答の言語を設定する](set-auto-attendant-languages-for-audio-conferencing.md)のに、電話会議の電話番号にダイヤルインしたときに、発信者をあいさつ電話会議の自動応答を使用します。この手順は、オーディオ プロバイダーとして Microsoft を使っている場合にのみ適用されます。
    
4. [電話会議の会議の PIN の長さを設定](set-the-pin-length-for-audio-conferencing-meetings.md)します。
    
> [!NOTE]
> この機能はまだ中国の 21 vianet 顧客に利用可能な Office 365 を使って操作します。詳細については、 [21 vianet が運営する Office 365 について](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE)参照してください。 
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>関連トピック

[音声会議よく寄せられる質問](audio-conferencing-common-questions.md)
  
[Skype for Business Online をセットアップします。](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[電話会議の電話番号](phone-numbers-for-audio-conferencing.md)
  
[オンライン会議と電話会議のオプションを設定します。](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)

