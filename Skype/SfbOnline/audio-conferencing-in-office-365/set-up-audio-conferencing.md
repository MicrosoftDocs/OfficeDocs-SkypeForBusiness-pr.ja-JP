---
title: Skype for Business および Microsoft Teams の電話会議のセットアップ
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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords:
- O365P_DialInConfDesc
ms.custom:
- Audio Conferencing
- LIL_Placement
description: '電話機を使用して電話会議に参加する必要のある社内のユーザー向けに、ダイヤルインまたは電話会議をセットアップする方法を説明します。 '
ms.openlocfilehash: 33e499719825a195484c6340bed09afeaa70f5ee
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850197"
---
# <a name="set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams"></a>Skype for Business および Microsoft Teams の電話会議のセットアップ

自分の組織内のユーザーが、会議にダイヤル インするために電話機を使用する必要がある場合があります。 Skype for Business と Microsoft Teams には、このような状況に最適な電話会議の機能があります。 ユーザーは、モバイル デバイスや PC 上の Skype for Business アプリや Microsoft Teams アプリを使用しなくても、電話機を使用して Skype for Business 会議や Microsoft Teams 会議を呼び出すことができます。 
  
必要なのは、会議を計画したり主催しようとしているユーザー向けに電話会議をセットアップすることだけです。 ダイヤルインする会議参加者には、割り当てられたライセンスやその他のセットアップは必要ありません。
  
電話会議についてよく寄せられる質問については、「[電話会議についてよくある質問](/MicrosoftTeams/audio-conferencing-common-questions)」を参照してください。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>手順 1: 自分の国/地域で電話会議が使用可能かどうか確認する
<a name="__top"> </a>


「[国・地域別の電話会議と通話プランの利用可能状況](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)」を開き、ご自分の国または地域を選択して、電話会議についての情報に加えて、電話システム、通話プラン、有料・無料通話番号、コミュニケーション クレジットについての情報も取得してください。 
 
## <a name="step-2-get-and-assign-licenses"></a>手順 2: ライセンスを取得して割り当てる
 
1. 電話会議では、ダイヤルイン会議をセットアップするユーザーごとにライセンスが必要です。 電話会議のために購入する必要のあるライセンスの種類と必要コストについては、「[Skype for Business と Microsoft Teams のアドイン ライセンス付与](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)」 を参照してください。
        
2. 電話会議ライセンスを購入した後は、それらのライセンスを、会議を計画したり開催しようとしている組織内のユーザーに割り当てる必要があります。 会議を計画したり主催しようとしてるユーザーに対して購入した「[法人向け Office 365 ライセンスの割り当てと削除](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)」を参照してください。
    
3. また、前の手順でライセンスを割り当てた同じユーザーに、コミュニケーション クレジット ライセンス (費用はかかりません) を割り当てることをおすすめします。 コミュニケーション クレジットのセットアップ方法については、「[組織向けにコミュニケーション クレジットをセットアップする](/microsoftteams/set-up-communications-credits-for-your-organization)」を参照してください。
    
> [!NOTE]
> 分毎課金の電話会議をセットアップすることもできます。 [こちら](/microsoftteams/audio-conferencing-pay-per-minute)を開いて、それらの使用方法の詳細をご覧ください。

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>手順 3: 会議ブリッジのサービス番号を取得する
<a name="__top"> </a>

電話会議では、ユーザーの電話番号を使うことはできません。サービス番号を取得する必要があります。 会議ブリッジ用に、有料または無料のサービス番号のいずれかを取得することができます。 有料サービス番号と無料サービス番号を取得する方法は 3 通りあります。 
  
- **Skype for Business 管理センターを使用する。** いくつかの国/地域では、Skype for Business 管理センターを使用して、会議ブリッジ用にサービス番号を取得できます。「[サービス電話番号の取得](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)」を参照してください。
    
- **既存のサービス番号を移行する。** 現在のサービス プロバイダーまたは電話通信会社から、Office 365 に既存の番号を移行します。 この方法の詳細については、「[Office 365 に電話番号を移行](/microsoftteams/transfer-phone-numbers-to-office-365)」または「[組織の電話番号を管理](/microsoftteams/manage-phone-numbers-for-your-organization)」を参照してください。  
  
- **新規の番号を取得するには、リクエスト フォームを使用してください。** 国や地域によっては、Skype for Business 管理センターを使用して新規のサービス番号を取得できない場合や、特定の電話番号や地域コードが必要になる場合があります。 その場合は、フォームをダウンロードして記入してからマイクロソフトに返送する必要があります。 詳細については「[組織の電話番号を管理](/microsoftteams/manage-phone-numbers-for-your-organization) 」を参照してください。 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>手順 4: 会議ブリッジにサービス番号を割り当てる
<a name="__top"> </a>

