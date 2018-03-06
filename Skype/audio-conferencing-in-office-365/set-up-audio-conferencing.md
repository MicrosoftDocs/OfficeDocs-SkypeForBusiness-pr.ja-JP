---
title: "Skype for Business および Microsoft Teams の電話会議のセットアップ"
ms.author: TONYSMIT
author: tonysmit
manager: scotv
ms.date: 11/22/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- O365P_DialInConfDesc
ms.prod: office-online-server
localization_priority: Normal
ms.collection:
- Adm_Skype4B_Online
- Adm_Skype4B_Online_Top
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- LIL_Placement
- Strat_SB_PSTN
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9

description: "Learn how to set up dial-in or audio conferencing (PSTN Conferencing) for the people in your business who need to join conference calls using a phone. "
---

# Skype for Business および Microsoft Teams の電話会議のセットアップ

組織内の人が電話機を使って会議にコールインする必要がある場合があります。Skype for Business および Microsoft Teams にはまさにこのような状況のために電話会議機能が含まれています。参加者は、モバイル機器や PC で Skype for Business または Microsoft Teams アプリを使用する代わりに、電話機を使って Skype for Business 会議や Microsoft Teams 会議にコールインできます。
  
必要なのは、会議をスケジュールまたは開催しようとしている人のために電話会議をセットアップすることだけです。ダイヤルインで参加する会議の出席者には、ライセンスの割り当てやその他のセットアップは必要ありません。
  
電話会議についてのよくある質問については、「[Audio Conferencing common questions](audio-conferencing-common-questions.md)」をご覧ください。
  
## 手順 1: ライセンスを購入して割り当てる
<a name="__top"> </a>

この手順を実行するには、[Office 365 の管理者ロールについて](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)としてログインしている必要があります。
  
1. Office 365 の電話会議がお住まいの国/地域で使用できるかを調べます。[国と地域の空き時間情報の電話会議とプランの呼び出し](../countries-and-region-availability-for-audio-conferencing-and-calling-plans/countries-and-region-availability-for-audio-conferencing-and-calling-plans.md)。
    
2. 電話会議のために購入する必要があるライセンスとその価格については、「[Skype for Business と Microsoft Teams のアドオン ライセンス](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)」をご覧の上、ライセンスを購入してください。
    
3. 会議をスケジュールまたは開催しようとしている組織内のユーザーに、購入した[一般法人向け Office 365 ライセンスの割り当てまたは解除方法](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)を割り当てます。
    
4. **電話会議**のアドオン ライセンスとコミュニケーション クレジット ライセンスを購入した場合は、それらも割り当てます。手順については「[Skype for Business と Microsoft Teams のライセンスを割り当てる](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)」をご覧ください。
    
## 手順 2: 電話会議プロバイダーを決定する
<a name="__top"> </a>

電話会議プロバイダーは *電話会議ブリッジ*  を提供します。会議ブリッジは会議のためのダイヤルイン電話番号、PIN、電話会議 ID を設定します。Microsoft またはサードパーティの電話会議プロバイダーのどちらを使うかを決めます。
  
> [!NOTE]
> Microsoft Teams ユーザーはサード パーティーの電話会議プロバイダーを使用できません。 
  
- **Microsoft を電話会議プロバイダーとして使用**: 電話会議の最も簡単な方法を希望される場合は、電話会議プロバイダーとして Microsoft を選択してください。
    
- **サードパーティを電話会議プロバイダーとして使用**: お客様がお住まいの国において Office 365 の電話会議を利用できない場合、場所が原因でサービスの品質が優れていない場合、または既存の契約がある場合は、サードパーティ電話会議プロバイダーを選択してください。プロバイダーを見つけるには、 **[Microsoft PinPoint](http://go.microsoft.com/fwlink/?LinkId=797530)** に移動してください。
    
> [!TIP]
> 組織内で、電話会議プロバイダーとして Microsoft を使用している人とサードパーティを使用している人が混在している場合がありますが、このような場合は、設定と管理がより複雑になります。 
  
電話会議プロバイダーとしての Microsoft とサードパーティ プロバイダーとの詳細な比較については、「[電話会議プロバイダーを比較する](compare-audio-conferencing-providers.md)」をご覧ください。
  
## 手順 3: 会議を開催またはスケジュールするユーザーに電話会議プロバイダーを割り当てる
<a name="__top"> </a>

これで、電話会議プロバイダーが決定したので、会議を開催またはスケジュールする組織内の人にプロバイダーを割り当てる必要があります。次のいずれかの操作を行います。
  
- [Microsoft を電話会議プロバイダーとして割り当てる](assign-microsoft-as-the-audio-conferencing-provider.md) 。
    
- [サードパーティを電話会議プロバイダーとして割り当てる](assign-a-third-party-as-the-audio-conferencing-provider.md) 。
    
## 手順 4: 会議出席依頼をセットアップする
<a name="__top"> </a>

次の手順は **オプション** ですが、多くの管理者が実行しています。
  
1. [会議出席依頼をカスタマイズする](../set-up-skype-for-business-online/customize-meeting-invitations.md) 。ユーザーに設定されるダイヤルイン番号は、出席者に送信される会議出席依頼に自動的に追加されます。ただし、独自に用意したヘルプと法的情報へのリンク、テキスト メッセージ、小さい会社ロゴなどを追加できます。
    
2. [出席依頼に含まれている会議の開催者のために電話会議の電話番号を設定する](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md) 。この電話番号は、ユーザーが予約する会議に表示されます。
    
3. 出席者が電話会議の電話番号にダイヤル インするときに、電話会議の自動案内で通話者への挨拶メッセージとして使用する[電話会議の自動案内の言語を設定する](set-auto-attendant-languages-for-audio-conferencing.md)します。この手順は、Microsoft を電話会議プロバイダーとして使用している場合のみに有効です。
    
4. [ダイヤルイン会議の PIN の長さを設定する](set-the-length-of-the-pin-for-audio-conferencing-meetings.md) 。
    
> [!NOTE]
> この機能は、現時点で中国の 21Vianet が運用している Office 365 を使用するお客様は使用できません。詳細については、「[Learn about Office 365 operated by 21Vianet](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE)」ご覧ください。 
  
||
|:-----|
|![LinkedIn ラーニングのショート アイコンです。](../images/7e5cb7c8-dc66-4c9a-a16d-a30f10a970bd.png) **Office 365 を初めてお使いの場合は**         、LinkedIn ラーニングによって提供された **Office 365 管理者および IT プロフェッショナル**向けの無料のビデオコースをご覧ください。 |
   
## 関連項目
<a name="__top"> </a>

#### 

[Audio Conferencing common questions](audio-conferencing-common-questions.md)
  
[Skype for Business Online のセットアップ](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[電話会議の電話番号](phone-numbers-for-audio-conferencing.md)
  
[オンライン会議と電話会議のオプションを設定する](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)

