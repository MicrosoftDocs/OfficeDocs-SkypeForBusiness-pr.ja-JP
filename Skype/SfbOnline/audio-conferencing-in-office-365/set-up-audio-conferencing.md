---
title: Skype for Business の電話会議をセットアップする
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- LIL_Placement
- O365P_DialInConfDesc
description: '電話を使用して電話会議に参加する必要がある社内ユーザーのダイヤルイン会議または電話会議をセットアップする方法について説明します。 '
ms.openlocfilehash: bfd9c9ec31736b0f7fc16f15a907c87406113871
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2020
ms.locfileid: "44163946"
---
# <a name="set-up-audio-conferencing-for-skype-for-business"></a>Skype for Business の電話会議をセットアップする

組織内のユーザーが、会議にダイヤル インするために電話機を使用する必要がある場合があります。 Skype for Business には、このような状況での電話会議機能が含まれています。 ユーザーは、モバイルデバイスや PC で Skype for Business アプリを使う代わりに、電話を使って Skype for Business 会議にコールインすることができます。 
  
電話会議の設定は、会議のスケジュールを設定または会議を進行するユーザーに対してのみ必要です。ダイヤルインで参加するユーザーについては、ライセンスの割り当てや他の設定は必要ありません。
  
電話会議についてよく寄せられる質問については、 [電話会議についてよくある質問](/MicrosoftTeams/audio-conferencing-common-questions) を参照してください。

## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>手順 1: 自分の国/地域で電話会議が使用可能かどうか確認する
<a name="__top"> </a>

「[国・地域別の電話会議と通話プランの利用可能状況](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)」を開き、ご自分の国または地域を選択して、電話会議についての情報に加えて、電話システム、通話プラン、有料・無料通話番号、コミュニケーション クレジットについての情報も取得してください。 
 
## <a name="step-2-get-and-assign-licenses"></a>手順 2: ライセンスを取得して割り当てる
 
1. 電話会議では、ダイヤルイン会議をセットアップするユーザーごとにライセンスが必要です。 電話会議用に購入する必要があるライセンスとその料金については、「 [Skype For business アドオンライセンス](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)」を参照してください。

    >[!NOTE] 
    > 電話会議は Office 365 Enterprise E5 ライセンスにアドオンとして含まれています。
        
2. 電話会議ライセンスを購入した後は、それらのライセンスを、会議を計画または開催しようとしている組織内のユーザーに割り当てる必要があります。 会議をスケジュールまたは開催しようとしている組織内のユーザーに、購入した一般[法人向け Microsoft 365 アプリのライセンスの割り当てまたは削除に関する](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)説明を参照してください。
    
3. また、前の手順でライセンスを割り当てた同じユーザーに、コミュニケーション クレジット ライセンス (費用はかかりません) を割り当てることをおすすめします。 コミュニケーション クレジットのセットアップ方法については、「[組織向けにコミュニケーション クレジットをセットアップする](/microsoftteams/set-up-communications-credits-for-your-organization)」を参照してください。
    
> [!NOTE]
> [分毎課金の電話会議](/microsoftteams/audio-conferencing-pay-per-minute)をセットアップすることもできます。

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>手順 3: 会議ブリッジのサービス番号を取得する
<a name="__top"> </a>

電話会議では、ユーザーの電話番号を使うことはできません。サービス番号を取得する必要があります。 会議ブリッジ用に、有料または無料のサービス番号のいずれかを取得することができます。 有料サービス番号と無料サービス番号を取得する方法は 3 通りあります。 
  
- **Skype For business 管理センターを使用**します。 一部の国/地域では、Skype for Business 管理センターを使って、会議ブリッジのサービス番号を取得できます。 「[サービス電話番号の取得](/microsoftteams/getting-service-phone-numbers)」を参照してください。
    
- **既存のサービス番号を移行する**。 現在のサービスプロバイダーまたは電話会社の既存の電話番号を Microsoft 365 または Office 365 に移植するか、またはその番号を移行する。 この方法の詳細については、「[Teams に電話番号を移行する](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams)」または「[組織の電話番号を管理する](/microsoftteams/manage-phone-numbers-for-your-organization)」を参照してください。  
  
- **申請書を使用して新しい番号を求める**。 場合によっては (国/地域によっては)、Skype for Business 管理センターを使用して新しいサービス番号を取得することはできません。または、特定の電話番号または市外局番が必要です。 その場合は、申請書をダウンロードして送信する必要があります。 詳細については「[組織の電話番号を管理](/microsoftteams/manage-phone-numbers-for-your-organization) 」を参照してください。 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>手順 4: 会議ブリッジにサービス番号を割り当てる
<a name="__top"> </a>

