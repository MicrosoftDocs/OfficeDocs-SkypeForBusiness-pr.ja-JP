---
title: "電話会議の電話番号"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/21/2017
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- LIL_Placement
- Strat_SB_PSTN
ms.assetid: 95a08f84-04e5-4f72-88a8-d6472a7c89d7

description: "Learn what countries and regions have dial-in conferencing numbers, and how they are automatically assigned."
---

# 電話会議の電話番号

> [!IMPORTANT]
> この記事は機械翻訳されています。機械翻訳についての「免責事項」をお読みください。 
  
Skype for Business および Microsoft Teams で **電話会議**をセットアップしているときに、ダイヤルイン番号が自動的に組織に割り当てられます。[ **Skype for Business 管理センター**] > [ **電話会議**] > [ **Microsoft ブリッジ**] に移動して、電話会議ブリッジに割り当てられた電話番号を見ることができます。「[ダイヤルイン会議のダイヤルイン番号のリストを表示する](see-a-list-of-audio-conferencing-numbers.md)」をご覧ください。
  
## 電話会議の利用可能範囲

電話会議を利用できる国と地域および都市の完全なリストについては、「[電話番号での PSTN 会議はこの国や地域で利用できますか?](https://support.office.com/article/1096d81e-7e14-488c-95d8-b8322e39c059)」ご覧ください。
  
## 会議の出席依頼に表示されるダイヤルイン電話番号

Skype for Business Online ユーザーまたは Microsoft Teams ユーザーが Outlook または Outlook Web アプリで会議を予約するときに、ユーザーに設定された既定の電話会議番号が会議の招待に表示されます。1 人以上のユーザーに別の既定の番号を選択したい場合は、[ **Skype for Business 管理センター**] > [ **電話会議**] > [ **ユーザー**] に移動して、番号を変更できます。「[出席依頼に含まれている会議の開催者のために電話会議の電話番号を設定する](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md)」をご覧ください。
  
その他のダイヤルイン番号は、会議の出席依頼の [ **電話番号の検索**] リンクをクリックして表示できます。
  
## 電話会議ブリッジで設定されたダイヤルイン電話番号

会議ブリッジに割り当てられる電話会議の電話番号には、 **共有** と **専用** の 2 種類があります。どちらの種類の番号でも、発信者が組織内で開催される電話会議に参加するために使用できます。
  
 **専用電話番号** とは、組織内のユーザーだけが使用できる電話番号のことです。誰かがこれらの番号のいずれかに電話をかけるときに使用する言語を変更できます。
  
 **共有電話番号** とは、他の Office 365 組織と共有できる電話番号です。誰かがこれらの番号のいずれかに通話するときに使用する言語は変更できません。
  
開催者に割り当てられる既定の電話会議番号は会議の招待状にのみ含まれるため、発信者は会議ブリッジに割り当てられた任意の電話番号を使用して、会議に参加できます。会議に参加するために使用する電話番号の一覧はそれぞれの会議の招待状に含まれる [ **電話番号の検索**] リンクを使用して利用できます。
  
## 自動的に割り当てられた電話会議の電話番号

共有の電話会議の電話番号は、電話会議で有効になると自動的に割り当てられます。電話番号が割り当てられる場合、電話番号は会議ブリッジの既定の電話番号として割り当てられます。ブリッジの既定の番号として割り当てられた電話番号は、組織の国/地域のものです。
  
> [!NOTE]
> 組織の国や地域の場所は、 **Office 365 管理センター**にサインインして、[ **会社プロファイル**] の下にあります。 
  
> [!CAUTION]
> ベネズエラ、インドネシアおよびアラブ首長国連邦 (UAE) では有料電話番号の利用は限られているため、これらの国/地域の組織には、電話会議の有料電話番号は自動的に割り当てられません。これらの場所からの無料電話番号は、利用可能なインベントリに応じて利用可能になります。 
  
電話会議の専用電話番号は、取得して自分の組織に割り当てることができるサービス番号です。サービス番号は、 **Skype for Business 管理センター**を使用して確認できます。詳細については、「[Skype for Business サービスの電話番号を取得する](../what-is-phone-system-in-office-365/getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md)」をご覧ください。
  
電話番号が自動的に組織に割り当てられる国/地域のリストを確認する場合は、「[国と地域の空き時間情報の電話会議とプランの呼び出し](../countries-and-region-availability-for-audio-conferencing-and-calling-plans/countries-and-region-availability-for-audio-conferencing-and-calling-plans.md)」をご覧ください。
  
## その他の情報

- 電話会議でサポートされる言語のリストを確認するには、「[音声会議でサポートされる言語](audio-conferencing-supported-languages.md)」をご覧ください。
    
- [Get-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617691) コマンドレットを使って、組織の電話会議の専用電話番号を表示できます。
    
- [Get-CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) コマンドレットを使って、ダイヤルインの専用電話番号に対して設定できる言語を表示できます。
    
- 電話会議の電話番号ごとに 4 言語まで、つまり第 1 言語 1 つと第 2 言語 3 つを設定できます。また、電話会議の専用電話番号に対して言語を設定することもできます。
    
- ユーザー用にダイヤルイン電話番号を設定する場合は、「[出席依頼に含まれている会議の開催者のために電話会議の電話番号を設定する](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md)」を参照してください。
    
||
|:-----|
|![LinkedIn ラーニングのショート アイコンです。](../images/7e5cb7c8-dc66-4c9a-a16d-a30f10a970bd.png) **Office 365 を初めてお使いの場合は**         、LinkedIn ラーニングによって提供された **Office 365 管理者および IT プロフェッショナル**向けの無料のビデオコースをご覧ください。 |
   
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **機械翻訳についての免責事項**: この記事の翻訳はコンピューター システムによって行われており、人間の手は加えられていません。マイクロソフトでは、英語を話さないユーザーがマイクロソフトの製品、サービス、テクノロジに関するコンテンツを理解するのに役立てるため、こうした機械翻訳を提供しています。記事は機械翻訳されているため、用語、構文、文法などに誤りがある場合があります。 
  
## 関連項目
<a name="MT_Footer"> </a>

#### 

[Office 365 でのダイヤルイン会議](../misctopics/dial-in-conferencing-in-office-365.md)