会議ブリッジ用に有料電話番号と無料電話番号のいずれかまたは両方を取得したら、それらの番号を割り当てて、会議の招集に使用できるようにする必要があります。  

電話会議ブリッジに新規の電話番号を割り当てるには:

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business 管理センターを使用する:**

 [**Office 365 管理センター**]  >  [**管理センター**]  >  [**Skype for Business**]  >  [**音声**]  >  [**電話番号**] の順に開き、電話番号を選択して [**割り当て**] をクリックします。

詳細については、「[電話会議ブリッジの電話番号を変更する](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)」を参照してください。

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>手順 5: 会議ブリッジ用の既定言語と第 2 言語を設定する
<a name="__top"> </a>

次に、電話会議の電話番号にダイヤルインした時に、呼び出しをしたユーザーに挨拶をするのに会議の自動応答で使用する「[電話会議の自動応答の言語を設定](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md)」します。 

![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Microsoft Teams と Skype for Business 管理センターを使用する: **

ダッシュボードから、[**会議**]  >  [**会議ブリッジ**] の順に開き、会議ブリッジ電話番号を選択して [**編集**] をクリックし、既定言語を選択します。

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business 管理センターを使用する:**

[**Office 365 管理センター**]  >  [**管理センター**]  >  [**Skype for Business**]  >  [**電話会議**]  >  [**Microsoft ブリッジの設定**] の順に開き、会議ブリッジ電話番号を選択して [**言語の設定**] をクリックします。

## <a name="step-6-set-your-conferencing-bridge-settings"></a>手順 6: 会議ブリッジを設定する
<a name="__top"> </a>
    
会議ブリッジをセットアップした後、使用する開始/終了の通知と PIN の長さが正しいかなど、既定の設定を確認します。正しくない場合は、変更することができます。 

![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Microsoft Teams と Skype for Business 管理センターを使用する: **

ダッシュボードから、[**会議**]  >  [**会議ブリッジ**]  >  [**ブリッジの設定**] の順に開きます。 [**ブリッジの設定**] ウィンドウが開きます。 詳細については、[電話会議ブリッジの設定を変更する](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge) を参照してください。

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business 管理センターを使用する:**

[**Office 365 管理センター**]  >  [**管理センター**]  >  [**Skype for Business**]  >  [**電話会議**]  >  [**Microsoft ブリッジの設定**] の順に開きます。 [**Microsoft ブリッジの設定** ] ページが開きます。 詳細については、[電話会議ブリッジの設定を変更する](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge) を参照してください。

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>手順 7: 会議を開催するユーザー向けにダイヤルインの電話番号を割り当てる

電話会議ブリッジを作成した後、ユーザー向けに有料番号と無料番号を設定する必要があります。

この操作を、会議を主催したり計画している組織内のすべてのユーザーに対して行う必要があります。 その手順は次のとおりです。

![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Microsoft Teams と Skype for Business 管理センターを使用する: **

ダッシュボードから、[**ユーザー**] をクリックしてリストからユーザーを選択し、[**編集**] をクリック、[**電話会議**] の次にある [**編集**] をクリックして、[**電話会議**] ウィンドウで [**有料番号**] と [**無料番号**] の番号リストから、番号を選択します。

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business 管理センターを使用する:**

[**Office 365 管理センター**]  >  [**Skype for Business**]  >  [**電話会議**]  >  [**ユーザー**] の順に開き、リストからユーザーを選択して [**編集**] をクリックします。 さらに詳細が必要な場合は、「[Microsoft を電話会議プロバイダーとして割り当てる](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md)」を参照してください。


## <a name="step-8-set-up-meeting-invitations-optional"></a>手順 8: 会議の招集をセットアップする（オプション）
<a name="__top"> </a>
 
ユーザー向けに設定されているダイヤルイン番号は、会議の出席者に送信される会議招集に自動的に追加されます。 ただし、必要に応じて、独自のヘルプや法律のリンク、テキスト メッセージ、小さな会社のグラフィックを追加できます。 「[会議出席依頼をカスタマイズする](../set-up-skype-for-business-online/customize-meeting-invitations.md)」を参照してください。
   
## <a name="related-topics"></a>このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。

[電話会議に関するよくある質問](/MicrosoftTeams/audio-conferencing-common-questions)
  
[Skype for Business Online のセットアップ](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[電話会議の電話番号](phone-numbers-for-audio-conferencing.md)
  
[オンライン会議、電話会議のオプションを設定](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