会議ブリッジ用に有料電話番号と無料電話番号のいずれかまたは両方を取得したら、それらの番号を割り当てて、会議の招集に使用できるようにする必要があります。  

電話会議ブリッジに新規の電話番号を割り当てるには:

![Skype for Business のロゴを表示したアイコン](../images/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**

 1. **[Microsoft 365 管理センター]** > **[管理センター]** > **[Teams]** > **[従来のポータル]** の順に移動します。
 2. **[音声]**  >  **[電話番号]** の順に選択します。
 3. 電話番号を選択し、**[割り当て]** をクリックします。

詳細については、「[電話会議ブリッジの電話番号を変更する](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)」を参照してください。

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>手順 5: 会議ブリッジ用の既定言語と第 2 言語を設定する
<a name="__top"> </a>

次に、電話会議の[自動応答の言語を設定](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md)して、会議の自動応答で電話会議の電話番号にダイヤルインするときに挨拶メッセージの発信者が通話を発信できるようにします。 

![Microsoft Teams ロゴを示すアイコン](../images/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**:

1. ダッシュボードから **[会議]** > **[会議ブリッジ]** の順に開きます。
2. 会議ブリッジ電話番号を選択して **[編集]** をクリックし、既定の言語を選択します。

![Skype for](../images/sfb-logo-30x30.png) **business 管理センターを使用し**た skype for business ロゴを示すアイコン:

1. 管理センターに**移動して**、管理センターの**Teams** > >**管理** > センターを開きます。
2. [**電話会議** > の**Microsoft bridge**] を選びます。 
3. 会議ブリッジの電話番号を選択し、[**言語の設定**] を選択して、[既定の言語] を選択します。

## <a name="step-6-set-your-conferencing-bridge-settings"></a>手順 6: 会議ブリッジを設定する
<a name="__top"> </a>
    
会議ブリッジをセットアップした後、使用する開始/終了の通知と PIN の長さが正しいかなど、既定の設定を確認します。正しくない場合は、変更することができます。 

![Microsoft Teams ロゴを示すアイコン](../images/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**:

1. ダッシュボードから **[会議]** > **[会議ブリッジ]** の順に開きます。
2. **[ブリッジの設定]** を選択します。 [**ブリッジの設定**] ウィンドウが開きます。 

詳細については、[電話会議ブリッジの設定を変更する](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge) を参照してください。

![Skype for Business のロゴを表示したアイコン](../images/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**

1. **[Microsoft 365 管理センター]** > **[管理センター]** > **[Teams]** > **[従来のポータル]** の順に移動します。
2. **電話会議** > の [**Microsoft bridge の設定**] を選びます。 [**Microsoft ブリッジの設定** ] ページが開きます。 

詳細については、[電話会議ブリッジの設定を変更する](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge) を参照してください。

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>手順 7: 会議を開催するユーザー向けにダイヤルインの電話番号を割り当てる

電話会議ブリッジを作成した後、ユーザー向けに有料番号と無料番号を設定する必要があります。

この操作を、会議を主催したり計画している組織内のすべてのユーザーに対して行う必要があります。 

![Microsoft Teams ロゴを示すアイコン](../images/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**:

1. ダッシュボードから **[ユーザー]** をクリックし、リストからユーザーを選択して **[編集]** を選択します。
2. **[電話会議]** の次にある **[編集]** をクリックしてから **[電話会議]** ウィンドウで **[有料番号]** と **[無料番号]** の番号リストから、番号を選択します。

![Skype for Business のロゴを表示したアイコン](../images/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**

1. **Microsoft 365 管理センター** > **Teams** > の**従来のポータル**に移動します。
2. [**電話会議** > **ユーザー**] を選択し、一覧からユーザーを選択して、[**編集**] をクリックします。 

さらに詳細が必要な場合は、「[Microsoft を電話会議プロバイダーとして割り当てる](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md)」を参照してください。


## <a name="step-8-set-up-meeting-invitations-optional"></a>手順 8: 会議の招集をセットアップする（オプション）
<a name="__top"> </a>
 
ユーザー向けに設定されているダイヤルイン番号は、会議の出席者に送信される会議招集に自動的に追加されます。 ただし、必要に応じて、独自のヘルプや法律のリンク、テキスト メッセージ、小さな会社のグラフィックを追加できます。 「[会議への招待状をカスタマイズする](../set-up-skype-for-business-online/customize-meeting-invitations.md)」を参照してください。
   
## <a name="related-topics"></a>関連項目

[電話会議に関するよくある質問](/MicrosoftTeams/audio-conferencing-common-questions)
  
[Skype for Business Online をセットアップする](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[電話会議の電話番号](phone-numbers-for-audio-conferencing.md)
  
[オンライン会議、電話会議のオプションを設定](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
